---
ms.openlocfilehash: ced0e75c32d26aed43afa61d498f2f0c438bf2d0
ms.sourcegitcommit: e0d9b18d2d4cbeb4a48890f3420a47e6a90abc53
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49347917"
---
<!-- markdownlint-disable MD002 MD041 -->

En esta sección, usará el SDK de Microsoft Graph para obtener el usuario que ha iniciado sesión.

## <a name="create-a-graph-service"></a>Crear un servicio de gráficos

Comience por implementar un servicio que el bot puede usar para obtener un **GraphServiceClient** del SDK de Microsoft Graph y, a continuación, poner dicho servicio a disposición del bot mediante la inserción de dependencias.

1. Cree un nuevo directorio en la raíz del proyecto denominado **Graph**. Cree un archivo nuevo en el directorio **./Graph** denominado **IGraphClientService.CS** y agregue el siguiente código.

    :::code language="csharp" source="../demo/GraphCalendarBot/Graph/IGraphClientService.cs" id="IGraphClientServiceSnippet":::

1. Cree un archivo nuevo en el directorio **./Graph** denominado **GraphClientService.CS** y agregue el siguiente código.

    :::code language="csharp" source="../demo/GraphCalendarBot/Graph/GraphClientService.cs" id="GraphClientServiceSnippet":::

1. Abra **./startup.CS** y agregue el siguiente código al final de la `ConfigureServices` función.

    :::code language="csharp" source="../demo/GraphCalendarBot/Startup.cs" id="AddGraphServiceSnippet":::

1. Abra **./Dialogs/MainDialog.CS**. Agregue las siguientes `using` instrucciones en la parte superior del archivo.

    ```csharp
    using System;
    using System.IO;
    using CalendarBot.Graph;
    using AdaptiveCards;
    using Microsoft.Graph;
    ```

1. Agregue la siguiente propiedad a la clase **MainDialog** .

    ```csharp
    private readonly IGraphClientService _graphClientService;
    ```

1. Busque el constructor de la clase **MainDialog** y actualice su firma para que tome un parámetro **IGraphServiceClient** .

    :::code language="csharp" source="../demo/GraphCalendarBot/Dialogs/MainDialog.cs" id="ConstructorSignatureSnippet" highlight="4":::

1. Agregue el siguiente código al constructor.

    ```csharp
    _graphClientService = graphClientService;
    ```

## <a name="get-the-logged-on-user"></a>Obtener el usuario que ha iniciado sesión

En esta sección, usará Microsoft Graph para obtener el nombre del usuario, la dirección de correo electrónico y la foto. A continuación, creará una tarjeta adaptable para mostrar la información.

1. Cree un nuevo archivo en la raíz del proyecto denominado **CardHelper.CS**. Agregue el siguiente código al archivo.

    ```csharp
    using AdaptiveCards;
    using Microsoft.Graph;
    using System;
    using System.IO;

    namespace CalendarBot
    {
        public class CardHelper
        {
            public static AdaptiveCard GetUserCard(User user, Stream photo)
            {
              // Create an Adaptive Card to display the user
                // See https://adaptivecards.io/designer/ for possibilities
                var userCard = new AdaptiveCard("1.2");

                var columns = new AdaptiveColumnSet();
                userCard.Body.Add(columns);

                var userPhotoColumn = new AdaptiveColumn { Width = AdaptiveColumnWidth.Auto };
                columns.Columns.Add(userPhotoColumn);

                userPhotoColumn.Items.Add(new AdaptiveImage {
                    Style = AdaptiveImageStyle.Person,
                    Size = AdaptiveImageSize.Small,
                    Url = GetDataUriFromPhoto(photo)
                });

                var userInfoColumn = new AdaptiveColumn {Width = AdaptiveColumnWidth.Stretch };
                columns.Columns.Add(userInfoColumn);

                userInfoColumn.Items.Add(new AdaptiveTextBlock {
                    Weight = AdaptiveTextWeight.Bolder,
                    Wrap = true,
                    Text = user.DisplayName
                });

                userInfoColumn.Items.Add(new AdaptiveTextBlock {
                    Spacing = AdaptiveSpacing.None,
                    IsSubtle = true,
                    Wrap = true,
                    Text = user.Mail ?? user.UserPrincipalName
                });

                return userCard;
            }

            private static Uri GetDataUriFromPhoto(Stream photo)
            {
                // Copy to a MemoryStream to get access to bytes
                var photoStream = new MemoryStream();
                photo.CopyTo(photoStream);

                var photoBytes = photoStream.ToArray();

                return new Uri($"data:image/png;base64,{Convert.ToBase64String(photoBytes)}");
            }
        }
    }
    ```

    Este código usa el paquete de NuGet **AdaptiveCard** para crear una tarjeta adaptable para mostrar el usuario.

1. Agregue la siguiente función a la clase **MainDialog** .

    :::code language="csharp" source="../demo/GraphCalendarBot/Dialogs/MainDialog.cs" id="DisplayLoggedInUserSnippet":::

    Considere lo que hace este código.

    - Usa **graphClient** para [obtener el usuario que ha iniciado sesión](https://docs.microsoft.com/graph/api/user-get?view=graph-rest-1.0).
        - Usa el `Select` método para limitar los campos que se devuelven.
    - Usa **graphClient** para [obtener la foto del usuario](https://docs.microsoft.com/graph/api/profilephoto-get?view=graph-rest-1.0)y solicitar el menor tamaño admitido de 48x48 píxeles.
    - Usa la clase **CardHelper** para construir una tarjeta adaptable y envía la tarjeta como datos adjuntos.

1. Reemplace el código dentro del `else if (command.StartsWith("show me"))` bloque `ProcessStepAsync` por lo siguiente.

    :::code language="csharp" source="../demo/GraphCalendarBot/Dialogs/MainDialog.cs" id="ShowMeSnippet" highlight="3":::

1. Guarde todos los cambios y reinicie el bot.

1. Use el emulador de bot Framework para conectarse al bot e inicie sesión. Seleccione el botón **Mostrar** para mostrar el usuario que ha iniciado sesión.

    ![Captura de pantalla de la tarjeta adaptable que muestra al usuario](images/user-card.png)

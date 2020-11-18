---
ms.openlocfilehash: 12a6c18b52e2bc9aba5ad69c8bb9ab8091c11a64
ms.sourcegitcommit: e0d9b18d2d4cbeb4a48890f3420a47e6a90abc53
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49347887"
---
<!-- markdownlint-disable MD002 MD041 -->

En esta sección, creará un proyecto de bot Framework.

1. Abra la interfaz de línea de comandos (CLI) en un directorio donde desee crear el proyecto. Ejecute el siguiente comando para crear un nuevo proyecto con la plantilla **Microsoft. bot. Framework. CSharp. EchoBot** .

    ```dotnetcli
    dotnet new echobot -n GraphCalendarBot
    ```

    > [!NOTE]
    > Si recibe un `No templates matched the input template name: echobot.` error, instale la plantilla con el siguiente comando y vuelva a ejecutar el comando anterior.
    >
    > ```dotnetcli
    > dotnet new -i Microsoft.Bot.Framework.CSharp.EchoBot
    > ```

1. Cambie el nombre de la clase **EchoBot** predeterminada a **CalendarBot**. Abra **./bots/EchoBot.CS** y reemplace todas las instancias de `EchoBot` por `CalendarBot` . Cambie el nombre del archivo a **CalendarBot.CS**.

1. Reemplace todas las instancias de `EchoBot` por con `CalendarBot` en los archivos **. CS** restantes.

1. En la CLI, cambie el directorio actual al directorio **GraphCalendarBot** y ejecute el siguiente comando para confirmar las compilaciones del proyecto.

    ```dotnetcli
    dotnet build
    ```

## <a name="add-nuget-packages"></a>Agregar paquetes NuGet

Antes de continuar, instale algunos paquetes NuGet adicionales que usará más adelante.

- [AdaptiveCards](https://www.nuget.org/packages/AdaptiveCards/) para permitir que el bot envíe tarjetas adaptables en las respuestas.
- [Microsoft. bot. Builder. Dialogs](https://www.nuget.org/packages/Microsoft.Bot.Builder.Dialogs/) para agregar compatibilidad con cuadros de diálogo al bot.
- [Microsoft. reconocedores. Text. Datatypes. TimexExpression](https://www.nuget.org/packages/Microsoft.Recognizers.Text.DataTypes.TimexExpression/) para convertir las expresiones Timex devueltas por los mensajes de bot en objetos **DateTime** .
- [Microsoft. Graph](https://www.nuget.org/packages/Microsoft.Graph/) para realizar llamadas a Microsoft Graph.

1. Ejecute los siguientes comandos en su CLI para instalar las dependencias.

    ```Shell
    dotnet add package AdaptiveCards --version 2.2.0
    dotnet add package Microsoft.Bot.Builder.Dialogs --version 4.10.3
    dotnet add package Microsoft.Bot.Builder.Integration.AspNet.Core --version 4.10.3
    dotnet add package Microsoft.Recognizers.Text.DataTypes.TimexExpression --version 1.4.1
    dotnet add package Microsoft.Graph --version 3.18.0
    ```

## <a name="test-the-bot"></a>Probar el bot

Antes de agregar código, pruebe el bot para asegurarse de que funciona correctamente y de que el emulador de entorno de bot está configurado para probarlo.

1. Inicie el bot ejecutando el siguiente comando.

    ```dotnetcli
    dotnet run
    ```

    > [!TIP]
    > Aunque puede usar cualquier editor de texto para editar los archivos de origen en el proyecto, se recomienda usar [Visual Studio Code](https://code.visualstudio.com/). Visual Studio Code ofrece compatibilidad de depuración, IntelliSense y más. Si usa Visual Studio Code, puede iniciar el bot mediante el menú **Run** de  ->  **Inicio de depuración** de ejecución.

1. Para confirmar que se está ejecutando el bot, abra el explorador y vaya a `http://localhost:3978` . Debería ver que **su bot está preparado.** Mensaje.

1. Abra el emulador de bot Framework. Elija el menú **archivo** y, a continuación, **abra bot**.

1. Escriba `http://localhost:3978/api/messages` en la **dirección URL del bot** y, después, seleccione **conectar**.

1. El bot responde `Hello and welcome!` en la ventana de chat. Envíe un mensaje al bot y confirme de nuevo que lo repite.

    ![Captura de pantalla del emulador de bot Framework conectado al bot](images/test-emulator.png)

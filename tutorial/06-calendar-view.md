---
ms.openlocfilehash: 65fd8e133174c6ac7bbbbc00487cabc72ebe561d
ms.sourcegitcommit: e0d9b18d2d4cbeb4a48890f3420a47e6a90abc53
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49347923"
---
<!-- markdownlint-disable MD002 MD041 -->

En esta sección, usará el SDK de Microsoft Graph para obtener los próximos tres próximos eventos en el calendario del usuario para la semana actual.

## <a name="get-a-calendar-view"></a>Obtener una vista de calendario

Una vista de calendario es una lista de eventos en el calendario de un usuario que se encuentran entre dos valores de fecha y hora. La ventaja de usar una vista de calendario es que incluye todas las apariciones de reuniones periódicas.

1. Abra **./CardHelper.CS** y agregue la siguiente función a la clase **CardHelper**

    :::code language="csharp" source="../demo/GraphCalendarBot/CardHelper.cs" id="GetEventCardSnippet":::

    Este código crea una tarjeta adaptable para representar un evento de calendario.

1. Abra **./Dialogs/MainDialog.CS** y agregue la siguiente función a la clase **MainDialog** .

    :::code language="csharp" source="../demo/GraphCalendarBot/Dialogs/MainDialog.cs" id="DisplayCalendarViewSnippet":::

    Considere lo que hace este código.

    - Obtiene el **MailboxSettings** del usuario para determinar la zona horaria preferida del usuario y los formatos de fecha y hora.
    - Establece los valores **startDateTime** y **endDateTime** en Now y el final de la semana, respectivamente. Define la ventana de tiempo que usa la vista de calendario.
    - Llama `graphClient.Me.CalendarView` con los siguientes detalles.
        - Establece el `Prefer: outlook.timezone` encabezado en la zona horaria preferida del usuario, lo que provoca que las horas de inicio y finalización de los eventos estén en la zona horaria del usuario.
        - Usa el `Top(3)` método para limitar los resultados a solo los tres primeros eventos.
        - Utiliza `Select` para limitar los campos devueltos a sólo los campos utilizados por el bot.
        - Se usa `OrderBy` para ordenar los eventos por hora de inicio.
    - Agrega una tarjeta adaptable para cada evento al mensaje de respuesta.

1. Reemplace el código dentro del `else if (command.StartsWith("show calendar"))` bloque `ProcessStepAsync` por lo siguiente.

    :::code language="csharp" source="../demo/GraphCalendarBot/Dialogs/MainDialog.cs" id="ShowCalendarSnippet" highlight="3":::

1. Guarde todos los cambios y reinicie el bot.

1. Use el emulador de bot Framework para conectarse al bot e inicie sesión. Seleccione el botón **Mostrar calendario** para mostrar la vista Calendario.

    ![Una captura de pantalla de la tarjeta adaptable que muestra los tres eventos siguientes](images/calendar-view.png)

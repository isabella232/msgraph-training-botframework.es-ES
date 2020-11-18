---
ms.openlocfilehash: 65fd8e133174c6ac7bbbbc00487cabc72ebe561d
ms.sourcegitcommit: e0d9b18d2d4cbeb4a48890f3420a47e6a90abc53
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49347923"
---
<!-- markdownlint-disable MD002 MD041 -->

<span data-ttu-id="31ec1-101">En esta sección, usará el SDK de Microsoft Graph para obtener los próximos tres próximos eventos en el calendario del usuario para la semana actual.</span><span class="sxs-lookup"><span data-stu-id="31ec1-101">In this section you'll use the Microsoft Graph SDK to get the next 3 upcoming events on the user's calendar for the current week.</span></span>

## <a name="get-a-calendar-view"></a><span data-ttu-id="31ec1-102">Obtener una vista de calendario</span><span class="sxs-lookup"><span data-stu-id="31ec1-102">Get a calendar view</span></span>

<span data-ttu-id="31ec1-103">Una vista de calendario es una lista de eventos en el calendario de un usuario que se encuentran entre dos valores de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="31ec1-103">A calendar view is a list of events on a user's calendar that fall between two date/time values.</span></span> <span data-ttu-id="31ec1-104">La ventaja de usar una vista de calendario es que incluye todas las apariciones de reuniones periódicas.</span><span class="sxs-lookup"><span data-stu-id="31ec1-104">The advantage of using a calendar view is that it includes any occurrences of recurring meetings.</span></span>

1. <span data-ttu-id="31ec1-105">Abra **./CardHelper.CS** y agregue la siguiente función a la clase **CardHelper**</span><span class="sxs-lookup"><span data-stu-id="31ec1-105">Open **./CardHelper.cs** and add the following function to the **CardHelper** class.</span></span>

    :::code language="csharp" source="../demo/GraphCalendarBot/CardHelper.cs" id="GetEventCardSnippet":::

    <span data-ttu-id="31ec1-106">Este código crea una tarjeta adaptable para representar un evento de calendario.</span><span class="sxs-lookup"><span data-stu-id="31ec1-106">This code builds an Adaptive Card to render a calendar event.</span></span>

1. <span data-ttu-id="31ec1-107">Abra **./Dialogs/MainDialog.CS** y agregue la siguiente función a la clase **MainDialog** .</span><span class="sxs-lookup"><span data-stu-id="31ec1-107">Open **./Dialogs/MainDialog.cs** and add the following function to the **MainDialog** class.</span></span>

    :::code language="csharp" source="../demo/GraphCalendarBot/Dialogs/MainDialog.cs" id="DisplayCalendarViewSnippet":::

    <span data-ttu-id="31ec1-108">Considere lo que hace este código.</span><span class="sxs-lookup"><span data-stu-id="31ec1-108">Consider what this code does.</span></span>

    - <span data-ttu-id="31ec1-109">Obtiene el **MailboxSettings** del usuario para determinar la zona horaria preferida del usuario y los formatos de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="31ec1-109">It gets the user's **MailboxSettings** to determine the user's preferred time zone and date/time formats.</span></span>
    - <span data-ttu-id="31ec1-110">Establece los valores **startDateTime** y **endDateTime** en Now y el final de la semana, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="31ec1-110">It sets the **startDateTime** and **endDateTime** values to now and the end of the week, respectively.</span></span> <span data-ttu-id="31ec1-111">Define la ventana de tiempo que usa la vista de calendario.</span><span class="sxs-lookup"><span data-stu-id="31ec1-111">This defines the window of time that the calendar view uses.</span></span>
    - <span data-ttu-id="31ec1-112">Llama `graphClient.Me.CalendarView` con los siguientes detalles.</span><span class="sxs-lookup"><span data-stu-id="31ec1-112">It calls `graphClient.Me.CalendarView` with the following details.</span></span>
        - <span data-ttu-id="31ec1-113">Establece el `Prefer: outlook.timezone` encabezado en la zona horaria preferida del usuario, lo que provoca que las horas de inicio y finalización de los eventos estén en la zona horaria del usuario.</span><span class="sxs-lookup"><span data-stu-id="31ec1-113">It sets the `Prefer: outlook.timezone` header to the user's preferred time zone, causing the start and end times for the events to be in the user's timezone.</span></span>
        - <span data-ttu-id="31ec1-114">Usa el `Top(3)` método para limitar los resultados a solo los tres primeros eventos.</span><span class="sxs-lookup"><span data-stu-id="31ec1-114">It uses the `Top(3)` method to limit the results to only the first 3 events.</span></span>
        - <span data-ttu-id="31ec1-115">Utiliza `Select` para limitar los campos devueltos a sólo los campos utilizados por el bot.</span><span class="sxs-lookup"><span data-stu-id="31ec1-115">It uses `Select` to limit the fields returned to just those fields used by the bot.</span></span>
        - <span data-ttu-id="31ec1-116">Se usa `OrderBy` para ordenar los eventos por hora de inicio.</span><span class="sxs-lookup"><span data-stu-id="31ec1-116">It uses `OrderBy` to sort the events by start time.</span></span>
    - <span data-ttu-id="31ec1-117">Agrega una tarjeta adaptable para cada evento al mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="31ec1-117">It adds an Adaptive Card for each event to the reply message.</span></span>

1. <span data-ttu-id="31ec1-118">Reemplace el código dentro del `else if (command.StartsWith("show calendar"))` bloque `ProcessStepAsync` por lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="31ec1-118">Replace the code inside the `else if (command.StartsWith("show calendar"))` block in `ProcessStepAsync` with the following.</span></span>

    :::code language="csharp" source="../demo/GraphCalendarBot/Dialogs/MainDialog.cs" id="ShowCalendarSnippet" highlight="3":::

1. <span data-ttu-id="31ec1-119">Guarde todos los cambios y reinicie el bot.</span><span class="sxs-lookup"><span data-stu-id="31ec1-119">Save all of your changes and restart the bot.</span></span>

1. <span data-ttu-id="31ec1-120">Use el emulador de bot Framework para conectarse al bot e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="31ec1-120">Use the Bot Framework Emulator to connect to the bot and log in.</span></span> <span data-ttu-id="31ec1-121">Seleccione el botón **Mostrar calendario** para mostrar la vista Calendario.</span><span class="sxs-lookup"><span data-stu-id="31ec1-121">Select the **Show calendar** button to display the calendar view.</span></span>

    ![Una captura de pantalla de la tarjeta adaptable que muestra los tres eventos siguientes](images/calendar-view.png)

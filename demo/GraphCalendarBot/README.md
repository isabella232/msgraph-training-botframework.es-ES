---
ms.openlocfilehash: c0fd9a9f5529f202c125d7f1e7c6b50fa9dc630d
ms.sourcegitcommit: e0d9b18d2d4cbeb4a48890f3420a47e6a90abc53
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49347898"
---
# <a name="graphcalendarbot"></a><span data-ttu-id="419dd-101">GraphCalendarBot</span><span class="sxs-lookup"><span data-stu-id="419dd-101">GraphCalendarBot</span></span>

<span data-ttu-id="419dd-102">Ejemplo de bot del ECO V4 de bot Framework.</span><span class="sxs-lookup"><span data-stu-id="419dd-102">Bot Framework v4 echo bot sample.</span></span>

<span data-ttu-id="419dd-103">Este bot se ha creado con [Bot Framework](https://dev.botframework.com), muestra cómo crear un bot sencillo que acepta la entrada del usuario y lo vuelve a mostrar.</span><span class="sxs-lookup"><span data-stu-id="419dd-103">This bot has been created using [Bot Framework](https://dev.botframework.com), it shows how to create a simple bot that accepts input from the user and echoes it back.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="419dd-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="419dd-104">Prerequisites</span></span>

- <span data-ttu-id="419dd-105">[.Net Core SDK](https://dotnet.microsoft.com/download) versión 3,1</span><span class="sxs-lookup"><span data-stu-id="419dd-105">[.NET Core SDK](https://dotnet.microsoft.com/download) version 3.1</span></span>

  ```bash
  # determine dotnet version
  dotnet --version
  ```

## <a name="to-try-this-sample"></a><span data-ttu-id="419dd-106">Para probar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="419dd-106">To try this sample</span></span>

- <span data-ttu-id="419dd-107">En un terminal, navegue a `GraphCalendarBot`</span><span class="sxs-lookup"><span data-stu-id="419dd-107">In a terminal, navigate to `GraphCalendarBot`</span></span>

    ```bash
    # change into project folder
    cd GraphCalendarBot
    ```

- <span data-ttu-id="419dd-108">Ejecutar el bot desde un terminal o desde Visual Studio, elija la opción A o B.</span><span class="sxs-lookup"><span data-stu-id="419dd-108">Run the bot from a terminal or from Visual Studio, choose option A or B.</span></span>

  <span data-ttu-id="419dd-109">A) desde un terminal</span><span class="sxs-lookup"><span data-stu-id="419dd-109">A) From a terminal</span></span>

  ```bash
  # run the bot
  dotnet run
  ```

  <span data-ttu-id="419dd-110">B) o de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="419dd-110">B) Or from Visual Studio</span></span>

  - <span data-ttu-id="419dd-111">Iniciar Visual Studio</span><span class="sxs-lookup"><span data-stu-id="419dd-111">Launch Visual Studio</span></span>
  - <span data-ttu-id="419dd-112">Archivo: > solución o proyecto de > abierto</span><span class="sxs-lookup"><span data-stu-id="419dd-112">File -> Open -> Project/Solution</span></span>
  - <span data-ttu-id="419dd-113">Ir a `GraphCalendarBot` carpeta</span><span class="sxs-lookup"><span data-stu-id="419dd-113">Navigate to `GraphCalendarBot` folder</span></span>
  - <span data-ttu-id="419dd-114">Seleccionar `GraphCalendarBot.csproj` archivo</span><span class="sxs-lookup"><span data-stu-id="419dd-114">Select `GraphCalendarBot.csproj` file</span></span>
  - <span data-ttu-id="419dd-115">Presione `F5` para ejecutar el proyecto</span><span class="sxs-lookup"><span data-stu-id="419dd-115">Press `F5` to run the project</span></span>

## <a name="testing-the-bot-using-bot-framework-emulator"></a><span data-ttu-id="419dd-116">Probar el bot con el emulador de control de bot</span><span class="sxs-lookup"><span data-stu-id="419dd-116">Testing the bot using Bot Framework Emulator</span></span>

<span data-ttu-id="419dd-117">[Bot Framework Emulator](https://github.com/microsoft/botframework-emulator) es una aplicación de escritorio que permite a los programadores de robots probar y depurar los bots en localhost o ejecutar de forma remota a través de un túnel.</span><span class="sxs-lookup"><span data-stu-id="419dd-117">[Bot Framework Emulator](https://github.com/microsoft/botframework-emulator) is a desktop application that allows bot developers to test and debug their bots on localhost or running remotely through a tunnel.</span></span>

- <span data-ttu-id="419dd-118">Instalar el emulador de bot Framework versión 4.9.0 o posterior a partir de [aquí](https://github.com/Microsoft/BotFramework-Emulator/releases)</span><span class="sxs-lookup"><span data-stu-id="419dd-118">Install the Bot Framework Emulator version 4.9.0 or greater from [here](https://github.com/Microsoft/BotFramework-Emulator/releases)</span></span>

### <a name="connect-to-the-bot-using-bot-framework-emulator"></a><span data-ttu-id="419dd-119">Conectar con el bot mediante el emulador de bot Framework</span><span class="sxs-lookup"><span data-stu-id="419dd-119">Connect to the bot using Bot Framework Emulator</span></span>

- <span data-ttu-id="419dd-120">Iniciar el emulador de Framework bot</span><span class="sxs-lookup"><span data-stu-id="419dd-120">Launch Bot Framework Emulator</span></span>
- <span data-ttu-id="419dd-121">Archivo-> bot abierto</span><span class="sxs-lookup"><span data-stu-id="419dd-121">File -> Open Bot</span></span>
- <span data-ttu-id="419dd-122">Escriba una dirección URL de bot de `http://localhost:3978/api/messages`</span><span class="sxs-lookup"><span data-stu-id="419dd-122">Enter a Bot URL of `http://localhost:3978/api/messages`</span></span>

## <a name="deploy-the-bot-to-azure"></a><span data-ttu-id="419dd-123">Implementar el bot en Azure</span><span class="sxs-lookup"><span data-stu-id="419dd-123">Deploy the bot to Azure</span></span>

<span data-ttu-id="419dd-124">Para obtener más información sobre la implementación de un bot en Azure, consulte [deploy Your bot to Azure](https://aka.ms/azuredeployment) para obtener una lista completa de las instrucciones de implementación.</span><span class="sxs-lookup"><span data-stu-id="419dd-124">To learn more about deploying a bot to Azure, see [Deploy your bot to Azure](https://aka.ms/azuredeployment) for a complete list of deployment instructions.</span></span>

## <a name="further-reading"></a><span data-ttu-id="419dd-125">Lecturas adicionales</span><span class="sxs-lookup"><span data-stu-id="419dd-125">Further reading</span></span>

- [<span data-ttu-id="419dd-126">Documentación de bot Framework</span><span class="sxs-lookup"><span data-stu-id="419dd-126">Bot Framework Documentation</span></span>](https://docs.botframework.com)
- [<span data-ttu-id="419dd-127">Conceptos básicos de bot</span><span class="sxs-lookup"><span data-stu-id="419dd-127">Bot Basics</span></span>](https://docs.microsoft.com/azure/bot-service/bot-builder-basics?view=azure-bot-service-4.0)
- [<span data-ttu-id="419dd-128">Procesamiento de actividad</span><span class="sxs-lookup"><span data-stu-id="419dd-128">Activity processing</span></span>](https://docs.microsoft.com/en-us/azure/bot-service/bot-builder-concept-activity-processing?view=azure-bot-service-4.0)
- [<span data-ttu-id="419dd-129">Introducción al servicio de bot de Azure</span><span class="sxs-lookup"><span data-stu-id="419dd-129">Azure Bot Service Introduction</span></span>](https://docs.microsoft.com/azure/bot-service/bot-service-overview-introduction?view=azure-bot-service-4.0)
- [<span data-ttu-id="419dd-130">Documentación del servicio de bot de Azure</span><span class="sxs-lookup"><span data-stu-id="419dd-130">Azure Bot Service Documentation</span></span>](https://docs.microsoft.com/azure/bot-service/?view=azure-bot-service-4.0)
- [<span data-ttu-id="419dd-131">Herramientas de .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="419dd-131">.NET Core CLI tools</span></span>](https://docs.microsoft.com/en-us/dotnet/core/tools/?tabs=netcore2x)
- [<span data-ttu-id="419dd-132">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="419dd-132">Azure CLI</span></span>](https://docs.microsoft.com/cli/azure/?view=azure-cli-latest)
- [<span data-ttu-id="419dd-133">Portal de Azure</span><span class="sxs-lookup"><span data-stu-id="419dd-133">Azure Portal</span></span>](https://portal.azure.com)
- [<span data-ttu-id="419dd-134">Comprensión del lenguaje mediante LUIS</span><span class="sxs-lookup"><span data-stu-id="419dd-134">Language Understanding using LUIS</span></span>](https://docs.microsoft.com/en-us/azure/cognitive-services/luis/)
- [<span data-ttu-id="419dd-135">Servicio de conector de robots y canales</span><span class="sxs-lookup"><span data-stu-id="419dd-135">Channels and Bot Connector Service</span></span>](https://docs.microsoft.com/en-us/azure/bot-service/bot-concepts?view=azure-bot-service-4.0)

<span data-ttu-id="419dd-136">Generado con `dotnet new echobot` v 4.10.2</span><span class="sxs-lookup"><span data-stu-id="419dd-136">Generated using `dotnet new echobot` v4.10.2</span></span>

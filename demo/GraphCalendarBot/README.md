---
ms.openlocfilehash: c0fd9a9f5529f202c125d7f1e7c6b50fa9dc630d
ms.sourcegitcommit: e0d9b18d2d4cbeb4a48890f3420a47e6a90abc53
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49347898"
---
# <a name="graphcalendarbot"></a>GraphCalendarBot

Ejemplo de bot del ECO V4 de bot Framework.

Este bot se ha creado con [Bot Framework](https://dev.botframework.com), muestra cómo crear un bot sencillo que acepta la entrada del usuario y lo vuelve a mostrar.

## <a name="prerequisites"></a>Requisitos previos

- [.Net Core SDK](https://dotnet.microsoft.com/download) versión 3,1

  ```bash
  # determine dotnet version
  dotnet --version
  ```

## <a name="to-try-this-sample"></a>Para probar este ejemplo

- En un terminal, navegue a `GraphCalendarBot`

    ```bash
    # change into project folder
    cd GraphCalendarBot
    ```

- Ejecutar el bot desde un terminal o desde Visual Studio, elija la opción A o B.

  A) desde un terminal

  ```bash
  # run the bot
  dotnet run
  ```

  B) o de Visual Studio

  - Iniciar Visual Studio
  - Archivo: > solución o proyecto de > abierto
  - Ir a `GraphCalendarBot` carpeta
  - Seleccionar `GraphCalendarBot.csproj` archivo
  - Presione `F5` para ejecutar el proyecto

## <a name="testing-the-bot-using-bot-framework-emulator"></a>Probar el bot con el emulador de control de bot

[Bot Framework Emulator](https://github.com/microsoft/botframework-emulator) es una aplicación de escritorio que permite a los programadores de robots probar y depurar los bots en localhost o ejecutar de forma remota a través de un túnel.

- Instalar el emulador de bot Framework versión 4.9.0 o posterior a partir de [aquí](https://github.com/Microsoft/BotFramework-Emulator/releases)

### <a name="connect-to-the-bot-using-bot-framework-emulator"></a>Conectar con el bot mediante el emulador de bot Framework

- Iniciar el emulador de Framework bot
- Archivo-> bot abierto
- Escriba una dirección URL de bot de `http://localhost:3978/api/messages`

## <a name="deploy-the-bot-to-azure"></a>Implementar el bot en Azure

Para obtener más información sobre la implementación de un bot en Azure, consulte [deploy Your bot to Azure](https://aka.ms/azuredeployment) para obtener una lista completa de las instrucciones de implementación.

## <a name="further-reading"></a>Lecturas adicionales

- [Documentación de bot Framework](https://docs.botframework.com)
- [Conceptos básicos de bot](https://docs.microsoft.com/azure/bot-service/bot-builder-basics?view=azure-bot-service-4.0)
- [Procesamiento de actividad](https://docs.microsoft.com/en-us/azure/bot-service/bot-builder-concept-activity-processing?view=azure-bot-service-4.0)
- [Introducción al servicio de bot de Azure](https://docs.microsoft.com/azure/bot-service/bot-service-overview-introduction?view=azure-bot-service-4.0)
- [Documentación del servicio de bot de Azure](https://docs.microsoft.com/azure/bot-service/?view=azure-bot-service-4.0)
- [Herramientas de .NET Core CLI](https://docs.microsoft.com/en-us/dotnet/core/tools/?tabs=netcore2x)
- [Azure CLI](https://docs.microsoft.com/cli/azure/?view=azure-cli-latest)
- [Portal de Azure](https://portal.azure.com)
- [Comprensión del lenguaje mediante LUIS](https://docs.microsoft.com/en-us/azure/cognitive-services/luis/)
- [Servicio de conector de robots y canales](https://docs.microsoft.com/en-us/azure/bot-service/bot-concepts?view=azure-bot-service-4.0)

Generado con `dotnet new echobot` v 4.10.2

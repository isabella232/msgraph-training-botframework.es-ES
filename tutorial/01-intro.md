---
ms.openlocfilehash: 0022448db76695894bfefca2543ad39c4fd07dcc
ms.sourcegitcommit: e0d9b18d2d4cbeb4a48890f3420a47e6a90abc53
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49347893"
---
<!-- markdownlint-disable MD002 MD041 -->

<span data-ttu-id="a6f94-101">Este tutorial le enseña a crear un bot Framework de bot que usa la API de Microsoft Graph para recuperar la información de calendario de un usuario.</span><span class="sxs-lookup"><span data-stu-id="a6f94-101">This tutorial teaches you how to build a Bot Framework bot that uses the Microsoft Graph API to retrieve calendar information for a user.</span></span>

> [!TIP]
> <span data-ttu-id="a6f94-102">Si prefiere descargar solo el tutorial completo, puede descargar o clonar el repositorio de [GitHub](https://github.com/microsoftgraph/msgraph-training-botframework).</span><span class="sxs-lookup"><span data-stu-id="a6f94-102">If you prefer to just download the completed tutorial, you can download or clone the [GitHub repository](https://github.com/microsoftgraph/msgraph-training-botframework).</span></span> <span data-ttu-id="a6f94-103">Consulte el archivo Léame de la carpeta **Demo** para obtener instrucciones sobre cómo configurar la aplicación con un identificador de aplicación y un secreto.</span><span class="sxs-lookup"><span data-stu-id="a6f94-103">See the README file in the **demo** folder for instructions on configuring the app with an app ID and secret.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a6f94-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a6f94-104">Prerequisites</span></span>

<span data-ttu-id="a6f94-105">Antes de iniciar este tutorial, debe tener instalado lo siguiente en el equipo de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="a6f94-105">Before you start this tutorial, you should have the following installed on your development machine.</span></span>

- [<span data-ttu-id="a6f94-106">.NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="a6f94-106">.NET Core SDK</span></span>](https://dotnet.microsoft.com/download)
- [<span data-ttu-id="a6f94-107">Emulador de bot Framework</span><span class="sxs-lookup"><span data-stu-id="a6f94-107">Bot Framework Emulator</span></span>](https://github.com/microsoft/BotFramework-Emulator/blob/master/README.md)

<span data-ttu-id="a6f94-108">También debe tener una cuenta de Microsoft personal con un buzón de correo en Outlook.com o una cuenta profesional o educativa de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a6f94-108">You should also have either a personal Microsoft account with a mailbox on Outlook.com, or a Microsoft work or school account.</span></span> <span data-ttu-id="a6f94-109">Si no tiene una cuenta de Microsoft, hay un par de opciones para obtener una cuenta gratuita:</span><span class="sxs-lookup"><span data-stu-id="a6f94-109">If you don't have a Microsoft account, there are a couple of options to get a free account:</span></span>

- <span data-ttu-id="a6f94-110">Puede [registrarse para obtener una nueva cuenta Microsoft personal](https://signup.live.com/signup?wa=wsignin1.0&rpsnv=12&ct=1454618383&rver=6.4.6456.0&wp=MBI_SSL_SHARED&wreply=https://mail.live.com/default.aspx&id=64855&cbcxt=mai&bk=1454618383&uiflavor=web&uaid=b213a65b4fdc484382b6622b3ecaa547&mkt=E-US&lc=1033&lic=1).</span><span class="sxs-lookup"><span data-stu-id="a6f94-110">You can [sign up for a new personal Microsoft account](https://signup.live.com/signup?wa=wsignin1.0&rpsnv=12&ct=1454618383&rver=6.4.6456.0&wp=MBI_SSL_SHARED&wreply=https://mail.live.com/default.aspx&id=64855&cbcxt=mai&bk=1454618383&uiflavor=web&uaid=b213a65b4fdc484382b6622b3ecaa547&mkt=E-US&lc=1033&lic=1).</span></span>
- <span data-ttu-id="a6f94-111">Puede [registrarse para el programa de desarrolladores de office 365](https://developer.microsoft.com/office/dev-program) para obtener una suscripción gratuita a Office 365.</span><span class="sxs-lookup"><span data-stu-id="a6f94-111">You can [sign up for the Office 365 Developer Program](https://developer.microsoft.com/office/dev-program) to get a free Office 365 subscription.</span></span>
- <span data-ttu-id="a6f94-112">Una suscripción a Azure.</span><span class="sxs-lookup"><span data-stu-id="a6f94-112">An Azure subscription.</span></span> <span data-ttu-id="a6f94-113">Si no tiene uno, cree una [cuenta gratuita](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) antes de empezar.</span><span class="sxs-lookup"><span data-stu-id="a6f94-113">If you do not have one, create a [free account](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) before you begin.</span></span>

> [!NOTE]
> <span data-ttu-id="a6f94-114">Este tutorial se ha escrito con .NET Core SDK versión 3.1.401.</span><span class="sxs-lookup"><span data-stu-id="a6f94-114">This tutorial was written with .NET Core SDK version 3.1.401.</span></span> <span data-ttu-id="a6f94-115">Los pasos de esta guía pueden funcionar con otras versiones, pero no se han probado.</span><span class="sxs-lookup"><span data-stu-id="a6f94-115">The steps in this guide may work with other versions, but that has not been tested.</span></span>

## <a name="feedback"></a><span data-ttu-id="a6f94-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a6f94-116">Feedback</span></span>

<span data-ttu-id="a6f94-117">Envíe sus comentarios sobre este tutorial en el [repositorio de github](https://github.com/microsoftgraph/msgraph-training-botframework).</span><span class="sxs-lookup"><span data-stu-id="a6f94-117">Please provide any feedback on this tutorial in the [GitHub repository](https://github.com/microsoftgraph/msgraph-training-botframework).</span></span>

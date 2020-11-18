---
ms.openlocfilehash: 9a320225c7e7e76506d73909a311fa019b1f74f3
ms.sourcegitcommit: e0d9b18d2d4cbeb4a48890f3420a47e6a90abc53
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49347857"
---
<!-- markdownlint-disable MD002 MD041 -->

<span data-ttu-id="f9afb-101">En este ejercicio, creará un registro nuevo de los canales de Bot y un registro de aplicaciones Web de Azure AD mediante Azure portal.</span><span class="sxs-lookup"><span data-stu-id="f9afb-101">In this exercise, you will create a new Bot Channels registration and an Azure AD web application registration using the Azure Portal.</span></span>

## <a name="create-a-bot-channels-registration"></a><span data-ttu-id="f9afb-102">Crear un registro de canales de bot</span><span class="sxs-lookup"><span data-stu-id="f9afb-102">Create a Bot Channels registration</span></span>

1. <span data-ttu-id="f9afb-103">Abra un explorador y vaya a [Azure portal](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="f9afb-103">Open a browser and navigate to the [Azure Portal](https://portal.azure.com).</span></span> <span data-ttu-id="f9afb-104">Inicie sesión con la cuenta asociada a su suscripción de Azure.</span><span class="sxs-lookup"><span data-stu-id="f9afb-104">Login using the account associated with your Azure subscription.</span></span>

1. <span data-ttu-id="f9afb-105">Seleccione el menú superior izquierdo y, a continuación, seleccione **crear un recurso**.</span><span class="sxs-lookup"><span data-stu-id="f9afb-105">Select the upper-left menu, then select **Create a resource**.</span></span>

    ![Captura de pantalla del menú del portal de Azure](images/create-resource.png)

1. <span data-ttu-id="f9afb-107">En la página **nueva** , busque `Bot Channel` y seleccione el **registro** de los canales de bot?</span><span class="sxs-lookup"><span data-stu-id="f9afb-107">On the **New** page, search for `Bot Channel` and select **Bot Channels Registration**.</span></span>

1. <span data-ttu-id="f9afb-108">En la página **registro de canales de bot** , seleccione **crear**.</span><span class="sxs-lookup"><span data-stu-id="f9afb-108">On the **Bot Channels Registration** page, select **Create**.</span></span>

1. <span data-ttu-id="f9afb-109">Rellene los campos obligatorios y deje el **punto de conexión de mensajería** en blanco.</span><span class="sxs-lookup"><span data-stu-id="f9afb-109">Fill in the required fields, and leave **Messaging endpoint** blank.</span></span> <span data-ttu-id="f9afb-110">El campo de **control de bot** debe ser único.</span><span class="sxs-lookup"><span data-stu-id="f9afb-110">The **Bot handle** field must be unique.</span></span> <span data-ttu-id="f9afb-111">Asegúrese de revisar los diferentes niveles de precios y seleccione qué tiene sentido en su escenario.</span><span class="sxs-lookup"><span data-stu-id="f9afb-111">Be sure to review the different pricing tiers and select what makes sense for your scenario.</span></span> <span data-ttu-id="f9afb-112">Si este es solo un ejercicio de aprendizaje, puede que quiera seleccionar la opción gratuita.</span><span class="sxs-lookup"><span data-stu-id="f9afb-112">If this is just a learning exercise, you may want to select the free option.</span></span>

1. <span data-ttu-id="f9afb-113">Seleccione el **identificador de aplicación y la contraseña de Microsoft y**, después, seleccione **crear nuevo**.</span><span class="sxs-lookup"><span data-stu-id="f9afb-113">Select the **Microsoft App ID and password**, then select **Create New**.</span></span>

1. <span data-ttu-id="f9afb-114">Seleccione **Crear identificador de aplicación en el portal de registro de la aplicación**.</span><span class="sxs-lookup"><span data-stu-id="f9afb-114">Select **Create App ID in the App Registration Portal**.</span></span> <span data-ttu-id="f9afb-115">Se abrirá una nueva ventana o pestaña en la hoja **registros** de la aplicación en Azure portal.</span><span class="sxs-lookup"><span data-stu-id="f9afb-115">This will open a new window or tab to the **App registrations** blade in the Azure Portal.</span></span>

1. <span data-ttu-id="f9afb-116">En la hoja **registros de aplicaciones** , seleccione **nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="f9afb-116">In the **App registrations** blade, select **New registration**.</span></span>

1. <span data-ttu-id="f9afb-117">Establezca los valores de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="f9afb-117">Set the values as follows.</span></span>

    - <span data-ttu-id="f9afb-118">Establezca **Nombre** como `Graph Calendar Bot`.</span><span class="sxs-lookup"><span data-stu-id="f9afb-118">Set **Name** to `Graph Calendar Bot`.</span></span>
    - <span data-ttu-id="f9afb-119">Establezca **Tipos de cuenta admitidos** en **Cuentas en cualquier directorio de organización y cuentas personales de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="f9afb-119">Set **Supported account types** to **Accounts in any organizational directory and personal Microsoft accounts**.</span></span>
    - <span data-ttu-id="f9afb-120">Deje **URI de redireccionamiento** vacía.</span><span class="sxs-lookup"><span data-stu-id="f9afb-120">Leave **Redirect URI** empty.</span></span>

    ![Captura de pantalla de la página registrar una aplicación](./images/aad-register-an-app.png)

1. <span data-ttu-id="f9afb-122">Seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="f9afb-122">Select **Register**.</span></span> <span data-ttu-id="f9afb-123">En la página de **Bot calendario de Graph** , copie el valor del identificador de la **aplicación (cliente)** y guárdelo, lo necesitará en los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="f9afb-123">On the **Graph Calendar Bot** page, copy the value of the **Application (client) ID** and save it, you will need it in the following steps.</span></span>

    ![Captura de pantalla del identificador de la aplicación del nuevo registro de la aplicación](./images/aad-application-id.png)

1. <span data-ttu-id="f9afb-125">Seleccione **Certificados y secretos** en **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="f9afb-125">Select **Certificates & secrets** under **Manage**.</span></span> <span data-ttu-id="f9afb-126">Seleccione el botón **Nuevo secreto de cliente**.</span><span class="sxs-lookup"><span data-stu-id="f9afb-126">Select the **New client secret** button.</span></span> <span data-ttu-id="f9afb-127">Escriba un valor en **Descripción** y seleccione una de las opciones para **Expires** y seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f9afb-127">Enter a value in **Description** and select one of the options for **Expires** and select **Add**.</span></span>

1. <span data-ttu-id="f9afb-128">Copie el valor del secreto de cliente antes de salir de esta página.</span><span class="sxs-lookup"><span data-stu-id="f9afb-128">Copy the client secret value before you leave this page.</span></span> <span data-ttu-id="f9afb-129">Lo necesitará en los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="f9afb-129">You will need it in the following steps.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f9afb-130">El secreto de cliente no se vuelve a mostrar, así que asegúrese de copiarlo en este momento.</span><span class="sxs-lookup"><span data-stu-id="f9afb-130">This client secret is never shown again, so make sure you copy it now.</span></span> <span data-ttu-id="f9afb-131">Tendrá que escribir este valor en varios lugares para mantenerlo seguro.</span><span class="sxs-lookup"><span data-stu-id="f9afb-131">You will need to enter this value in multiple places so keep it safe.</span></span>

1. <span data-ttu-id="f9afb-132">Vuelva a la ventana de registro del canal de bot en el explorador y pegue el identificador de la aplicación en el campo **identificador de aplicación de Microsoft** .</span><span class="sxs-lookup"><span data-stu-id="f9afb-132">Return to the Bot Channel Registration window in your browser, and paste the application ID into the **Microsoft App ID** field.</span></span> <span data-ttu-id="f9afb-133">Pegue el secreto de cliente en el campo **contraseña** .</span><span class="sxs-lookup"><span data-stu-id="f9afb-133">Paste your client secret into the **Password** field.</span></span> <span data-ttu-id="f9afb-134">Seleccione **ACEPTAR**.</span><span class="sxs-lookup"><span data-stu-id="f9afb-134">Select **OK**.</span></span>

1. <span data-ttu-id="f9afb-135">En la página de registro de los **canales de bots** , seleccione **crear**.</span><span class="sxs-lookup"><span data-stu-id="f9afb-135">On the **Bots Channels Registration** page, select **Create**.</span></span>

1. <span data-ttu-id="f9afb-136">Espere a que se cree el registro de los canales de bot?</span><span class="sxs-lookup"><span data-stu-id="f9afb-136">Wait for the Bot Channels registration to be created.</span></span> <span data-ttu-id="f9afb-137">Una vez creado, vuelva a la Página principal de Azure portal y, a continuación, seleccione **servicios de bot**.</span><span class="sxs-lookup"><span data-stu-id="f9afb-137">Once created, return to the Home page in the Azure Portal, then select **Bot Services**.</span></span> <span data-ttu-id="f9afb-138">Seleccione el nuevo registro de canal bots para ver sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="f9afb-138">Select your new Bots Channel registration to view its properties.</span></span>

## <a name="create-a-web-app-registration"></a><span data-ttu-id="f9afb-139">Creación de un registro de aplicaciones Web</span><span class="sxs-lookup"><span data-stu-id="f9afb-139">Create a web app registration</span></span>

1. <span data-ttu-id="f9afb-140">Vuelva a la sección **registros de aplicaciones** de Azure portal.</span><span class="sxs-lookup"><span data-stu-id="f9afb-140">Return to the **App registrations** section of the Azure Portal.</span></span>

1. <span data-ttu-id="f9afb-141">Seleccione **Nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="f9afb-141">Select **New registration**.</span></span> <span data-ttu-id="f9afb-142">En la página **Registrar una aplicación**, establezca los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="f9afb-142">On the **Register an application** page, set the values as follows.</span></span>

    - <span data-ttu-id="f9afb-143">Establezca **Nombre** como `Graph Calendar Bot Auth`.</span><span class="sxs-lookup"><span data-stu-id="f9afb-143">Set **Name** to `Graph Calendar Bot Auth`.</span></span>
    - <span data-ttu-id="f9afb-144">Establezca **Tipos de cuenta admitidos** en **Cuentas en cualquier directorio de organización y cuentas personales de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="f9afb-144">Set **Supported account types** to **Accounts in any organizational directory and personal Microsoft accounts**.</span></span>
    - <span data-ttu-id="f9afb-145">En **URI de redirección**, establezca la primera lista desplegable en `Web` y establezca el valor `https://token.botframework.com/.auth/web/redirect`.</span><span class="sxs-lookup"><span data-stu-id="f9afb-145">Under **Redirect URI**, set the first drop-down to `Web` and set the value to `https://token.botframework.com/.auth/web/redirect`.</span></span>

1. <span data-ttu-id="f9afb-146">Seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="f9afb-146">Select **Register**.</span></span> <span data-ttu-id="f9afb-147">En la página **autenticación de bot de calendario de Graph** , copie el valor del identificador de la **aplicación (cliente)** y guárdelo, lo necesitará en los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="f9afb-147">On the **Graph Calendar Bot Auth** page, copy the value of the **Application (client) ID** and save it, you will need it in the following steps.</span></span>

1. <span data-ttu-id="f9afb-148">Seleccione **Certificados y secretos** en **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="f9afb-148">Select **Certificates & secrets** under **Manage**.</span></span> <span data-ttu-id="f9afb-149">Seleccione el botón **Nuevo secreto de cliente**.</span><span class="sxs-lookup"><span data-stu-id="f9afb-149">Select the **New client secret** button.</span></span> <span data-ttu-id="f9afb-150">Escriba un valor en **Descripción** y seleccione una de las opciones para **Expires** y seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f9afb-150">Enter a value in **Description** and select one of the options for **Expires** and select **Add**.</span></span>

1. <span data-ttu-id="f9afb-151">Copie el valor del secreto de cliente antes de salir de esta página.</span><span class="sxs-lookup"><span data-stu-id="f9afb-151">Copy the client secret value before you leave this page.</span></span> <span data-ttu-id="f9afb-152">Lo necesitará en los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="f9afb-152">You will need it in the following steps.</span></span>

1. <span data-ttu-id="f9afb-153">Seleccione **permisos de API** y, a continuación, seleccione **Agregar un permiso**.</span><span class="sxs-lookup"><span data-stu-id="f9afb-153">Select **API permissions**, then select **Add a permission**.</span></span>

1. <span data-ttu-id="f9afb-154">Seleccione **Microsoft Graph** y, a continuación, seleccione **permisos delegados**.</span><span class="sxs-lookup"><span data-stu-id="f9afb-154">Select **Microsoft Graph**, then select **Delegated permissions**.</span></span>

1. <span data-ttu-id="f9afb-155">Seleccione los siguientes permisos y, a continuación, seleccione **Agregar permisos**.</span><span class="sxs-lookup"><span data-stu-id="f9afb-155">Select the following permissions, then select **Add permissions**.</span></span>

    - <span data-ttu-id="f9afb-156">**openid**</span><span class="sxs-lookup"><span data-stu-id="f9afb-156">**openid**</span></span>
    - <span data-ttu-id="f9afb-157">**profile**</span><span class="sxs-lookup"><span data-stu-id="f9afb-157">**profile**</span></span>
    - <span data-ttu-id="f9afb-158">**Calendars.ReadWrite**</span><span class="sxs-lookup"><span data-stu-id="f9afb-158">**Calendars.ReadWrite**</span></span>
    - <span data-ttu-id="f9afb-159">**MailboxSettings.Read**</span><span class="sxs-lookup"><span data-stu-id="f9afb-159">**MailboxSettings.Read**</span></span>

    ![Una captura de pantalla de los permisos configurados](images/configured-permissions.png)

### <a name="about-permissions"></a><span data-ttu-id="f9afb-161">Acerca de los permisos</span><span class="sxs-lookup"><span data-stu-id="f9afb-161">About permissions</span></span>

<span data-ttu-id="f9afb-162">Considere lo que cada uno de esos ámbitos de permisos permite que el bot haga y lo que el bot usará para ellos.</span><span class="sxs-lookup"><span data-stu-id="f9afb-162">Consider what each of those permission scopes allows the bot to do, and what the bot will use them for.</span></span>

- <span data-ttu-id="f9afb-163">**OpenID** y **Profile**: permite que el bot inicie sesión en los usuarios y obtenga información básica de Azure ad en el token de identidad.</span><span class="sxs-lookup"><span data-stu-id="f9afb-163">**openid** and **profile**: allows the bot to sign users in and get basic information from Azure AD in the identity token.</span></span>
- <span data-ttu-id="f9afb-164">**Calendars. ReadWrite**: permite al bot leer el calendario del usuario y agregar nuevos eventos al calendario del usuario.</span><span class="sxs-lookup"><span data-stu-id="f9afb-164">**Calendars.ReadWrite**: allows the bot to read the user's calendar and to add new events to the user's calendar.</span></span>
- <span data-ttu-id="f9afb-165">**MailboxSettings. Read**: permite al bot leer la configuración del buzón de correo del usuario.</span><span class="sxs-lookup"><span data-stu-id="f9afb-165">**MailboxSettings.Read**: allows the bot to read the user's mailbox settings.</span></span> <span data-ttu-id="f9afb-166">El bot usará esto para obtener la zona horaria seleccionada del usuario.</span><span class="sxs-lookup"><span data-stu-id="f9afb-166">The bot will use this to get the user's selected time zone.</span></span>
- <span data-ttu-id="f9afb-167">**User. Read**: permite al bot obtener el perfil del usuario de Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="f9afb-167">**User.Read**: allows the bot to get the user's profile from Microsoft Graph.</span></span> <span data-ttu-id="f9afb-168">El bot usará esto para obtener el nombre del usuario.</span><span class="sxs-lookup"><span data-stu-id="f9afb-168">The bot will use this to get the user's name.</span></span>

## <a name="add-oauth-connection-to-the-bot"></a><span data-ttu-id="f9afb-169">Agregar conexión OAuth al bot</span><span class="sxs-lookup"><span data-stu-id="f9afb-169">Add OAuth connection to the bot</span></span>

1. <span data-ttu-id="f9afb-170">Navegue hasta la página de registro de los canales de bot de bot en Azure portal.</span><span class="sxs-lookup"><span data-stu-id="f9afb-170">Navigate to your bot's Bot Channels Registration page on the Azure Portal.</span></span> <span data-ttu-id="f9afb-171">Seleccione **configuración** en **Administración de bot**.</span><span class="sxs-lookup"><span data-stu-id="f9afb-171">Select **Settings** under **Bot Management**.</span></span>

1. <span data-ttu-id="f9afb-172">En **configuración de conexión de OAuth** cerca de la parte inferior de la página, seleccione **Agregar configuración**.</span><span class="sxs-lookup"><span data-stu-id="f9afb-172">Under **OAuth Connection Settings** near the bottom of the page, select **Add Setting**.</span></span>

1. <span data-ttu-id="f9afb-173">Rellene el formulario como sigue y, a continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f9afb-173">Fill in the form as follows, then select **Save**.</span></span>

    - <span data-ttu-id="f9afb-174">**Name**: `GraphBotAuth`</span><span class="sxs-lookup"><span data-stu-id="f9afb-174">**Name**: `GraphBotAuth`</span></span>
    - <span data-ttu-id="f9afb-175">**Proveedor**: **Azure Active Directory V2**</span><span class="sxs-lookup"><span data-stu-id="f9afb-175">**Provider**: **Azure Active Directory v2**</span></span>
    - <span data-ttu-id="f9afb-176">**Identificador de cliente**: el identificador de aplicación del registro de **autenticación de bot de calendario de Graph** .</span><span class="sxs-lookup"><span data-stu-id="f9afb-176">**Client id**: The application ID of your **Graph Calendar Bot Auth** registration.</span></span>
    - <span data-ttu-id="f9afb-177">**Secreto de cliente**: el secreto de cliente del registro de **autenticación de bot de calendario de Graph** .</span><span class="sxs-lookup"><span data-stu-id="f9afb-177">**Client secret**: The client secret of your **Graph Calendar Bot Auth** registration.</span></span>
    - <span data-ttu-id="f9afb-178">**Dirección URL de intercambio de token**: dejar en blanco</span><span class="sxs-lookup"><span data-stu-id="f9afb-178">**Token Exchange URL**: Leave blank</span></span>
    - <span data-ttu-id="f9afb-179">**Identificador de inquilino**: `common`</span><span class="sxs-lookup"><span data-stu-id="f9afb-179">**Tenant ID**: `common`</span></span>
    - <span data-ttu-id="f9afb-180">**Ámbitos**: `openid profile Calendars.ReadWrite MailboxSettings.Read User.Read`</span><span class="sxs-lookup"><span data-stu-id="f9afb-180">**Scopes**: `openid profile Calendars.ReadWrite MailboxSettings.Read User.Read`</span></span>

1. <span data-ttu-id="f9afb-181">Seleccione la entrada **GraphBotAuth** en **configuración de conexión de OAuth**.</span><span class="sxs-lookup"><span data-stu-id="f9afb-181">Select the **GraphBotAuth** entry under **OAuth Connection Settings**.</span></span>

1. <span data-ttu-id="f9afb-182">Seleccione **probar conexión**.</span><span class="sxs-lookup"><span data-stu-id="f9afb-182">Select **Test Connection**.</span></span> <span data-ttu-id="f9afb-183">Se abrirá una nueva ventana o ficha del explorador para iniciar el flujo de OAuth.</span><span class="sxs-lookup"><span data-stu-id="f9afb-183">This opens a new browser window or tab to start the OAuth flow.</span></span>

1. <span data-ttu-id="f9afb-184">Si es necesario, inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="f9afb-184">If necessary, sign in.</span></span> <span data-ttu-id="f9afb-185">Revise la lista de permisos solicitados y, después, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f9afb-185">Review the list of requested permissions, then select **Accept**.</span></span>

1. <span data-ttu-id="f9afb-186">Debe ver un mensaje de **prueba de conexión a ' GraphBotAuth ' correcta** .</span><span class="sxs-lookup"><span data-stu-id="f9afb-186">You should see a **Test Connection to 'GraphBotAuth' Succeeded** message.</span></span>

> [!TIP]
> <span data-ttu-id="f9afb-187">Puede seleccionar el botón **copiar token** en esta página y pegar el token en [https://jwt.ms](https://jwt.ms) para ver las notificaciones dentro del token.</span><span class="sxs-lookup"><span data-stu-id="f9afb-187">You can select the **Copy Token** button on this page, and paste the token into [https://jwt.ms](https://jwt.ms) to see the claims inside the token.</span></span> <span data-ttu-id="f9afb-188">Esto es útil al solucionar problemas de errores de autenticación.</span><span class="sxs-lookup"><span data-stu-id="f9afb-188">This is useful when troubleshooting authentication errors.</span></span>

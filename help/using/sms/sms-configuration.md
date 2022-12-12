---
solution: Journey Optimizer
product: journey optimizer
title: SMS configuration
description: Learn how to configure your environment to send SMS with Journey Optimizer
role: Admin
level: Intermediate
exl-id: 4dcd22ed-bf7e-4789-ab7b-33544c857db8
---
# Configure SMS channel {#sms-configuration}

[!DNL Journey Optimizer] allows you to create your journeys and send messages to targeted audience. 

Before sending SMS, configure your instance. You need to [integrate the provider settings](#create-api) with Journey Optimizer and [create an SMS surface](#message-preset-sms) (i.e. SMS preset). These steps must be performed by an [Adobe Journey Optimizer system administrator](../start/path/administrator.md).

>[!IMPORTANT]
>
>Adobe Journey Optimizer currently integrates with third-party providers such as Sinch and Twilio, who offer SMS services independent of Adobe Journey Optimizer.  Prior to SMS configuration, you must create an account with one of these SMS providers to receive the API Token and Service ID which will enable you to establish the connection between Adobe Journey Optimizer and the applicable SMS provider. Your use of SMS services will be subject to additional terms and conditions from the applicable SMS provider. Given that Sinch and Twilio are third-party products available to Adobe Journey Optimizer users via an integration, for any issues or inquiries related to the SMS services, users of Sinch or Twilio will need to contact the applicable SMS provider for assistance. Adobe does not control and is not responsible for third-party products.
>

## Create new API credential {#create-api}

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_api_header"
>title="Configure your SMS vendor with Journey Optimizer"
>abstract="Select your vendor and fill in your SMS API credentials."

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_api"
>title="Configure your SMS vendor with Journey Optimizer"
>abstract="Before sending SMS, you must integrate the provider settings with Journey Optimizer. Once done, you will need to create an SMS surface. These steps must be performed by an Adobe Journey Optimizer system administrator."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/sms/sms-configuration.html?lang=en#message-preset-sms" text="Create an SMS channel surface"

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_configuration"
>title="Select the SMS vendor configuration"
>abstract="Select the API credentials configured for your SMS vendor."

To configure your SMS vendor with Journey Optimizer, follow these steps:

1. Access the **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL API Credentials]** menu, then click **[!UICONTROL Create API credential]**.

    ![](assets/sms_6.png)

1. Select your **[!UICONTROL SMS vendor]**:

    * [!DNL Sinch]. To find your **[!UICONTROL Service ID]** and **[!UICONTROL API Token]**, access SMS > APIs menu from your Sinch account.
    * [!DNL Twilio]. To find your **[!UICONTROL Service ID]** and **[!UICONTROL API Token]**, access the Account Info pane of the Console Dashboard page.

1. Enter a **[!UICONTROL Name]** for your API Credential.

1. Enter your **[!UICONTROL Service ID]** and **[!UICONTROL API Token]**.

    ![](assets/sms_7.png)

1. Click **[!UICONTROL Submit]** when you finished the configuration of your API credentials.

After creating and configuring your API credential, you now need to create a channel surface (i.e. message preset) for SMS messages.

## Create a channel surface for SMS messages {#message-preset-sms}

>[!CONTEXTUALHELP]
>id="ajo_admin_surface_sms_type"
>title="Define the SMS category"
>abstract="Select the type of SMS messages that will be sent when using this surface: Marketing for promotional SMS messages, which require user consent, or Transactional for non-commercial SMS messages, that can also be sent to unsubscribed profiles in specific contexts."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/privacy/consent/opt-out.html#sms-opt-out-management" text="Opt-out in marketing SMS messages"

Once your SMS channel has been configured, you need to create a channel surface to be able to send SMS messages from **[!DNL Journey Optimizer]**.

To create a channel surface, follow these steps:

1. Access the **[!UICONTROL Channels]** > **[!UICONTROL Branding]** > **[!UICONTROL Channel surfaces]** menu, then click **[!UICONTROL Create channel surface]**.

    ![](assets/preset-create.png)

1. Enter a name and a description (optional) for the surface, then select the SMS channel.

    ![](assets/sms_preset.png)

    >[!NOTE]
    >
    > Names must begin with a letter (A-Z). It can only contain alpha-numeric characters. You can also use underscore `_`, dot`.` and hyphen `-` characters.

1. Configure the **SMS** settings.

     ![](assets/preset-sms.png)

    * Select the **[!UICONTROL SMS Type]** that will be sent with the surface: **[!UICONTROL Transactional]** or **[!UICONTROL Marketing]**.
    
    * Select the **[!UICONTROL SMS configuration]** to associate with the surface.
        
      For more on how to configure your environment to send SMS messages, refer to [this section](#create-api).

    * Enter the **[!UICONTROL Sender number]** ​you want to use for your communications.

    * Select your **[!UICONTROL SMS Execution Field]** to select the **[!UICONTROL Profile attribute]** associated with the profiles' phone numbers.

1. Once all the parameters have been configured, click **[!UICONTROL Submit]** to confirm. You can also save the channel surface as draft and resume its configuration later on.

    ![](assets/sms_preset_2.png)

1. Once the channel surface has been created, it displays in the list with the **[!UICONTROL Processing]** status.

    >[!NOTE]
    >
    >If the checks are not successful, learn more on the possible failure reasons in [this section](#monitor-channel-surfaces).  

1. Once the checks are successful, the channel surface gets the **[!UICONTROL Active]** status. It is ready to be used to deliver messages.

    ![](assets/preset-active.png)

You are now ready to send SMS messages with Journey Optimizer.

**Related topics**

* [Create an SMS message](create-sms.md)
* [Add a message in a journey](../building-journeys/journeys-message.md)
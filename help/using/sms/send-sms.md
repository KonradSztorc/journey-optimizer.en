---
solution: Journey Optimizer
product: journey optimizer
title: Preview and test your SMS message
description: Learn how to preview and test your SMS message in Journey Optimizer
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: 31c9b080-e334-4a11-af33-4c6f115c70a4
---
# Preview and test your SMS message {#send-sms}

## Preview your SMS {#preview-sms}

Once your message content has been defined, you can use test profiles to preview and test it. If you inserted personalized content, you can check how this content is displayed in the message, using test profile data.

1. Click **[!UICONTROL Simulate content]**.

1. Click **[!UICONTROL Manage test profiles]** to add a test profile.

1. Find your test profile with the **[!UICONTROL Identity namespace]** and **[!UICONTROL Identity value]** fields. Then, click **[!UICONTROL Add profile]**.

    ![](assets/sms_preview_3.png)

1. Once you selected your test profile, you can close the **[!UICONTROL Add test profile]** window.

1. From the **Preview & test** window, test profile data is added to the message content.

    ![](assets/sms_preview_2.png)


## Validate your SMS{#sms-validate}

You must check alerts in the upper section of the editor. Some of them are simple warnings, but others can prevent you from sending the message. Two types of alerts can happen: warnings and errors.

* **Warnings** refer to recommendations and best practices. For example, a warning message is displayed if your SMS message is empty.

* **Errors** prevent you from testing or activating the journey, or publishing the campaign, as long as they are not resolved. For example, an error message warns you when the subject line is missing.

![](assets/sms-alert-button.png)

>[!NOTE]
>
> To improve your deliverability, use the phone numbers in the formats supported by the provider. For example, Twilio and Sinch only support phone numbers in E.164 format.

## Send your SMS{#sms-send}

When your SMS message is ready, complete the configuration of your [journey](../building-journeys/journey-gs.md) or [campaign](../campaigns/create-campaign.md) to send it.

**Related topics**

* [Configure SMS channel](sms-configuration.md)
* [SMS report](../reports/journey-global-report.md#sms-global)
* [Create an SMS message](create-sms.md)
* [Add a message in a journey](../building-journeys/journeys-message.md)

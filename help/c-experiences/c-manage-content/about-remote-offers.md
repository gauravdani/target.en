---
description: Use remote offers to host content outside of Target that Target references and delivers to users' websites. This content might be in a content management or other system, either for ease-of-use or for security reasons.
keywords: remote offer;remote offer selection matrix;cached content;dynamic content
seo-description: Use remote offers to host content outside of Target that Target references and delivers to users' websites. This content might be in a content management or other system, either for ease-of-use or for security reasons.
seo-title: Create remote offers
solution: Target
title: Create remote offers
topic: Standard
uuid: 5aaff281-e96c-41a6-849e-2c3b0e35f161
---

# Create remote offers{#create-remote-offers}

Use remote offers to host content outside of Target that Target references and delivers to users' websites. This content might be in a content management or other system, either for ease-of-use or for security reasons.

>[!NOTE]
>
>Remote offers can be created only in the forms-based composer. Content will be injected in the mbox locations, so these are most likely not appropriate for a global mbox.
>
>[!DNL Target Classic] included similar features: [!UICONTROL Offer on Your Site] and [!UICONTROL Offer Outside Test&Target].

Some examples of remote offers include:

* Different versions of your cross-sells 
* Dynamic shopping cart messages 
* Forms 
* Calculators 
* Interest rate updates

**To create a remote offer:**

1. Click **[!UICONTROL Offers]**, then select the **[!UICONTROL Code Offers]** tab. 
1. Click **[!UICONTROL Create]** > **[!UICONTROL Remote Offer]**.

   ![](assets/remote_offer_ui.png)

1. Provide a descriptive name for the offer.

   A descriptive name helps you and others quickly find the offer in the [!UICONTROL Assets] library. 

1. Specify the remote URL for the remote offer:

   | Option | Description |
   |--- |--- |
   |Cached|The content for a cached remote offer is served from Target.<br>Every two hours, [!DNL Target] fetches the content at the remote URL and then stores the content inside Target. When visitors load a site with an experience that includes a remote offer, the offer is delivered by Target.<br>Cached remote offers provide enhanced security because somebody logged in toTarget cannot change the content. To change the content, someone would need to log in to the content management or other system and change the content there.<br>You can specify an absolute or relative URL for a cached remote offer.|
   |Dynamic|A dynamic remote offer is served from the content management or other system rather than from Target.<br>You might not want the content periodically cached and then delivered by Target whenever visitors load a site with an experience that includes a remote offer. Instead, you want to call the system that is hosting the content, possibly pass in specific information so that the returned offer can be dynamic, or different, for each user.<br>For example, if a user logs in to a website for a credit card that includes an experience with a dynamic remote offer, you could pass parameters into the URL for the user's account information. Then the website could provide user-specific information, such as account balance.<br>Click [!UICONTROL Add Parameter] to add one or more mbox or request parameters.|

1. Click **[!UICONTROL Save]**.

## Best Practices for Using Remote Offers {#section_7718512D08E14121B6F6B8C38134F4BC}

Best practices for using remote offers in your activities:

* If your offer resides in the same domain as the mboxes, using the [!UICONTROL Cached] option lets you use relative URLs in describing your offer location.

  This means that when you move your activity from your staging servers to production, the content will automatically be accessible without having to change the URL manually. 

* If your test involves data dynamically generated by your server, the [!UICONTROL Dynamic] option might be the right choice. 
* If you plan to test only the appearance of your existing remote offer content, use the [!UICONTROL Visual Experience Composer] to change the look and feel of the content that is returned from the content management system. 
* Use the Remote Offer Selection Matrix to help you choose the offer best suited for your specific case. Consult your account representative if you have questions.

## How Dynamic Remote Offers Work {#concept_CC2A969420B34364A9FA78C1CE251818}

Dynamic remote offers use your dynamic page technology to pass values to the offer.

The offer is executed after you render the page. An invisible iframe gathers the data, copies it out of the frame and inserts in on the page, loading your passed values.

![](assets/remote_offer_howitworks_2.jpeg)

## Remote Offer Selection Matrix {#reference_B23BEDD29DDD47709A7651AFD27E776B}

The Remote Offer Selection Matrix helps you decide which type of remote offer to choose: [!UICONTROL Cached] or [!UICONTROL Dynamic].

| Feature | Cached | Dynamic |
|--- |--- |--- |
|Updates each time a visitor makes a request|No|Yes|
|Content updates|Cached every 2 hours|Updated immediately upon each request|
|Load time|Faster|Slower due to request processing|
|Can see JavaScript on page|Yes|No, but can pass via URL|
|Offers can include JavaScript|Yes|No|
|Offer URL|Absolute or Relative|Relative|
|Requesting computer|Adobe servers|The visitor's computer, which carries the visitor's cookies|
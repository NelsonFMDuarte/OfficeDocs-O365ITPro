---
title: "Create DNS records at Freenom for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c

description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Freenom for Office 365."
---

# Create DNS records at Freenom for Office 365

[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for. 
  
> [!CAUTION]
> The Freenom website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 plan you use, there are significant service limitations, and you may want to switch to a different DNS hosting provider. 
  
If despite the service limitations, you choose to manage your own Office 365 DNS records at Freenom, follow the steps in this article to verify your domain and set up DNS records for email and other services.
  
﻿These are the main records to add.
  
- [ Add a TXT record for verification ](create-dns-records-at-freenom.md#bkmk_txt)
    
- [Add an MX record so email for your domain will come to Office 365](create-dns-records-at-freenom.md#bkmk_mx)
    
- [Add the CNAME records that are required for Office 365](create-dns-records-at-freenom.md#bkmk_cname)
    
- [Add a TXT record for SPF to help prevent email spam](create-dns-records-at-freenom.md#bkmk_spf)
    
To learn about webhosting and DNS for websites with Office 365, see﻿ [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification
<a name="bkmk_txt"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/). You'll be prompted to log in.
    
    ![Freenom login](../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Choose **Services**, and then choose **My Domains**.
    
    ![Freenom select Services and My Domains](../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. For the domain that you want to edit, choose **Manage Domain**.
    
    ![Freenom select Manage Domain](../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Choose **Manage Freenom DNS**.
    
    ![Freenom Manage Freenom DNS](../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. Under **Add Record**, in the **Type** column, choose **TXT** from the menu. 
    
    ![Freenom Add Record type TXT](../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. In the boxes for the new record, type or copy and paste the values from the following table. 
    
|**﻿Name**|**﻿Type**|**﻿TTL**|**﻿Target**|
|:-----|:-----|:-----|:-----|
|﻿(leave blank)  <br/> |﻿TXT  <br/> |﻿3600 (seconds)  <br/> |MS=msXXXXXXXX  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Freenom TXT values for verification](../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. Choose **Save Changes**.
    
    ![Freenom TXT record Save Changes](../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
    ![Domain name selected in Office 365 Admin Center](../media/c61204f1-a025-448b-a2a1-c4d7abee7a06.png)
  
3. On the **Setup** page, choose **Start setup**.
    
    ![Start setup](../media/5f6578af-ae32-49e8-b283-ec2d080420da.png)
  
4. On the **Verify domain** page, choose **Verify**.
    
    ![Verify](../media/c256ab1d-03f2-498e-bb63-19e4d49a6b97.png)
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add an MX record so email for your domain will come to Office 365
<a name="bkmk_mx"> </a>

1. To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/). You'll be prompted to log in.
    
    ![Freenom login](../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Choose **Services**, and then choose **My Domains**.
    
    ![Freenom select Services and My Domains](../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. For the domain that you want to edit, choose **Manage Domain**.
    
    ![Freenom select Manage Domain](../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Set the name serves for your domain to the default Freenom name servers. Choose **Management Tools**, and then choose **Nameservers**.
    
    ![Freenom Nameservers setting](../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. Make sure **Use default nameservers** is selected, and then choose **Change Nameservers**.
    
    ![Freenom Change Nameservers](../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. Choose **Manage Freenom DNS**.
    
    ![Freenom choose Manage Freenom DNS](../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. Under **Add Record**, in the **Type** column, choose **MX** from the menu. 
    
    ![Freenom Add Record type MX](../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. In the boxes for the new record, type or copy and paste the values from the first row of the following table. 
    
|**﻿Name**|**﻿Type**|**﻿TTL**|**﻿Target**|**﻿Priority**|
|:-----|:-----|:-----|:-----|:-----|
|﻿(leave blank)  <br/> |﻿MX (Mail Exchanger)  <br/> |﻿3600 (seconds)  <br/> |\<domain-key\>.mail.protection.outlook.com  <br/> > [!NOTE]> Get your  *\<domain-key\>*  from your Office 365 portal account.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |﻿10  <br/> For more information about priority, see [What is MX priority?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9) <br/> |
   
    ![Freenom MX record](../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. ﻿Choose **Save Changes**.
    
    ![Freenom MX record Save Changes](../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. If there are any other MX records, delete them all. For each record, choose **Delete**. When the message **Do you really want to remove this entry?** appears, choose **OK**.
    
## Add the CNAME records that are required for Office 365
<a name="bkmk_cname"> </a>

1. To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/). You'll be prompted to log in.
    
    ![Freenom login](../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Choose **Services**, and then choose **My Domains**.
    
    ![Freenom select Services and My Domains](../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. For the domain that you want to edit, choose **Manage Domain**.
    
    ![Freenom select Manage Domain](../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Choose **Manage Freenom DNS**.
    
    ![Freenom choose Manage Freenom DNS](../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. Under **Add Record**, in the **Type** column, choose **CNAME** from the menu. 
    
    ![Freenom Add Record type CNAME](../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. Create the first CNAME record. In the boxes for the new record, type or copy and paste the values from the first row of the following table. 
    
|**﻿Name**|**﻿Record type**|**﻿TTL**|**﻿Target**|
|:-----|:-----|:-----|:-----|
|autodiscover  <br/> |CNAME  <br/> |3600 (seconds)  <br/> |autodiscover.outlook.com  <br/> |
|sip  <br/> |CNAME  <br/> |3600 (seconds)  <br/> |sipdir.online.lync.com  <br/> |
|lyncdiscover  <br/> |CNAME  <br/> |3600 (seconds)  <br/> |webdir.online.lync.com  <br/> |
|msoid  <br/> |CNAME  <br/> |3600 (seconds)  <br/> |clientconfig.microsoftonline-p.net  <br/> |
|enterpriseregistration  <br/> |CNAME  <br/> |3600 (seconds)  <br/> |enterpriseregistration.windows.net  <br/> |
|enterpriseenrollment  <br/> |CNAME  <br/> |3600 (seconds)  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> |
   
    ![Freenom CNAME values](../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. ﻿Choose **﻿Save Changes**.
    
    ![Freenom CNAME Save Changes](../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. Repeat the previous steps to create the other five CNAME records. 
    
    For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.
    
## Add a TXT record for SPF to help prevent email spam
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. Need examples? Check out these [](external-domain-name-system-records.md#BKMK_SPFrecords). To validate your SPF record, you can use one of these [SPF validation tools](92a43f6a-4651-455a-a1cc-300684bedcfa.md). 
  
1. To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/). You'll be prompted to log in.
    
    ![Freenom login](../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Choose **Services**, and then choose **My Domains**.
    
    ![Freenom select Services and My Domains](../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. For the domain that you want to edit, choose **Manage Domain**.
    
    ![Freenom select Manage Domain](../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Choose **Manage Freenom DNS**.
    
    ![Freenom choose Manage Freenom DNS](../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. Under **Add Record**, in the **Type** column, choose **TXT** from the menu. 
    
    ![Freenom Add Record type TXT](../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. In the boxes for the new record, type or copy and paste the following values. 
    
|**﻿Name**|**﻿Record type**|**﻿TTL**|**﻿Target**|
|:-----|:-----|:-----|:-----|
|﻿(leave blank)  <br/> |﻿TXT  <br/> |﻿3600 (seconds)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> > [!NOTE]> We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
   
    ![Freenom TXT values for SPF](../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. ﻿Choose **Save Changes**.
    
    ![Freenom TXT record for SPF Save Changes](../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

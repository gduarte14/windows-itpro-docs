---
title: Link the GPO to the Domain (Windows)
description: Learn how to link a GPO to the Active Directory container for the target devices, after you configure it in Windows Defender Firewall with Advanced Security.
ms.reviewer: jekrynit
ms.author: paoloma
ms.prod: m365-security
ms.localizationpriority: medium
author: paolomatarazzo
manager: aaroncz
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.date: 09/08/2021
ms.technology: windows-sec
appliesto: 
  - ✅ <b>Windows 10</b>
  - ✅ <b>Windows 11</b>
  - ✅ <b>Windows Server 2016</b>
  - ✅ <b>Windows Server 2019</b>
  - ✅ <b>Windows Server 2022</b>
---

# Link the GPO to the Domain


After you create the GPO and configure it with security group filters and WMI filters, you must link the GPO to the container in Active Directory that contains all of the target devices.

If the filters comprehensively control the application of the GPO to only the correct devices, then you can link the GPO to the domain container. Alternatively, you can link the GPO to a site container or organizational unit if you want to limit application of the GPO to that subset of devices.

**Administrative credentials**

To complete this procedure, you must be a member of the Domain Admins group, or otherwise be delegated permissions to modify the GPOs.

To link the GPO to the domain container in Active Directory

1.  Open the Group Policy Management console.

2.  In the navigation pane, expand **Forest:** *YourForestName*, expand **Domains**, and then expand *YourDomainName*.

3.  Right-click *YourDomainName*, and then click **Link an Existing GPO**.

4.  In the **Select GPO** dialog box, select the GPO that you want to deploy, and then click **OK**.

5.  The GPO appears in the **Linked Group Policy Objects** tab in the details pane and as a linked item under the domain container in the navigation pane.

6.  You can adjust the order of the linked GPOs to ensure that the higher priority GPOs are processed last. Select a GPO and click the up or down arrows to move it. The GPOs are processed by the client device from the highest link order number to the lowest.

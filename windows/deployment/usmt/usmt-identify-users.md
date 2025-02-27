---
title: Identify Users (Windows 10)
description: Learn how to identify users you plan to migrate, as well as how to migrate local accounts and domain accounts.
ms.reviewer: 
manager: dougeby
ms.author: aaroncz
ms.prod: w10
author: aczechowski
ms.topic: article
ms.localizationpriority: medium
---

# Identify Users

It is important to carefully consider how you plan to migrate users. By default, all users are migrated by User State Migration Tool (USMT) 5.0. You must specify which users to include by using the command line. You cannot specify users in the .xml files. For instructions on how to migrate users, see [Migrate User Accounts](usmt-migrate-user-accounts.md).

## In this topic

- [Migrating Local Accounts](#bkmk-8)
- [Migrating Domain Accounts](#bkmk-9)
- [Command-Line Options](#bkmk-7)

## <a href="" id="bkmk-8"></a>Migrating Local Accounts

Before migrating local accounts, note the following:

- [You must explicitly specify that local accounts that are not on the destination computer should be migrated.](#bkmk-8) If you are migrating local accounts and the local account does not exist on the destination computer, you must use the **/lac** option when using the LoadState command. If the **/lac** option is not specified, no local user accounts will be migrated.

- [Consider whether to enable user accounts that are new to the destination computer.](#bkmk-8) The **/lae** option enables the account that was created with the **/lac** option. However, if you create a disabled local account by using only the **/lac** option, a local administrator must enable the account on the destination computer.

- [Be careful when specifying a password for local accounts.](#bkmk-8) If you create the local account with a blank password, anyone could log on to that account on the destination computer. If you create the local account with a password, the password is available to anyone with access to the USMT command-line tools.

>[!NOTE]
>If there are multiple users on a computer, and you specify a password with the **/lac** option, all migrated users will have the same password.

## <a href="" id="bkmk-9"></a>Migrating Domain Accounts

The source and destination computers do not need to be connected to the domain for domain user profiles to be migrated.

## <a href="" id="bkmk-7"></a>Command-Line Options

USMT provides several options to migrate multiple users on a single computer. The following command-line options specify which users to migrate.

- [Specifying users.](#bkmk-8) You can specify which users to migrate with the **/all**, **/ui**, **/uel**, and **/ue** options with both the ScanState and LoadState command-line tools.

  >[!IMPORTANT]
  >The **/uel** option excludes users based on the **LastModified** date of the Ntuser.dat file. The **/uel** option is not valid in offline migrations.

- [Moving users to another domain.](#bkmk-8) You can move user accounts to another domain using the **/md** option with the LoadState command-line tool.

- [Creating local accounts.](#bkmk-8) You can create and enable local accounts using the **/lac** and **/lae** options with the LoadState command-line tool.

- [Renaming user accounts.](#bkmk-8) You can rename user accounts using the **/mu** option.

  >[!NOTE]
  >By default, if a user name is not specified in any of the command-line options, the user will be migrated.

## Related topics

[Determine What to Migrate](usmt-determine-what-to-migrate.md)<br>
[ScanState Syntax](usmt-scanstate-syntax.md)<br>
[LoadState Syntax](usmt-loadstate-syntax.md)

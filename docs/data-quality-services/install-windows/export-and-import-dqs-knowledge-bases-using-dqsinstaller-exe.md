---
title: "Export and import DQS knowledge bases using DQSInstaller.exe"
description: Learn how to use the DQSInstaller.exe to export and import DQS Knowledge bases for SQL Server Data Quality Services (DQS).
author: swinarko
ms.author: sawinark
ms.date: "03/01/2017"
ms.service: sql
ms.subservice: data-quality-services
ms.topic: conceptual
ms.custom: seo-lt-2019
---
# Export and Import DQS Knowledge Bases Using DQSInstaller.exe

[!INCLUDE [sql-windows-only](../../includes/applies-to-version/sql-windows-only.md)]

  For an existing installation of DQS, you can export all the knowledge bases in your [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] to a DQS backup file (.dqsb) at once, and then later use the .dqsb file to import all the knowledge bases to a different [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] at once by running the DQSInstaller.exe file from the command prompt. For more information about running DQSInstaller.exe from the command prompt, see [Run DQSInstaller.exe from Command Prompt](../../data-quality-services/install-windows/run-dqsinstaller-exe-to-complete-data-quality-server-installation.md#CommandPrompt) in [Run DQSInstaller.exe to Complete Data Quality Server Installation](../../data-quality-services/install-windows/run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).  
  
 This feature enables you to take a backup of *all* your knowledge bases in [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] at once without having to individually export each knowledge base to a .dqs file by using [!INCLUDE[ssDQSClient](../../includes/ssdqsclient-md.md)]. Similarly, you can import *all* the knowledge bases from the backup file into another [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] at once without having to individually import each knowledge base from a .dqs file by using [!INCLUDE[ssDQSClient](../../includes/ssdqsclient-md.md)]. This is particularly useful for backing up and restoring your knowledge bases when you are uninstalling [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] on a computer, and then reinstalling it on a different computer. You can easily export all the knowledge bases in an existing installation of [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] to a DQS backup file (.dqsb), and then import all the knowledge bases from the backup file after installing [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] on a different computer.  
  
##  <a name="export"></a> Exporting Knowledge Bases to .dqsb File  
 You can export all the knowledge bases in the existing [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] at any time or while uninstalling [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)].  
  
-   To export all the knowledge bases in a [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] to a DQS backup file (.dqsb), run DQSInstaller.exe with the `exportkbs` parameter from the command prompt, along with the full path and file name where you want to export the knowledge bases. For example, to export all the knowledge bases to the DQSBackup.dqsb file in the C: drive:  
  
    ```  
    dqsinstaller.exe -exportkbs c:\DQSBackup.dqsb  
    ```  
  
    > [!NOTE]  
    >  If the provided file name already exists at the specified location, the installer prompts you whether to overwrite the file.  
  
-   To export all the knowledge bases to a DQS backup file while uninstalling [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)], run DQSInstaller.exe with the `uninstall` parameter from the command prompt, along with the full path and file name where you want to export the knowledge bases. For example, to export all the knowledge bases to the DQSBackup.dqsb file in the C: drive, and then uninstall [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)]:  
  
    ```  
    dqsinstaller.exe -uninstall c:\DQSBackup.dqsb  
    ```  
  
    > [!NOTE]  
    >  If you do not specify the full path and file name of the DQS backup file while uninstalling [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] from the command prompt using the `uninstall` parameter, a message is displayed stating that all the knowledge bases will be deleted, and allows you to choose whether to continue with the uninstall process.  
  
##  <a name="import"></a> Importing Knowledge Bases from .dqsb File  
 You can import all the knowledge bases from a DQS backup file (.dqsb) after completing the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] installation. To import knowledge bases, you must have a valid DQS backup file (.dqsb).  
  
 Run the DQSInstaller.exe file with the `importkbs` parameter from the command prompt, along with the full path and file name from where you want to import the knowledge bases. For example, to import all the knowledge bases from the DQSBackup.dqsb file in the C: drive:  
  
```  
dqsinstaller.exe -importkbs c:\DQSBackup.dqsb  
```  
  
 If there are existing knowledge bases in your [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] with the same name as the ones you are importing, the names of the imported knowledge bases will be appended with an underscore (_) followed by an integer value starting with 1. For example, if the "CompanyName" domain is duplicate, the imported domain name will be "CompanyName_1."  
  
## See Also  
 [Run DQSInstaller.exe to Complete Data Quality Server Installation](../../data-quality-services/install-windows/run-dqsinstaller-exe-to-complete-data-quality-server-installation.md)   
 [Install Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md)   
 [Export a Knowledge Base to a .dqs File](../../data-quality-services/export-a-knowledge-base-to-a-dqs-file.md)   
 [Import a Knowledge Base from a .dqs File](../../data-quality-services/import-a-knowledge-base-from-a-dqs-file.md)  
  
  

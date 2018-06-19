---
title: Sysprep による BizTalk Server VHD (BizTalk Server サンプル) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35f0146d-60ed-4265-983a-0e3665ef2ae4
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc6ec29ece503f324758cdc08a6ff1351c066af4
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007771"
---
# <a name="sysprep-a-biztalk-server-vhd-biztalk-server-sample"></a>Sysprep による BizTalk Server VHD の準備 (BizTalk Server サンプル)
Sysprep は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がインストールされている仮想マシンのスナップショットを作成し、他の仮想マシンに簡単に展開できるようにします。  
  
## <a name="prerequisites"></a>前提条件  
 Sysprep を使用するのには、HYPER-V で仮想マシンの使用のある程度の知識が必要です。 BizTalk Server とその前提条件のすべてのクリーンで標準インストールと仮想マシンも必要です。  
  
 Sysprep は Windows Server 2008 および Windows Vista SP1 で動作します。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 Sysprep は、他の仮想マシンに簡単に展開できるように、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] インストールの VHD を作成します (オペレーティング システムとすべての前提条件を含みます)。 Sysprep を使用して作成されたイメージは、初めて起動するときに、ドメインに参加するために新しいコンピューター名を選択します。 BizTalk Server が正常に実行されるには、レジストリおよびデータベースに格納されているコンピューター名のさまざまなインスタンスを更新する必要があります。  
  
 このドキュメントでは、BizTalk Server は単一のコンピューターで実行するように構成されているものとし、コンピューター名の他のインスタンスを新しい名前で更新する方法を示します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルは、SDK がある次の場所にあります。  
  
 \<*パスのサンプル*\>\Admin\Sysprep\  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
> [!NOTE]
>  次の表の .vbs ファイルと .cmd ファイルはすべて Sysprep の応答ファイル (Sysprep.xml および SetupCompletecmd.txt) で自動化されており、ここでは参照のためにのみ示してあります。 これらのスクリプトを手動で実行する必要がある場合は、表に示されている順序で実行してください。  
  
|ファイル|Description|  
|----------|-----------------|  
|Sysprep.xml|応答ファイル|  
|SetupCompletecmd.txt|応答ファイル|  
|ReplaceMachineName.vbs|目的: は、ファイルを開き、現在のコンピューター名を指定する文字列のすべてのインスタンスで置き換えます。 他のスクリプトおよび xml ファイルを準備し、bm.exe.config を更新するのに便利です。<br /><br /> 使用法: ReplaceMachineName.vbs\<ファイルを開く\>\<を置換する文字列\>|  
|UpdateRegistry.vbs|目的: は、BizTalk のレジストリ設定に格納されているコンピューター名を更新します。<br /><br /> 使用法: UpdateRegistry.vbs \<UpdateInfo.xml\>です。 この xml ファイルの $(OLDCOMPUTERNAME) および $(NEWCOMPUTERNAME) のすべてのインスタンスを置き換えてください。|  
|UpdateDatabase.vbs|目的: は、BizTalk 管理データベースに格納されているコンピューター名を更新します。<br /><br /> 使用法: UpdateDatabase.vbs \<UpdateInfo.xml\>|  
|UpdateBAMDb.vbs|目的: は、BAM データベースに格納されているコンピューター名を更新します。<br /><br /> 使用法: UpdateBamDb.vbs \<UpdateInfo.xml\>|  
|UpdateSSO.cmd|目的: は、エンタープライズ シングル サインオン (SSO) シークレット サーバーを再構成します。<br /><br /> 使用法: sso.cmd \<UpdateInfo.xml\>|  
|UpdateSqlServerAndInstanceName.cmd|目的: SQL および SQL Express を再構成するには、一連の依存サービスを再起動し、BAMAlerts を再登録します。<br /><br /> 使用法: は、スクリプトを編集し、$(NEWCOMPUTERNAME) のすべてのインスタンスを置き換えると BAM 警告の serviceusername および servicepassword を更新します。 その後、UpdateSqlServerAndInstanceName.cmd を実行し、1 番目の引数として古いコンピューター名を渡します。|  
  
## <a name="creating-the-answer-files-and-running-sysprep"></a>応答ファイルの作成と Sysprep の実行  
  
#### <a name="to-create-the-answer-files"></a>応答ファイルを作成するには  
  
1.  インストールし、仮想マシンで BizTalk Server を構成します。 Sysprep はカスタマイズされたインストールをサポートしないので、必ず既定のインストールと構成オプションを使用します。  
  
2.  含まれる "scripts" フォルダーの内容を仮想マシンの C:\Scripts にコピーします。  
  
3.  Sysprep.xml で次の行を変更することにより、sysprep 応答ファイルを準備します。 (注: これらの行が付いている、"!" 前にします。)これらをテンプレートとして使用して、または独自に作成および経由でコピー、 \<FirstLogonCommands\>セクションです。  
  
    -   $(OLDCOMPUTERNAME) 仮想マシンの現在のコンピューター名に置き換えます。  
  
    -   ユーザー アカウント  
  
    -   パスワード  
  
    -   会社に関するすべての詳細も、UpdateSqlServerAndInstance.cmd および作成する Sysprep.xml で更新する必要があります。  
  
     使用して最初から、Sysprep 応答ファイルを作成する代わりに、[自動インストール キット (AIK)](http://www.microsoft.com/downloads/details.aspx?FamilyID=94bb6e34-d890-4932-81a5-5b50c657de08&DisplayLang=en) Windows Server 2008 でします。 いることを確認、 \<FirstLogonCommands\>セクションには、サンプルが一致するため、BizTalk スクリプトが最初の起動で実行します。  
  
#### <a name="to-run-sysprep"></a>Sysprep を実行するには  
  
1.  コマンド プロンプトを開き、Sysprep を実行します。 次のようなコマンドを使用します。  
  
    ```  
    C:\windows\system32\sysprep\sysprep.exe /oobe /generalize /shutdown /unattend:c:\scripts\unattend_Win2K8x64.xml  
    ```  
  
2.  Sysprep の実行には約 30 分かかります。 完了すると、仮想マシンを自動的にシャットダウンします。  
  
3.  仮想マシンがシャットダウンされた後、スナップショットをマージし、VHD ファイルを安全な場所にコピーします。  
  
4.  VHD は、オペレーティング システム、BizTalk Server、すべての前提条件を完備し、他の仮想マシンに展開できる状態になっています。  
  
 **SetupCompletecmd.txt**  
  
```  
del /Q /F c:\windows\system32\sysprep\sysprep.xml  
SqlCmd -s . -d Repository -A -Q "drop login [PDC08-CSD\Administrator]"  
SqlCmd -s . -d Repository -A -Q "create login [$(COMPUTERNAME)\Administrator] from windows"  
SqlCmd -s . -d Repository -A -Q "EXEC sp_changedbowner [$(COMPUTERNAME)\Administrator]"  
  
```  
  
 **Sysprep.xml**  
  
```  
- <!--   
References:  
"Unattended Installation Settings Reference" @ http://technet.microsoft.com/library/cc749204.aspx  
"How to Sysprep in Windows 2008 " @ http://briandesmond.com/blog/how-to-sysprep-in-windows-2008  
  
Make sure to modify the values specified for the   
<Credentials> and <DomainAccounts> sections of this unattend file.  
  
SetupComplete.cmd should be copied to the C:\Windows\Setup\Scripts\ folder before running sysprep.  
Contents of SetupComplete.cmd:  
  
del /Q /F c:\windows\system32\sysprep\sysprep.xml   
SqlCmd -s . -d Repository -A -Q "drop login [PDC08-CSD\Administrator]"  
SqlCmd -s . -d Repository -A -Q "create login [$(COMPUTERNAME)\Administrator] from windows"  
SqlCmd -s . -d Repository -A -Q "EXEC sp_changedbowner [$(COMPUTERNAME)\Administrator]"  
  
Sysprep.xml (this file) should be copied to the C:\Windows\System32\sysprep\ folder.  
  
Run sysprep with the following options:  
  
sysprep /generalize /oobe /shutdown /unattend:sysprep.xml  
  -->   
  <?xml version="1.0" encoding="utf-8" ?>   
- <unattend xmlns="urn:schemas-microsoft-com:unattend">  
- <settings pass="oobeSystem">  
- <component name="Microsoft-Windows-International-Core" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <InputLocale>0409:00000409</InputLocale>   
  <SystemLocale>en-US</SystemLocale>   
  <UILanguage>en-US</UILanguage>   
  <UILanguageFallback>en-US</UILanguageFallback>   
  <UserLocale>en-US</UserLocale>   
  </component>  
- <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
- <UserAccounts>  
- <!--   
This sets the password for the Administrator account back to pass@word1   
  -->   
- <AdministratorPassword>  
  <Value>pass@word1</Value>   
  <PlainText>true</PlainText>   
  </AdministratorPassword>  
- <!--   
Enter the appropriate value for the <Name> and <Domain> elements here,   
this group/account will be added to the local Administrators and Remote Desktop Users groups.  
  -->   
- <DomainAccounts>  
- <DomainAccountList wcm:action="add">  
- <DomainAccount wcm:action="add">  
  <Name>MSMQ4TR</Name>   
  <Group>Administrators;RemoteDesktopUsers</Group>   
  </DomainAccount>  
  <Domain>Northamerica.corp.microsoft.com</Domain>   
  </DomainAccountList>  
- <!--   
Additional DomainAccountList section. Uncomment/modify this section if you need to add   
groups / users from multiple domains to the local Administrators and Remote Desktop Users groups.  
                    <DomainAccountList wcm:action="add">  
                        <DomainAccount wcm:action="add">  
                            <Name>OsloVM_NTDev</Name>  
                            <Group>Administrators;RemoteDesktopUsers</Group>  
                        </DomainAccount>  
                        <Domain>Ntdev.corp.microsoft.com</Domain>  
                    </DomainAccountList>  
  -->   
  </DomainAccounts>  
  </UserAccounts>  
- <!--   
The new computer name is generated using a combination of <RegisteredOwner>, <RegisteredOrganization>, and random alphanumeric characters. Since <RegisteredOrganization> is blank, the new computer name will be OsloVPC-*******.  
  -->   
  <RegisteredOwner>OsloVPC</RegisteredOwner>   
  <TimeZone>Pacific Standard Time</TimeZone>   
- <Display>  
  <ColorDepth>16</ColorDepth>   
  <HorizontalResolution>1024</HorizontalResolution>   
  <VerticalResolution>768</VerticalResolution>   
  </Display>  
  <RegisteredOrganization />   
  <StartPanelOff>true</StartPanelOff>   
  <ShowWindowsLive>false</ShowWindowsLive>   
  <DoNotCleanTaskBar>true</DoNotCleanTaskBar>   
  <DisableAutoDaylightTimeSet>false</DisableAutoDaylightTimeSet>   
  <BluetoothTaskbarIconEnabled>false</BluetoothTaskbarIconEnabled>   
- <VisualEffects>  
  <FontSmoothing>ClearType</FontSmoothing>   
  </VisualEffects>  
  </component>  
  </settings>  
- <settings pass="specialize">  
- <component name="Microsoft-Windows-IE-ESC" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <IEHardenAdmin>false</IEHardenAdmin>   
  <IEHardenUser>false</IEHardenUser>   
  </component>  
- <component name="Microsoft-Windows-UnattendedJoin" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
- <!--   
Enter credentials for a user account that has permissions to join a computer to the domain specified in the <JoinDomain> element. (Note: you must enter your password in plaintext here. This file will be deleted at the conclusion of Windows setup by SetupComplete.cmd in the C:\Windows\Setup\Scripts\ folder. For more information see the bottom of "How to Sysprep in Windows 2008" @ http://briandesmond.com/blog/how-to-sysprep-in-windows-2008)  
  -->   
- <Identification>  
- <Credentials>  
  <Domain>northamerica</Domain>   
  <Username>davidhamilton</Username>   
  <Password>******</Password>   
  </Credentials>  
  <JoinDomain>Redmond.corp.microsoft.com</JoinDomain>   
  </Identification>  
  </component>  
- <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
- <!--   
By specifying a value of "*" for <ComputerName>, Windows setup will generate a new computer name using a combination of <RegisteredOwner>, <RegisteredOrganization>, and random alphanumeric characters. Since <RegisteredOrganization> is blank, the new computer name will be OsloVPC-*******  
  -->   
  <ComputerName>*</ComputerName>   
  <RegisteredOrganization />   
- <!--   
The new computer name is generated using a combination of <RegisteredOwner>, <RegisteredOrganization>, and random alphanumeric characters. Since <RegisteredOrganization> is blank, the new computer name will be OsloVPC-*******.   
  -->   
  <RegisteredOwner>OsloVPC</RegisteredOwner>   
  <ShowWindowsLive>false</ShowWindowsLive>   
  <BluetoothTaskbarIconEnabled>false</BluetoothTaskbarIconEnabled>   
- <!--   
This setting will copy the profile of the original image to the renamed image when set to true   
  -->   
  <CopyProfile>true</CopyProfile>   
  <DisableAutoDaylightTimeSet>false</DisableAutoDaylightTimeSet>   
  <DoNotCleanTaskBar>true</DoNotCleanTaskBar>   
  </component>  
  </settings>  
- <settings pass="generalize">  
- <component name="Microsoft-Windows-Security-Licensing-SLC" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <SkipRearm>1</SkipRearm>   
  </component>  
- <component name="Microsoft-Windows-OutOfBoxExperience" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <DoNotOpenInitialConfigurationTasksAtLogon>true</DoNotOpenInitialConfigurationTasksAtLogon>   
  </component>  
- <component name="Microsoft-Windows-ServerManager-SvrMgrNc" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <DoNotOpenServerManagerAtLogon>true</DoNotOpenServerManagerAtLogon>   
  </component>  
  </settings>  
  <cpi:offlineImage cpi:source="catalog:e:/sources/install_windows longhorn serverenterprise.clg" xmlns:cpi="urn:schemas-microsoft-com:cpi" />   
  </unattend>  
- <!--   
When the virtual machine is started, Windows setup will:  
  
 - Assign the copy a random computer name: "OsloVPC-*****"  
 - Reset the local Administrators password to pass@word1  
 - Join the domain specified in the sysprep.xml file (under Microsoft-Windows-UnattendedJoin\Identification\JoinDomain)  
 - Add the groups/users specified under <DomainAccounts> to the local Administrators and the local Remote Desktop Users group.  
  
Known issues:  
  
 - Sysprep removes the Server Manager icon from the Quick Launch toolbar, investigating how to prevent this.  
 - To start SQL Server Management Studio, either connect to the new server name (OsloVPC-*******) or else connect to ".".  The "Server name:" drop-down box in SQL Server Management Studio is pre-populated with "PDC08-CSD" which will not work since the computer name has been changed by sysprep.  
 - There are some known issues associated with changing the computer name; renaming the computer after everything was installed was not a design, development or test requirement for this milestone.  
  -->  
```  
  
## <a name="comments"></a>コメント  
 これらのスクリプトでは、Microsoft Office SharePoint Server は変更されません。 Windows SharePoint Services アダプターを使用している場合は、おそらく、Microsoft Office SharePoint Server を再構成した後、HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\TPM の下の SharePointAdapterManagementGroup キーを更新することが必要になります。
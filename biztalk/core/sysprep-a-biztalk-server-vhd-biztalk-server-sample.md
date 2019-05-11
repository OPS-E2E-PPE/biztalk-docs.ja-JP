---
title: Sysprep による BizTalk Server VHD (BizTalk Server サンプル) |Microsoft Docs
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
ms.openlocfilehash: 2791dc77e70e294afbe1e3ef8670df3a03282dda
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393865"
---
# <a name="sysprep-a-biztalk-server-vhd-biztalk-server-sample"></a><span data-ttu-id="a30de-102">Sysprep による BizTalk Server VHD (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="a30de-102">Sysprep a BizTalk Server VHD (BizTalk Server Sample)</span></span>
<span data-ttu-id="a30de-103">Sysprep を使用して仮想マシンのスナップショットを作成する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]他の仮想マシンに簡単に展開をインストールします。</span><span class="sxs-lookup"><span data-stu-id="a30de-103">Sysprep creates a snapshot of a virtual machine with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installed for quick deployment on other virtual machines.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a30de-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="a30de-104">Prerequisites</span></span>  
 <span data-ttu-id="a30de-105">Sysprep を使用する前に、HYPER-V と仮想マシンの使用の知識が必要です。</span><span class="sxs-lookup"><span data-stu-id="a30de-105">Before using Sysprep, you should have some knowledge of using virtual machines with Hyper-V.</span></span> <span data-ttu-id="a30de-106">BizTalk Server とその前提条件のすべての一般的なクリーン インストールと仮想マシンも必要です。</span><span class="sxs-lookup"><span data-stu-id="a30de-106">You should also have a virtual machine with a clean, typical installation of BizTalk Server and all of its prerequisites.</span></span>  
  
 <span data-ttu-id="a30de-107">Sysprep は、Windows Server 2008 および Windows Vista SP1 で実行されます。</span><span class="sxs-lookup"><span data-stu-id="a30de-107">Sysprep will run on Windows Server 2008 and Windows Vista with SP1.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="a30de-108">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="a30de-108">What This Sample Does</span></span>  
 <span data-ttu-id="a30de-109">Sysprep の VHD の作成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]他の仮想マシンに簡単に展開 (オペレーティング システムとすべての前提条件を含む) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="a30de-109">Sysprep creates a VHD of a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation (including the operating system and all prerequisites) for quick deployment on other virtual machines.</span></span> <span data-ttu-id="a30de-110">Sysprep を使用して作成されたイメージでは、新しいコンピューター名を初めて起動するとき、ドメインに参加するために選択します。</span><span class="sxs-lookup"><span data-stu-id="a30de-110">An image created using Sysprep will choose a new computer name in order to join the domain the first time it starts.</span></span> <span data-ttu-id="a30de-111">正しく動作している BizTalk Server を取得するには、レジストリおよびデータベースに格納されているコンピューター名のさまざまなインスタンスを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a30de-111">To get BizTalk Server running properly, it is necessary to update various instances of the computer name that are stored in the registry and databases.</span></span>  
  
 <span data-ttu-id="a30de-112">このドキュメントでは、BizTalk Server が 1 台のコンピューター上で実行するように構成し、新しい名前でコンピューター名の他のインスタンスを更新する方法を示しています。 前提としています。</span><span class="sxs-lookup"><span data-stu-id="a30de-112">This document assumes that BizTalk Server is configured to run on a single computer, and shows how to update other instances of the computer name with the new name.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="a30de-113">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="a30de-113">Where to Find This Sample</span></span>  
 <span data-ttu-id="a30de-114">このサンプルは、SDK がある次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="a30de-114">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="a30de-115">\<*Samples Path*\>\Admin\Sysprep\\</span><span class="sxs-lookup"><span data-stu-id="a30de-115">\<*Samples Path*\>\Admin\Sysprep\\</span></span>  
  
 <span data-ttu-id="a30de-116">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="a30de-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a30de-117">次の表の .vbs、.cmd ファイルは、Sysprep 応答ファイル (Sysprep.xml および SetupCompletecmd.txt) で自動化され、参照専用のここで表示されます。</span><span class="sxs-lookup"><span data-stu-id="a30de-117">The .vbs and .cmd files in the table below are all automated in the Sysprep answer files (Sysprep.xml and SetupCompletecmd.txt), and are listed here for reference only.</span></span> <span data-ttu-id="a30de-118">これらのスクリプトを手動で実行する必要がある場合は、テーブルに出現する順序で実行します。</span><span class="sxs-lookup"><span data-stu-id="a30de-118">If you do need to run these scripts manually, run them in the order that they appear in the table.</span></span>  
  
|<span data-ttu-id="a30de-119">ファイル</span><span class="sxs-lookup"><span data-stu-id="a30de-119">File</span></span>|<span data-ttu-id="a30de-120">説明</span><span class="sxs-lookup"><span data-stu-id="a30de-120">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="a30de-121">Sysprep.xml</span><span class="sxs-lookup"><span data-stu-id="a30de-121">Sysprep.xml</span></span>|<span data-ttu-id="a30de-122">応答ファイル</span><span class="sxs-lookup"><span data-stu-id="a30de-122">Answer file</span></span>|  
|<span data-ttu-id="a30de-123">SetupCompletecmd.txt</span><span class="sxs-lookup"><span data-stu-id="a30de-123">SetupCompletecmd.txt</span></span>|<span data-ttu-id="a30de-124">応答ファイル</span><span class="sxs-lookup"><span data-stu-id="a30de-124">Answer file</span></span>|  
|<span data-ttu-id="a30de-125">ReplaceMachineName.vbs</span><span class="sxs-lookup"><span data-stu-id="a30de-125">ReplaceMachineName.vbs</span></span>|<span data-ttu-id="a30de-126">目的:ファイルを開き、指定した文字列のすべてのインスタンスを現在のコンピューター名に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="a30de-126">Purpose: Opens a file and replaces all instances of a given string with the current computer name.</span></span> <span data-ttu-id="a30de-127">Bm.exe.config を更新して、その他のスクリプトおよび xml ファイルを準備するに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a30de-127">Useful to prepare the other script and xml files, and to update bm.exe.config.</span></span><br /><br /> <span data-ttu-id="a30de-128">使用法:ReplaceMachineName.vbs\<ファイルを開く\>\<を置換する文字列\></span><span class="sxs-lookup"><span data-stu-id="a30de-128">Usage: ReplaceMachineName.vbs \<file to open\> \<string to replace\></span></span>|  
|<span data-ttu-id="a30de-129">UpdateRegistry.vbs</span><span class="sxs-lookup"><span data-stu-id="a30de-129">UpdateRegistry.vbs</span></span>|<span data-ttu-id="a30de-130">目的:BizTalk のレジストリ設定に格納されているコンピューター名を更新します。</span><span class="sxs-lookup"><span data-stu-id="a30de-130">Purpose: Updates the computer name stored in the BizTalk registry settings.</span></span><br /><br /> <span data-ttu-id="a30de-131">使用法:UpdateRegistry.vbs \<UpdateInfo.xml\>します。</span><span class="sxs-lookup"><span data-stu-id="a30de-131">Usage: UpdateRegistry.vbs \<UpdateInfo.xml\>.</span></span> <span data-ttu-id="a30de-132">$ (Oldcomputername) および $(NEWCOMPUTERNAME) この xml ファイル内のすべてのインスタンスを置換してください。</span><span class="sxs-lookup"><span data-stu-id="a30de-132">Make sure to replace all instances of $(OLDCOMPUTERNAME) and $(NEWCOMPUTERNAME) in this xml file.</span></span>|  
|<span data-ttu-id="a30de-133">UpdateDatabase.vbs</span><span class="sxs-lookup"><span data-stu-id="a30de-133">UpdateDatabase.vbs</span></span>|<span data-ttu-id="a30de-134">目的:BizTalk 管理データベースに格納されているコンピューター名を更新します。</span><span class="sxs-lookup"><span data-stu-id="a30de-134">Purpose: Updates the computer name stored in the BizTalk Management databases.</span></span><br /><br /> <span data-ttu-id="a30de-135">使用法:UpdateDatabase.vbs \<UpdateInfo.xml\></span><span class="sxs-lookup"><span data-stu-id="a30de-135">Usage: UpdateDatabase.vbs \<UpdateInfo.xml\></span></span>|  
|<span data-ttu-id="a30de-136">UpdateBAMDb.vbs</span><span class="sxs-lookup"><span data-stu-id="a30de-136">UpdateBAMDb.vbs</span></span>|<span data-ttu-id="a30de-137">目的:BAM データベースに格納されているコンピューター名を更新します。</span><span class="sxs-lookup"><span data-stu-id="a30de-137">Purpose: Updates the computer name stored in the BAM databases.</span></span><br /><br /> <span data-ttu-id="a30de-138">使用法:UpdateBamDb.vbs \<UpdateInfo.xml\></span><span class="sxs-lookup"><span data-stu-id="a30de-138">Usage: UpdateBamDb.vbs \<UpdateInfo.xml\></span></span>|  
|<span data-ttu-id="a30de-139">UpdateSSO.cmd</span><span class="sxs-lookup"><span data-stu-id="a30de-139">UpdateSSO.cmd</span></span>|<span data-ttu-id="a30de-140">目的:エンタープライズ シングル サインオン (SSO) シークレット サーバーを再構成します。</span><span class="sxs-lookup"><span data-stu-id="a30de-140">Purpose: Reconfigures the Enterprise Single Sign-on (SSO) secret server.</span></span><br /><br /> <span data-ttu-id="a30de-141">使用法: sso.cmd \<UpdateInfo.xml\></span><span class="sxs-lookup"><span data-stu-id="a30de-141">Usage: sso.cmd \<UpdateInfo.xml\></span></span>|  
|<span data-ttu-id="a30de-142">UpdateSqlServerAndInstanceName.cmd</span><span class="sxs-lookup"><span data-stu-id="a30de-142">UpdateSqlServerAndInstanceName.cmd</span></span>|<span data-ttu-id="a30de-143">目的:SQL および SQL Express を再構成するには、一連の依存サービスが再起動され、BAMAlerts を登録します。</span><span class="sxs-lookup"><span data-stu-id="a30de-143">Purpose: Reconfigures SQL and SQL Express, restarts a series of dependent services, and reregisters BAMAlerts.</span></span><br /><br /> <span data-ttu-id="a30de-144">使用法:スクリプトを編集し、$(NEWCOMPUTERNAME) のすべてのインスタンスを置換し、BAM 警告の serviceusername および servicepassword を更新します。</span><span class="sxs-lookup"><span data-stu-id="a30de-144">Usage: Edit the script and replace all instances of $(NEWCOMPUTERNAME), and update the serviceusername and servicepassword for BAM Alerts.</span></span> <span data-ttu-id="a30de-145">最初の引数として古いコンピューター名を渡す UpdateSqlServerAndInstanceName.cmd を実行します。</span><span class="sxs-lookup"><span data-stu-id="a30de-145">Then run UpdateSqlServerAndInstanceName.cmd passing the old computer name as the first argument.</span></span>|  
  
## <a name="creating-the-answer-files-and-running-sysprep"></a><span data-ttu-id="a30de-146">応答ファイルの作成と Sysprep の実行</span><span class="sxs-lookup"><span data-stu-id="a30de-146">Creating the Answer Files and Running Sysprep</span></span>  
  
#### <a name="to-create-the-answer-files"></a><span data-ttu-id="a30de-147">応答ファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="a30de-147">To create the answer files</span></span>  
  
1. <span data-ttu-id="a30de-148">インストールし、仮想マシンで BizTalk Server を構成します。</span><span class="sxs-lookup"><span data-stu-id="a30de-148">Install and configure BizTalk Server on a virtual machine.</span></span> <span data-ttu-id="a30de-149">Sysprep はカスタマイズされたインストールをサポートしていないために、既定のインストールと構成オプションを使用することを確認します。</span><span class="sxs-lookup"><span data-stu-id="a30de-149">Be sure to use default installation and configuration options, since Sysprep does not support customized installation.</span></span>  
  
2. <span data-ttu-id="a30de-150">仮想マシン上の C:\Scripts に含まれる"scripts"フォルダーの内容をコピーします。</span><span class="sxs-lookup"><span data-stu-id="a30de-150">Copy the contents of the included “scripts” folder to C:\Scripts on the virtual machine.</span></span>  
  
3. <span data-ttu-id="a30de-151">Sysprep.xml で次の行を変更することにより、sysprep 応答ファイルを準備します。</span><span class="sxs-lookup"><span data-stu-id="a30de-151">Prepare a sysprep answer file by modifying the following lines in Sysprep.xml.</span></span> <span data-ttu-id="a30de-152">(注。これらの行が付いて、"!"</span><span class="sxs-lookup"><span data-stu-id="a30de-152">(Note: These lines are marked with a “!”</span></span> <span data-ttu-id="a30de-153">前にします。)これらをテンプレートとして使用または独自に作成および経由でコピー、 \<FirstLogonCommands\>セクション。</span><span class="sxs-lookup"><span data-stu-id="a30de-153">before them.) You can use these as a template, or make your own and copy over the \<FirstLogonCommands\> section.</span></span>  
  
   - <span data-ttu-id="a30de-154">$ (Oldcomputername) 仮想マシンの現在のコンピューター名に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="a30de-154">$(OLDCOMPUTERNAME) Replace with the current computer name of the virtual machine.</span></span>  
  
   - <span data-ttu-id="a30de-155">ユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="a30de-155">User accounts</span></span>  
  
   - <span data-ttu-id="a30de-156">パスワード</span><span class="sxs-lookup"><span data-stu-id="a30de-156">Passwords</span></span>  
  
   - <span data-ttu-id="a30de-157">任意の会社の詳細は、UpdateSqlServerAndInstance.cmd および作成する Sysprep.xml でも更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a30de-157">Any company details should also be updated in UpdateSqlServerAndInstance.cmd and your Sysprep.xml.</span></span>  
  
     <span data-ttu-id="a30de-158">使用して最初から、Sysprep 応答ファイルを作成する代わりに、[自動インストール キット (AIK)](http://www.microsoft.com/downloads/details.aspx?FamilyID=94bb6e34-d890-4932-81a5-5b50c657de08&DisplayLang=en) Windows Server 2008 でします。</span><span class="sxs-lookup"><span data-stu-id="a30de-158">Alternatively, you can create a Sysprep answer file from scratch using use the [Automated Installation Kit (AIK)](http://www.microsoft.com/downloads/details.aspx?FamilyID=94bb6e34-d890-4932-81a5-5b50c657de08&DisplayLang=en) on Windows Server 2008.</span></span> <span data-ttu-id="a30de-159">いることを確認、 \<FirstLogonCommands\>セクションに、サンプルと一致する場合、最初の起動時に BizTalk スクリプトが実行されますので。</span><span class="sxs-lookup"><span data-stu-id="a30de-159">Ensure that your \<FirstLogonCommands\> section matches the samples so the BizTalk scripts will run on the first boot.</span></span>  
  
#### <a name="to-run-sysprep"></a><span data-ttu-id="a30de-160">Sysprep を実行するには</span><span class="sxs-lookup"><span data-stu-id="a30de-160">To run Sysprep</span></span>  
  
1. <span data-ttu-id="a30de-161">コマンド プロンプトを開き、Sysprep を実行します。</span><span class="sxs-lookup"><span data-stu-id="a30de-161">Open a command prompt and run Sysprep.</span></span> <span data-ttu-id="a30de-162">コマンドはのようになります。</span><span class="sxs-lookup"><span data-stu-id="a30de-162">The command will look something like:</span></span>  
  
   ```  
   C:\windows\system32\sysprep\sysprep.exe /oobe /generalize /shutdown /unattend:c:\scripts\unattend_Win2K8x64.xml  
   ```  
  
2. <span data-ttu-id="a30de-163">Sysprep の実行に約 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="a30de-163">Sysprep takes about half an hour to run.</span></span> <span data-ttu-id="a30de-164">これが完了したら、自動的にシャット ダウン、仮想マシン。</span><span class="sxs-lookup"><span data-stu-id="a30de-164">When it is complete, it will automatically shut down the virtual machine.</span></span>  
  
3. <span data-ttu-id="a30de-165">仮想マシンがシャット ダウン後に、すべてのスナップショットをマージし、安全な場所に VHD ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="a30de-165">After the virtual machine has been shut down, merge any snapshots, and copy your VHD file to a safe location.</span></span>  
  
4. <span data-ttu-id="a30de-166">VHD は、他の仮想マシンは、オペレーティング システム、BizTalk Server では、すべての前提条件と完全に展開する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="a30de-166">Your VHD is now ready to be deployed on other virtual machines, complete with operating system, BizTalk Server, and all prerequisites.</span></span>  
  
   <span data-ttu-id="a30de-167">**SetupCompletecmd.txt**</span><span class="sxs-lookup"><span data-stu-id="a30de-167">**SetupCompletecmd.txt**</span></span>  
  
```  
del /Q /F c:\windows\system32\sysprep\sysprep.xml  
SqlCmd -s . -d Repository -A -Q "drop login [PDC08-CSD\Administrator]"  
SqlCmd -s . -d Repository -A -Q "create login [$(COMPUTERNAME)\Administrator] from windows"  
SqlCmd -s . -d Repository -A -Q "EXEC sp_changedbowner [$(COMPUTERNAME)\Administrator]"  
  
```  
  
 <span data-ttu-id="a30de-168">**Sysprep.xml**</span><span class="sxs-lookup"><span data-stu-id="a30de-168">**Sysprep.xml**</span></span>  
  
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
  
## <a name="comments"></a><span data-ttu-id="a30de-169">コメント</span><span class="sxs-lookup"><span data-stu-id="a30de-169">Comments</span></span>  
 <span data-ttu-id="a30de-170">これらのスクリプトでは、Microsoft Office SharePoint Server は変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="a30de-170">These scripts do not modify Microsoft Office SharePoint Server.</span></span> <span data-ttu-id="a30de-171">Microsoft Office SharePoint Server を再構成し、HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\ の下の SharePointAdapterManagementGroup キーを更新する必要があります、Windows SharePoint Services アダプターを使用している場合TPM です。</span><span class="sxs-lookup"><span data-stu-id="a30de-171">If you are using the Windows SharePoint Services adapter, you will probably need to reconfigure Microsoft Office SharePoint Server and then update the SharePointAdapterManagementGroup key under HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\TPM.</span></span>
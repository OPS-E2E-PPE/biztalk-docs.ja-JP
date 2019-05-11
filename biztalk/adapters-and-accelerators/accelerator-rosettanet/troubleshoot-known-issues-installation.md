---
title: BizTalk RosettaNet アクセラレータ (BTARN) での既知の問題は、BizTalk Server にインストールのトラブルシューティングと |Microsoft Docs"
description: BizTalk Server で BTARN のインストールで SQL では、ホスト インスタンス、および既知のエラーのサービス アカウントをインストールするための推奨事項
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 493a46d63fa85f181b2e019c307b7b5be66c9d72
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280442"
---
# <a name="troubleshoot-the-installation-and-see-the-known-install-issues"></a><span data-ttu-id="0c082-103">インストールのトラブルシューティングし、インストールの既知の問題を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c082-103">Troubleshoot the installation and see the known install issues</span></span>


## <a name="do-not-install-sql-server-on-the-domain-controller-computer"></a><span data-ttu-id="0c082-104">ドメイン コント ローラー コンピューター上の SQL サーバーをインストールしません。</span><span class="sxs-lookup"><span data-stu-id="0c082-104">Do not install SQL Server on the domain controller computer</span></span>  
 <span data-ttu-id="0c082-105">ドメイン コント ローラー コンピューターと同じコンピューターに SQL Server をインストールする場合は、SQL 送信ポートを作成する際、次のエラー メッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="0c082-105">If you install SQL Server on the same computer as your domain controller computer, it returns the following error message when it is trying to create the SQL send ports:</span></span>  

```
Error: Failed updating binding information.  
BindingException: Could not validate TransportTypeData or Address properties for Primary Transport of Send Port 'SendPort1'. Exception from HRESULT: 0x80131500.  
Error: Failed updating binding information.  
BindingException: Could not validate TransportTypeData or Address properties for Primary Transport of Send Port 'SendPort1'. Exception from HRESULT: 0x80131500  
```

> [!IMPORTANT]
>  <span data-ttu-id="0c082-106">ドメイン コント ローラーのコンピューターで SQL Server をインストールできません。</span><span class="sxs-lookup"><span data-stu-id="0c082-106">Do not install SQL Server on the domain controller computer.</span></span>  

## <a name="service-account-for-the-application-pools-must-be-the-same-as-the-service-account-for-the-isolated-host-and-host-instances"></a><span data-ttu-id="0c082-107">アプリケーション プールのサービス アカウントには、分離ホストとホスト インスタンスのサービス アカウントと同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c082-107">Service account for the application pools must be the same as the service account for the Isolated Host and Host instances</span></span>  
 <span data-ttu-id="0c082-108">設定の BTARN アプリケーション プール サービス アカウントが別の分離ホスト アカウントの場合は、BTARN は受信メッセージが正しく処理されません。</span><span class="sxs-lookup"><span data-stu-id="0c082-108">If the service account set for the BTARN application pools is different from the Isolated Host account, BTARN does not process incoming messages correctly.</span></span> <span data-ttu-id="0c082-109">受信 .aspx ページが、パイプラインを呼び出すと、パイプラインには適切な証明書へのアクセスはありません。</span><span class="sxs-lookup"><span data-stu-id="0c082-109">When the receive .aspx page calls the pipeline, the pipeline does not have access to the appropriate certificates.</span></span> <span data-ttu-id="0c082-110">そのため、受信メッセージの暗号化を解除したりしない署名を検証します。</span><span class="sxs-lookup"><span data-stu-id="0c082-110">Therefore, it does not decrypt the incoming message or validate the signature.</span></span> <span data-ttu-id="0c082-111">また、メッセージ ボックス データベースにアクセスすることができません。</span><span class="sxs-lookup"><span data-stu-id="0c082-111">Also, it won't be able to access the MessageBox database.</span></span>  


## <a name="known-install-issues"></a><span data-ttu-id="0c082-112">インストールの既知の問題</span><span class="sxs-lookup"><span data-stu-id="0c082-112">Known install issues</span></span>


### <a name="btarn-http-front-end-feature-configuration-fails"></a><span data-ttu-id="0c082-113">BTARN HTTP フロント エンド機能の構成が失敗します。</span><span class="sxs-lookup"><span data-stu-id="0c082-113">BTARN HTTP Front End Feature configuration fails</span></span>  
 <span data-ttu-id="0c082-114">**問題**</span><span class="sxs-lookup"><span data-stu-id="0c082-114">**Problem**</span></span>  

 <span data-ttu-id="0c082-115">BTARN HTTP フロント エンド機能のみをインストールするカスタム インストールを実行する場合、次のエラーでセットアップが完了した後に、BTARN の構成が失敗します。</span><span class="sxs-lookup"><span data-stu-id="0c082-115">If you perform a custom installation to install only the BTARN HTTP Front End feature, BTARN configuration may fail with the following error after setup has completed:</span></span> 

`Failed to create object for feature: WebApp`  

 <span data-ttu-id="0c082-116">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="0c082-116">**Resolution**</span></span>  

<span data-ttu-id="0c082-117">手動でファイルをコピーして再構成します。</span><span class="sxs-lookup"><span data-stu-id="0c082-117">Manually copy files and reconfigure:</span></span> 

1. <span data-ttu-id="0c082-118">BizTalk Server コンピューターから BTARN HTTP フロント エンド機能がインストールされているコンピューターに次の 2 つのファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="0c082-118">Copy the following two files from an BizTalk Server computer to the computer on which you installed the BTARN HTTP Front End feature:</span></span>

   - <span data-ttu-id="0c082-119">Microsoft.VC80.ATL.manifest</span><span class="sxs-lookup"><span data-stu-id="0c082-119">Microsoft.VC80.ATL.manifest</span></span>  

   - <span data-ttu-id="0c082-120">atl80.dll</span><span class="sxs-lookup"><span data-stu-id="0c082-120">atl80.dll</span></span>  

     <span data-ttu-id="0c082-121">2 つのファイルのソース フォルダーは、Visual Studio は、BizTalk Server と同じコンピューターにインストールされて場合、<*ドライブ*>: \Program Files\Microsoft Visual Studio < バージョン\>\VC\redist\x86\Microsoft.VC100.ATL.</span><span class="sxs-lookup"><span data-stu-id="0c082-121">If Visual Studio is installed on the same computer as BizTalk Server, the source folder for the two files is <*drive*>:\Program Files\Microsoft Visual Studio <version\>\VC\redist\x86\Microsoft.VC100.ATL.</span></span>  

     <span data-ttu-id="0c082-122">同じ BizTalk Server コンピューターに Visual Studio がインストールされていない場合、2 つのファイルのソース フォルダーは <*ドライブ*>: \WINDOWS\WinSxS します。</span><span class="sxs-lookup"><span data-stu-id="0c082-122">If Visual Studio is not installed on the same BizTalk Server computer, the source folder for the two files is under <*drive*>:\WINDOWS\WinSxS.</span></span>  

2. <span data-ttu-id="0c082-123">BTARN HTTP フロント エンド機能がインストールされているコンピューターにコピーしたファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="0c082-123">Add the copied files to the computer on which you installed BTARN HTTP Front End feature.</span></span> <span data-ttu-id="0c082-124">既定では、ファイルのコピー <*ドライブ*>: \Program Files\Microsoft BizTalk Accelerator for RosettaNet。</span><span class="sxs-lookup"><span data-stu-id="0c082-124">By default, copy the files to <*drive*>:\Program Files\Microsoft BizTalk Accelerator for RosettaNet.</span></span>  

3. <span data-ttu-id="0c082-125">HTTP フロント エンド コンピューターにファイルをコピーした後、実行**Configuration.exe**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="0c082-125">After you have copied the files to the HTTP Front End computer, run **Configuration.exe** again.</span></span>  

### <a name="some-btarn-assemblies-stay-in-gac-after-uninstalling"></a><span data-ttu-id="0c082-126">一部の BTARN アセンブリが GAC にアンインストールした後に維持します。</span><span class="sxs-lookup"><span data-stu-id="0c082-126">Some BTARN Assemblies stay in GAC after uninstalling</span></span>  
 <span data-ttu-id="0c082-127">**問題**</span><span class="sxs-lookup"><span data-stu-id="0c082-127">**Problem**</span></span>  

 <span data-ttu-id="0c082-128">BTARN をアンインストールすると、一部のアセンブリはグローバル アセンブリ キャッシュ (GAC) に残ります。</span><span class="sxs-lookup"><span data-stu-id="0c082-128">When you uninstall BTARN, some assemblies remain in the global assembly cache (GAC).</span></span>  

 <span data-ttu-id="0c082-129">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="0c082-129">**Resolution**</span></span>  

 <span data-ttu-id="0c082-130">BTARN を再インストールする前に、GAC からアセンブリを削除します。</span><span class="sxs-lookup"><span data-stu-id="0c082-130">Remove the assemblies from the GAC before reinstalling BTARN.</span></span>  

 <span data-ttu-id="0c082-131">使用して、 **BtarnClean**ユーティリティ、SDK アセンブリを削除するからです。</span><span class="sxs-lookup"><span data-stu-id="0c082-131">Use the **BtarnClean** utility from the SDK to remove the assemblies.</span></span> <span data-ttu-id="0c082-132">ユーティリティは、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="0c082-132">The utility performs the following actions:</span></span>  

- <span data-ttu-id="0c082-133">停止し、すべての BTARN オーケストレーションの参加を解除します。</span><span class="sxs-lookup"><span data-stu-id="0c082-133">Stops and unenlists all the BTARN orchestrations.</span></span>  

- <span data-ttu-id="0c082-134">停止し、関連するすべてのポートを削除します。</span><span class="sxs-lookup"><span data-stu-id="0c082-134">Stops and deletes all the associated ports.</span></span>  

- <span data-ttu-id="0c082-135">すべての Microsoft.Solutions.BTARN.\* アセンブリの展開を解除します。</span><span class="sxs-lookup"><span data-stu-id="0c082-135">Undeploys all the Microsoft.Solutions.BTARN.\* assemblies.</span></span>  

  <span data-ttu-id="0c082-136">ユーティリティを実行した後、GAC にアセンブリが残ってがある場合は、Windows エクスプ ローラーを開き、"C:\Windows\Assembly"フォルダーに移動および Microsoft.Solutions.BTARN で始まるすべてのアセンブリを手動で削除します。</span><span class="sxs-lookup"><span data-stu-id="0c082-136">After running the utility, if there are assemblies remaining in the GAC, open Windows Explorer, go to the "C:\Windows\Assembly" folder, and then manually delete all assemblies starting with Microsoft.Solutions.BTARN.</span></span>  

### <a name="service-unavailable-error-on-64-bit-os"></a><span data-ttu-id="0c082-137">64 ビット OS 上のサービス利用不可エラー</span><span class="sxs-lookup"><span data-stu-id="0c082-137">Service Unavailable error on 64-bit OS</span></span>
 <span data-ttu-id="0c082-138">**問題**</span><span class="sxs-lookup"><span data-stu-id="0c082-138">**Problem**</span></span>  

 <span data-ttu-id="0c082-139">取得することがあります、 `Service Unavailable` BTARN HTTP にアクセスしようとするときにエラーが 64 ビット Windows オペレーティング システム上の場所を受信します。</span><span class="sxs-lookup"><span data-stu-id="0c082-139">You may get a `Service Unavailable` error when trying to access the BTARN HTTP receive location on 64-bit Windows operating systems.</span></span>  

 <span data-ttu-id="0c082-140">**原因**</span><span class="sxs-lookup"><span data-stu-id="0c082-140">**Cause**</span></span>  

 <span data-ttu-id="0c082-141">この問題は"RPCProxy.dll"ISAPI によって発生することができますフィルター。</span><span class="sxs-lookup"><span data-stu-id="0c082-141">This issue can be caused by the "RPCProxy.dll" ISAPI filter.</span></span>  

 <span data-ttu-id="0c082-142">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="0c082-142">**Resolution**</span></span>  

<span data-ttu-id="0c082-143">RPC プロキシ ISAPI フィルターへの参照を削除し、IIS を再起動します。</span><span class="sxs-lookup"><span data-stu-id="0c082-143">Remove references to the RPC proxy ISAPI filter and restart IIS:</span></span>

1.  <span data-ttu-id="0c082-144">インターネット インフォメーション サービス (IIS) マネージャーで、右クリックして**Websites**、順にクリックします**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="0c082-144">In Internet Information Services (IIS) Manager, right-click **Web Sites**, and then click **Properties**.</span></span>  

2.  <span data-ttu-id="0c082-145">**Web サイトのプロパティ**ダイアログ ボックスで、 をクリックして、 **ISAPI フィルター**  タブで、削除**RPC プロキシ**フィルター処理、およびクリックして**ok**します。</span><span class="sxs-lookup"><span data-stu-id="0c082-145">In the **Web Site Properties** dialog box, click the **ISAPI filters** tab, remove **RPC Proxy** filter, and then click **OK**.</span></span>  

3.  <span data-ttu-id="0c082-146">IIS を再起動します。</span><span class="sxs-lookup"><span data-stu-id="0c082-146">Restart IIS.</span></span>  

4.  <span data-ttu-id="0c082-147">IIS を再起動した後にアクセスすることをお試しください http://localhost します。</span><span class="sxs-lookup"><span data-stu-id="0c082-147">After you have restarted IIS, try accessing http://localhost.</span></span> <span data-ttu-id="0c082-148">インターネット ブラウザーから 400 メッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="0c082-148">You should get the 400 message back from the Internet browser.</span></span>  

### <a name="sql-server-mixed-mode-not-supported"></a><span data-ttu-id="0c082-149">SQL Server 混在モードはサポートされていません</span><span class="sxs-lookup"><span data-stu-id="0c082-149">SQL Server Mixed Mode not supported</span></span>  
<span data-ttu-id="0c082-150">BTARN は、混在モードで SQL Server をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="0c082-150">BTARN does not support SQL Server in mixed mode.</span></span>  

### <a name="run-setupx64bat-to-set-up-the-double-action-pipautomation-orchestration-sample"></a><span data-ttu-id="0c082-151">ダブル アクション PIPAutomation オーケストレーション サンプルを設定する setupx64.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="0c082-151">Run setupx64.bat to set up the double action PIPAutomation orchestration sample</span></span> 

<span data-ttu-id="0c082-152">\Program Files\Microsoft BizTalk Accelerator for rosettanet \sdk\pipautomation\doubleaction フォルダー Double Action PIPAutomation Orchestration サンプルを設定するには、setupx64.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="0c082-152">Run setupx64.bat in \Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction folder to set up the Double Action PIPAutomation Orchestration sample.</span></span>

### <a name="download-the-btarn-setup-file-from-the-web-to-a-temp-folder"></a><span data-ttu-id="0c082-153">BTARN セットアップ ファイルを Web から一時フォルダーにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="0c082-153">Download the BTARN Setup File from the Web to a Temp Folder</span></span>  
 <span data-ttu-id="0c082-154">**問題**</span><span class="sxs-lookup"><span data-stu-id="0c082-154">**Problem**</span></span>  

 <span data-ttu-id="0c082-155">BTARN の自己解凍形式実行可能ファイル、Web からダウンロードして実行可能ファイルの BizTalk 実行しようとしたときに、BizTalk Server のルート フォルダーに保存すると**セットアップ ウィザード**BTARN セットアップ ウィザードではなく、実行します。</span><span class="sxs-lookup"><span data-stu-id="0c082-155">If you download the BTARN self-extracting executable file from the Web, and save it to the BizTalk Server root folder, when you attempt to run the executable, the BizTalk **Setup Wizard** runs, instead of the BTARN Setup wizard.</span></span>  

 <span data-ttu-id="0c082-156">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="0c082-156">**Resolution**</span></span>  

 <span data-ttu-id="0c082-157">BTARN の自己解凍形式の実行可能ファイルをダウンロードし、一時フォルダーにファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="0c082-157">Download the BTARN self-extracting executable, and save the file to a temp folder.</span></span>

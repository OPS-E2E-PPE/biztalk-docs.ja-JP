---
title: インポートまたはエクスポートする BizTalk の設定を使用して設定のダッシュ ボード |Microsoft ドキュメント
description: BizTalk Server 管理コンソールを使用して、インポートまたは BizTalk Server 環境の間の設定をエクスポートするには
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc2f0b44-d79b-4f95-811a-0843e3d6d1c8
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e33b8659701ab991f7b7467c8ab3edd8b79def4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255138"
---
# <a name="use-settings-dashboard-to-import-or-export-biztalk-settings"></a><span data-ttu-id="9d722-103">設定ダッシュ ボードを使用して、インポートまたは BizTalk の設定をエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="9d722-103">Use Settings Dashboard to import or export BizTalk Settings</span></span> 

## <a name="overview"></a><span data-ttu-id="9d722-104">概要</span><span class="sxs-lookup"><span data-stu-id="9d722-104">Overview</span></span>
<span data-ttu-id="9d722-105">BizTalk 設定ダッシュボードを使用して、ある [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境から設定をエクスポートして別の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境にインポートすることで、問題解決までの全体的な時間を短縮できます。</span><span class="sxs-lookup"><span data-stu-id="9d722-105">Using the BizTalk Settings Dashboard, you can export the settings from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment and import them to another [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment, thereby reducing the overall time-to-solution.</span></span> <span data-ttu-id="9d722-106">これは、管理者がステージング環境で [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のパフォーマンスを調整し、適正な結果が得られた時点で設定を実稼働環境にインポートする場合、特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9d722-106">This is especially useful in scenarios where the administrators try to tune [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] performance in a staging environment, and upon achieving the desired results, they can import the settings into a production environment.</span></span> <span data-ttu-id="9d722-107">このトピックでは、設定ダッシュボードを使用して、BizTalk グループ、ホスト、およびホスト インスタンスの設定をインポートする手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="9d722-107">This topic provides step-by-step procedure to import the BizTalk Group, Host, and Host Instance settings using Settings Dashboard.</span></span>  

> [!TIP]
> <span data-ttu-id="9d722-108">BTSTask コマンド ライン ユーティリティは、インポートまたはグループ、ホスト、およびホスト インスタンスの設定をエクスポートするも使用できます。</span><span class="sxs-lookup"><span data-stu-id="9d722-108">The BTSTask command-line utility can also be used to import or export the Group, Host, and Host Instance settings.</span></span> <span data-ttu-id="9d722-109">参照してください[インポートまたはエクスポート BizTalk の設定を使用して BTSTask](how-to-import-biztalk-settings-using-btstask.md)です。</span><span class="sxs-lookup"><span data-stu-id="9d722-109">See [Import or export BizTalk Settings Using BTSTask](how-to-import-biztalk-settings-using-btstask.md).</span></span>

  
## <a name="prerequisites"></a><span data-ttu-id="9d722-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="9d722-110">Prerequisites</span></span>  
 <span data-ttu-id="9d722-111">この操作を実行するには、BizTalk Server 管理者グループのメンバーとしてサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d722-111">To perform this operation, you must be signed in as a member of the BizTalk Server Administrators group.</span></span>  
  
## <a name="import-the-biztalk-group-host-and-host-instance-settings"></a><span data-ttu-id="9d722-112">BizTalk グループ、ホスト、およびホスト インスタンスの設定をインポートします。</span><span class="sxs-lookup"><span data-stu-id="9d722-112">Import the BizTalk group, host, and host instance settings</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="9d722-113">BizTalk Server の設定を特定の環境からインポートするには、それらの設定を XML ファイルとして保存およびエクスポートしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d722-113">To import the BizTalk Server settings from a certain environment, you should have already saved and exported those settings in an XML file.</span></span> <span data-ttu-id="9d722-114">**BizTalk の設定をエクスポート**(」を参照) または[インポートまたはエクスポート BizTalk の設定を使用して BTSTask](how-to-import-biztalk-settings-using-btstask.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="9d722-114">**Export BizTalk Settings** (in this topic) or [Import or export BizTalk Settings Using BTSTask](how-to-import-biztalk-settings-using-btstask.md) can help.</span></span>
  
 <span data-ttu-id="9d722-115">XML ファイルをインポートすることで、対象コンピューターで必要な BizTalk Server 設定をレプリケートできます。</span><span class="sxs-lookup"><span data-stu-id="9d722-115">By importing the XML file, you can replicate the required BizTalk Server settings on the target machine.</span></span> <span data-ttu-id="9d722-116">設定ダッシュボードを使用すると、グループ、ホスト、およびホスト インスタンスの設定をインポートし、そのプロパティを相互にマップできます。</span><span class="sxs-lookup"><span data-stu-id="9d722-116">Using the Settings dashboard, you can import the Group, Host, and Host Instance settings and map the properties of one to another.</span></span> <span data-ttu-id="9d722-117">次に設定をインポートする際に必要な前提条件を示します。</span><span class="sxs-lookup"><span data-stu-id="9d722-117">Following are the necessary assumptions for importing the settings:</span></span>  
  
-   <span data-ttu-id="9d722-118">BizTalk Server トポロジがインポート元の環境からインポート先の環境まで一貫している。</span><span class="sxs-lookup"><span data-stu-id="9d722-118">The BizTalk Server topology is consistent from the source environment to the destination environment.</span></span>  
  
-   <span data-ttu-id="9d722-119">インポート元の環境からインポート先の環境にまたがるホスト定義をマップできる。</span><span class="sxs-lookup"><span data-stu-id="9d722-119">The host definitions across source and destination environments can be mapped.</span></span> <span data-ttu-id="9d722-120">インポート元の環境にあるすべてのホストを、インポート先の環境にあるホストにマップできる。</span><span class="sxs-lookup"><span data-stu-id="9d722-120">You should be able to map all hosts in the source environment with those in the destination environment.</span></span>  
  
-   <span data-ttu-id="9d722-121">インポート先環境には、インポート元環境と (同じかまたは) 似たハードウェアがあります。</span><span class="sxs-lookup"><span data-stu-id="9d722-121">The destination environment has hardware similar (if not identical) to the source environment.</span></span> <span data-ttu-id="9d722-122">一部の設定は基礎となるハードウェアに依存しているため、これは重要です。</span><span class="sxs-lookup"><span data-stu-id="9d722-122">This is essential as some of the settings depend on the underlying hardware.</span></span>  

### <a name="import-steps"></a><span data-ttu-id="9d722-123">インポート手順</span><span class="sxs-lookup"><span data-stu-id="9d722-123">Import steps</span></span>
  
1.  <span data-ttu-id="9d722-124">**BizTalk Server 管理コンソール**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を右クリックして**BizTalk グループ**、クリックして**設定**です。</span><span class="sxs-lookup"><span data-stu-id="9d722-124">In the **BizTalk Server Administration Console**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Settings**.</span></span>  
  
2.  <span data-ttu-id="9d722-125">**BizTalk 設定ダッシュ ボード**ダイアログ ボックスで、をクリックして**インポート**です。</span><span class="sxs-lookup"><span data-stu-id="9d722-125">In the **BizTalk Settings Dashboard** dialog box, click **Import**.</span></span> <span data-ttu-id="9d722-126">**設定のインポート ウィザード** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d722-126">The **Import Settings Wizard** dialog box appears.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9d722-127">**宛先グループ**の設定をインポートする対象コンピューターのグループ情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d722-127">The **Destination Group** displays the group information of the target machine where you want to import the settings.</span></span>  
  
     <span data-ttu-id="9d722-128">![設定をインポートするファイルの場所を指定](../core/media/importsettings-filelocation.jpg "ImportSettings_FileLocation")</span><span class="sxs-lookup"><span data-stu-id="9d722-128">![Specify the file location to import settings](../core/media/importsettings-filelocation.jpg "ImportSettings_FileLocation")</span></span>  
  
3.  <span data-ttu-id="9d722-129">クリックして、**ファイルの場所を指定** ページで、クリックして![設定ファイルの参照](../core/media/importsettings-filelocationbrowse.gif "ImportSettings_FileLocationBrowse")です。</span><span class="sxs-lookup"><span data-stu-id="9d722-129">Click the **Specify File Location** page, and then click ![Browse the settings file](../core/media/importsettings-filelocationbrowse.gif "ImportSettings_FileLocationBrowse").</span></span> <span data-ttu-id="9d722-130">ファイル エクスプローラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d722-130">The file explorer appears.</span></span>  
  
4.  <span data-ttu-id="9d722-131">ソース環境設定を含む XML ファイルを選択し、クリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="9d722-131">Select the XML file containing the source environment settings, and then click **Open**.</span></span> <span data-ttu-id="9d722-132">**ファイルの場所**XML ファイルのパスを表示し、**ソース グループ**ソース マシンのグループの情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="9d722-132">The **File Location** displays the path of the XML file and the **Source Group** is populated with the group information of the source machine.</span></span> <span data-ttu-id="9d722-133">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d722-133">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="9d722-134">**ホスト マッピング** ページで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="9d722-134">On the **Host Mapping** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="9d722-135">**送信先ホスト**一覧で、送信元ホストを指定し、をクリックする移行先ホストを選択**追加**です。</span><span class="sxs-lookup"><span data-stu-id="9d722-135">From the **Destination Hosts** list, select a destination host for which you want to specify the source host, and then click **Add**.</span></span>  
  
         <span data-ttu-id="9d722-136">![ホスト マッピング](../core/media/importsettings-hostmapping.gif "ImportSettings_HostMapping")</span><span class="sxs-lookup"><span data-stu-id="9d722-136">![Host Mapping](../core/media/importsettings-hostmapping.gif "ImportSettings_HostMapping")</span></span>  
  
    2.  <span data-ttu-id="9d722-137">**ソース エンティティの選択**ダイアログ ボックスでは、ソース ホストを選択し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="9d722-137">In the **Select Source Entity** dialog box, select the source host, and then click **OK**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="9d722-138">1 つのソース ホストに複数の送信先ホストにマップする手順を繰り返します**5a**と**5b**です。</span><span class="sxs-lookup"><span data-stu-id="9d722-138">To map multiple destination hosts to a single source host, repeat the steps **5a** and **5b**.</span></span>  
  
    3.  <span data-ttu-id="9d722-139">**ホスト マッピング**] ページで [**次**です。</span><span class="sxs-lookup"><span data-stu-id="9d722-139">In the **Host Mapping** page, click **Next**.</span></span>  
  
6.  <span data-ttu-id="9d722-140">**ホスト インスタンス マッピング** ページで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="9d722-140">In the **Host Instance Mapping** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="9d722-141">インポート元ホスト インスタンスを指定し、をクリックする移行先ホスト インスタンスを選択、インポート先ホスト インスタンスの一覧から**追加**です。</span><span class="sxs-lookup"><span data-stu-id="9d722-141">From the list of destination host instances, select a destination host instance for which you want to specify the source host instance, and then click **Add**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="9d722-142">ホスト インスタンスは、ホスト マッピングで指定された対応するホストにのみマップできます。</span><span class="sxs-lookup"><span data-stu-id="9d722-142">Host instances can be mapped only to the corresponding host that has been created in the Host Mapping.</span></span> <span data-ttu-id="9d722-143">マッピングを指定する場合など、 **SourceHost1**にマップされて**DestinationHost1**のインスタンス、 **DestinationHost1**インスタンスにしかマップできません**SourceHost1**です。</span><span class="sxs-lookup"><span data-stu-id="9d722-143">For example, if you specify a mapping where **SourceHost1** is mapped to **DestinationHost1**, then the instances of **DestinationHost1** can only be mapped to the instances of **SourceHost1**.</span></span>  
        >   
        >  <span data-ttu-id="9d722-144">上記の制約はインポート ウィザードによって管理され、この制約に従う必要があります。従わない場合、BizTalk タスクによってエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="9d722-144">The import wizard manages the above constraint, you need to follow this constraint else BizTalk tasks will throw errors.</span></span>  
        >   
        >  <span data-ttu-id="9d722-145">規則を使用する必要があります**HostName:MachineName**マップ ファイルのホスト インスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d722-145">You need to use the convention **HostName:MachineName** to specify a host instance in a map file.</span></span> <span data-ttu-id="9d722-146">たとえば、 **Host1:Server1**マップ ファイルを表しているインスタンスの**Host1**が実行されているか**Server1**です。</span><span class="sxs-lookup"><span data-stu-id="9d722-146">For example, **Host1:Server1** in a map file denotes that the instance of **Host1** is running or available on **Server1**.</span></span>  
  
         <span data-ttu-id="9d722-147">![ホスト インスタンス マッピング](../core/media/importsettings-hostinstancemapping.gif "ImportSettings_HostInstanceMapping")</span><span class="sxs-lookup"><span data-stu-id="9d722-147">![Host Instance Mapping](../core/media/importsettings-hostinstancemapping.gif "ImportSettings_HostInstanceMapping")</span></span>  
  
    2.  <span data-ttu-id="9d722-148">**ソース エンティティの選択**ダイアログ ボックスで、インポート元ホスト インスタンスを選択し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="9d722-148">In the **Select Source Entity** dialog box, select the source host instance, and then click **OK**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="9d722-149">複数のインポート先ホスト インスタンスを 1 つのソース ホストのインスタンスをマップする手順を繰り返します**6a**に**6b**です。</span><span class="sxs-lookup"><span data-stu-id="9d722-149">To map multiple destination host instances to a single source host instance, repeat the steps **6a** to **6b**.</span></span>  
  
    3.  <span data-ttu-id="9d722-150">**ホスト インスタンス マッピング** タブで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="9d722-150">In the **Host Instance Mapping** tab, click **Next**.</span></span>  
  
7.  <span data-ttu-id="9d722-151">**インポートの概要**ダイアログ ボックスでは、としての送信先と送信元の環境を作成したすべてのインポート設定がある場合は、必要に応じて、ことを確認し、をクリックして**インポート**です。</span><span class="sxs-lookup"><span data-stu-id="9d722-151">In the **Import Summary** dialog box, verify if all the import settings for destination and source environments you created are as desired, and then click **Import**.</span></span> <span data-ttu-id="9d722-152">**進行**ページ、設定のインポートの進行状況を示しています。</span><span class="sxs-lookup"><span data-stu-id="9d722-152">The **Progress** page shows the progress of import of the settings.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="9d722-153">BizTalk Server 設定のインポートを元に戻すことはできません。</span><span class="sxs-lookup"><span data-stu-id="9d722-153">You cannot undo the import of BizTalk Server settings.</span></span> <span data-ttu-id="9d722-154">クリックした場合**インポート**、設定のインポート元環境から送信先の環境にプロセスが開始されると**キャンセル**は無効になります。</span><span class="sxs-lookup"><span data-stu-id="9d722-154">If you click **Import**, the process for importing the settings from source environment to destination environment is initiated and **Cancel** is disabled.</span></span> <span data-ttu-id="9d722-155">クリックする前にインポートを続行するかを確認してください。**インポート**です。</span><span class="sxs-lookup"><span data-stu-id="9d722-155">Ensure you want to proceed with import before clicking **Import**.</span></span>  
  
8.  <span data-ttu-id="9d722-156">**インポート結果** タブで、グループ、ホスト、およびホスト インスタンスの設定のインポートの状態を確認し、をクリックして**完了**インポート操作を完了します。</span><span class="sxs-lookup"><span data-stu-id="9d722-156">In the **Import Results** tab, check the import status of the Group, Host, and Host Instance settings, and then click **Finish** to complete the import operation.</span></span> <span data-ttu-id="9d722-157">インポート元の環境からインポートしたすべての設定が、インポート先の環境に適用されます。</span><span class="sxs-lookup"><span data-stu-id="9d722-157">All the imported source environment settings are applied to the destination environment.</span></span>  
  
     <span data-ttu-id="9d722-158">![結果のインポート](../core/media/importsettings-importresults.gif "ImportSettings_ImportResults")</span><span class="sxs-lookup"><span data-stu-id="9d722-158">![Import Results](../core/media/importsettings-importresults.gif "ImportSettings_ImportResults")</span></span>  

## <a name="export-the-biztalk-group-host-and-host-instance-settings"></a><span data-ttu-id="9d722-159">BizTalk グループ、ホスト、およびホスト インスタンスの設定をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="9d722-159">Export the BizTalk group, host, and host instance settings</span></span>  

1.  <span data-ttu-id="9d722-160">**BizTalk Server 管理コンソール**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を右クリックして**BizTalk グループ**、クリックして**設定**です。</span><span class="sxs-lookup"><span data-stu-id="9d722-160">In the **BizTalk Server Administration Console**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Settings**.</span></span>  
  
2.  <span data-ttu-id="9d722-161">**BizTalk 設定ダッシュ ボード**ダイアログ ボックスで、をクリックして**エクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="9d722-161">In the **BizTalk Settings Dashboard** dialog box, click **Export**.</span></span> <span data-ttu-id="9d722-162">**[名前を付けて保存]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d722-162">The **Save As** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="9d722-163">BizTalk の現在の設定を保存する場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="9d722-163">Browse to the location where you want to save the current BizTalk settings.</span></span> <span data-ttu-id="9d722-164">ファイル名を入力、XML 形式で、種類を選択してをクリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="9d722-164">Enter the filename, select the type as XML format, and then click **Save**.</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="9d722-165">いないいないはお勧め、エクスポートされた XML ファイルを手動で更新します。</span><span class="sxs-lookup"><span data-stu-id="9d722-165">We do not not recommended manually updating the exported XML file.</span></span> <span data-ttu-id="9d722-166">更新された XML ファイルを実稼働環境にインポートするときにデータ型の不一致または手動で編集によって導入されたその他のエラーのため、インポート処理が失敗します。</span><span class="sxs-lookup"><span data-stu-id="9d722-166">When you import an updated XML file to a production environment, the import process might fail due to some data type mismatch or other errors introduced by manual editing.</span></span>  

## <a name="see-also"></a><span data-ttu-id="9d722-167">参照</span><span class="sxs-lookup"><span data-stu-id="9d722-167">See Also</span></span>  
 [<span data-ttu-id="9d722-168">BizTalk server 設定ダッシュ ボードを使用してパフォーマンス チューニング</span><span class="sxs-lookup"><span data-stu-id="9d722-168">Using Settings Dashboard for BizTalk Server Performance Tuning</span></span>](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)
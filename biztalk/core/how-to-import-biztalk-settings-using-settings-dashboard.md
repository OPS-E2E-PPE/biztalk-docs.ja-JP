---
title: インポートまたはエクスポートする BizTalk の設定を使用して設定のダッシュ ボード |Microsoft Docs
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
ms.openlocfilehash: c2a825158f43ea085fd0e84aeb15001ea88b6d7f
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752778"
---
# <a name="use-settings-dashboard-to-import-or-export-biztalk-settings"></a><span data-ttu-id="ed44a-103">設定ダッシュ ボードを使用して、インポートまたは BizTalk の設定をエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="ed44a-103">Use Settings Dashboard to import or export BizTalk Settings</span></span> 

## <a name="overview"></a><span data-ttu-id="ed44a-104">概要</span><span class="sxs-lookup"><span data-stu-id="ed44a-104">Overview</span></span>
<span data-ttu-id="ed44a-105">BizTalk 設定ダッシュボードを使用して、ある [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境から設定をエクスポートして別の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境にインポートすることで、問題解決までの全体的な時間を短縮できます。</span><span class="sxs-lookup"><span data-stu-id="ed44a-105">Using the BizTalk Settings Dashboard, you can export the settings from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment and import them to another [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment, thereby reducing the overall time-to-solution.</span></span> <span data-ttu-id="ed44a-106">これは、管理者がステージング環境で [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のパフォーマンスを調整し、適正な結果が得られた時点で設定を実稼働環境にインポートする場合、特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ed44a-106">This is especially useful in scenarios where the administrators try to tune [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] performance in a staging environment, and upon achieving the desired results, they can import the settings into a production environment.</span></span> <span data-ttu-id="ed44a-107">このトピックでは、設定ダッシュボードを使用して、BizTalk グループ、ホスト、およびホスト インスタンスの設定をインポートする手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="ed44a-107">This topic provides step-by-step procedure to import the BizTalk Group, Host, and Host Instance settings using Settings Dashboard.</span></span>  

> [!TIP]
> <span data-ttu-id="ed44a-108">BTSTask コマンド ライン ユーティリティをインポートまたはグループ、ホスト、およびホスト インスタンスの設定をエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ed44a-108">The BTSTask command-line utility can also be used to import or export the Group, Host, and Host Instance settings.</span></span> <span data-ttu-id="ed44a-109">参照してください[インポートまたはエクスポート BizTalk の設定を使用して BTSTask](how-to-import-biztalk-settings-using-btstask.md)します。</span><span class="sxs-lookup"><span data-stu-id="ed44a-109">See [Import or export BizTalk Settings Using BTSTask](how-to-import-biztalk-settings-using-btstask.md).</span></span>

  
## <a name="prerequisites"></a><span data-ttu-id="ed44a-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="ed44a-110">Prerequisites</span></span>  
 <span data-ttu-id="ed44a-111">この操作を実行するには、BizTalk Server 管理者グループのメンバーとしてサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed44a-111">To perform this operation, you must be signed in as a member of the BizTalk Server Administrators group.</span></span>  
  
## <a name="import-the-biztalk-group-host-and-host-instance-settings"></a><span data-ttu-id="ed44a-112">BizTalk グループ、ホスト、およびホスト インスタンスの設定をインポートします。</span><span class="sxs-lookup"><span data-stu-id="ed44a-112">Import the BizTalk group, host, and host instance settings</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="ed44a-113">BizTalk Server の設定を特定の環境からインポートするには、それらの設定を XML ファイルとして保存およびエクスポートしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed44a-113">To import the BizTalk Server settings from a certain environment, you should have already saved and exported those settings in an XML file.</span></span> <span data-ttu-id="ed44a-114">**BizTalk の設定をエクスポート**(」を参照) または[インポートまたはエクスポート BizTalk の設定を使用して BTSTask](how-to-import-biztalk-settings-using-btstask.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="ed44a-114">**Export BizTalk Settings** (in this topic) or [Import or export BizTalk Settings Using BTSTask](how-to-import-biztalk-settings-using-btstask.md) can help.</span></span>
  
 <span data-ttu-id="ed44a-115">XML ファイルをインポートすることで、対象コンピューターで必要な BizTalk Server 設定をレプリケートできます。</span><span class="sxs-lookup"><span data-stu-id="ed44a-115">By importing the XML file, you can replicate the required BizTalk Server settings on the target machine.</span></span> <span data-ttu-id="ed44a-116">設定ダッシュボードを使用すると、グループ、ホスト、およびホスト インスタンスの設定をインポートし、そのプロパティを相互にマップできます。</span><span class="sxs-lookup"><span data-stu-id="ed44a-116">Using the Settings dashboard, you can import the Group, Host, and Host Instance settings and map the properties of one to another.</span></span> <span data-ttu-id="ed44a-117">次に設定をインポートする際に必要な前提条件を示します。</span><span class="sxs-lookup"><span data-stu-id="ed44a-117">Following are the necessary assumptions for importing the settings:</span></span>  
  
-   <span data-ttu-id="ed44a-118">BizTalk Server トポロジがインポート元の環境からインポート先の環境まで一貫している。</span><span class="sxs-lookup"><span data-stu-id="ed44a-118">The BizTalk Server topology is consistent from the source environment to the destination environment.</span></span>  
  
-   <span data-ttu-id="ed44a-119">インポート元の環境からインポート先の環境にまたがるホスト定義をマップできる。</span><span class="sxs-lookup"><span data-stu-id="ed44a-119">The host definitions across source and destination environments can be mapped.</span></span> <span data-ttu-id="ed44a-120">インポート元の環境にあるすべてのホストを、インポート先の環境にあるホストにマップできる。</span><span class="sxs-lookup"><span data-stu-id="ed44a-120">You should be able to map all hosts in the source environment with those in the destination environment.</span></span>  
  
-   <span data-ttu-id="ed44a-121">インポート先環境には、インポート元環境と (同じかまたは) 似たハードウェアがあります。</span><span class="sxs-lookup"><span data-stu-id="ed44a-121">The destination environment has hardware similar (if not identical) to the source environment.</span></span> <span data-ttu-id="ed44a-122">一部の設定は基礎となるハードウェアに依存しているため、これは重要です。</span><span class="sxs-lookup"><span data-stu-id="ed44a-122">This is essential as some of the settings depend on the underlying hardware.</span></span>  

### <a name="import-steps"></a><span data-ttu-id="ed44a-123">インポートの手順</span><span class="sxs-lookup"><span data-stu-id="ed44a-123">Import steps</span></span>
  
1. <span data-ttu-id="ed44a-124">**BizTalk Server 管理コンソール**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を右クリックして**BizTalk グループ**、 をクリックし、**設定**します。</span><span class="sxs-lookup"><span data-stu-id="ed44a-124">In the **BizTalk Server Administration Console**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Settings**.</span></span>  
  
2. <span data-ttu-id="ed44a-125">**BizTalk 設定ダッシュ ボード**ダイアログ ボックスで、をクリックして**インポート**します。</span><span class="sxs-lookup"><span data-stu-id="ed44a-125">In the **BizTalk Settings Dashboard** dialog box, click **Import**.</span></span> <span data-ttu-id="ed44a-126">**設定のインポート ウィザード** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed44a-126">The **Import Settings Wizard** dialog box appears.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ed44a-127">**宛先グループ**の設定をインポートするターゲット コンピューターのグループ情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="ed44a-127">The **Destination Group** displays the group information of the target machine where you want to import the settings.</span></span>  
  
    <span data-ttu-id="ed44a-128">![設定をインポートするファイルの場所を指定](../core/media/importsettings-filelocation.jpg "ImportSettings_FileLocation")</span><span class="sxs-lookup"><span data-stu-id="ed44a-128">![Specify the file location to import settings](../core/media/importsettings-filelocation.jpg "ImportSettings_FileLocation")</span></span>  
  
3. <span data-ttu-id="ed44a-129">をクリックして、**ファイルの場所を指定**] ページの [クリックして![設定ファイルの参照](../core/media/importsettings-filelocationbrowse.gif "ImportSettings_FileLocationBrowse")します。</span><span class="sxs-lookup"><span data-stu-id="ed44a-129">Click the **Specify File Location** page, and then click ![Browse the settings file](../core/media/importsettings-filelocationbrowse.gif "ImportSettings_FileLocationBrowse").</span></span> <span data-ttu-id="ed44a-130">ファイル エクスプローラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed44a-130">The file explorer appears.</span></span>  
  
4. <span data-ttu-id="ed44a-131">ソース環境の設定を含む XML ファイルを選択し、クリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="ed44a-131">Select the XML file containing the source environment settings, and then click **Open**.</span></span> <span data-ttu-id="ed44a-132">**ファイルの場所**XML ファイルのパスが表示されます、**ソース グループ**ソース マシンのグループの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed44a-132">The **File Location** displays the path of the XML file and the **Source Group** is populated with the group information of the source machine.</span></span> <span data-ttu-id="ed44a-133">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed44a-133">Click **Next**.</span></span>  
  
5. <span data-ttu-id="ed44a-134">**ホスト マッピング**ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ed44a-134">On the **Host Mapping** page, do the following:</span></span>  
  
   1.  <span data-ttu-id="ed44a-135">**宛先ホスト**一覧で、ソース ホストを指定し、クリックする移行先ホストを選択します。**追加**します。</span><span class="sxs-lookup"><span data-stu-id="ed44a-135">From the **Destination Hosts** list, select a destination host for which you want to specify the source host, and then click **Add**.</span></span>  
  
        <span data-ttu-id="ed44a-136">![ホスト マッピング](../core/media/importsettings-hostmapping.gif "ImportSettings_HostMapping")</span><span class="sxs-lookup"><span data-stu-id="ed44a-136">![Host Mapping](../core/media/importsettings-hostmapping.gif "ImportSettings_HostMapping")</span></span>  
  
   2.  <span data-ttu-id="ed44a-137">**ソース エンティティの選択** ダイアログ ボックスでは、ソース ホストを選択し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="ed44a-137">In the **Select Source Entity** dialog box, select the source host, and then click **OK**.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="ed44a-138">1 つのソースのホストに複数の送信先ホストにマップする手順を繰り返します**5a**と**5b**します。</span><span class="sxs-lookup"><span data-stu-id="ed44a-138">To map multiple destination hosts to a single source host, repeat the steps **5a** and **5b**.</span></span>  
  
   3.  <span data-ttu-id="ed44a-139">**ホスト マッピング**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="ed44a-139">In the **Host Mapping** page, click **Next**.</span></span>  
  
6. <span data-ttu-id="ed44a-140">**ホスト インスタンス マッピング**ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ed44a-140">In the **Host Instance Mapping** page, do the following:</span></span>  
  
   1.  <span data-ttu-id="ed44a-141">インポート先ホスト インスタンスの一覧から、ソース ホスト インスタンスを指定し、クリックする宛先のホスト インスタンスを選択します。**追加**します。</span><span class="sxs-lookup"><span data-stu-id="ed44a-141">From the list of destination host instances, select a destination host instance for which you want to specify the source host instance, and then click **Add**.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="ed44a-142">ホスト インスタンスは、ホスト マッピングで指定された対応するホストにのみマップできます。</span><span class="sxs-lookup"><span data-stu-id="ed44a-142">Host instances can be mapped only to the corresponding host that has been created in the Host Mapping.</span></span> <span data-ttu-id="ed44a-143">たとえば、次のマッピングを指定する場所**SourceHost1**にマップされます**DestinationHost1**のインスタンスでは、 **DestinationHost1**インスタンスにしかマップできません**SourceHost1**します。</span><span class="sxs-lookup"><span data-stu-id="ed44a-143">For example, if you specify a mapping where **SourceHost1** is mapped to **DestinationHost1**, then the instances of **DestinationHost1** can only be mapped to the instances of **SourceHost1**.</span></span>  
       >   
       >  <span data-ttu-id="ed44a-144">上記の制約はインポート ウィザードによって管理され、この制約に従う必要があります。従わない場合、BizTalk タスクによってエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="ed44a-144">The import wizard manages the above constraint, you need to follow this constraint else BizTalk tasks will throw errors.</span></span>  
       >   
       >  <span data-ttu-id="ed44a-145">規則を使用する必要がある**HostName:MachineName**マップ ファイルのホスト インスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ed44a-145">You need to use the convention **HostName:MachineName** to specify a host instance in a map file.</span></span> <span data-ttu-id="ed44a-146">たとえば、 **Host1:Server1**マップ ファイルを表しているインスタンスの**Host1**が実行中か**Server1**します。</span><span class="sxs-lookup"><span data-stu-id="ed44a-146">For example, **Host1:Server1** in a map file denotes that the instance of **Host1** is running or available on **Server1**.</span></span>  
  
        <span data-ttu-id="ed44a-147">![ホスト インスタンス マッピング](../core/media/importsettings-hostinstancemapping.gif "ImportSettings_HostInstanceMapping")</span><span class="sxs-lookup"><span data-stu-id="ed44a-147">![Host Instance Mapping](../core/media/importsettings-hostinstancemapping.gif "ImportSettings_HostInstanceMapping")</span></span>  
  
   2.  <span data-ttu-id="ed44a-148">**ソース エンティティの選択** ダイアログ ボックスで、ソース ホスト インスタンスを選択し、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="ed44a-148">In the **Select Source Entity** dialog box, select the source host instance, and then click **OK**.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="ed44a-149">複数の宛先ホスト インスタンスを 1 つのソース ホスト インスタンスをマップする手順を繰り返します**6a**に**6b**します。</span><span class="sxs-lookup"><span data-stu-id="ed44a-149">To map multiple destination host instances to a single source host instance, repeat the steps **6a** to **6b**.</span></span>  
  
   3.  <span data-ttu-id="ed44a-150">**ホスト インスタンス マッピング**] タブで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="ed44a-150">In the **Host Instance Mapping** tab, click **Next**.</span></span>  
  
7. <span data-ttu-id="ed44a-151">**インポートの概要**ダイアログ ボックスで、確認としての送信先と送信元の環境を作成したすべてのインポート設定がある場合は、必要に応じてをクリックして**インポート**します。</span><span class="sxs-lookup"><span data-stu-id="ed44a-151">In the **Import Summary** dialog box, verify if all the import settings for destination and source environments you created are as desired, and then click **Import**.</span></span> <span data-ttu-id="ed44a-152">**進行状況**ページには、設定のインポートの進行状況が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed44a-152">The **Progress** page shows the progress of import of the settings.</span></span>  
  
   > [!WARNING]
   >  <span data-ttu-id="ed44a-153">BizTalk Server 設定のインポートを元に戻すことはできません。</span><span class="sxs-lookup"><span data-stu-id="ed44a-153">You cannot undo the import of BizTalk Server settings.</span></span> <span data-ttu-id="ed44a-154">クリックすると**インポート**、送信先の環境にソース環境から設定をインポートするためのプロセスが開始されると**キャンセル**は無効です。</span><span class="sxs-lookup"><span data-stu-id="ed44a-154">If you click **Import**, the process for importing the settings from source environment to destination environment is initiated and **Cancel** is disabled.</span></span> <span data-ttu-id="ed44a-155">クリックする前にインポートを続行することを確認**インポート**します。</span><span class="sxs-lookup"><span data-stu-id="ed44a-155">Ensure you want to proceed with import before clicking **Import**.</span></span>  
  
8. <span data-ttu-id="ed44a-156">**インポート結果** タブで、グループ、ホスト、およびホスト インスタンスの設定のインポートの状態を確認し、をクリックし、**完了**インポート操作を完了します。</span><span class="sxs-lookup"><span data-stu-id="ed44a-156">In the **Import Results** tab, check the import status of the Group, Host, and Host Instance settings, and then click **Finish** to complete the import operation.</span></span> <span data-ttu-id="ed44a-157">インポート元の環境からインポートしたすべての設定が、インポート先の環境に適用されます。</span><span class="sxs-lookup"><span data-stu-id="ed44a-157">All the imported source environment settings are applied to the destination environment.</span></span>  
  
    <span data-ttu-id="ed44a-158">![結果のインポート](../core/media/importsettings-importresults.gif "ImportSettings_ImportResults")</span><span class="sxs-lookup"><span data-stu-id="ed44a-158">![Import Results](../core/media/importsettings-importresults.gif "ImportSettings_ImportResults")</span></span>  

## <a name="export-the-biztalk-group-host-and-host-instance-settings"></a><span data-ttu-id="ed44a-159">BizTalk グループ、ホスト、およびホスト インスタンスの設定をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="ed44a-159">Export the BizTalk group, host, and host instance settings</span></span>  

1. <span data-ttu-id="ed44a-160">**BizTalk Server 管理コンソール**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を右クリックして**BizTalk グループ**、 をクリックし、**設定**します。</span><span class="sxs-lookup"><span data-stu-id="ed44a-160">In the **BizTalk Server Administration Console**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Settings**.</span></span>  
  
2. <span data-ttu-id="ed44a-161">**BizTalk 設定ダッシュ ボード**ダイアログ ボックスで、をクリックして**エクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="ed44a-161">In the **BizTalk Settings Dashboard** dialog box, click **Export**.</span></span> <span data-ttu-id="ed44a-162">**[名前を付けて保存]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed44a-162">The **Save As** dialog box appears.</span></span>  
  
3. <span data-ttu-id="ed44a-163">BizTalk の現在の設定を保存する場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="ed44a-163">Browse to the location where you want to save the current BizTalk settings.</span></span> <span data-ttu-id="ed44a-164">ファイル名を入力、XML の形式として、種類の選択および順にクリックします**保存**します。</span><span class="sxs-lookup"><span data-stu-id="ed44a-164">Enter the filename, select the type as XML format, and then click **Save**.</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="ed44a-165">エクスポートされた XML ファイルを手動で更新することはお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="ed44a-165">We do not recommended manually updating the exported XML file.</span></span> <span data-ttu-id="ed44a-166">運用環境に更新された XML ファイルをインポートすると、インポート プロセスが失敗するデータ型の不一致または手動で編集で導入されたその他のエラーのためです。</span><span class="sxs-lookup"><span data-stu-id="ed44a-166">When you import an updated XML file to a production environment, the import process might fail due to some data type mismatch or other errors introduced by manual editing.</span></span>  

## <a name="see-also"></a><span data-ttu-id="ed44a-167">参照</span><span class="sxs-lookup"><span data-stu-id="ed44a-167">See Also</span></span>  
 [<span data-ttu-id="ed44a-168">BizTalk Server パフォーマンス チューニングのための設定ダッシュボードの使用</span><span class="sxs-lookup"><span data-stu-id="ed44a-168">Using Settings Dashboard for BizTalk Server Performance Tuning</span></span>](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)

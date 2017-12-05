---
title: "BAM 開発プロセスの概要 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 098db3f6-2a61-4cc8-88c7-2299c2e2a55e
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78ae5f1c61f2a00359e88acd75c093e2b6c2fb91
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="overview-of-the-bam-development-process"></a><span data-ttu-id="bbc09-102">BAM 開発プロセスの概要</span><span class="sxs-lookup"><span data-stu-id="bbc09-102">Overview of the BAM Development Process</span></span>
<span data-ttu-id="bbc09-103">このトピックでは、開発プロセス、および BAM データを格納するデータベースおよびテーブルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bbc09-103">This topic describes the development process and the database and tables that store BAM data.</span></span>  
  
## <a name="prerequisites-for-developing-with-bam"></a><span data-ttu-id="bbc09-104">BAM を使用した開発に必要なスキルと知識</span><span class="sxs-lookup"><span data-stu-id="bbc09-104">Prerequisites for Developing with BAM</span></span>  
 <span data-ttu-id="bbc09-105">BAM を使用した開発を開始するにあたっては、次の前提条件に注意してください。</span><span class="sxs-lookup"><span data-stu-id="bbc09-105">Note the following prerequisites before you begin developing with BAM:</span></span>  
  
-   <span data-ttu-id="bbc09-106">アプリケーションをインストルメント化するには、アクティビティの展開が必要です。</span><span class="sxs-lookup"><span data-stu-id="bbc09-106">To instrument an application you must have an activity deployed.</span></span>  
  
-   <span data-ttu-id="bbc09-107">SQL Server データベースに対する DBO 権限を持っているし、BAM イベント ライター ロール セキュリティ コンテキストのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbc09-107">You must have DBO rights to the SQL Server databases and be a member of the BAM Event Writer Role security context.</span></span>  
  
-   <span data-ttu-id="bbc09-108">Microsoft .NET 4 を使用すると、アプリケーションを開発するのに必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbc09-108">You must use Microsoft .NET 4 to develop your application.</span></span> <span data-ttu-id="bbc09-109">使用すること (C#) お勧めしますが、任意の .NET 言語を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bbc09-109">You can use any .NET language, although we recommend that you use C#.</span></span>  
  
-   <span data-ttu-id="bbc09-110">コンピューターに Microsoft.BizTalk.BAM.EventObservation.dll をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbc09-110">You must have the Microsoft.BizTalk.BAM.EventObservation.dll installed on your computer.</span></span> <span data-ttu-id="bbc09-111">DLL は 2 とおりの方法で入手できます。</span><span class="sxs-lookup"><span data-stu-id="bbc09-111">You can obtain the DLL in two ways:</span></span>  
  
    -   <span data-ttu-id="bbc09-112">BizTalk Server 構成マネージャーを使用して BAM ツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="bbc09-112">Use the BizTalk Server Configuration Manager to install the BAM tools.</span></span> <span data-ttu-id="bbc09-113">構成マネージャーを使用することをお勧めします。構成マネージャーによって、アップグレードに必要なエントリがレジストリに自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="bbc09-113">We recommend that you use the Configuration Manager because it places appropriate entries in the registry that facilitate upgrades.</span></span> <span data-ttu-id="bbc09-114">BAM を構成する方法の詳細については、次を参照してください。[を構成する BAM ツールを使用して、Configuration Manager](http://go.microsoft.com/fwlink/?LinkId=70561) (http://go.microsoft.com/fwlink/?LinkId=70561)。</span><span class="sxs-lookup"><span data-stu-id="bbc09-114">For more information about configuring BAM, see [Configuring BAM Tools Using the Configuration Manager](http://go.microsoft.com/fwlink/?LinkId=70561) (http://go.microsoft.com/fwlink/?LinkId=70561).</span></span>  
  
    -   <span data-ttu-id="bbc09-115">DLL が既にインストールされているコンピューターからコピーします。</span><span class="sxs-lookup"><span data-stu-id="bbc09-115">Copy the DLL from a computer on which they have already been installed.</span></span> <span data-ttu-id="bbc09-116">Microsoft BizTalk Server に存在する DLL\<バージョン\>\Tracking フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="bbc09-116">The DLL resides in the Microsoft BizTalk Server \<version\>\Tracking folder.</span></span>  
  
## <a name="bam-development-process"></a><span data-ttu-id="bbc09-117">BAM 開発プロセス</span><span class="sxs-lookup"><span data-stu-id="bbc09-117">BAM Development Process</span></span>  
 <span data-ttu-id="bbc09-118">次の図は、BAM 開発フローを示しています。</span><span class="sxs-lookup"><span data-stu-id="bbc09-118">The following figure describes the BAM development flow.</span></span>  
  
 <span data-ttu-id="bbc09-119">![BAM 開発作業の流れ](../core/media/dwb-bamdevelopmentflowc.gif "dwb_bamdevelopmentflowc")</span><span class="sxs-lookup"><span data-stu-id="bbc09-119">![BAM development work flow](../core/media/dwb-bamdevelopmentflowc.gif "dwb_bamdevelopmentflowc")</span></span>  
  
 <span data-ttu-id="bbc09-120">BAM を使用したソリューションの開発の基本的な手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bbc09-120">The following procedure lists the basic steps for developing a solution with BAM.</span></span>  
  
#### <a name="to-develop-a-bam-enabled-solution"></a><span data-ttu-id="bbc09-121">BAM によるソリューションを開発するには</span><span class="sxs-lookup"><span data-stu-id="bbc09-121">To develop a BAM-enabled solution</span></span>  
  
1.  <span data-ttu-id="bbc09-122">Excel 用 BAM アドインを使用した監視モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="bbc09-122">Create an observation model with the BAM Add-in for Excel.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bbc09-123">この手順で説明する手順の例で、BAM API (BizTalk Server サンプル) にあります[http://go.microsoft.com/fwlink/?LinkId=69968](http://go.microsoft.com/fwlink/?LinkId=69968)です。</span><span class="sxs-lookup"><span data-stu-id="bbc09-123">Examples of the steps noted in this procedure can be found in the BAM API (BizTalk Server sample) at [http://go.microsoft.com/fwlink/?LinkId=69968](http://go.microsoft.com/fwlink/?LinkId=69968).</span></span>  
  
2.  <span data-ttu-id="bbc09-124">BAM 管理ユーティリティを使用して、アクティビティを PID に展開します。</span><span class="sxs-lookup"><span data-stu-id="bbc09-124">Use the BAM Management utility to deploy the activity to the PID.</span></span>  
  
3.  <span data-ttu-id="bbc09-125">BAM EventStream コードを追加することによって、アプリケーションをインストルメント化します。</span><span class="sxs-lookup"><span data-stu-id="bbc09-125">Instrument the application by adding your BAM EventStream code.</span></span>  
  
4.  <span data-ttu-id="bbc09-126">アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="bbc09-126">Run the application.</span></span> <span data-ttu-id="bbc09-127">これを実行する場合、コードの内容は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="bbc09-127">When you do this, the code will:</span></span>  
  
    -   <span data-ttu-id="bbc09-128">プレース ホルダー レコードを bam _ 追加\<*アクティビティ名*\>_Active テーブル。</span><span class="sxs-lookup"><span data-stu-id="bbc09-128">Add a placeholder record to the BAM_\<*activity name*\>_Active table.</span></span>  
  
    -   <span data-ttu-id="bbc09-129">レコードのデータ項目を更新します。</span><span class="sxs-lookup"><span data-stu-id="bbc09-129">Update the data items in the record.</span></span>  
  
    -   <span data-ttu-id="bbc09-130">アクティビティを終了し、bam _ にレコードを移動\<*アクティビティ名**\>_completed テーブル。</span><span class="sxs-lookup"><span data-stu-id="bbc09-130">End the activity and move the record to the BAM_\<*activity name**\>_completed table.</span></span>  
  
## <a name="where-bam-data-is-stored"></a><span data-ttu-id="bbc09-131">BAM データの格納場所</span><span class="sxs-lookup"><span data-stu-id="bbc09-131">Where BAM Data Is Stored</span></span>  
 <span data-ttu-id="bbc09-132">BAM は、BAM イベントの処理に使用する EventStream クラスを持つ EventObservation 名前空間を提供します。</span><span class="sxs-lookup"><span data-stu-id="bbc09-132">BAM provides the EventObservation namespace that contains the EventStream classes that are used to handle BAM events.</span></span>  
  
 <span data-ttu-id="bbc09-133">BAM 追跡データは、BAM プライマリ インポート データベース (PID) に格納されます。</span><span class="sxs-lookup"><span data-stu-id="bbc09-133">BAM tracking data is stored in the BAM Primary Import database (PID).</span></span> <span data-ttu-id="bbc09-134">BAM 管理ユーティリティを使用して監視モデルを展開すると、次の 5 つのテーブルが PID に作成されます。</span><span class="sxs-lookup"><span data-stu-id="bbc09-134">When you deploy an observation model using the BAM Management utility, the following five tables are created in the PID.</span></span>  
  
|<span data-ttu-id="bbc09-135">名前</span><span class="sxs-lookup"><span data-stu-id="bbc09-135">Name</span></span>|<span data-ttu-id="bbc09-136">Description</span><span class="sxs-lookup"><span data-stu-id="bbc09-136">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="bbc09-137">アクティブ テーブル</span><span class="sxs-lookup"><span data-stu-id="bbc09-137">Active table</span></span>|<span data-ttu-id="bbc09-138">Bam _ という名前\<*アクティビティ名*\>_Active、このテーブルがまだ完了していないこの種類のアクティビティを格納します。</span><span class="sxs-lookup"><span data-stu-id="bbc09-138">Named bam_\<*activity name*\>_Active, this table holds the activities of this type that have not yet completed.</span></span>|  
|<span data-ttu-id="bbc09-139">アクティブ リレーションシップ テーブル</span><span class="sxs-lookup"><span data-stu-id="bbc09-139">Active relationships table</span></span>|<span data-ttu-id="bbc09-140">Bam _ という名前\<*アクティビティ名*\>_ActiveRelationships、このテーブルにはまだ完了していないアクティビティの関連のアクティビティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bbc09-140">Named bam_\<*activity name*\>_ActiveRelationships, this table contains the related activities for the activity that have not yet completed.</span></span>|  
|<span data-ttu-id="bbc09-141">Continuation テーブル</span><span class="sxs-lookup"><span data-stu-id="bbc09-141">Continuations table</span></span>|<span data-ttu-id="bbc09-142">Bam _ という名前\<*アクティビティ名*\>_continuations、次の表に、アクティビティの continuation アクティビティ、アクティビティが一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="bbc09-142">Named bam_\<*activity name*\>_continuations, this table lists the continuations activities for the activity.</span></span>|  
|<span data-ttu-id="bbc09-143">完了したテーブル</span><span class="sxs-lookup"><span data-stu-id="bbc09-143">Completed table</span></span>|<span data-ttu-id="bbc09-144">Bam _ という名前\<*アクティビティ名*\>_completed です。</span><span class="sxs-lookup"><span data-stu-id="bbc09-144">Named bam_\<*activity name*\>_completed.</span></span>|  
|<span data-ttu-id="bbc09-145">完了したリレーションシップ テーブル</span><span class="sxs-lookup"><span data-stu-id="bbc09-145">Completed Relationships table</span></span>|<span data-ttu-id="bbc09-146">Bam _ という名前\<*アクティビティ名*\>_CompletedRelationships、次の表に、アクティビティの完了した関連アクティビティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bbc09-146">Named bam_\<*activity name*\>_CompletedRelationships, this table contains the completed related activities for the activity.</span></span>|  
  
 <span data-ttu-id="bbc09-147">BAM アクティビティの 4 つのデータ型を取得します。</span><span class="sxs-lookup"><span data-stu-id="bbc09-147">You capture four types of data in a BAM activity:</span></span>  
  
-   <span data-ttu-id="bbc09-148">文字列</span><span class="sxs-lookup"><span data-stu-id="bbc09-148">String</span></span>  
  
-   <span data-ttu-id="bbc09-149">Data/Time (一般的にマイルストーンと呼ばれます)</span><span class="sxs-lookup"><span data-stu-id="bbc09-149">Data/Time (commonly referred to as milestones)</span></span>  
  
-   <span data-ttu-id="bbc09-150">Integer</span><span class="sxs-lookup"><span data-stu-id="bbc09-150">Integer</span></span>  
  
-   <span data-ttu-id="bbc09-151">Float</span><span class="sxs-lookup"><span data-stu-id="bbc09-151">Float</span></span>
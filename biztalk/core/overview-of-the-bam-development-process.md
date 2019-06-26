---
title: BAM 開発プロセスの概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 098db3f6-2a61-4cc8-88c7-2299c2e2a55e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a5665e5c8b9cdf098972b6d2c82d772c5cdfee7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393399"
---
# <a name="overview-of-the-bam-development-process"></a><span data-ttu-id="d403b-102">BAM 開発プロセスの概要</span><span class="sxs-lookup"><span data-stu-id="d403b-102">Overview of the BAM Development Process</span></span>
<span data-ttu-id="d403b-103">このトピックでは、開発プロセスと、データベースおよび BAM データを格納するテーブルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d403b-103">This topic describes the development process and the database and tables that store BAM data.</span></span>  
  
## <a name="prerequisites-for-developing-with-bam"></a><span data-ttu-id="d403b-104">BAM を使用した開発の前提条件</span><span class="sxs-lookup"><span data-stu-id="d403b-104">Prerequisites for Developing with BAM</span></span>  
 <span data-ttu-id="d403b-105">BAM を使用した開発を開始する前に、次の前提条件に注意してください。</span><span class="sxs-lookup"><span data-stu-id="d403b-105">Note the following prerequisites before you begin developing with BAM:</span></span>  
  
-   <span data-ttu-id="d403b-106">アプリケーションをインストルメント化するには、アクティビティの展開が必要です。</span><span class="sxs-lookup"><span data-stu-id="d403b-106">To instrument an application you must have an activity deployed.</span></span>  
  
-   <span data-ttu-id="d403b-107">SQL Server データベースの DBO 権限を持っているし、BAM イベント ライター ロール セキュリティ コンテキストのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d403b-107">You must have DBO rights to the SQL Server databases and be a member of the BAM Event Writer Role security context.</span></span>  
  
-   <span data-ttu-id="d403b-108">Microsoft .NET 4 を使用して、アプリケーションを開発する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d403b-108">You must use Microsoft .NET 4 to develop your application.</span></span> <span data-ttu-id="d403b-109">任意の .NET 言語を使用できますが、使用することをお勧めします。C#します。</span><span class="sxs-lookup"><span data-stu-id="d403b-109">You can use any .NET language, although we recommend that you use C#.</span></span>  
  
-   <span data-ttu-id="d403b-110">Microsoft.BizTalk.BAM.EventObservation.dll をコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d403b-110">You must have the Microsoft.BizTalk.BAM.EventObservation.dll installed on your computer.</span></span> <span data-ttu-id="d403b-111">2 つの方法で DLL を入手できます。</span><span class="sxs-lookup"><span data-stu-id="d403b-111">You can obtain the DLL in two ways:</span></span>  
  
    -   <span data-ttu-id="d403b-112">BAM ツールをインストールするのにには、BizTalk Server 構成マネージャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="d403b-112">Use the BizTalk Server Configuration Manager to install the BAM tools.</span></span> <span data-ttu-id="d403b-113">レジストリのアップグレードに適切なエントリに配置するために、Configuration Manager を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d403b-113">We recommend that you use the Configuration Manager because it places appropriate entries in the registry that facilitate upgrades.</span></span> <span data-ttu-id="d403b-114">BAM を構成する方法の詳細については、次を参照してください。[を構成する BAM ツールを使用して、Configuration Manager](http://go.microsoft.com/fwlink/?LinkId=70561) (http://go.microsoft.com/fwlink/?LinkId=70561) します。</span><span class="sxs-lookup"><span data-stu-id="d403b-114">For more information about configuring BAM, see [Configuring BAM Tools Using the Configuration Manager](http://go.microsoft.com/fwlink/?LinkId=70561) (http://go.microsoft.com/fwlink/?LinkId=70561).</span></span>  
  
    -   <span data-ttu-id="d403b-115">既にインストールされているコンピューターから DLL をコピーします。</span><span class="sxs-lookup"><span data-stu-id="d403b-115">Copy the DLL from a computer on which they have already been installed.</span></span> <span data-ttu-id="d403b-116">Microsoft BizTalk Server で、DLL が存在する\<バージョン\>\Tracking フォルダー。</span><span class="sxs-lookup"><span data-stu-id="d403b-116">The DLL resides in the Microsoft BizTalk Server \<version\>\Tracking folder.</span></span>  
  
## <a name="bam-development-process"></a><span data-ttu-id="d403b-117">BAM 開発プロセス</span><span class="sxs-lookup"><span data-stu-id="d403b-117">BAM Development Process</span></span>  
 <span data-ttu-id="d403b-118">次の図には、BAM 開発フローについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d403b-118">The following figure describes the BAM development flow.</span></span>  
  
 <span data-ttu-id="d403b-119">![BAM 開発作業の流れ](../core/media/dwb-bamdevelopmentflowc.gif "dwb_bamdevelopmentflowc")</span><span class="sxs-lookup"><span data-stu-id="d403b-119">![BAM development work flow](../core/media/dwb-bamdevelopmentflowc.gif "dwb_bamdevelopmentflowc")</span></span>  
  
 <span data-ttu-id="d403b-120">次の手順では、BAM によるソリューションを開発するための基本的な手順が一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="d403b-120">The following procedure lists the basic steps for developing a solution with BAM.</span></span>  
  
#### <a name="to-develop-a-bam-enabled-solution"></a><span data-ttu-id="d403b-121">BAM が有効なソリューションを開発するには</span><span class="sxs-lookup"><span data-stu-id="d403b-121">To develop a BAM-enabled solution</span></span>  
  
1.  <span data-ttu-id="d403b-122">Excel 用 BAM アドインに監視モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="d403b-122">Create an observation model with the BAM Add-in for Excel.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d403b-123">この手順でメモした手順の例については、BAM api (BizTalk Server サンプル) で見つかります[ http://go.microsoft.com/fwlink/?LinkId=69968](http://go.microsoft.com/fwlink/?LinkId=69968)します。</span><span class="sxs-lookup"><span data-stu-id="d403b-123">Examples of the steps noted in this procedure can be found in the BAM API (BizTalk Server sample) at [http://go.microsoft.com/fwlink/?LinkId=69968](http://go.microsoft.com/fwlink/?LinkId=69968).</span></span>  
  
2.  <span data-ttu-id="d403b-124">アクティビティを PID に展開するのにには、BAM 管理ユーティリティを使用します。</span><span class="sxs-lookup"><span data-stu-id="d403b-124">Use the BAM Management utility to deploy the activity to the PID.</span></span>  
  
3.  <span data-ttu-id="d403b-125">BAM EventStream コードを追加することで、アプリケーションをインストルメント化します。</span><span class="sxs-lookup"><span data-stu-id="d403b-125">Instrument the application by adding your BAM EventStream code.</span></span>  
  
4.  <span data-ttu-id="d403b-126">アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="d403b-126">Run the application.</span></span> <span data-ttu-id="d403b-127">これを行うと、コードが行われます。</span><span class="sxs-lookup"><span data-stu-id="d403b-127">When you do this, the code will:</span></span>  
  
    -   <span data-ttu-id="d403b-128">プレース ホルダー レコードが、bam _ \<*アクティビティ名*\>_Active テーブル。</span><span class="sxs-lookup"><span data-stu-id="d403b-128">Add a placeholder record to the BAM_\<*activity name*\>_Active table.</span></span>  
  
    -   <span data-ttu-id="d403b-129">レコード内のデータ項目を更新します。</span><span class="sxs-lookup"><span data-stu-id="d403b-129">Update the data items in the record.</span></span>  
  
    -   <span data-ttu-id="d403b-130">アクティビティを終了し、bam _ にレコードを移動\<\* アクティビティ名 \* \*\>_completed テーブル。</span><span class="sxs-lookup"><span data-stu-id="d403b-130">End the activity and move the record to the BAM_\<\*activity name\*\*\>_completed table.</span></span>  
  
## <a name="where-bam-data-is-stored"></a><span data-ttu-id="d403b-131">BAM データの保存場所</span><span class="sxs-lookup"><span data-stu-id="d403b-131">Where BAM Data Is Stored</span></span>  
 <span data-ttu-id="d403b-132">BAM では、BAM イベントを処理するために使用する EventStream クラスを含む持つ EventObservation 名前空間を提供します。</span><span class="sxs-lookup"><span data-stu-id="d403b-132">BAM provides the EventObservation namespace that contains the EventStream classes that are used to handle BAM events.</span></span>  
  
 <span data-ttu-id="d403b-133">BAM の追跡データは、BAM プライマリ インポート データベース (PID) に格納されます。</span><span class="sxs-lookup"><span data-stu-id="d403b-133">BAM tracking data is stored in the BAM Primary Import database (PID).</span></span> <span data-ttu-id="d403b-134">BAM 管理ユーティリティを使用して監視モデルを展開するときに、次の 5 つのテーブルが PID に作成されます。</span><span class="sxs-lookup"><span data-stu-id="d403b-134">When you deploy an observation model using the BAM Management utility, the following five tables are created in the PID.</span></span>  
  
|<span data-ttu-id="d403b-135">名前</span><span class="sxs-lookup"><span data-stu-id="d403b-135">Name</span></span>|<span data-ttu-id="d403b-136">説明</span><span class="sxs-lookup"><span data-stu-id="d403b-136">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="d403b-137">アクティブなテーブル</span><span class="sxs-lookup"><span data-stu-id="d403b-137">Active table</span></span>|<span data-ttu-id="d403b-138">Bam _ という名前\<*アクティビティ名*\>(_a)、このテーブルにはまだ完了していないこの種類のアクティビティが格納されます。</span><span class="sxs-lookup"><span data-stu-id="d403b-138">Named bam_\<*activity name*\>_Active, this table holds the activities of this type that have not yet completed.</span></span>|  
|<span data-ttu-id="d403b-139">アクティブ リレーションシップ テーブル</span><span class="sxs-lookup"><span data-stu-id="d403b-139">Active relationships table</span></span>|<span data-ttu-id="d403b-140">Bam _ という名前\<*アクティビティ名*\>_ActiveRelationships、このテーブルにはまだ完了していないアクティビティの関連のアクティビティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d403b-140">Named bam_\<*activity name*\>_ActiveRelationships, this table contains the related activities for the activity that have not yet completed.</span></span>|  
|<span data-ttu-id="d403b-141">Continuation テーブル</span><span class="sxs-lookup"><span data-stu-id="d403b-141">Continuations table</span></span>|<span data-ttu-id="d403b-142">Bam _ という名前\<*アクティビティ名*\>_continuations、次の表に、アクティビティの continuation アクティビティが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="d403b-142">Named bam_\<*activity name*\>_continuations, this table lists the continuations activities for the activity.</span></span>|  
|<span data-ttu-id="d403b-143">完了したテーブル</span><span class="sxs-lookup"><span data-stu-id="d403b-143">Completed table</span></span>|<span data-ttu-id="d403b-144">Bam _ という名前\<*アクティビティ名*\>_completed します。</span><span class="sxs-lookup"><span data-stu-id="d403b-144">Named bam_\<*activity name*\>_completed.</span></span>|  
|<span data-ttu-id="d403b-145">完了したリレーションシップ テーブル</span><span class="sxs-lookup"><span data-stu-id="d403b-145">Completed Relationships table</span></span>|<span data-ttu-id="d403b-146">Bam _ という名前\<*アクティビティ名*\>_CompletedRelationships、次の表に、アクティビティの完了した関連アクティビティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d403b-146">Named bam_\<*activity name*\>_CompletedRelationships, this table contains the completed related activities for the activity.</span></span>|  
  
 <span data-ttu-id="d403b-147">4 つの種類のデータを BAM アクティビティをキャプチャするには。</span><span class="sxs-lookup"><span data-stu-id="d403b-147">You capture four types of data in a BAM activity:</span></span>  
  
-   <span data-ttu-id="d403b-148">String</span><span class="sxs-lookup"><span data-stu-id="d403b-148">String</span></span>  
  
-   <span data-ttu-id="d403b-149">日付/時刻 (マイルス トーンとも呼ばれます)</span><span class="sxs-lookup"><span data-stu-id="d403b-149">Data/Time (commonly referred to as milestones)</span></span>  
  
-   <span data-ttu-id="d403b-150">Integer</span><span class="sxs-lookup"><span data-stu-id="d403b-150">Integer</span></span>  
  
-   <span data-ttu-id="d403b-151">float</span><span class="sxs-lookup"><span data-stu-id="d403b-151">Float</span></span>
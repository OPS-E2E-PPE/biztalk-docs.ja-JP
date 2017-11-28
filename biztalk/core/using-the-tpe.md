---
title: "TPE を使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking Profile Editor, about Tracking Profile Editor
- tracking profiles, prerequisites
ms.assetid: ebe9a5da-66ec-482d-8aac-892a829ca996
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0fa826ce68042336c2b6e4fb006ecb278a3f981
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-tpe"></a><span data-ttu-id="af2f6-102">TPE の使用</span><span class="sxs-lookup"><span data-stu-id="af2f6-102">Using the TPE</span></span>
<span data-ttu-id="af2f6-103">オーケストレーションとプロパティを BAM アクティビティ定義にマップするには、追跡プロファイル エディター (TPE) を使用します。</span><span class="sxs-lookup"><span data-stu-id="af2f6-103">You use the Tracking Profile Editor (TPE) to map orchestrations and properties to BAM activity definitions.</span></span>  
  
 <span data-ttu-id="af2f6-104">TPE のユーザーは、マイルストーンやコンテキスト データ ("表示希望リスト" と呼ばれることもある) などの BAM アクティビティの項目間にマップ (つまり追跡プロファイル) を作成し、これらの項目の BizTalk ソリューション ソースを作成します。</span><span class="sxs-lookup"><span data-stu-id="af2f6-104">Users of the TPE create a map, or tracking profile, between items in a BAM activity such as milestones and contextual data (sometimes called the "visibility wish-list") and the BizTalk solution sources for those items.</span></span>  
  
 <span data-ttu-id="af2f6-105">**追跡プロファイルの作成**</span><span class="sxs-lookup"><span data-stu-id="af2f6-105">**Creating a Tracking Profile**</span></span>  
  
 <span data-ttu-id="af2f6-106">たとえば、「PO を受信しました」というマイルス トーンを含む BAM アクティビティ</span><span class="sxs-lookup"><span data-stu-id="af2f6-106">For example, consider a BAM activity that includes a milestone called “PO Received.”</span></span> <span data-ttu-id="af2f6-107">開発者は、他の BizTalk Server 開発ツールでプロセスを作成することから、実際のプロセスが注文書が経由は処理を開始するメッセージング ポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="af2f6-107">The developer knows, from having created processes in other BizTalk Server development tools, that the actual process includes a messaging port through which purchase orders flow to initiate processing.</span></span> <span data-ttu-id="af2f6-108">開発者は、"PO 受領済み" というアクティビティ マイルストーンが、ソリューションのポートの "PortEndTime" という BizTalk メッセージング プロパティに適切に関連付けられていると判断しました。</span><span class="sxs-lookup"><span data-stu-id="af2f6-108">The developer determines that the activity milestone, called “PO Received,” is most correctly associated with a BizTalk messaging property called “PortEndTime” for the port in the solution.</span></span> <span data-ttu-id="af2f6-109">開発者は、追跡プロファイルを完成するために、アクティビティを読み込み、イベント ソースを選択し、イベント ソースの適切な項目をアクティビティ ツリー定義の対応するノード上にドラッグ アンド ドロップして、必要なマッピングを行います。</span><span class="sxs-lookup"><span data-stu-id="af2f6-109">The developer makes this and any other mappings to complete the tracking profile by loading the activity, selecting event sources, and dragging the appropriate items from the event source and dropping them on the corresponding nodes in the activity tree definition.</span></span>  
  
 <span data-ttu-id="af2f6-110">**プロファイルを作成するための前提条件**</span><span class="sxs-lookup"><span data-stu-id="af2f6-110">**Prerequisites for Creating a Profile**</span></span>  
  
 <span data-ttu-id="af2f6-111">追跡プロファイルを作成するには、次の 2 つの前提条件が満たされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="af2f6-111">There are two prerequisites for creating a tracking profile:</span></span>  
  
1.  <span data-ttu-id="af2f6-112">BAM アクティビティが全体的な監視モデルの一部としてビジネス アナリストによって定義され、システム管理者によって展開されている。</span><span class="sxs-lookup"><span data-stu-id="af2f6-112">A BAM activity has been defined by the business analyst, as part of an overall observation model, and has been deployed by the system administrator.</span></span>  
  
2.  <span data-ttu-id="af2f6-113">BizTalk ソリューション (オーケストレーション、スキーマ、マップ、パイプラインなど) がターゲット環境に正しく展開されている。</span><span class="sxs-lookup"><span data-stu-id="af2f6-113">A BizTalk solution (including orchestrations, schemas, map, and pipelines) has been successfully deployed in the target environment.</span></span>  
  
 <span data-ttu-id="af2f6-114">インストール後にデータベースから取得されるデータは TPE に挿入されないので、これらの前提条件が必要となります。</span><span class="sxs-lookup"><span data-stu-id="af2f6-114">These prerequisites are necessary since after installation the TPE is not populated with any data to retrieve from the databases.</span></span>  
  
 <span data-ttu-id="af2f6-115">**カスタマイズされた BAM ソリューションのプロファイルを作成します。**</span><span class="sxs-lookup"><span data-stu-id="af2f6-115">**Creating a Profile for Customized BAM Solutions**</span></span>  
  
 <span data-ttu-id="af2f6-116">追跡プロファイルを使用できるのは、インターセプターを持つランタイムに関してのみです。</span><span class="sxs-lookup"><span data-stu-id="af2f6-116">Tracking profiles are only relevant to run-times that have an interceptor.</span></span> <span data-ttu-id="af2f6-117">BAM API を使用したカスタム コードから構成される BAM ソリューションの場合は、関連付けられている BAM ランタイム インターセプターがありません。したがって、BAM にデータを送信する方法は、次の 2 つしかありません。</span><span class="sxs-lookup"><span data-stu-id="af2f6-117">For BAM solutions that consist of custom code using the BAM APIs, there is no associated BAM run-time interceptor, and sending data to BAM can be done in only one of two ways:</span></span>  
  
-   <span data-ttu-id="af2f6-118">BAM API を使用して直接送信する。</span><span class="sxs-lookup"><span data-stu-id="af2f6-118">Directly through the BAM APIs.</span></span> <span data-ttu-id="af2f6-119">開発者は、BAM API を使用して、BAM インフラストラクチャにイベント データを明示的に送信できます。</span><span class="sxs-lookup"><span data-stu-id="af2f6-119">Using the APIs developers can explicitly send event data to the BAM infrastructure.</span></span> <span data-ttu-id="af2f6-120">詳細については、BAM Api を使用して、次を参照してください。[イベント ストリームを使用した BAM アクティビティを実装する](../core/implementing-bam-activities-with-event-streams.md)です。</span><span class="sxs-lookup"><span data-stu-id="af2f6-120">For more information about using the BAM APIs, see [Implementing BAM Activities with Event Streams](../core/implementing-bam-activities-with-event-streams.md).</span></span>  
  
-   <span data-ttu-id="af2f6-121">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロパティを介して間接的に送信する。</span><span class="sxs-lookup"><span data-stu-id="af2f6-121">Indirectly, through [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] properties.</span></span> <span data-ttu-id="af2f6-122">カスタム アセンブリを呼び出す際に、関連する傍受テクノロジ (カスタム パイプラインなど) や式/アクション図形が含まれているランタイム コンテキストの内部でカスタム コードを実行している場合は、上記の BAM API か、従来のデータ昇格技法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="af2f6-122">In the case where the custom code is executing inside some run-time context that does have an associated interception technology, such as a custom pipeline - or expression/action shapes in invoking a custom assembly, You can use the BAM APIs as noted above or use traditional data promotion techniques.</span></span> <span data-ttu-id="af2f6-123">プロパティを昇格させて TPE にアクセスできるようにします。これにより、適切なコンテキスト プロパティを使用して、イベント データと BAM アクティビティ項目との関連付けを TPE 内に作成できるようになります。</span><span class="sxs-lookup"><span data-stu-id="af2f6-123">By promoting the properties you make them accessible to the TPE and the association of that event data to a BAM activity item can then be made in the TPE using the correct context property.</span></span> <span data-ttu-id="af2f6-124">プロパティの昇格の詳細については、次を参照してください。[プロパティの昇格](../core/promoting-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="af2f6-124">For more information about promoting properties, see [Promoting Properties](../core/promoting-properties.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="af2f6-125">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="af2f6-125">In This Section</span></span>  
  
-   [<span data-ttu-id="af2f6-126">追跡プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="af2f6-126">Creating Tracking Profiles</span></span>](../core/creating-tracking-profiles.md)  
  
-   [<span data-ttu-id="af2f6-127">孤立した追跡プロファイルを削除する方法</span><span class="sxs-lookup"><span data-stu-id="af2f6-127">How to Remove Orphaned Tracking Profiles</span></span>](../core/how-to-remove-orphaned-tracking-profiles.md)  
  
-   [<span data-ttu-id="af2f6-128">複数の Continuation を使用します。</span><span class="sxs-lookup"><span data-stu-id="af2f6-128">Using Multiple Continuations</span></span>](../core/using-multiple-continuations.md)
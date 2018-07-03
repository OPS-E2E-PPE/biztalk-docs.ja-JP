---
title: 追跡プロファイルについて | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracking profiles, about tracking profiles
- tracking profiles, Tracking Profile Editor
- Tracking Profile Editor, tracking profiles
- tracking profiles
ms.assetid: b579bdc4-7c69-4fa0-bbc1-f98170c13d4f
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9dbcdd4ff93749de5059b80fecfa140e41df422
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977878"
---
# <a name="what-is-a-tracking-profile"></a><span data-ttu-id="5312b-103">追跡プロファイルについて</span><span class="sxs-lookup"><span data-stu-id="5312b-103">What Is a Tracking Profile?</span></span>
<span data-ttu-id="5312b-104">プロファイルとは、ビジネス プロセスを定義する一連の特性です。</span><span class="sxs-lookup"><span data-stu-id="5312b-104">A profile is a set of characteristics that define a business process.</span></span> <span data-ttu-id="5312b-105">追跡プロファイルには、アクティビティからオーケストレーションやポートへの特性のマッピングが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5312b-105">A tracking profile contains the mapping of these characteristics from an activity to orchestrations and ports.</span></span> <span data-ttu-id="5312b-106">追跡プロファイルは、ファイル名拡張子に .btt の付いたファイルです。</span><span class="sxs-lookup"><span data-stu-id="5312b-106">A tracking profile is a file with a .btt file name extension.</span></span>  
  
## <a name="using-tracking-profiles-in-the-tpe"></a><span data-ttu-id="5312b-107">TPE での追跡プロファイルの使用</span><span class="sxs-lookup"><span data-stu-id="5312b-107">Using tracking profiles in the TPE</span></span>  
 <span data-ttu-id="5312b-108">TPE のユーザーは、BAM アクティビティ内の項目とその項目に対応する BizTalk Server ソリューションとの間に、マップ (追跡プロファイル) を作成します。</span><span class="sxs-lookup"><span data-stu-id="5312b-108">Users of the TPE create a map, or tracking profile, between items in a BAM activity and the BizTalk Server solution sources for those items.</span></span> <span data-ttu-id="5312b-109">BAM アクティビティは、マイルストーンやコンテキスト データ ("表示希望リスト") で構成され、追跡プロファイルが従うビジネスの作業単位を定義します。</span><span class="sxs-lookup"><span data-stu-id="5312b-109">BAM activities consist of the milestones and contextual data that make up the "visibility wish-list" and define a unit of work in the business that the tracking profile follows.</span></span> <span data-ttu-id="5312b-110">アクティビティの詳細については、次を参照してください。[イベント ストリームを使用した BAM のアクティビティを実装する](../core/implementing-bam-activities-with-event-streams.md)します。</span><span class="sxs-lookup"><span data-stu-id="5312b-110">For more information about activities, see [Implementing BAM Activities with Event Streams](../core/implementing-bam-activities-with-event-streams.md).</span></span>  
  
 <span data-ttu-id="5312b-111">TPE を使用して追跡プロファイルを作成する場合は、次のオブジェクトを操作します。</span><span class="sxs-lookup"><span data-stu-id="5312b-111">When you create a tracking profile using the TPE, you are working with the following objects:</span></span>  
  
- <span data-ttu-id="5312b-112">BAM アクティビティ</span><span class="sxs-lookup"><span data-stu-id="5312b-112">BAM activities</span></span>  
  
- <span data-ttu-id="5312b-113">展開済みアセンブリの BizTalk オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="5312b-113">BizTalk orchestrations in deployed assemblies</span></span>  
  
- <span data-ttu-id="5312b-114">受信ポートと送信ポート</span><span class="sxs-lookup"><span data-stu-id="5312b-114">Receive and send ports</span></span>  
  
- <span data-ttu-id="5312b-115">展開済みアセンブリのメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="5312b-115">Message schemas in deployed assemblies</span></span>  
  
- <span data-ttu-id="5312b-116">コンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="5312b-116">Context properties</span></span>  
  
- <span data-ttu-id="5312b-117">BAM プライマリ インポート データベース</span><span class="sxs-lookup"><span data-stu-id="5312b-117">BAM Primary Import database</span></span>  
  
- <span data-ttu-id="5312b-118">BizTalk 管理データベース</span><span class="sxs-lookup"><span data-stu-id="5312b-118">BizTalk Management database</span></span>  
  
- <span data-ttu-id="5312b-119">BizTalk 追跡データベース</span><span class="sxs-lookup"><span data-stu-id="5312b-119">BizTalk Tracking database</span></span>  
  
  <span data-ttu-id="5312b-120">オーケストレーションからデータ抽出を定義するには、メッセージ スキーマ、オーケストレーション図形、およびコンテキスト プロパティから、ビジネス マイルストーン (イベント) およびデータ項目フォルダーに項目をドロップします。</span><span class="sxs-lookup"><span data-stu-id="5312b-120">You define the data extraction from an orchestration by dropping items from message schemas, orchestration shapes, and context properties into business milestone (event) and data item folders.</span></span>  
  
  <span data-ttu-id="5312b-121">たとえば、ある BAM アクティビティに "PO 受領済み" というマイルストーンが含まれていて、処理を開始するために注文書が経由するメッセージング ポートがあるとします。</span><span class="sxs-lookup"><span data-stu-id="5312b-121">For example, consider a BAM activity that includes a milestone called PO Received and has a Messaging port through which purchase orders flow to initiate processing.</span></span> <span data-ttu-id="5312b-122">この場合、開発者は `PO Received` マイルストーンを、ソリューションのポートの `PortEndTime` という BizTalk メッセージング プロパティに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="5312b-122">Developers can associate the `PO Received` milestone with a BizTalk Messaging property called `PortEndTime` for the port in their solution.</span></span> <span data-ttu-id="5312b-123">つまり、受信ポートがそのアクションを完了して、`PortEndTime` プロパティを設定した結果として、PO が正しく受信されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="5312b-123">Semantically, this indicates that the PO is successfully received once the receive port concludes its action and populates the `PortEndTime` property.</span></span> <span data-ttu-id="5312b-124">開発者は、このマッピングやその他のマッピングを行い、追跡プロファイルを完成させます。</span><span class="sxs-lookup"><span data-stu-id="5312b-124">The developer makes this and any other mappings to complete the tracking profile.</span></span> <span data-ttu-id="5312b-125">アクティビティ内の項目はすべて、BizTalk Server ソースがあればマップされます。データまたはイベントのソースが、BizTalk Server の実行環境外のプロセスから取得するものである場合は、マップされずに API 呼び出しによって直接設定されます。</span><span class="sxs-lookup"><span data-stu-id="5312b-125">All items in the activity are mapped if they have a BizTalk Server source, or are left unmapped to be populated by API calls directly if the source of the data or event is from a process outside of BizTalk Server’s run-time environment.</span></span>  
  
  <span data-ttu-id="5312b-126">TPE 内の各ペインやビューにはそれぞれ固有の機能がありますが、すべてのビューおよびフォルダーに共通して、情報の検索や操作に役立つナビゲーション機能もあります。</span><span class="sxs-lookup"><span data-stu-id="5312b-126">Although each pane or view in the TPE has a unique function, all the views and folders have similar navigational features to help you find and manipulate information.</span></span>  
  
## <a name="who-uses-tracking-profiles-and-the-tpe"></a><span data-ttu-id="5312b-127">追跡プロファイルと TPE の使用者について</span><span class="sxs-lookup"><span data-stu-id="5312b-127">Who uses tracking profiles and the TPE?</span></span>  
 <span data-ttu-id="5312b-128">企業の統合開発に参加しているユーザーは、追跡プロファイルと TPE を使用して、BizTalk Server イベント ソースを BAM ターゲット アクティビティにマップします。</span><span class="sxs-lookup"><span data-stu-id="5312b-128">Users involved with enterprise integration development use tracking profiles and the TPE to map BizTalk Server event sources to BAM target activities.</span></span> <span data-ttu-id="5312b-129">展開時に、完成した .btt ファイルを IT 実装に渡します。</span><span class="sxs-lookup"><span data-stu-id="5312b-129">The resulting .btt file is handed off to IT Implementation for deployment.</span></span>  
  
 <span data-ttu-id="5312b-130">IT 実装を担当するユーザーは、通常、コマンド ライン ツール (BTTDeploy) を使用して追跡プロファイルを適用します。</span><span class="sxs-lookup"><span data-stu-id="5312b-130">IT Implementation users will typically apply tracking profiles using command-line tools (BTTDeploy).</span></span> <span data-ttu-id="5312b-131">また、直接 TPE を使用して追跡プロファイルを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="5312b-131">The IT user can also use the TPE directly to apply the tracking profile.</span></span>  
  
 <span data-ttu-id="5312b-132">IT 運用を担当するユーザーは、特に、ビジネス要件の変更を受け、(バックアップや復元など、必要なデータベース操作を含めて) スケジュールに基づいて追跡プロファイルを定期的に更新する役割を担う場合があります。</span><span class="sxs-lookup"><span data-stu-id="5312b-132">Users in IT Operations may be responsible for periodic updates to tracking profiles on a scheduled basis (including any database operations required, such as backup and restore), especially as a result of changes in business requirements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5312b-133">参照</span><span class="sxs-lookup"><span data-stu-id="5312b-133">See Also</span></span>  
 [<span data-ttu-id="5312b-134">Xml-data Reduced を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5312b-134">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)
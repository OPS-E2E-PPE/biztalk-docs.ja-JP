---
title: "メッセージ追跡について | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HAT, metadata
- HAT, messages
- messages, tracking
- data, HAT
- metadata, tracking
- tracking, metadata
- HAT, data security
- tracking, messages
- configuring [HAT tracking], messages
- data, security
ms.assetid: 51cec59d-b411-4d8f-b771-7b2cf0f38945
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d76a4bd4133906a7949fac9e63816168506f412
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="what-is-message-tracking"></a><span data-ttu-id="d8c2d-103">メッセージ追跡について</span><span class="sxs-lookup"><span data-stu-id="d8c2d-103">What is Message Tracking?</span></span>
<span data-ttu-id="d8c2d-104">メッセージとは、通常は、実行中のビジネス プロセスやアプリケーション間で交換されるデータの電子的なインスタンスのことです。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-104">A message is an electronic instance of data, as typically exchanged between two running business processes or applications.</span></span> <span data-ttu-id="d8c2d-105">メッセージ インスタンスは、メッセージ本文、メッセージ プロパティ、およびメタデータで構成されています。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-105">A message instance is made up of a message body, message properties, and metadata.</span></span>  
  
 <span data-ttu-id="d8c2d-106">BizTalk Server 管理コンソールを使用すると、メッセージ本文およびメッセージ プロパティの追跡を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-106">You can use the BizTalk Server Administration Console to enable message body and message property tracking.</span></span> <span data-ttu-id="d8c2d-107">このコンソールでは、追跡したメッセージ本文を表示できます。表示内容には、スキーマ情報、厳密な名前、および生成されたメッセージの昇格させたすべてのプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-107">There you can also view the tracked message body, including schema information, strong name, and all the promoted properties for the generated message.</span></span>  
  
## <a name="message-body"></a><span data-ttu-id="d8c2d-108">メッセージ本文</span><span class="sxs-lookup"><span data-stu-id="d8c2d-108">Message Body</span></span>  
 <span data-ttu-id="d8c2d-109">メッセージ本文を追跡すると、送受信されたメッセージの記録が提供されます。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-109">Tracking the message body provides a record of messages sent and received.</span></span> <span data-ttu-id="d8c2d-110">サービス インスタンスの処理が完了したメッセージを保存するには、メッセージ本文の追跡を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-110">You must have message body tracking turned on in order to save messages after service instances processing is complete.</span></span> <span data-ttu-id="d8c2d-111">追跡オプションを設定してから、メッセージを表示できるようになるまでに数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-111">After you have set the tracking options, it can take a few minutes before you can view the messages.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d8c2d-112">すべてのメッセージ ボックス データベースに対して、SQL Server エージェント サービスが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-112">The SQL Server Agent service must be running on all MessageBox databases.</span></span> <span data-ttu-id="d8c2d-113">Trackedmessages_copy _\<MessageBoxName\>ジョブにより、メッセージ本文の追跡クエリおよび WMI を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-113">The TrackedMessages_Copy_\<MessageBoxName\> job makes message bodies available to tracking queries and WMI.</span></span> <span data-ttu-id="d8c2d-114">メッセージ本文を効率的にコピーするには、メッセージ ボックス データベースにし、trackedmessages_copy _ により、BizTalk 追跡 (BizTalkDTADb) データベースを定期的にコピーされる\<MessageBoxName\>ジョブです。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-114">To efficiently copy the message bodies, they remain in the MessageBox database and are periodically copied to the BizTalk Tracking (BizTalkDTADb) database by the TrackedMessages_Copy_\<MessageBoxName\> job.</span></span> <span data-ttu-id="d8c2d-115">SQL Server エージェント サービスを実行していることも、アーカイブおよび削除のプロセスが正しく動作するための前提条件です。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-115">Having the SQL Server Agent service running is also a prerequisite for the archiving and purging process to work correctly.</span></span>  
  
 <span data-ttu-id="d8c2d-116">追跡メッセージを使用して、確認メッセージを提供したり、トラブルシューティングを行ったり、トランザクションの履歴のデータ マイニングを行ったりすることができます。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-116">You can use tracked messages to provide confirmation of receipt, to enable troubleshooting, and to allow data mining of historical transactions.</span></span> <span data-ttu-id="d8c2d-117">メッセージ本文は、ポート、パイプライン、およびオーケストレーションの入出力として追跡できます。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-117">You can track the message bodies at the input and output of ports, pipelines, and orchestrations.</span></span> <span data-ttu-id="d8c2d-118">これらのメッセージは、BizTalk Server 管理コンソール、Operations オブジェクト モデル (OM) (推奨)、または Windows Management Instrumentation (WMI) アプリケーション プログラミング インターフェイス (API) を使用して回復できます。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-118">You can recover these messages using the BizTalk Server Administration Console, using the Operations object model (OM) (recommended) or through Windows Management Instrumentation (WMI) application programming interfaces (APIs).</span></span>  
  
 <span data-ttu-id="d8c2d-119">BizTalk Server では、追跡ポイントを通過できなかったメッセージが追跡されません。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-119">BizTalk Server does not track messages that do not successfully make it through one of the tracking points.</span></span> <span data-ttu-id="d8c2d-120">場合によっては — が有効でないためにメッセージを中断する場合や、ホストがメッセージを指定していないかどうかなど、追跡されているせず保留キューに配置することもします。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-120">In some cases—such as when a message is suspended because it is invalid, or if no host is expecting the message—it may be placed in the Suspended queue without being tracked.</span></span> <span data-ttu-id="d8c2d-121">このようなメッセージを終了した場合、そのメッセージに関する記録は何も残りません。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-121">If you terminate this message there will be no record of it.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d8c2d-122">メッセージ本文の追跡は、法的に拘束力のある監査の代わりになるものではなく、否認不可はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-122">Message body tracking is not a substitute for legally binding auditing, and does not support nonrepudiation.</span></span>  
  
## <a name="message-properties"></a><span data-ttu-id="d8c2d-123">メッセージ プロパティ</span><span class="sxs-lookup"><span data-stu-id="d8c2d-123">Message Properties</span></span>  
 <span data-ttu-id="d8c2d-124">メッセージ プロパティには、昇格されたプロパティ、ルーティング情報、および取引先データが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-124">Message properties include promoted properties, routing information, and trading partner data.</span></span> <span data-ttu-id="d8c2d-125">メッセージ プロパティの追跡を行うと、各メッセージの昇格されたプロパティの記録が結果一覧で提供されるため、追跡している何千ものメッセージから特定のメッセージを探し出すことができます。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-125">Message property tracking enables you to locate a specific message from the thousands that you may have tracked, by providing a record of promoted properties for each message in the results list.</span></span> <span data-ttu-id="d8c2d-126">メッセージを特定したら、これらのプロパティのいずれかを使用してメッセージ自体のサブセットを追跡できます。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-126">You can then track a subset of the message itself, using one of these properties.</span></span>  
  
 <span data-ttu-id="d8c2d-127">コンテキスト プロパティを追跡するには、追跡したプロパティを格納するためのコンテキストで使用される名前空間のプロパティ スキーマを定義します。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-127">To track context properties, you define a property schema for the namespace used in the context to store the properties.</span></span> <span data-ttu-id="d8c2d-128">このビューで、追跡するコンテキスト プロパティを選択できます。BizTalk Server では、選択したコンテキスト プロパティを昇格されたメッセージ プロパティの追跡と同等の方法で追跡します。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-128">From there, you can select the context properties you want to track. BizTalk Server tracks them in the same way it tracks promoted message properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8c2d-129">スキーマに含まれる各プロパティには異なる名前を付けてください。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-129">Make sure you give different names to the properties in the schema.</span></span> <span data-ttu-id="d8c2d-130">重複した名前が存在すると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-130">An error message appears if you create duplicate names.</span></span>  
  
 <span data-ttu-id="d8c2d-131">たとえば、スキーマ エディターを使用して、[PO Number] フィールドを [Purchase Order] スキーマから昇格させることができます。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-131">For example, you could use the Schema Editor to promote the PO Number field from a Purchase Order schema.</span></span> <span data-ttu-id="d8c2d-132">これにより、[メッセージ ビューの検索] を使用し、この追跡フィールドに特定の値 ([PO Number] が 16995 など) を持つメッセージ インスタンスを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-132">Then, using the Find Message View, you could find the message instances that contain a particular value for that tracked field, such as PO Number = 16995.</span></span>  
  
 <span data-ttu-id="d8c2d-133">メッセージ プロパティの追跡では、選択したフィールドのみを追跡するため、メッセージ本文の追跡よりもオーバーヘッドがはるかに少なくて済みます。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-133">Message property tracking creates much less overhead than message body tracking, because message property tracking only tracks the selected fields.</span></span> <span data-ttu-id="d8c2d-134">メッセージ プロパティの追跡オプションを設定してから、プロパティを表示できるようになるまでに数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-134">After you set the tracking options for the message property, it can take a few minutes before you can view the properties.</span></span>  
  
## <a name="metadata"></a><span data-ttu-id="d8c2d-135">メタデータ</span><span class="sxs-lookup"><span data-stu-id="d8c2d-135">Metadata</span></span>  
 <span data-ttu-id="d8c2d-136">メタデータとは、メッセージ インスタンスの識別子、メッセージをログに記録するオーケストレーションやパイプライン、オーケストレーションやパイプラインがメッセージをログに記録した日時、および追跡に関連する他の詳細情報のことです。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-136">Metadata, such as the message instance identifier, the orchestration or pipeline logging the message, the point at which the orchestration or pipeline logs the message, and other relevant tracking details.</span></span> <span data-ttu-id="d8c2d-137">メッセージ ボックス データベースに格納されているメッセージをビジネス プロセスにルーティングするには、そのメッセージにメッセージの種類や送信元などのコンテキスト プロパティが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-137">For a message in the MessageBox database to route to a business process, it must contain context properties such as message type and origin.</span></span> <span data-ttu-id="d8c2d-138">このようなプロパティがメタデータになります。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-138">These properties become metadata.</span></span> <span data-ttu-id="d8c2d-139">メッセージとサービス インスタンスの追跡では、サブスクリプションの条件を使用して、このメタデータに対してクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-139">Message and service instance tracking uses subscription criteria to query against this metadata.</span></span>  
  
 <span data-ttu-id="d8c2d-140">BizTalk Server 管理コンソールを使用して、特定のシステム スキーマを選択することによりコンテキスト プロパティを昇格させることができます。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-140">Through the BizTalk Server Administration Console, you can promote context properties by selecting the particular system schema.</span></span> <span data-ttu-id="d8c2d-141">システム スキーマは、[Applications\BizTalk.System\Schemas] ノードにあります。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-141">The system schemas are located in the Applications\BizTalk.System\Schemas node.</span></span> <span data-ttu-id="d8c2d-142">BizTalk Server がこれらのコンテキスト プロパティをグローバルに追跡、つまり、すべてのメッセージ追跡ようになりました、特定のコンテキスト プロパティです。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-142">BizTalk Server tracks these context properties globally—that is, all messages now track the particular context property.</span></span> <span data-ttu-id="d8c2d-143">そのため、BizTalk 追跡データベースのサイズが大幅に増加することがあります。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-143">This may significantly increase the size of the BizTalk Tracking database.</span></span>  
  
## <a name="sensitive-data"></a><span data-ttu-id="d8c2d-144">機密データ</span><span class="sxs-lookup"><span data-stu-id="d8c2d-144">Sensitive Data</span></span>  
 <span data-ttu-id="d8c2d-145">次のデータを保護することができます。対応するスキーマ プロパティ ウィンドウにデータが表示されないようにすることで、データの追跡を回避します。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-145">You can secure the following data ensuring that it does not appear in corresponding schemas property window and therefore becomes unavailable for tracking.</span></span>  
  
-   <span data-ttu-id="d8c2d-146">適用、 **isSensitive**プロパティ スキーマでは、機密なプロパティを属性の構成の選択の追跡メッセージ プロパティの表示が不要になったようにします。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-146">Apply the **isSensitive** attribute to any sensitive properties in a property schema, so that it is no longer visible in the Message Property tracking configuration selections.</span></span>  
  
-   <span data-ttu-id="d8c2d-147">すべての既定のトランスポートには機密データとして指定されているパスワードが含まれているため、追跡できません。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-147">All out-of-box transports contain passwords marked as sensitive, so the transports cannot be tracked.</span></span>  
  
-   <span data-ttu-id="d8c2d-148">また、機密なプロパティは管理データベースに格納されないため、データベースから直接追跡オプションを構成しても、機密なプロパティを追跡することはできません。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-148">In addition, these sensitive properties are no longer in the Management database, so if you are setting tracking options directly in the database, they are unavailable for tracking.</span></span>  
  
-   <span data-ttu-id="d8c2d-149">有線ネットワークで送信されるメッセージ本文を追跡すると、メッセージ追跡により、追跡されるメッセージ本文のショートカットから、すべてのトランスポートのプロパティが削除されます。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-149">If you track outbound on-the-wire message bodies, message tracking removes all the transport properties from the shortcut of the tracked message body.</span></span> <span data-ttu-id="d8c2d-150">そのため、メッセージ追跡では、追跡されるメッセージ本文のショートカットから送信トランスポートのプロパティを削除するだけでなく、受信トランスポートのプロパティも削除します。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-150">Therefore, in addition to removing outbound transport properties from the shortcut of the tracked message body, message tracking also removes properties from inbound transports.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="d8c2d-151">昇格させたプロパティには、機密データを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-151">A promoted property can contain sensitive data.</span></span> <span data-ttu-id="d8c2d-152">グループ ハブ ページから、追跡クエリが機密性の高いデータを含むプロパティを追跡する場合、追跡クエリを実行するアクセス許可を持つユーザーはこのデータを表示できます。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-152">If tracking queries from the Group Hub page track a property which includes sensitive data, any user with permissions to run the tracking queries can view this data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8c2d-153">参照</span><span class="sxs-lookup"><span data-stu-id="d8c2d-153">See Also</span></span>  
 [<span data-ttu-id="d8c2d-154">BizTalk Server 管理コンソールを使用して追跡を構成します。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-154">Configuring Tracking Using the BizTalk Server Administration Console</span></span>](http://msdn.microsoft.com/en-us/49b7f9d3-60b5-41bd-ba8b-029253926bef)
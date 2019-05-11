---
title: メッセージ追跡について | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e20978905628072269b0acf0990d67dc4582b414
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394032"
---
# <a name="what-is-message-tracking"></a><span data-ttu-id="9f2d9-103">メッセージ追跡について</span><span class="sxs-lookup"><span data-stu-id="9f2d9-103">What is Message Tracking?</span></span>
<span data-ttu-id="9f2d9-104">メッセージは通常 2 つの間で交換されるデータの電子的なインスタンスのビジネス プロセスやアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-104">A message is an electronic instance of data, as typically exchanged between two running business processes or applications.</span></span> <span data-ttu-id="9f2d9-105">メッセージ本文、メッセージのプロパティおよびメタデータのメッセージ インスタンスが構成されます。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-105">A message instance is made up of a message body, message properties, and metadata.</span></span>  
  
 <span data-ttu-id="9f2d9-106">BizTalk Server 管理コンソールを使用して、メッセージ本文とメッセージ プロパティの追跡を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-106">You can use the BizTalk Server Administration Console to enable message body and message property tracking.</span></span> <span data-ttu-id="9f2d9-107">あるスキーマ情報、厳密な名前は、生成されたメッセージのすべての昇格させたプロパティなど、追跡されるメッセージ本文を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-107">There you can also view the tracked message body, including schema information, strong name, and all the promoted properties for the generated message.</span></span>  
  
## <a name="message-body"></a><span data-ttu-id="9f2d9-108">メッセージ本文</span><span class="sxs-lookup"><span data-stu-id="9f2d9-108">Message Body</span></span>  
 <span data-ttu-id="9f2d9-109">メッセージ本文の追跡には、送受信されるメッセージの記録が提供します。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-109">Tracking the message body provides a record of messages sent and received.</span></span> <span data-ttu-id="9f2d9-110">本文の追跡サービス インスタンスの処理後にメッセージを保存するにはオンになってが完了したメッセージが必要です。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-110">You must have message body tracking turned on in order to save messages after service instances processing is complete.</span></span> <span data-ttu-id="9f2d9-111">追跡オプションを設定した後は、メッセージを表示する前に数分かかります。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-111">After you have set the tracking options, it can take a few minutes before you can view the messages.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9f2d9-112">すべてのメッセージ ボックス データベースでは、SQL Server エージェント サービスを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-112">The SQL Server Agent service must be running on all MessageBox databases.</span></span> <span data-ttu-id="9f2d9-113">Trackedmessages_copy _\<MessageBoxName\>ジョブにより、メッセージ本文の追跡クエリおよび WMI を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-113">The TrackedMessages_Copy_\<MessageBoxName\> job makes message bodies available to tracking queries and WMI.</span></span> <span data-ttu-id="9f2d9-114">メッセージ本文を効率的にコピーするには、メッセージ ボックス データベースに保持し、trackedmessages_copy _ では、BizTalk 追跡 (BizTalkDTADb) データベースに定期的にコピーが\<MessageBoxName\>ジョブ。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-114">To efficiently copy the message bodies, they remain in the MessageBox database and are periodically copied to the BizTalk Tracking (BizTalkDTADb) database by the TrackedMessages_Copy_\<MessageBoxName\> job.</span></span> <span data-ttu-id="9f2d9-115">SQL Server エージェント サービスが実行されていることが正常に動作する、アーカイブおよび削除のプロセスの前提条件もです。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-115">Having the SQL Server Agent service running is also a prerequisite for the archiving and purging process to work correctly.</span></span>  
  
 <span data-ttu-id="9f2d9-116">追跡メッセージを使用して、トラブルシューティングするには、有効にすると、トランザクションの履歴のデータ マイニングを行ったり、受信確認を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-116">You can use tracked messages to provide confirmation of receipt, to enable troubleshooting, and to allow data mining of historical transactions.</span></span> <span data-ttu-id="9f2d9-117">入力と出力のポート、パイプライン、およびオーケストレーションでメッセージ本文を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-117">You can track the message bodies at the input and output of ports, pipelines, and orchestrations.</span></span> <span data-ttu-id="9f2d9-118">Windows Management Instrumentation (WMI) を介してアプリケーション プログラミング インターフェイス (Api) または (推奨) Operations オブジェクト モデル (OM) を使用して、BizTalk Server 管理コンソールを使用してこれらのメッセージを回復できます。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-118">You can recover these messages using the BizTalk Server Administration Console, using the Operations object model (OM) (recommended) or through Windows Management Instrumentation (WMI) application programming interfaces (APIs).</span></span>  
  
 <span data-ttu-id="9f2d9-119">BizTalk Server では、正常に、それはない追跡ポイントのいずれかでメッセージを追跡しません。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-119">BizTalk Server does not track messages that do not successfully make it through one of the tracking points.</span></span> <span data-ttu-id="9f2d9-120">場合によってが有効でないために、メッセージが中断されたときや、ホストがメッセージを指定していないかどうかなど、追跡されているせず保留キューに配置する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-120">In some cases—such as when a message is suspended because it is invalid, or if no host is expecting the message—it may be placed in the Suspended queue without being tracked.</span></span> <span data-ttu-id="9f2d9-121">このメッセージを終了する場合は書き留めてことはありません。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-121">If you terminate this message there will be no record of it.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9f2d9-122">メッセージ本文の追跡では、監査、法的拘束に代わるものでないし、否認防止をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-122">Message body tracking is not a substitute for legally binding auditing, and does not support nonrepudiation.</span></span>  
  
## <a name="message-properties"></a><span data-ttu-id="9f2d9-123">メッセージのプロパティ</span><span class="sxs-lookup"><span data-stu-id="9f2d9-123">Message Properties</span></span>  
 <span data-ttu-id="9f2d9-124">メッセージ プロパティには、昇格させたプロパティ、ルーティング情報、およびパートナーのデータを取引先が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-124">Message properties include promoted properties, routing information, and trading partner data.</span></span> <span data-ttu-id="9f2d9-125">メッセージ プロパティの追跡を使用することがありますが、によって追跡結果リスト内の各メッセージの昇格させたプロパティの記録を提供する何千もの特定のメッセージを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-125">Message property tracking enables you to locate a specific message from the thousands that you may have tracked, by providing a record of promoted properties for each message in the results list.</span></span> <span data-ttu-id="9f2d9-126">追跡しは、メッセージのサブセットを使用してこれらのプロパティのいずれか。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-126">You can then track a subset of the message itself, using one of these properties.</span></span>  
  
 <span data-ttu-id="9f2d9-127">コンテキストのプロパティを追跡するには、プロパティを格納するコンテキストで使用する名前空間のプロパティ スキーマを定義します。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-127">To track context properties, you define a property schema for the namespace used in the context to store the properties.</span></span> <span data-ttu-id="9f2d9-128">そこから、追跡するコンテキスト プロパティを選択できます。BizTalk Server では、昇格させたメッセージ プロパティを追跡する同じ方法でそれらを追跡します。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-128">From there, you can select the context properties you want to track. BizTalk Server tracks them in the same way it tracks promoted message properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9f2d9-129">スキーマのプロパティに別の名前を付けることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-129">Make sure you give different names to the properties in the schema.</span></span> <span data-ttu-id="9f2d9-130">重複する名前を作成する場合、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-130">An error message appears if you create duplicate names.</span></span>  
  
 <span data-ttu-id="9f2d9-131">たとえば、注文書スキーマから PO 番号フィールドを昇格させるスキーマ エディターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-131">For example, you could use the Schema Editor to promote the PO Number field from a Purchase Order schema.</span></span> <span data-ttu-id="9f2d9-132">次に、メッセージの検索ビューを使用して検索できます追跡フィールドに PO 番号などの特定の値が含まれているメッセージ インスタンス 16995 します。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-132">Then, using the Find Message View, you could find the message instances that contain a particular value for that tracked field, such as PO Number = 16995.</span></span>  
  
 <span data-ttu-id="9f2d9-133">メッセージ プロパティの追跡は、メッセージ プロパティの追跡のみが選択したフィールドは追跡するために、メッセージ本文の追跡よりもはるかに少ないオーバーヘッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-133">Message property tracking creates much less overhead than message body tracking, because message property tracking only tracks the selected fields.</span></span> <span data-ttu-id="9f2d9-134">メッセージ プロパティの追跡オプションを設定した後は、プロパティを表示する前に数分かかります。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-134">After you set the tracking options for the message property, it can take a few minutes before you can view the properties.</span></span>  
  
## <a name="metadata"></a><span data-ttu-id="9f2d9-135">メタデータ</span><span class="sxs-lookup"><span data-stu-id="9f2d9-135">Metadata</span></span>  
 <span data-ttu-id="9f2d9-136">メッセージ インスタンス識別子、オーケストレーションまたはパイプラインがオーケストレーションまたはパイプライン ログ メッセージ、およびその他の追跡に関連する詳細ポイント、メッセージをログ記録などのメタデータ。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-136">Metadata, such as the message instance identifier, the orchestration or pipeline logging the message, the point at which the orchestration or pipeline logs the message, and other relevant tracking details.</span></span> <span data-ttu-id="9f2d9-137">ビジネス プロセスにルーティングするメッセージ ボックス データベース内のメッセージには、メッセージの種類や送信元などのコンテキスト プロパティを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-137">For a message in the MessageBox database to route to a business process, it must contain context properties such as message type and origin.</span></span> <span data-ttu-id="9f2d9-138">これらのプロパティでは、メタデータになります。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-138">These properties become metadata.</span></span> <span data-ttu-id="9f2d9-139">メッセージとサービス インスタンスの追跡では、配信登録の条件を使用して、このメタデータに対してクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-139">Message and service instance tracking uses subscription criteria to query against this metadata.</span></span>  
  
 <span data-ttu-id="9f2d9-140">BizTalk Server 管理コンソールを通じて、特定のシステム スキーマを選択して、コンテキスト プロパティを昇格できます。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-140">Through the BizTalk Server Administration Console, you can promote context properties by selecting the particular system schema.</span></span> <span data-ttu-id="9f2d9-141">すべてのシステム スキーマ Applications\BizTalk.System\Schemas ノードに配置されます。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-141">The system schemas are located in the Applications\BizTalk.System\Schemas node.</span></span> <span data-ttu-id="9f2d9-142">BizTalk Server がこれらのコンテキスト プロパティをグローバルに追跡します-今すぐのすべてのメッセージ、特定のコンテキスト プロパティの追跡は、します。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-142">BizTalk Server tracks these context properties globally—that is, all messages now track the particular context property.</span></span> <span data-ttu-id="9f2d9-143">これにより、BizTalk 追跡データベースのサイズが大幅に増加します。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-143">This may significantly increase the size of the BizTalk Tracking database.</span></span>  
  
## <a name="sensitive-data"></a><span data-ttu-id="9f2d9-144">機密データ</span><span class="sxs-lookup"><span data-stu-id="9f2d9-144">Sensitive Data</span></span>  
 <span data-ttu-id="9f2d9-145">対応するスキーマのプロパティ ウィンドウでは表示されずがそのため、追跡のために使用できなくなったことを確認する次のデータをセキュリティで保護することができます。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-145">You can secure the following data ensuring that it does not appear in corresponding schemas property window and therefore becomes unavailable for tracking.</span></span>  
  
-   <span data-ttu-id="9f2d9-146">適用、 **isSensitive**属性プロパティ スキーマでは、機密なプロパティが不要になったメッセージ プロパティの構成の選択内容の追跡で表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-146">Apply the **isSensitive** attribute to any sensitive properties in a property schema, so that it is no longer visible in the Message Property tracking configuration selections.</span></span>  
  
-   <span data-ttu-id="9f2d9-147">すべての既定のトランスポートには、トランスポートを追跡することはできませんので、機密性の高い、指定されているパスワードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-147">All out-of-box transports contain passwords marked as sensitive, so the transports cannot be tracked.</span></span>  
  
-   <span data-ttu-id="9f2d9-148">さらに、これらの機密性の高いプロパティはで、管理データベースのため、追跡に使用できる追跡データベースで直接オプションを設定する場合はありません。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-148">In addition, these sensitive properties are no longer in the Management database, so if you are setting tracking options directly in the database, they are unavailable for tracking.</span></span>  
  
-   <span data-ttu-id="9f2d9-149">送信の送信中にメッセージ本文を追跡する場合、メッセージ追跡は追跡メッセージ本文のショートカットからすべてのトランスポートのプロパティを削除します。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-149">If you track outbound on-the-wire message bodies, message tracking removes all the transport properties from the shortcut of the tracked message body.</span></span> <span data-ttu-id="9f2d9-150">そのため、追跡メッセージ本文のショートカットから送信トランスポートのプロパティを削除、だけでなくメッセージの追跡プロパティも削除します受信トランスポート。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-150">Therefore, in addition to removing outbound transport properties from the shortcut of the tracked message body, message tracking also removes properties from inbound transports.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="9f2d9-151">昇格させたプロパティは、機密データを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-151">A promoted property can contain sensitive data.</span></span> <span data-ttu-id="9f2d9-152">グループ ハブ ページから、追跡クエリは、機密データを含むプロパティを追跡、追跡クエリを実行するアクセス許可を持つすべてのユーザーはこのデータを表示できます。</span><span class="sxs-lookup"><span data-stu-id="9f2d9-152">If tracking queries from the Group Hub page track a property which includes sensitive data, any user with permissions to run the tracking queries can view this data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f2d9-153">参照</span><span class="sxs-lookup"><span data-stu-id="9f2d9-153">See Also</span></span>  
 [<span data-ttu-id="9f2d9-154">BizTalk Server 管理コンソールの使用の追跡の構成</span><span class="sxs-lookup"><span data-stu-id="9f2d9-154">Configuring Tracking Using the BizTalk Server Administration Console</span></span>](http://msdn.microsoft.com/49b7f9d3-60b5-41bd-ba8b-029253926bef)

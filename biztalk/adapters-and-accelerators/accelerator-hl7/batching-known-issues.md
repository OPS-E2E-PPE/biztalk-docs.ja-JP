---
title: 既知の問題をバッチ処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, known issues
- known issues, batching
ms.assetid: 25c645eb-845d-483a-8f77-398e7dfe0c8f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b47246662c5945f8ef09040ec7a8aa49326f59db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204498"
---
# <a name="batching-known-issues"></a><span data-ttu-id="b2614-102">バッチ処理に関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="b2614-102">Batching Known Issues</span></span>
<span data-ttu-id="b2614-103">このセクションには、バッチ処理のエラーを回避するために役立つ有用な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b2614-103">This section contains useful information that may help you avoid batching errors.</span></span>  
  
## <a name="batch-trailer-segment-fts-and-bts-fields-are-accepted-even-if-they-are-strings"></a><span data-ttu-id="b2614-104">文字列にある場合でも、バッチ トレーラー セグメント (FTS および BTS) フィールドが受け入れられます</span><span class="sxs-lookup"><span data-stu-id="b2614-104">Batch trailer segment (FTS and BTS) fields are accepted even if they are strings</span></span>  
 <span data-ttu-id="b2614-105">HL7 は、HL7 のさまざまなバージョンの異なる方法で FTS および BTS セグメント内のフィールドを指定します。</span><span class="sxs-lookup"><span data-stu-id="b2614-105">HL7 specifies the fields in FTS and BTS segments differently in the various versions of HL7.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="b2614-106">として文字列データ型の不整合を回避するには、すべてのフィールドを定義します。</span><span class="sxs-lookup"><span data-stu-id="b2614-106"> defines all of the fields as String data type to avoid inconsistency.</span></span>  
  
## <a name="data-type-of-an-ack-to-a-batch-message"></a><span data-ttu-id="b2614-107">バッチ メッセージに ACK のデータ型</span><span class="sxs-lookup"><span data-stu-id="b2614-107">Data type of an ACK to a batch message</span></span>  
 <span data-ttu-id="b2614-108">バッチ メッセージを送信元パーティの断片化がオフの場合、MSH10 への応答で生成された確認 (ACK) メッセージには、フィールド (メッセージ コントロール ID) はバッチ メッセージの MSH10 フィールドの他の任意のデータ型ではなく、GUID になります。</span><span class="sxs-lookup"><span data-stu-id="b2614-108">In an acknowledgment (ACK) message generated in response to a batch message, if fragmentation for source party is turned off, then the MSH10 field (message control ID) will be a GUID, rather than any other data type of the MSH10 field in the batch message.</span></span>  
  
## <a name="btahl7-configuration-explorer-and-create-batch-orchestrations-are-not-two-way-synchronized"></a><span data-ttu-id="b2614-109">BTAHL7 構成エクスプ ローラーとバッチの作成のオーケストレーションが双方向ではない同期</span><span class="sxs-lookup"><span data-stu-id="b2614-109">BTAHL7 Configuration Explorer and Create Batch orchestrations are not two-way synchronized</span></span>  
 <span data-ttu-id="b2614-110">F5 キーを押した場合でも、バッチ コントロール スケジュールの現在の状態を表示できない可能性がある[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーで、両方を確認する必要がありますと[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]現在の構成のエクスプ ローラーおよび状態と動作状況の追跡 (HAT) ツールバッチ コントロール スケジュールの状態です。</span><span class="sxs-lookup"><span data-stu-id="b2614-110">You may not able to view the current status of the batch control schedule even if you press F5 in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer, and may have to check both [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer and the Health and Activity Tracking (HAT) tool for the current status of the batch control schedule.</span></span>  
  
## <a name="two-parsing-errors-logged-when-messages-in-batch-inbatch-out-scenario-contain-validation-errors"></a><span data-ttu-id="b2614-111">ときに 2 つの解析エラーのログ記録のメッセージでバッチ/バッチをシナリオに検証エラーを含める</span><span class="sxs-lookup"><span data-stu-id="b2614-111">Two parsing errors logged when messages in Batch In/Batch Out scenario contain validation errors</span></span>  
 <span data-ttu-id="b2614-112">バッチ内の最初のメッセージのバッチをシナリオ (複数のメッセージがバッチ ヘッダーのないバッチ) には、検証エラーが含まれています/[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]イベント ログに 2 つのエラーをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="b2614-112">When the first message in the Batch In/Batch Out scenario (multiple messages batched without batch headers) contains validation errors, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] logs two errors in the Event Log.</span></span> <span data-ttu-id="b2614-113">最初のエラーが、バッチの最初のメッセージに関連し、メッセージの残りの部分に関連する 2 番目のエラーです。</span><span class="sxs-lookup"><span data-stu-id="b2614-113">The first error pertains to the first message in the batch, and the second error pertains to the remainder of the messages.</span></span>  
  
## <a name="subscription-using-the-btsmessagetype-property-for-the-batch-inbatch-out-scenario-with-fragmentation-disabled-is-not-supported"></a><span data-ttu-id="b2614-114">サブスクリプションは、BTS を使用します。バッチの MessageType プロパティで無効になっている断片化のバッチをシナリオがサポートされていません</span><span class="sxs-lookup"><span data-stu-id="b2614-114">Subscription using the BTS.MessageType property for the Batch In/Batch Out scenario with fragmentation disabled is not supported</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="b2614-115">使用してサブスクリプションをサポートしていません、 **BTS です。MessageType**バッチのプロパティで複数のメッセージ型から構成されるインターチェンジとして無効になっている断片化とシナリオをバッチ/です。</span><span class="sxs-lookup"><span data-stu-id="b2614-115"> does not support subscription using the **BTS.MessageType** property for the Batch In/Batch Out scenario with fragmentation disabled as an interchange that may consist of multiple message types.</span></span>  
  
## <a name="entire-batch-suspended-after-erroneous-message-in-the-batch-inbatch-out-scenario"></a><span data-ttu-id="b2614-116">バッチ内のエラー メッセージの後に中断されているバッチ全体のシナリオをバッチ処理/</span><span class="sxs-lookup"><span data-stu-id="b2614-116">Entire batch suspended after erroneous message in the Batch In/Batch Out scenario</span></span>  
 <span data-ttu-id="b2614-117">場合、致命的なパーサー エラーがメッセージ (たとえば、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] MSH 9、または読み込めませんでしたメッセージのスキーマを MSH 12 または本文を解析しません) が断片化されるバッチ内で発生したでバッチ アウト シナリオでは、すべてのデータは、エラー メッセージが中断された後でも/場合、。回復可能なインターチェンジのサポートが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="b2614-117">If a message with fatal parser errors (for example, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does not parse MSH 9 or MSH 12 or body schema for the message failed to load) is encountered in a fragmented Batch In/Batch Out scenario, any data after the erroneous message is suspended even if the recoverable interchange support has been enabled.</span></span>  
  
## <a name="batch-of-acks-get-routed-to-the-source-party-of-the-first-message-in-batch-inbatch-out-scenario"></a><span data-ttu-id="b2614-118">Ack のバッチのバッチの最初のメッセージの送信元パーティにルーティングのシナリオをバッチ処理/</span><span class="sxs-lookup"><span data-stu-id="b2614-118">Batch of Acks get routed to the source party of the first message in Batch In/Batch Out Scenario</span></span>  
 <span data-ttu-id="b2614-119">内でバッチ/Ack のシナリオ バッチのバッチを取得、最初のメッセージのソース パーティ情報に基づくのでルーティング受信内のすべてのメッセージ バッチのソースと変換先のパーティが同じにすると、この機能プログラムがあると想定します。</span><span class="sxs-lookup"><span data-stu-id="b2614-119">In Batch In/ Batch Out scenario batch of Acks get routed based on the source party information of the first message, because this functionality assume that for all the messages in inbound batch the source and destination parties are same.</span></span>  
  
## <a name="batch-of-acks-does-not-get-routed-to-the-source-party-when-two-way-receive-port-is-used-in-batch-in-batch-out-scenario"></a><span data-ttu-id="b2614-120">Ack のバッチと双方向の送信元パーティにルーティングされませんは受信ポートはバッチで使用のシナリオをバッチ処理/</span><span class="sxs-lookup"><span data-stu-id="b2614-120">Batch of Acks does not get routed to the source party when two-way receive port is used in Batch In/ Batch Out scenario</span></span>  
 <span data-ttu-id="b2614-121">要求-応答が発生した場合の受信ポート、ACK または NACK バッチは BIBO シナリオの送信元パーティにルーティングされません。</span><span class="sxs-lookup"><span data-stu-id="b2614-121">In case of request-response receive port the ACK/NACK batch does not get routed to the source party for BIBO scenario.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2614-122">参照</span><span class="sxs-lookup"><span data-stu-id="b2614-122">See Also</span></span>  
 [<span data-ttu-id="b2614-123">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b2614-123">Known Issues</span></span>](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)
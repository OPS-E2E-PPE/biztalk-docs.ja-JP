---
title: 既知の問題をバッチ処理 |Microsoft Docs
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
ms.openlocfilehash: ae2c9fb3abf43d7eb62c0c78d03c30a33b45995c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251800"
---
# <a name="batching-known-issues"></a><span data-ttu-id="41441-102">バッチ処理に関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="41441-102">Batching Known Issues</span></span>
<span data-ttu-id="41441-103">このセクションには、エラーをバッチ処理を回避するために役立つ有用な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="41441-103">This section contains useful information that may help you avoid batching errors.</span></span>  
  
## <a name="batch-trailer-segment-fts-and-bts-fields-are-accepted-even-if-they-are-strings"></a><span data-ttu-id="41441-104">文字列にある場合でも、バッチ トレーラー セグメント (FTS および BTS) フィールドが受け入れられます</span><span class="sxs-lookup"><span data-stu-id="41441-104">Batch trailer segment (FTS and BTS) fields are accepted even if they are strings</span></span>  
 <span data-ttu-id="41441-105">HL7 の HL7 のさまざまなバージョンの異なる方法で FTS および BTS のセグメントが、フィールドを指定します。</span><span class="sxs-lookup"><span data-stu-id="41441-105">HL7 specifies the fields in FTS and BTS segments differently in the various versions of HL7.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="41441-106">不整合を回避するために文字列データ型としては、すべてのフィールドを定義します。</span><span class="sxs-lookup"><span data-stu-id="41441-106">defines all of the fields as String data type to avoid inconsistency.</span></span>  
  
## <a name="data-type-of-an-ack-to-a-batch-message"></a><span data-ttu-id="41441-107">ACK をバッチ メッセージのデータ型</span><span class="sxs-lookup"><span data-stu-id="41441-107">Data type of an ACK to a batch message</span></span>  
 <span data-ttu-id="41441-108">フィールド (メッセージのコントロール ID)、受信確認 (ACK) メッセージのバッチ メッセージには、送信元パーティの断片化がオフの場合、その後、MSH10 への応答で生成されたバッチ メッセージの MSH10 フィールドの他の任意のデータ型ではなく、GUID になります。</span><span class="sxs-lookup"><span data-stu-id="41441-108">In an acknowledgment (ACK) message generated in response to a batch message, if fragmentation for source party is turned off, then the MSH10 field (message control ID) will be a GUID, rather than any other data type of the MSH10 field in the batch message.</span></span>  
  
## <a name="btahl7-configuration-explorer-and-create-batch-orchestrations-are-not-two-way-synchronized"></a><span data-ttu-id="41441-109">BTAHL7 構成エクスプ ローラーと作成のバッチ オーケストレーションは双方向同期</span><span class="sxs-lookup"><span data-stu-id="41441-109">BTAHL7 Configuration Explorer and Create Batch orchestrations are not two-way synchronized</span></span>  
 <span data-ttu-id="41441-110">F5 キーを押す場合でも、バッチのコントロールのスケジュールの現在の状態を表示することができない可能性がある[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーで、両方をチェックする必要がありますと[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーと、状態と動作状況の追跡 (HAT) ツールで、現在のバッチのコントロールのスケジュールの状態です。</span><span class="sxs-lookup"><span data-stu-id="41441-110">You may not able to view the current status of the batch control schedule even if you press F5 in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer, and may have to check both [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer and the Health and Activity Tracking (HAT) tool for the current status of the batch control schedule.</span></span>  
  
## <a name="two-parsing-errors-logged-when-messages-in-batch-inbatch-out-scenario-contain-validation-errors"></a><span data-ttu-id="41441-111">ときに 2 つの解析エラーのログ記録のメッセージのバッチ処理/バッチ アウト シナリオは、検証エラーを含めることが</span><span class="sxs-lookup"><span data-stu-id="41441-111">Two parsing errors logged when messages in Batch In/Batch Out scenario contain validation errors</span></span>  
 <span data-ttu-id="41441-112">バッチ内の最初のメッセージで/バッチ アウト シナリオ (複数のメッセージがバッチ ヘッダーのないバッチ) には、検証エラーが含まれています。[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]イベント ログに 2 つのエラー ログに記録します。</span><span class="sxs-lookup"><span data-stu-id="41441-112">When the first message in the Batch In/Batch Out scenario (multiple messages batched without batch headers) contains validation errors, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] logs two errors in the Event Log.</span></span> <span data-ttu-id="41441-113">最初のエラーが、バッチの最初のメッセージに関連し、2 番目のエラーに関連するメッセージの残りの部分。</span><span class="sxs-lookup"><span data-stu-id="41441-113">The first error pertains to the first message in the batch, and the second error pertains to the remainder of the messages.</span></span>  
  
## <a name="subscription-using-the-btsmessagetype-property-for-the-batch-inbatch-out-scenario-with-fragmentation-disabled-is-not-supported"></a><span data-ttu-id="41441-114">サブスクリプションは、BTS を使用します。バッチの MessageType プロパティで無効になっている断片化とバッチ アウト シナリオはサポートされていません</span><span class="sxs-lookup"><span data-stu-id="41441-114">Subscription using the BTS.MessageType property for the Batch In/Batch Out scenario with fragmentation disabled is not supported</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="41441-115">使用してサブスクリプションをサポートしていません、 **BTS します。MessageType**バッチのプロパティで/バッチ アウト シナリオと複数のメッセージの種類で構成されるインターチェンジとしては無効に断片化が発生します。</span><span class="sxs-lookup"><span data-stu-id="41441-115">does not support subscription using the **BTS.MessageType** property for the Batch In/Batch Out scenario with fragmentation disabled as an interchange that may consist of multiple message types.</span></span>  
  
## <a name="entire-batch-suspended-after-erroneous-message-in-the-batch-inbatch-out-scenario"></a><span data-ttu-id="41441-116">バッチ内のエラーのあるメッセージの後に中断されたバッチ全体で/バッチ アウト シナリオ</span><span class="sxs-lookup"><span data-stu-id="41441-116">Entire batch suspended after erroneous message in the Batch In/Batch Out scenario</span></span>  
 <span data-ttu-id="41441-117">致命的なパーサー エラーのあるメッセージの場合 (たとえば、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] MSH 9 または読み込みに失敗したメッセージのスキーマを MSH 12 または本文を解析しません) が断片化したバッチで発生したで/バッチ アウト シナリオ、エラー メッセージが中断された後、すべてのデータも場合、回復可能なインターチェンジのサポートが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="41441-117">If a message with fatal parser errors (for example, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does not parse MSH 9 or MSH 12 or body schema for the message failed to load) is encountered in a fragmented Batch In/Batch Out scenario, any data after the erroneous message is suspended even if the recoverable interchange support has been enabled.</span></span>  
  
## <a name="batch-of-acks-get-routed-to-the-source-party-of-the-first-message-in-batch-inbatch-out-scenario"></a><span data-ttu-id="41441-118">バッチの最初のメッセージの送信元パーティにルーティングされる Ack のバッチで/バッチ アウト シナリオ</span><span class="sxs-lookup"><span data-stu-id="41441-118">Batch of Acks get routed to the source party of the first message in Batch In/Batch Out Scenario</span></span>  
 <span data-ttu-id="41441-119">内でバッチ処理/バッチ アウト シナリオ バッチ Ack のルーティング、最初のメッセージのソースのパーティ情報に基づいて受信ですべてのメッセージ バッチのソースおよび変換先のパーティが同じにするこの機能仮定できないためです。</span><span class="sxs-lookup"><span data-stu-id="41441-119">In Batch In/ Batch Out scenario batch of Acks get routed based on the source party information of the first message, because this functionality assume that for all the messages in inbound batch the source and destination parties are same.</span></span>  
  
## <a name="batch-of-acks-does-not-get-routed-to-the-source-party-when-two-way-receive-port-is-used-in-batch-in-batch-out-scenario"></a><span data-ttu-id="41441-120">Ack のバッチと双方向の送信元パーティにルーティングされませんは受信ポートはバッチで使用で/バッチ アウト シナリオ</span><span class="sxs-lookup"><span data-stu-id="41441-120">Batch of Acks does not get routed to the source party when two-way receive port is used in Batch In/ Batch Out scenario</span></span>  
 <span data-ttu-id="41441-121">要求-応答が発生した場合の受信ポート、ACK または NACK バッチは BIBO シナリオでは、ソース パーティにルーティングされません。</span><span class="sxs-lookup"><span data-stu-id="41441-121">In case of request-response receive port the ACK/NACK batch does not get routed to the source party for BIBO scenario.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41441-122">参照</span><span class="sxs-lookup"><span data-stu-id="41441-122">See Also</span></span>  
 [<span data-ttu-id="41441-123">既知の問題</span><span class="sxs-lookup"><span data-stu-id="41441-123">Known Issues</span></span>](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)
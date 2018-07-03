---
title: ACK メッセージ モード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message modes, ACK messages
- messages, acknowledgements
- acknowledgements, message modes
- ACK message modes
ms.assetid: ab4a9470-dab2-46d4-8d0a-54dc12f2fa90
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 181617a41ba892a8ac04f2bf2154bbe78e8c892e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967857"
---
# <a name="ack-message-modes"></a><span data-ttu-id="993e7-102">ACK メッセージ モード</span><span class="sxs-lookup"><span data-stu-id="993e7-102">ACK Message Modes</span></span>
<span data-ttu-id="993e7-103">確認 (ACK) メッセージ、Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 受信確認モードおよび生成する ACK の MSH15 および MSH16 フィールドを設定するために使用する値を決定します。</span><span class="sxs-lookup"><span data-stu-id="993e7-103">For acknowledgment (ACK) messages, Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) determines the acknowledgment mode and values to use for populating MSH15 and MSH16 fields of the ACK you want to generate.</span></span> <span data-ttu-id="993e7-104">これらの値は、取引先管理 (TPM) の構成に存在します。</span><span class="sxs-lookup"><span data-stu-id="993e7-104">These values are present in the Trading Partner Management (TPM) configuration.</span></span> <span data-ttu-id="993e7-105">次の値は ACK モードのことです。</span><span class="sxs-lookup"><span data-stu-id="993e7-105">The following values are possible for ACK mode:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="993e7-106">次の一覧で、HL7 仕様には、1 ~ 3 のアイテムと MSH15 と MSH16 の値が含まれていることが定められています。</span><span class="sxs-lookup"><span data-stu-id="993e7-106">In the following list, the HL7 specification mandates items 1 through 3 and that they contain MSH15 and MSH16 values.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="993e7-107"> 受信確認を生成しないことを示すために 4 項目を定義します。</span><span class="sxs-lookup"><span data-stu-id="993e7-107"> defines item 4 to signify that an acknowledgment should not be generated.</span></span>  
  
1. <span data-ttu-id="993e7-108">元のヘッダーと本文の検証後に送信された 1 つ確認します。</span><span class="sxs-lookup"><span data-stu-id="993e7-108">Original - One ACK sent after validating the header and body.</span></span> <span data-ttu-id="993e7-109">このモードには、スキーマの検証が含まれます。</span><span class="sxs-lookup"><span data-stu-id="993e7-109">This mode involves schema validation.</span></span>  
  
2. <span data-ttu-id="993e7-110">拡張 - 2 つの ACK メッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="993e7-110">Enhanced - Two ACK messages sent:</span></span>  
  
   -   <span data-ttu-id="993e7-111">ACK – を受け入れ、受信側システム ヘッダーの検証後にこの種類の確認を送信します。</span><span class="sxs-lookup"><span data-stu-id="993e7-111">Accept ACK – The receiving system sends this type of ACK after validation of the header.</span></span> <span data-ttu-id="993e7-112">この確認は、メッセージがデータベースにコミットである、発信側アプリケーションに通知します。</span><span class="sxs-lookup"><span data-stu-id="993e7-112">This ACK signals to the initiating application that the message is committed to the database.</span></span>  
  
   -   <span data-ttu-id="993e7-113">アプリケーション ACK が受信側システムでは、ヘッダーおよび本文を含む、完全なメッセージの検証後にこの種類の確認を送信します。</span><span class="sxs-lookup"><span data-stu-id="993e7-113">Application ACK- The receiving system sends this type of ACK after complete message validation, including the header and the body.</span></span>  
  
3. <span data-ttu-id="993e7-114">遅延された - 2 つの ACK メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="993e7-114">Deferred - Two ACK messages sent.</span></span>  
  
   - <span data-ttu-id="993e7-115">元のモード: ヘッダーと本文の検証後に、この種類の確認が受信側のシステムに送信します。</span><span class="sxs-lookup"><span data-stu-id="993e7-115">Original Mode: The receiving system sends this type of ACK after validation of the header and body.</span></span> <span data-ttu-id="993e7-116">このモードには、スキーマの検証が含まれます。</span><span class="sxs-lookup"><span data-stu-id="993e7-116">This mode involves schema validation.</span></span>  
  
   - <span data-ttu-id="993e7-117">遅延モード: 基幹業務アプリケーションは、処理した後、メッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="993e7-117">Deferred Mode: The line-of-business application acknowledges the message after processing it.</span></span> <span data-ttu-id="993e7-118">アプリケーションに遅延メッセージを配信する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、スタンドアロンのメッセージとして処理することと、変換先に配信します。</span><span class="sxs-lookup"><span data-stu-id="993e7-118">The application delivers the deferred message to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], which process it as a stand-alone message and delivers it to the destination.</span></span>  
  
4. <span data-ttu-id="993e7-119">静的 - 成功した場合にまたはエラー発生時の確認を送信します。</span><span class="sxs-lookup"><span data-stu-id="993e7-119">Static - An on success or on failure ACK sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="993e7-120">参照</span><span class="sxs-lookup"><span data-stu-id="993e7-120">See Also</span></span>  
 <span data-ttu-id="993e7-121">[作成して、受信確認の処理](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="993e7-121">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 <span data-ttu-id="993e7-122">[プログラミング ガイド](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md) </span><span class="sxs-lookup"><span data-stu-id="993e7-122">[Programming Guide](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md) </span></span>  
 <span data-ttu-id="993e7-123">[ACK プロセス モデル](../../adapters-and-accelerators/accelerator-hl7/ack-process-model.md) </span><span class="sxs-lookup"><span data-stu-id="993e7-123">[ACK Process Model](../../adapters-and-accelerators/accelerator-hl7/ack-process-model.md) </span></span>  
 [<span data-ttu-id="993e7-124">静的受信確認</span><span class="sxs-lookup"><span data-stu-id="993e7-124">Static Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/static-acknowledgments.md)
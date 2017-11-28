---
title: "ACK メッセージ モード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message modes, ACK messages
- messages, acknowledgements
- acknowledgements, message modes
- ACK message modes
ms.assetid: ab4a9470-dab2-46d4-8d0a-54dc12f2fa90
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 122f0851005c7d8abba6c1739ae86a1d65d89625
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="ack-message-modes"></a><span data-ttu-id="99128-102">ACK メッセージ モード</span><span class="sxs-lookup"><span data-stu-id="99128-102">ACK Message Modes</span></span>
<span data-ttu-id="99128-103">確認 (ACK) メッセージの[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 受信確認モードおよびを生成する ACK の MSH15 および MSH16 フィールドを設定するために使用する値を決定します。</span><span class="sxs-lookup"><span data-stu-id="99128-103">For acknowledgment (ACK) messages, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) determines the acknowledgment mode and values to use for populating MSH15 and MSH16 fields of the ACK you want to generate.</span></span> <span data-ttu-id="99128-104">これらの値は、取引先管理 (TPM) 構成内に存在します。</span><span class="sxs-lookup"><span data-stu-id="99128-104">These values are present in the Trading Partner Management (TPM) configuration.</span></span> <span data-ttu-id="99128-105">次の値は、ACK モードの可能な。</span><span class="sxs-lookup"><span data-stu-id="99128-105">The following values are possible for ACK mode:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="99128-106">次の一覧には、HL7 仕様は、1 ~ 3 のアイテムと MSH15 と MSH16 の値が含まれている定められています。</span><span class="sxs-lookup"><span data-stu-id="99128-106">In the following list, the HL7 specification mandates items 1 through 3 and that they contain MSH15 and MSH16 values.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="99128-107">項目を受信確認を生成されないことを示すために 4 を定義します。</span><span class="sxs-lookup"><span data-stu-id="99128-107"> defines item 4 to signify that an acknowledgment should not be generated.</span></span>  
  
1.  <span data-ttu-id="99128-108">元のヘッダーと本文の検証後に送信された 1 つ確認します。</span><span class="sxs-lookup"><span data-stu-id="99128-108">Original - One ACK sent after validating the header and body.</span></span> <span data-ttu-id="99128-109">このモードには、スキーマの検証が含まれます。</span><span class="sxs-lookup"><span data-stu-id="99128-109">This mode involves schema validation.</span></span>  
  
2.  <span data-ttu-id="99128-110">拡張 - 2 つの ACK メッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="99128-110">Enhanced - Two ACK messages sent:</span></span>  
  
    -   <span data-ttu-id="99128-111">ACK – を受け入れる受信側システムでは、ヘッダーの検証後にこの種類の確認を送信します。</span><span class="sxs-lookup"><span data-stu-id="99128-111">Accept ACK – The receiving system sends this type of ACK after validation of the header.</span></span> <span data-ttu-id="99128-112">この確認は、メッセージがデータベースにコミットされることを発信側アプリケーションに通知します。</span><span class="sxs-lookup"><span data-stu-id="99128-112">This ACK signals to the initiating application that the message is committed to the database.</span></span>  
  
    -   <span data-ttu-id="99128-113">アプリケーション ACK の受信側システムでは、ヘッダーおよび本文を含む、完全なメッセージの検証後にこの種類の確認を送信します。</span><span class="sxs-lookup"><span data-stu-id="99128-113">Application ACK- The receiving system sends this type of ACK after complete message validation, including the header and the body.</span></span>  
  
3.  <span data-ttu-id="99128-114">遅延の 2 つの ACK メッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="99128-114">Deferred - Two ACK messages sent.</span></span>  
  
    -   <span data-ttu-id="99128-115">元のモード: 受信側システムは、ヘッダーと本文の検証後にこの種類の確認を送信します。</span><span class="sxs-lookup"><span data-stu-id="99128-115">Original Mode: The receiving system sends this type of ACK after validation of the header and body.</span></span> <span data-ttu-id="99128-116">このモードには、スキーマの検証が含まれます。</span><span class="sxs-lookup"><span data-stu-id="99128-116">This mode involves schema validation.</span></span>  
  
    -   <span data-ttu-id="99128-117">遅延モード: 処理した後、基幹業務アプリケーションがメッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="99128-117">Deferred Mode: The line-of-business application acknowledges the message after processing it.</span></span> <span data-ttu-id="99128-118">アプリケーション メッセージを配信の遅延を[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、スタンドアロンのメッセージとして処理され、送信先に配信します。</span><span class="sxs-lookup"><span data-stu-id="99128-118">The application delivers the deferred message to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], which process it as a stand-alone message and delivers it to the destination.</span></span>  
  
4.  <span data-ttu-id="99128-119">静的 - 成功した場合に、または送信される ACK エラー発生時にします。</span><span class="sxs-lookup"><span data-stu-id="99128-119">Static - An on success or on failure ACK sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99128-120">参照</span><span class="sxs-lookup"><span data-stu-id="99128-120">See Also</span></span>  
 <span data-ttu-id="99128-121">[作成して、受信確認の処理](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="99128-121">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 <span data-ttu-id="99128-122">[プログラミング ガイド](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md) </span><span class="sxs-lookup"><span data-stu-id="99128-122">[Programming Guide](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md) </span></span>  
 <span data-ttu-id="99128-123">[ACK プロセス モデル](../../adapters-and-accelerators/accelerator-hl7/ack-process-model.md) </span><span class="sxs-lookup"><span data-stu-id="99128-123">[ACK Process Model](../../adapters-and-accelerators/accelerator-hl7/ack-process-model.md) </span></span>  
 [<span data-ttu-id="99128-124">静的な受信確認</span><span class="sxs-lookup"><span data-stu-id="99128-124">Static Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/static-acknowledgments.md)
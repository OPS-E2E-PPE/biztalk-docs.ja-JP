---
title: 受信確認 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, acknowledgements
- parties, acknowledgements
- acknowledgements, about acknowledgements
- acknowledgements, messages
- acknowledgements, parties
ms.assetid: d25352a4-bae9-4de9-a504-2339bea25c4a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46dedd4f2173fd4a3ad36c272963334b4ce66a20
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969787"
---
# <a name="acknowledgments"></a><span data-ttu-id="676af-102">受信確認</span><span class="sxs-lookup"><span data-stu-id="676af-102">Acknowledgments</span></span>
<span data-ttu-id="676af-103">HL7 の Microsoft BizTalk Accelerator を使用してパーティ レベルで HL7 受信確認を構成する ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 構成エクスプ ローラー。</span><span class="sxs-lookup"><span data-stu-id="676af-103">You configure HL7 acknowledgments at the party level using Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) Configuration Explorer.</span></span> <span data-ttu-id="676af-104">受信確認が受信場所 (MLLP アダプターでは可能性があります) および、HL7 HL7 メッセージを送信しているパーティに適用 2.X 受信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="676af-104">Acknowledgments apply to parties that are sending HL7 messages through a receive location (possibly the MLLP adapter) and the HL7 2.X receive pipeline.</span></span> <span data-ttu-id="676af-105">メッセージの解析と検証が完了すると[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]の検証プロセスの結果 (成功またはエラー) が含まれる受信確認メッセージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="676af-105">When a message completes parsing and validation, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] can create an acknowledgment message that contains the result (success or error) of the validation process.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="676af-106"> 2 つの方法のいずれかで受信確認メッセージを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="676af-106"> can return acknowledgment messages in one of two ways.</span></span> <span data-ttu-id="676af-107">元の送信元パーティには、双方向で元のメッセージが送信された場合の受信ポートの構成、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]その元のポートの場所でメッセージを受信確認を返します。</span><span class="sxs-lookup"><span data-stu-id="676af-107">If the original sending party submitted the original message through a two-way receive port configuration, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] returns the acknowledgment message through that original port location.</span></span> <span data-ttu-id="676af-108">元の送信ポートが一方向で元のメッセージを送信し、ポート、表示される[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]メッセージ ボックス データベースに受信確認メッセージを送信し、サブスクリプション モデルを使用して、ルーティングします。[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]</span><span class="sxs-lookup"><span data-stu-id="676af-108">If the original sending port submitted the original message through a one-way receive port, then [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] submits the acknowledgment message into the MessageBox database and routes it using the subscription model.[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]</span></span> <span data-ttu-id="676af-109">受信メッセージを (MSH 3.1) HL7 メッセージの送信元アプリケーションのフィールド内の値に基づいて自動的に処理するためには、関係者の関連付けを実行します。</span><span class="sxs-lookup"><span data-stu-id="676af-109">performs party association for receive message processing automatically based on the value within the sending application field of the HL7 message (MSH 3.1).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="676af-110">参照</span><span class="sxs-lookup"><span data-stu-id="676af-110">See Also</span></span>  
 [<span data-ttu-id="676af-111">メッセージ フロー</span><span class="sxs-lookup"><span data-stu-id="676af-111">Message Flow</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-flow.md)
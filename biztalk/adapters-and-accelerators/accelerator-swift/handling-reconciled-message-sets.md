---
title: 照合済みのメッセージ セットの処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAA
- messages, reconciled sets
ms.assetid: 05cd0cf6-f0fd-4cbe-83c6-1ed5f2da8822
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fc9f35f9381f82df90acb92e9536bbd967901a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209042"
---
# <a name="handling-reconciled-message-sets"></a><span data-ttu-id="ba6ac-102">処理は、メッセージの設定を調整</span><span class="sxs-lookup"><span data-stu-id="ba6ac-102">Handling Reconciled Message Sets</span></span>
<span data-ttu-id="ba6ac-103">SAA にへの応答が返されるときに[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]メッセージ ボックスで、応答を記録し、応答または応答を元のメッセージに一致します。</span><span class="sxs-lookup"><span data-stu-id="ba6ac-103">When SAA returns a response to [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)], [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] records the response in the MessageBox, and matches the response or responses to the original message.</span></span> <span data-ttu-id="ba6ac-104">この情報を使用してカスタム アプリケーションの動作を実装することができます。</span><span class="sxs-lookup"><span data-stu-id="ba6ac-104">You can implement custom application behavior using this information.</span></span> <span data-ttu-id="ba6ac-105">これを行うには、調整/応答メッセージのセットに対する顧客固有の反応を実装するカスタムのハンドラーを開発します。</span><span class="sxs-lookup"><span data-stu-id="ba6ac-105">To do so, develop custom handlers that implement customer-specific reactions to reconciled message/response sets.</span></span> <span data-ttu-id="ba6ac-106">次のカスタム ハンドラーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ba6ac-106">You can create custom handlers that do the following:</span></span>  
  
-   <span data-ttu-id="ba6ac-107">SWIFT 受信しなかったことが正常にからメッセージを示す MTS21_FIN_ACKNAK 負の値確認のメッセージで FRR が関連付けられたメッセージを処理[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ba6ac-107">Process messages that FRR has correlated with a MTS21_FIN_ACKNAK negative-acknowledgment message, which indicates that SWIFT did not successfully receive the message from [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="ba6ac-108">これは、メッセージを修正して再 SAA および SWIFT ネットワークで修復後にメッセージが正常に表示されることが望まれます送信修理会社を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="ba6ac-108">This can enable a repairer to fix the message and re-send it to SAA and the SWIFT network, which after the repair will hopefully be able to receive the message successfully.</span></span> <span data-ttu-id="ba6ac-109">このソリューションの詳細については、次を参照してください。 [FRR NAK ハンドラー サンプル](../../adapters-and-accelerators/accelerator-swift/frr-nak-handler-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="ba6ac-109">For more information about this solution, see [FRR NAK Handler Sample](../../adapters-and-accelerators/accelerator-swift/frr-nak-handler-sample.md).</span></span>  
  
-   <span data-ttu-id="ba6ac-110">セット内のメッセージの関係を示す一意のファイル名を持つファイルのフォルダーに、オーケストレーションによって公開されたメッセージ応答セットを削除します。</span><span class="sxs-lookup"><span data-stu-id="ba6ac-110">Drop message-response sets published by the orchestration into a file folder with unique file names indicating the relationships of the messages in the set.</span></span> <span data-ttu-id="ba6ac-111">これらのメッセージでビジネス ロジックを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ba6ac-111">You can then perform business logic on these messages.</span></span>  
  
-   <span data-ttu-id="ba6ac-112">タイムアウトになったメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="ba6ac-112">Process timed-out messages.</span></span>  
  
-   <span data-ttu-id="ba6ac-113">メッセージ送信の結果を記録し、実際のメッセージを破棄します。</span><span class="sxs-lookup"><span data-stu-id="ba6ac-113">Log the results of message transmission and then discard the actual messages.</span></span>
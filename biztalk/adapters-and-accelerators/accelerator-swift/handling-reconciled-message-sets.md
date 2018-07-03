---
title: 調整のメッセージ セットの処理 |Microsoft Docs
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
ms.openlocfilehash: 3d3a06955e0072348098ddd7f191bf4862fb119a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986091"
---
# <a name="handling-reconciled-message-sets"></a><span data-ttu-id="f186e-102">調整されたメッセージ セットの処理</span><span class="sxs-lookup"><span data-stu-id="f186e-102">Handling Reconciled Message Sets</span></span>
<span data-ttu-id="f186e-103">SAA にへの応答が返されるときに[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]メッセージ ボックスで、応答を記録し、応答や、元のメッセージに対する応答に一致します。</span><span class="sxs-lookup"><span data-stu-id="f186e-103">When SAA returns a response to [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)], [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] records the response in the MessageBox, and matches the response or responses to the original message.</span></span> <span data-ttu-id="f186e-104">この情報を使用してカスタム アプリケーションの動作を実装することができます。</span><span class="sxs-lookup"><span data-stu-id="f186e-104">You can implement custom application behavior using this information.</span></span> <span data-ttu-id="f186e-105">これを行うには、調整/応答メッセージのセットに対する顧客固有の反応を実装するカスタム ハンドラーを開発します。</span><span class="sxs-lookup"><span data-stu-id="f186e-105">To do so, develop custom handlers that implement customer-specific reactions to reconciled message/response sets.</span></span> <span data-ttu-id="f186e-106">次のカスタム ハンドラーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f186e-106">You can create custom handlers that do the following:</span></span>  

- <span data-ttu-id="f186e-107">SWIFT によってからのメッセージが正常に受信しないようにを示します、MTS21_FIN_ACKNAK 負では受信確認メッセージの FRR が相関関係するメッセージを処理[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f186e-107">Process messages that FRR has correlated with a MTS21_FIN_ACKNAK negative-acknowledgment message, which indicates that SWIFT did not successfully receive the message from [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="f186e-108">これは、メッセージを修正し、SAA と SWIFT ネットワークのメッセージが正常に表示されることができれば、その後の修復に再び送信修理会社を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="f186e-108">This can enable a repairer to fix the message and re-send it to SAA and the SWIFT network, which after the repair will hopefully be able to receive the message successfully.</span></span> <span data-ttu-id="f186e-109">このソリューションの詳細については、次を参照してください。 [FRR NAK ハンドラー サンプル](../../adapters-and-accelerators/accelerator-swift/frr-nak-handler-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="f186e-109">For more information about this solution, see [FRR NAK Handler Sample](../../adapters-and-accelerators/accelerator-swift/frr-nak-handler-sample.md).</span></span>  

- <span data-ttu-id="f186e-110">セット内のメッセージの関係を示す一意のファイル名を持つファイル フォルダーに、オーケストレーションによって公開されたメッセージ応答セットを削除します。</span><span class="sxs-lookup"><span data-stu-id="f186e-110">Drop message-response sets published by the orchestration into a file folder with unique file names indicating the relationships of the messages in the set.</span></span> <span data-ttu-id="f186e-111">これらのメッセージにビジネス ロジックを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f186e-111">You can then perform business logic on these messages.</span></span>  

- <span data-ttu-id="f186e-112">タイムアウト メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="f186e-112">Process timed-out messages.</span></span>  

- <span data-ttu-id="f186e-113">メッセージ送信の結果を記録し、実際のメッセージを破棄します。</span><span class="sxs-lookup"><span data-stu-id="f186e-113">Log the results of message transmission and then discard the actual messages.</span></span>

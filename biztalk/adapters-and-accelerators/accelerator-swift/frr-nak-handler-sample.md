---
title: FRR NAK ハンドラー サンプル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, NAKs
- examples, FRR
- NAKs
- acknowledgements
- FRR, examples
- examples, FRR NAK handler
ms.assetid: be992507-ba8c-461f-a563-f1d7b2ab221d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5c39c564595852fa8c19d3d9f26b5ba5946f6c3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377563"
---
# <a name="frr-nak-handler-sample"></a><span data-ttu-id="9d094-102">FRR NAK ハンドラー サンプル</span><span class="sxs-lookup"><span data-stu-id="9d094-102">FRR NAK Handler Sample</span></span>
<span data-ttu-id="9d094-103">FRR NAK ハンドラー サンプルでは、迅速な応答を FIN 応答の調整 (FRR) が関連付けられたメッセージを処理するカスタム ハンドラーを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9d094-103">The FRR NAK Handler sample demonstrates how to create a custom handler to process messages that FIN Response Reconciliation (FRR) has correlated with SWIFT responses.</span></span> <span data-ttu-id="9d094-104">このカスタム ハンドラーでは、する SWIFT 正常から受信しなかったメッセージ A4SWIFT を示す MTS21_FIN_ACKNAK 負では受信確認のメッセージの FRR が関連付けられたメッセージが処理されます。</span><span class="sxs-lookup"><span data-stu-id="9d094-104">This custom handler processes messages that FRR has correlated with a MTS21_FIN_ACKNAK negative-acknowledgment message, which indicates that SWIFT did not successfully receive the message from A4SWIFT.</span></span> <span data-ttu-id="9d094-105">カスタム ハンドラーは、エラー オブジェクトを 2 つの部分のメッセージがメッセージになります、メッセージに追加し、メッセージ修復オーケストレーションが、メッセージを取得するプロパティを昇格させます。</span><span class="sxs-lookup"><span data-stu-id="9d094-105">The custom handler adds an error object to the message, making the message a two-part message, and promotes the properties that cause the message-repair orchestration to pick up the message.</span></span> <span data-ttu-id="9d094-106">その結果、修理会社は、メッセージを修正し、SWIFT Alliance アクセス (SAA) を再送信できます。</span><span class="sxs-lookup"><span data-stu-id="9d094-106">As a result, a repairer can fix the message and resend it to SWIFT Alliance Access (SAA).</span></span>  
  
 <span data-ttu-id="9d094-107">**サンプル コンポーネント**</span><span class="sxs-lookup"><span data-stu-id="9d094-107">**Sample Components**</span></span>  
  
 <span data-ttu-id="9d094-108">FRR NAK ハンドラー サンプルには、次のコンポーネントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9d094-108">The FRR NAK Handler sample includes the following components:</span></span>  
  
- <span data-ttu-id="9d094-109">**RepairSWIFTRejectedMessage.odx します。**</span><span class="sxs-lookup"><span data-stu-id="9d094-109">**RepairSWIFTRejectedMessage.odx.**</span></span> <span data-ttu-id="9d094-110">このオーケストレーションは、SWIFT 正常に受信できなかった、修理会社が修正し、メッセージの再送信できるようにメッセージ修復オーケストレーションにルーティングするメッセージを処理するカスタム ハンドラーです。</span><span class="sxs-lookup"><span data-stu-id="9d094-110">This orchestration is the custom handler that processes a message that SWIFT could not successfully receive, routing it to the message-repair orchestration so a repairer can fix and resend the message.</span></span>  
  
- <span data-ttu-id="9d094-111">**RepairSWIFTRejectedMessage.btproj.**</span><span class="sxs-lookup"><span data-stu-id="9d094-111">**RepairSWIFTRejectedMessage.btproj.**</span></span> <span data-ttu-id="9d094-112">このプロジェクトには、構築およびデプロイするには、RepairSWIFTRejectedMessage.odx と、プロジェクトに必要な参照が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9d094-112">This project includes RepairSWIFTRejectedMessage.odx and the references required for the project to build and deploy.</span></span>  
  
- <span data-ttu-id="9d094-113">**RepairSWIFTRejectedMessage.sln.**</span><span class="sxs-lookup"><span data-stu-id="9d094-113">**RepairSWIFTRejectedMessage.sln.**</span></span> <span data-ttu-id="9d094-114">このソリューションには、RepairSWIFTRejectedMessage.btproj プロジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9d094-114">This solution includes the RepairSWIFTRejectedMessage.btproj project.</span></span>  
  
  <span data-ttu-id="9d094-115">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9d094-115">This section contains:</span></span>  
  
- [<span data-ttu-id="9d094-116">FRR NAK ハンドラー サンプルの実装</span><span class="sxs-lookup"><span data-stu-id="9d094-116">Implementing the FRR NAK Handler Sample</span></span>](../../adapters-and-accelerators/accelerator-swift/implementing-the-frr-nak-handler-sample.md)  
  
- [<span data-ttu-id="9d094-117">FRR NAK ハンドラー サンプルのしくみ</span><span class="sxs-lookup"><span data-stu-id="9d094-117">How the FRR NAK Handler Sample Works</span></span>](../../adapters-and-accelerators/accelerator-swift/how-the-frr-nak-handler-sample-works.md)  
  

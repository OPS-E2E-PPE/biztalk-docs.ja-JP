---
title: "FRR NAK ハンドラー サンプル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, NAKs
- examples, FRR
- NAKs
- acknowledgements
- FRR, examples
- examples, FRR NAK handler
ms.assetid: be992507-ba8c-461f-a563-f1d7b2ab221d
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a3881b8bcf4b62af7653ef6214b4fccdf8402d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="frr-nak-handler-sample"></a><span data-ttu-id="a06dd-102">FRR NAK ハンドラーのサンプル</span><span class="sxs-lookup"><span data-stu-id="a06dd-102">FRR NAK Handler Sample</span></span>
<span data-ttu-id="a06dd-103">FRR NAK ハンドラーのサンプルでは、迅速な応答を FIN 対応調整 (FRR) が関連付けられたメッセージを処理するカスタム ハンドラーを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a06dd-103">The FRR NAK Handler sample demonstrates how to create a custom handler to process messages that FIN Response Reconciliation (FRR) has correlated with SWIFT responses.</span></span> <span data-ttu-id="a06dd-104">このカスタム ハンドラーを SWIFT 正常から取得されなかったメッセージ A4SWIFT を示す MTS21_FIN_ACKNAK 負の値確認のメッセージで FRR が関連付けられたメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="a06dd-104">This custom handler processes messages that FRR has correlated with a MTS21_FIN_ACKNAK negative-acknowledgment message, which indicates that SWIFT did not successfully receive the message from A4SWIFT.</span></span> <span data-ttu-id="a06dd-105">カスタム ハンドラーは、2 部構成のメッセージでは、メッセージを作成、メッセージにエラー オブジェクトを追加し、発生するメッセージ修復オーケストレーションがメッセージを取得するプロパティを昇格させます。</span><span class="sxs-lookup"><span data-stu-id="a06dd-105">The custom handler adds an error object to the message, making the message a two-part message, and promotes the properties that cause the message-repair orchestration to pick up the message.</span></span> <span data-ttu-id="a06dd-106">その結果、修理会社は、メッセージを修正し、SWIFT Alliance アクセス (SAA) に再送信できます。</span><span class="sxs-lookup"><span data-stu-id="a06dd-106">As a result, a repairer can fix the message and resend it to SWIFT Alliance Access (SAA).</span></span>  
  
 <span data-ttu-id="a06dd-107">**サンプル コンポーネント**</span><span class="sxs-lookup"><span data-stu-id="a06dd-107">**Sample Components**</span></span>  
  
 <span data-ttu-id="a06dd-108">FRR NAK ハンドラー サンプルには、次のコンポーネントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a06dd-108">The FRR NAK Handler sample includes the following components:</span></span>  
  
-   <span data-ttu-id="a06dd-109">**RepairSWIFTRejectedMessage.odx です。**</span><span class="sxs-lookup"><span data-stu-id="a06dd-109">**RepairSWIFTRejectedMessage.odx.**</span></span> <span data-ttu-id="a06dd-110">このオーケストレーションは、SWIFT が正常に受信できません、修理会社が修正し、メッセージを再送信できるように、メッセージ修復オーケストレーションにルーティングするメッセージを処理するカスタム ハンドラーです。</span><span class="sxs-lookup"><span data-stu-id="a06dd-110">This orchestration is the custom handler that processes a message that SWIFT could not successfully receive, routing it to the message-repair orchestration so a repairer can fix and resend the message.</span></span>  
  
-   <span data-ttu-id="a06dd-111">**RepairSWIFTRejectedMessage.btproj です。**</span><span class="sxs-lookup"><span data-stu-id="a06dd-111">**RepairSWIFTRejectedMessage.btproj.**</span></span> <span data-ttu-id="a06dd-112">このプロジェクトには、ビルドおよび配置するには、RepairSWIFTRejectedMessage.odx と、プロジェクトに必要な参照が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a06dd-112">This project includes RepairSWIFTRejectedMessage.odx and the references required for the project to build and deploy.</span></span>  
  
-   <span data-ttu-id="a06dd-113">**RepairSWIFTRejectedMessage.sln です。**</span><span class="sxs-lookup"><span data-stu-id="a06dd-113">**RepairSWIFTRejectedMessage.sln.**</span></span> <span data-ttu-id="a06dd-114">このソリューションには、RepairSWIFTRejectedMessage.btproj プロジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a06dd-114">This solution includes the RepairSWIFTRejectedMessage.btproj project.</span></span>  
  
 <span data-ttu-id="a06dd-115">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a06dd-115">This section contains:</span></span>  
  
-   [<span data-ttu-id="a06dd-116">FRR NAK ハンドラーのサンプルを実装します。</span><span class="sxs-lookup"><span data-stu-id="a06dd-116">Implementing the FRR NAK Handler Sample</span></span>](../../adapters-and-accelerators/accelerator-swift/implementing-the-frr-nak-handler-sample.md)  
  
-   [<span data-ttu-id="a06dd-117">FRR NAK ハンドラーのサンプルのしくみ</span><span class="sxs-lookup"><span data-stu-id="a06dd-117">How the FRR NAK Handler Sample Works</span></span>](../../adapters-and-accelerators/accelerator-swift/how-the-frr-nak-handler-sample-works.md)  
  

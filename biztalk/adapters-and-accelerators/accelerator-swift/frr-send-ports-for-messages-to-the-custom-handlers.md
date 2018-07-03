---
title: カスタム ハンドラーへのメッセージの FRR 送信ポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, send ports
- custom handlers
- FRR, custom handlers
- send ports, FRR
- send ports, custom handlers
ms.assetid: 486d7410-fde1-4a9b-a9c2-64c1ed85ebc0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df8ba2b085268f2c0c272b81b27768db716b63c0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996155"
---
# <a name="frr-send-ports-for-messages-to-the-custom-handlers"></a><span data-ttu-id="53e1e-102">カスタム ハンドラーへのメッセージの FRR 送信ポート</span><span class="sxs-lookup"><span data-stu-id="53e1e-102">FRR Send Ports for Messages to the Custom Handlers</span></span>
<span data-ttu-id="53e1e-103">FRR でカスタム ハンドラーを有効にする、FRR 送信ポートの一連のカスタム ハンドラーへの特定の種類の元のメッセージのコピーのルーティングを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53e1e-103">To enable custom handlers for FRR, you must create a series of FRR send ports, each one of which routes a copy of an original message of a certain type to the custom handlers.</span></span> <span data-ttu-id="53e1e-104">これらの送信ポートには次のパイプライン コンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="53e1e-104">These send ports must have the following pipeline components:</span></span>  

- <span data-ttu-id="53e1e-105">アセンブル ステージで SWIFT アセンブラー</span><span class="sxs-lookup"><span data-stu-id="53e1e-105">The SWIFT assembler in the Assemble stage</span></span>  

- <span data-ttu-id="53e1e-106">エンコード段階で SWIFTSendFrrComponent パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="53e1e-106">The SWIFTSendFrrComponent pipeline component in the Encode stage</span></span>  

  <span data-ttu-id="53e1e-107">カテゴリ 0 ~ 9 の SWIFT FIN メッセージが正常に送信されませんを除くすべてのメッセージ、送信ポートは、次のフィルターが必要です。</span><span class="sxs-lookup"><span data-stu-id="53e1e-107">For all messages except Category 0 to 9 SWIFT FIN messages that are not successfully sent, the send port must have the following filters:</span></span>  

- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="53e1e-108">_SendingServiceType = = [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService</span><span class="sxs-lookup"><span data-stu-id="53e1e-108">_SendingServiceType == [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService</span></span>  

- <span data-ttu-id="53e1e-109">BTS します。操作は、メッセージの種類ごとに必要な値に設定します。</span><span class="sxs-lookup"><span data-stu-id="53e1e-109">BTS.Operation set to the value required for each message type.</span></span> <span data-ttu-id="53e1e-110">BTS の考えられる値。Operation プロパティでは、表を参照して[カスタム ハンドラーへの送信用として FRR 送信ポートを作成する](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)します。</span><span class="sxs-lookup"><span data-stu-id="53e1e-110">For the possible values for the BTS.Operation property, see the table in [Creating the FRR Send Ports for Sending to the Custom Handlers](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md).</span></span>  

  <span data-ttu-id="53e1e-111">正常に送信されないカテゴリ 0 ~ 9 の SWIFT FIN メッセージ、送信ポートは、次のフィルターが必要です。</span><span class="sxs-lookup"><span data-stu-id="53e1e-111">For Category 0 to 9 SWIFT FIN messages that are not successfully sent, the send port must have the following filters:</span></span>  

- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="53e1e-112">_SendingServiceTyp = =[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService</span><span class="sxs-lookup"><span data-stu-id="53e1e-112">_SendingServiceTyp==[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService</span></span>  

- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="53e1e-113">_FrrFailed true = =</span><span class="sxs-lookup"><span data-stu-id="53e1e-113">_FrrFailed==True</span></span>  

- <span data-ttu-id="53e1e-114">BTS します。操作 = =[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSendMTMsg</span><span class="sxs-lookup"><span data-stu-id="53e1e-114">BTS.Operation==[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSendMTMsg</span></span>  

- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="53e1e-115">_FRRFailedReason は、メッセージの種類ごとに必要な値に設定します。</span><span class="sxs-lookup"><span data-stu-id="53e1e-115">_FRRFailedReason set to the value required for each message type.</span></span> <span data-ttu-id="53e1e-116">BTS の考えられる値。Operation プロパティでは、表を参照して[カスタム ハンドラーへの送信用として FRR 送信ポートを作成する](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)します。</span><span class="sxs-lookup"><span data-stu-id="53e1e-116">For the possible values for the BTS.Operation property, see the table in [Creating the FRR Send Ports for Sending to the Custom Handlers](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md).</span></span>

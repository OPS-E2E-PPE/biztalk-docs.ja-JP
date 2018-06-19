---
title: カスタム ハンドラーへのメッセージの送信ポートを FRR |Microsoft ドキュメント
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
ms.openlocfilehash: e6babc312ddad7d77a96e29bc9e59ec9298aa6ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207834"
---
# <a name="frr-send-ports-for-messages-to-the-custom-handlers"></a><span data-ttu-id="a20d4-102">カスタム ハンドラーへのメッセージの送信ポートを FRR</span><span class="sxs-lookup"><span data-stu-id="a20d4-102">FRR Send Ports for Messages to the Custom Handlers</span></span>
<span data-ttu-id="a20d4-103">FRR でカスタム ハンドラーを有効にするのには、特定の型の元のメッセージのコピーをカスタム ハンドラーにルーティングする一連の FRR 送信ポートを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a20d4-103">To enable custom handlers for FRR, you must create a series of FRR send ports, each one of which routes a copy of an original message of a certain type to the custom handlers.</span></span> <span data-ttu-id="a20d4-104">これらの送信ポートには次のパイプライン コンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="a20d4-104">These send ports must have the following pipeline components:</span></span>  
  
-   <span data-ttu-id="a20d4-105">アセンブル ステージに SWIFT アセンブラー</span><span class="sxs-lookup"><span data-stu-id="a20d4-105">The SWIFT assembler in the Assemble stage</span></span>  
  
-   <span data-ttu-id="a20d4-106">エンコード ステージに SWIFTSendFrrComponent パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a20d4-106">The SWIFTSendFrrComponent pipeline component in the Encode stage</span></span>  
  
 <span data-ttu-id="a20d4-107">カテゴリ、0 ~ 9 SWIFT FIN メッセージが正常に送信されないことを除き、すべてのメッセージの送信ポートは、次のフィルターが必要です。</span><span class="sxs-lookup"><span data-stu-id="a20d4-107">For all messages except Category 0 to 9 SWIFT FIN messages that are not successfully sent, the send port must have the following filters:</span></span>  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="a20d4-108">_SendingServiceType = = [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService</span><span class="sxs-lookup"><span data-stu-id="a20d4-108">_SendingServiceType == [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService</span></span>  
  
-   <span data-ttu-id="a20d4-109">BTS です。操作は、メッセージの種類ごとに必要な値に設定します。</span><span class="sxs-lookup"><span data-stu-id="a20d4-109">BTS.Operation set to the value required for each message type.</span></span> <span data-ttu-id="a20d4-110">BTS の考えられる値です。操作のプロパティ内のテーブルを参照してください[FRR 送信ポートを作成するカスタム ハンドラーに送信の](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)します。</span><span class="sxs-lookup"><span data-stu-id="a20d4-110">For the possible values for the BTS.Operation property, see the table in [Creating the FRR Send Ports for Sending to the Custom Handlers](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md).</span></span>  
  
 <span data-ttu-id="a20d4-111">正常に送信されていないカテゴリ、0 ~ 9 SWIFT FIN メッセージ、送信ポートは、次のフィルターが必要です。</span><span class="sxs-lookup"><span data-stu-id="a20d4-111">For Category 0 to 9 SWIFT FIN messages that are not successfully sent, the send port must have the following filters:</span></span>  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="a20d4-112">_SendingServiceTyp = =[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService</span><span class="sxs-lookup"><span data-stu-id="a20d4-112">_SendingServiceTyp==[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService</span></span>  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="a20d4-113">_FrrFailed = = true</span><span class="sxs-lookup"><span data-stu-id="a20d4-113">_FrrFailed==True</span></span>  
  
-   <span data-ttu-id="a20d4-114">BTS です。操作 = =[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSendMTMsg</span><span class="sxs-lookup"><span data-stu-id="a20d4-114">BTS.Operation==[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSendMTMsg</span></span>  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="a20d4-115">_FRRFailedReason は、メッセージの種類ごとに必要な値に設定します。</span><span class="sxs-lookup"><span data-stu-id="a20d4-115">_FRRFailedReason set to the value required for each message type.</span></span> <span data-ttu-id="a20d4-116">BTS の考えられる値です。操作のプロパティ内のテーブルを参照してください[FRR 送信ポートを作成するカスタム ハンドラーに送信の](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)します。</span><span class="sxs-lookup"><span data-stu-id="a20d4-116">For the possible values for the BTS.Operation property, see the table in [Creating the FRR Send Ports for Sending to the Custom Handlers](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md).</span></span>
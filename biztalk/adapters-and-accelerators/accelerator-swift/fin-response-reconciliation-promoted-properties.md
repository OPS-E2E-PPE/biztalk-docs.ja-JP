---
title: FIN Response Reconciliation の昇格させたプロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- promoted properties, FIN Response Reconciliation
- FIN Response Reconciliation, promoted properties
ms.assetid: 1a638e9e-61eb-482c-8856-b1aea36c449c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23d1460163b67618c3f7e15f1c8bd14ecdd97556
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377874"
---
# <a name="fin-response-reconciliation-promoted-properties"></a><span data-ttu-id="9bf87-102">FIN Response Reconciliation の昇格させたプロパティ</span><span class="sxs-lookup"><span data-stu-id="9bf87-102">FIN Response Reconciliation Promoted Properties</span></span>
<span data-ttu-id="9bf87-103">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FIN Response Reconciliation の機能には、次の昇格させたプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9bf87-103">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FIN Response Reconciliation feature includes the following promoted properties.</span></span>  
  
|<span data-ttu-id="9bf87-104">昇格させた名</span><span class="sxs-lookup"><span data-stu-id="9bf87-104">Promoted name</span></span>|<span data-ttu-id="9bf87-105">説明</span><span class="sxs-lookup"><span data-stu-id="9bf87-105">Description</span></span>|<span data-ttu-id="9bf87-106">データ型</span><span class="sxs-lookup"><span data-stu-id="9bf87-106">Data type</span></span>|<span data-ttu-id="9bf87-107">値の範囲</span><span class="sxs-lookup"><span data-stu-id="9bf87-107">Value range</span></span>|<span data-ttu-id="9bf87-108">使用例</span><span class="sxs-lookup"><span data-stu-id="9bf87-108">Usage example</span></span>|  
|-------------------|-----------------|---------------|-----------------|-------------------|  
|<span data-ttu-id="9bf87-109">**A4SWIFT_FRRFailed**</span><span class="sxs-lookup"><span data-stu-id="9bf87-109">**A4SWIFT_FRRFailed**</span></span>|<span data-ttu-id="9bf87-110">このプロパティは、メインのメッセージを送信するときに、負のシナリオでは昇格されます。</span><span class="sxs-lookup"><span data-stu-id="9bf87-110">This property is promoted in a negative scenario when sending out the main message.</span></span>|<span data-ttu-id="9bf87-111">ブール値</span><span class="sxs-lookup"><span data-stu-id="9bf87-111">Boolean</span></span>|<span data-ttu-id="9bf87-112">True</span><span class="sxs-lookup"><span data-stu-id="9bf87-112">True</span></span><br /><br /> <span data-ttu-id="9bf87-113">False</span><span class="sxs-lookup"><span data-stu-id="9bf87-113">False</span></span>|<span data-ttu-id="9bf87-114">FRR 送信ポートのフィルター式のカスタム ハンドラーに失敗したメッセージを送信するために使用します。</span><span class="sxs-lookup"><span data-stu-id="9bf87-114">Used in the filter expression of an FRR send port to send a failed message to a custom handler.</span></span>|  
|<span data-ttu-id="9bf87-115">**A4SWIFT_FrrFailedReason**</span><span class="sxs-lookup"><span data-stu-id="9bf87-115">**A4SWIFT_FrrFailedReason**</span></span>|<span data-ttu-id="9bf87-116">元のメッセージが処理されなかったことが正常に SAA/SWIFT によってを示します。</span><span class="sxs-lookup"><span data-stu-id="9bf87-116">Indicates that the original message was not successfully processed by SAA/SWIFT.</span></span>|<span data-ttu-id="9bf87-117">String</span><span class="sxs-lookup"><span data-stu-id="9bf87-117">String</span></span>|<span data-ttu-id="9bf87-118">-   \<NAKErrorCode\></span><span class="sxs-lookup"><span data-stu-id="9bf87-118">-   \<NAKErrorCode\></span></span><br /><span data-ttu-id="9bf87-119">-   TimedOut</span><span class="sxs-lookup"><span data-stu-id="9bf87-119">-   TimedOut</span></span><br /><span data-ttu-id="9bf87-120">-TransportError</span><span class="sxs-lookup"><span data-stu-id="9bf87-120">-   TransportError</span></span><br /><span data-ttu-id="9bf87-121">-   Delayed_NAK</span><span class="sxs-lookup"><span data-stu-id="9bf87-121">-   Delayed_NAK</span></span><br /><span data-ttu-id="9bf87-122">-AbortReceived</span><span class="sxs-lookup"><span data-stu-id="9bf87-122">-   AbortReceived</span></span>|<span data-ttu-id="9bf87-123">FRR 送信ポートのフィルター式のカスタム ハンドラーに失敗したメッセージを送信するために使用します。</span><span class="sxs-lookup"><span data-stu-id="9bf87-123">Used in the filter expression of an FRR send port to send a failed message to a custom handler.</span></span>|  
|<span data-ttu-id="9bf87-124">**A4SWIFT_FRRCorrelationToken**</span><span class="sxs-lookup"><span data-stu-id="9bf87-124">**A4SWIFT_FRRCorrelationToken**</span></span>|<span data-ttu-id="9bf87-125">送信、MT の一意の関連付けトークンを示す*xxx*メッセージ。</span><span class="sxs-lookup"><span data-stu-id="9bf87-125">Indicates the unique correlation token of the outbound MT*xxx* message.</span></span>|<span data-ttu-id="9bf87-126">String</span><span class="sxs-lookup"><span data-stu-id="9bf87-126">String</span></span>|-|<span data-ttu-id="9bf87-127">FRR にこのプロパティを比較し、 **MQMD_CorrelID** FIN 応答のコンテキスト プロパティ。</span><span class="sxs-lookup"><span data-stu-id="9bf87-127">FRR compares this property to the **MQMD_CorrelID** context property of the FIN response.</span></span>|  
|<span data-ttu-id="9bf87-128">**A4SWIFT_SendingServiceType**</span><span class="sxs-lookup"><span data-stu-id="9bf87-128">**A4SWIFT_SendingServiceType**</span></span>|<span data-ttu-id="9bf87-129">FRR サービス メッセージを送信することを示します。</span><span class="sxs-lookup"><span data-stu-id="9bf87-129">Indicates the FRR service that sends the message.</span></span>|<span data-ttu-id="9bf87-130">String</span><span class="sxs-lookup"><span data-stu-id="9bf87-130">String</span></span>|<span data-ttu-id="9bf87-131">A4SWIFT_FrrService</span><span class="sxs-lookup"><span data-stu-id="9bf87-131">A4SWIFT_FrrService</span></span>|<span data-ttu-id="9bf87-132">昇格するときに**A4SWIFT_FRRFailed**が True に設定します。</span><span class="sxs-lookup"><span data-stu-id="9bf87-132">Promoted when **A4SWIFT_FRRFailed** is set to True.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9bf87-133">参照</span><span class="sxs-lookup"><span data-stu-id="9bf87-133">See Also</span></span>  
 <span data-ttu-id="9bf87-134">[A4swift _ \* 昇格させたプロパティ](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md) </span><span class="sxs-lookup"><span data-stu-id="9bf87-134">[A4SWIFT_\* Promoted Properties](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md) </span></span>  
 [<span data-ttu-id="9bf87-135">Message Repair and New Submission の昇格プロパティ</span><span class="sxs-lookup"><span data-stu-id="9bf87-135">Message Repair and New Submission Promoted Properties</span></span>](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission-promoted-properties.md)
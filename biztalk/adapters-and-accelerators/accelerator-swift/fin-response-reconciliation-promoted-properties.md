---
title: "昇格させたプロパティの FIN 対応調整 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- promoted properties, FIN Response Reconciliation
- FIN Response Reconciliation, promoted properties
ms.assetid: 1a638e9e-61eb-482c-8856-b1aea36c449c
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14a3e3a004dcb9e58abde08345352c02f0914801
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="fin-response-reconciliation-promoted-properties"></a><span data-ttu-id="94311-102">昇格させたプロパティの FIN 対応調整</span><span class="sxs-lookup"><span data-stu-id="94311-102">FIN Response Reconciliation Promoted Properties</span></span>
<span data-ttu-id="94311-103">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FIN 対応調整の機能には、次の昇格させたプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="94311-103">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FIN Response Reconciliation feature includes the following promoted properties.</span></span>  
  
|<span data-ttu-id="94311-104">昇格の名前</span><span class="sxs-lookup"><span data-stu-id="94311-104">Promoted name</span></span>|<span data-ttu-id="94311-105">Description</span><span class="sxs-lookup"><span data-stu-id="94311-105">Description</span></span>|<span data-ttu-id="94311-106">データ型</span><span class="sxs-lookup"><span data-stu-id="94311-106">Data type</span></span>|<span data-ttu-id="94311-107">値の範囲</span><span class="sxs-lookup"><span data-stu-id="94311-107">Value range</span></span>|<span data-ttu-id="94311-108">使用例</span><span class="sxs-lookup"><span data-stu-id="94311-108">Usage example</span></span>|  
|-------------------|-----------------|---------------|-----------------|-------------------|  
|<span data-ttu-id="94311-109">**A4SWIFT_FRRFailed**</span><span class="sxs-lookup"><span data-stu-id="94311-109">**A4SWIFT_FRRFailed**</span></span>|<span data-ttu-id="94311-110">メインのメッセージを送信するときに、このプロパティは、負の値のシナリオで昇格します。</span><span class="sxs-lookup"><span data-stu-id="94311-110">This property is promoted in a negative scenario when sending out the main message.</span></span>|<span data-ttu-id="94311-111">ブール値</span><span class="sxs-lookup"><span data-stu-id="94311-111">Boolean</span></span>|<span data-ttu-id="94311-112">True</span><span class="sxs-lookup"><span data-stu-id="94311-112">True</span></span><br /><br /> <span data-ttu-id="94311-113">False</span><span class="sxs-lookup"><span data-stu-id="94311-113">False</span></span>|<span data-ttu-id="94311-114">カスタム ハンドラーに障害が発生したメッセージを送信する FRR 送信ポートのフィルター式で使用します。</span><span class="sxs-lookup"><span data-stu-id="94311-114">Used in the filter expression of an FRR send port to send a failed message to a custom handler.</span></span>|  
|<span data-ttu-id="94311-115">**A4SWIFT_FrrFailedReason**</span><span class="sxs-lookup"><span data-stu-id="94311-115">**A4SWIFT_FrrFailedReason**</span></span>|<span data-ttu-id="94311-116">元のメッセージが処理されなかったことが正常に SAA/SWIFT によってを示します。</span><span class="sxs-lookup"><span data-stu-id="94311-116">Indicates that the original message was not successfully processed by SAA/SWIFT.</span></span>|<span data-ttu-id="94311-117">文字列</span><span class="sxs-lookup"><span data-stu-id="94311-117">String</span></span>|<span data-ttu-id="94311-118">-   \<NAKErrorCode ></span><span class="sxs-lookup"><span data-stu-id="94311-118">-   \<NAKErrorCode></span></span><br /><span data-ttu-id="94311-119">はタイムアウトしました</span><span class="sxs-lookup"><span data-stu-id="94311-119">-   TimedOut</span></span><br /><span data-ttu-id="94311-120">-TransportError</span><span class="sxs-lookup"><span data-stu-id="94311-120">-   TransportError</span></span><br /><span data-ttu-id="94311-121">-Delayed_NAK</span><span class="sxs-lookup"><span data-stu-id="94311-121">-   Delayed_NAK</span></span><br /><span data-ttu-id="94311-122">-AbortReceived</span><span class="sxs-lookup"><span data-stu-id="94311-122">-   AbortReceived</span></span>|<span data-ttu-id="94311-123">カスタム ハンドラーに障害が発生したメッセージを送信する FRR 送信ポートのフィルター式で使用します。</span><span class="sxs-lookup"><span data-stu-id="94311-123">Used in the filter expression of an FRR send port to send a failed message to a custom handler.</span></span>|  
|<span data-ttu-id="94311-124">**A4SWIFT_FRRCorrelationToken**</span><span class="sxs-lookup"><span data-stu-id="94311-124">**A4SWIFT_FRRCorrelationToken**</span></span>|<span data-ttu-id="94311-125">送信 MT の一意の関連付けトークンを示す*xxx*メッセージ。</span><span class="sxs-lookup"><span data-stu-id="94311-125">Indicates the unique correlation token of the outbound MT*xxx* message.</span></span>|<span data-ttu-id="94311-126">文字列</span><span class="sxs-lookup"><span data-stu-id="94311-126">String</span></span>|-|<span data-ttu-id="94311-127">FRR が、このプロパティを比較し、 **MQMD_CorrelID** FIN 応答のコンテキスト プロパティです。</span><span class="sxs-lookup"><span data-stu-id="94311-127">FRR compares this property to the **MQMD_CorrelID** context property of the FIN response.</span></span>|  
|<span data-ttu-id="94311-128">**A4SWIFT_SendingServiceType**</span><span class="sxs-lookup"><span data-stu-id="94311-128">**A4SWIFT_SendingServiceType**</span></span>|<span data-ttu-id="94311-129">FRR サービス メッセージを送信することを示します。</span><span class="sxs-lookup"><span data-stu-id="94311-129">Indicates the FRR service that sends the message.</span></span>|<span data-ttu-id="94311-130">文字列</span><span class="sxs-lookup"><span data-stu-id="94311-130">String</span></span>|<span data-ttu-id="94311-131">A4SWIFT_FrrService</span><span class="sxs-lookup"><span data-stu-id="94311-131">A4SWIFT_FrrService</span></span>|<span data-ttu-id="94311-132">昇格させた場合**A4SWIFT_FRRFailed**が True に設定します。</span><span class="sxs-lookup"><span data-stu-id="94311-132">Promoted when **A4SWIFT_FRRFailed** is set to True.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="94311-133">参照</span><span class="sxs-lookup"><span data-stu-id="94311-133">See Also</span></span>  
 <span data-ttu-id="94311-134">[A4SWIFT_ * 昇格させたプロパティ](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md) </span><span class="sxs-lookup"><span data-stu-id="94311-134">[A4SWIFT_* Promoted Properties](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md) </span></span>  
 [<span data-ttu-id="94311-135">Message Repair and New Submission の昇格させたプロパティ</span><span class="sxs-lookup"><span data-stu-id="94311-135">Message Repair and New Submission Promoted Properties</span></span>](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission-promoted-properties.md)
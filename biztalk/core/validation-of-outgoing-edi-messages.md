---
title: "送信 EDI メッセージの検証 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 491303c0-b585-409e-a289-a2f6f9f82469
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 946e90eb58c9b81e0cd7fa9bf2c02cc49af021ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="validation-of-outgoing-edi-messages"></a><span data-ttu-id="67ffe-102">送信 EDI メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="67ffe-102">Validation of Outgoing EDI Messages</span></span>
<span data-ttu-id="67ffe-103">EDI 送信パイプラインは、送信対象のメッセージを処理するとき、エンベロープとメッセージ データに対して一連の検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="67ffe-103">When the EDI send pipeline processes a message to be sent, it performs a series of validations on the envelope and message data.</span></span> <span data-ttu-id="67ffe-104">これらの処理のうちの一部は常に実行されますが、有効にした場合にのみ実行される処理もあります。</span><span class="sxs-lookup"><span data-stu-id="67ffe-104">Some of these processes are always performed; some are performed only if you enable them.</span></span> <span data-ttu-id="67ffe-105">これらの検証には、以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="67ffe-105">These validations include the following:</span></span>  
  
-   <span data-ttu-id="67ffe-106">トランザクション セットのデータ要素のメッセージ スキーマに対するスキーマ検証。</span><span class="sxs-lookup"><span data-stu-id="67ffe-106">Schema validation of the transaction-set data elements against the message schema.</span></span> <span data-ttu-id="67ffe-107">これは常に実行されます。</span><span class="sxs-lookup"><span data-stu-id="67ffe-107">This is always performed.</span></span>  
  
-   <span data-ttu-id="67ffe-108">トランザクション セットのデータ要素に対するクロスフィールド検証 (X12 でエンコードされたメッセージのみ)。</span><span class="sxs-lookup"><span data-stu-id="67ffe-108">Cross-field validation on transaction set data elements (X12-encoded messages only).</span></span> <span data-ttu-id="67ffe-109">これは、メッセージ スキーマで有効になっている場合に実行されます。</span><span class="sxs-lookup"><span data-stu-id="67ffe-109">This is performed if it is enabled in the message schema.</span></span>  
  
-   <span data-ttu-id="67ffe-110">トランザクション セットのデータ要素に対して実行される EDI 検証。</span><span class="sxs-lookup"><span data-stu-id="67ffe-110">EDI validation performed on transaction-set data elements.</span></span> <span data-ttu-id="67ffe-111">これは、ような状況は、アグリーメントでプロパティが有効な場合に実行されます。</span><span class="sxs-lookup"><span data-stu-id="67ffe-111">This is performed if enabled in agreement properties.</span></span>  
  
-   <span data-ttu-id="67ffe-112">トランザクション セットのデータ要素に対して実行される拡張検証。</span><span class="sxs-lookup"><span data-stu-id="67ffe-112">Extended validation performed on transaction-set data elements.</span></span> <span data-ttu-id="67ffe-113">これは、ような状況は、アグリーメントでプロパティが有効な場合に実行されます。</span><span class="sxs-lookup"><span data-stu-id="67ffe-113">This is performed if enabled in agreement properties.</span></span>  
  
-   <span data-ttu-id="67ffe-114">X12 標準に準拠した、トランザクション セットとグループのマッピングに基づく、単一のグループ内のトランザクション セットの検証。</span><span class="sxs-lookup"><span data-stu-id="67ffe-114">Validation of the transaction sets within a single group based on the transaction set – group mapping, according to X12 standards.</span></span> <span data-ttu-id="67ffe-115">これは、実行される場合にのみ、**受信バッチ処理オプション**プロパティに設定されている**インターチェンジの保存 - エラーでインターチェンジを中断**または**インターチェンジのトランザクションを中断エラーの設定**です。</span><span class="sxs-lookup"><span data-stu-id="67ffe-115">This is performed only when the **Inbound batch processing option** property is set to **Preserve Interchange - suspend Interchange on Error** or **Preserve Interchange - suspend Transaction Sets on Error**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67ffe-116">参照</span><span class="sxs-lookup"><span data-stu-id="67ffe-116">See Also</span></span>  
 <span data-ttu-id="67ffe-117">[EDI 構造検証](../core/edi-structural-validation.md) </span><span class="sxs-lookup"><span data-stu-id="67ffe-117">[EDI Structural Validation](../core/edi-structural-validation.md) </span></span>  
 <span data-ttu-id="67ffe-118">[アグリーメントのプロパティの検証](../core/agreement-properties-validation.md) </span><span class="sxs-lookup"><span data-stu-id="67ffe-118">[Agreement Properties Validation](../core/agreement-properties-validation.md) </span></span>  
 <span data-ttu-id="67ffe-119">[EDI の種類 (データ要素) の検証](../core/edi-type-data-element-validation.md) </span><span class="sxs-lookup"><span data-stu-id="67ffe-119">[EDI Type (Data Element) Validation](../core/edi-type-data-element-validation.md) </span></span>  
 <span data-ttu-id="67ffe-120">[拡張 (BTS-XSD) 検証](../core/extended-bts-xsd-validation.md) </span><span class="sxs-lookup"><span data-stu-id="67ffe-120">[Extended (BTS-XSD) Validation](../core/extended-bts-xsd-validation.md) </span></span>  
 <span data-ttu-id="67ffe-121">[スキーマの検証](../core/schema-validation2.md) </span><span class="sxs-lookup"><span data-stu-id="67ffe-121">[Schema Validation](../core/schema-validation2.md) </span></span>  
 [<span data-ttu-id="67ffe-122">クロス フィールド セグメント検証</span><span class="sxs-lookup"><span data-stu-id="67ffe-122">Cross Field-Segment Validation</span></span>](../core/cross-field-segment-validation.md)
---
title: 受信した EDI メッセージの検証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c56a3c0-042e-4611-8131-d51098064f0f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1af8946cf94747f74db25d1854d2157a36370cbc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292600"
---
# <a name="validation-of-received-edi-messages"></a><span data-ttu-id="f22ff-102">受信した EDI メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="f22ff-102">Validation of Received EDI Messages</span></span>
<span data-ttu-id="f22ff-103">EDI 受信パイプライン、受信メッセージの処理、エンベロープとメッセージのデータに対して一連の検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="f22ff-103">When the EDI receive pipeline processes an incoming message, it performs a series of validations on the envelope and message data.</span></span> <span data-ttu-id="f22ff-104">これらのプロセスの一部は常に実行します。一部は、それらを有効にした場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="f22ff-104">Some of these processes are always performed; some are performed only if you enable them.</span></span> <span data-ttu-id="f22ff-105">これらの検証を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="f22ff-105">These validations include the following:</span></span>  
  
-   <span data-ttu-id="f22ff-106">**常に実行される検証は**:</span><span class="sxs-lookup"><span data-stu-id="f22ff-106">**The validations that are always performed are**:</span></span>  
  
    -   <span data-ttu-id="f22ff-107">インターチェンジのエンベロープの構造の検証。</span><span class="sxs-lookup"><span data-stu-id="f22ff-107">Validation of the structure of the interchange envelope.</span></span>  
  
    -   <span data-ttu-id="f22ff-108">取引パートナー契約 (またはアグリーメントが定義されていない場合はフォールバック アグリーメント) に対するエンベロープの検証。</span><span class="sxs-lookup"><span data-stu-id="f22ff-108">Validation of the envelope against trading partner agreement (or fallback agreement if no agreement is defined).</span></span>  
  
    -   <span data-ttu-id="f22ff-109">制御スキーマと照らし合わせたエンベロープのスキーマの検証。</span><span class="sxs-lookup"><span data-stu-id="f22ff-109">Schema validation of the envelope against the control schema.</span></span>  
  
    -   <span data-ttu-id="f22ff-110">メッセージ スキーマと照らし合わせたトランザクション セット データ要素のスキーマの検証。</span><span class="sxs-lookup"><span data-stu-id="f22ff-110">Schema validation of the transaction-set data elements against the message schema.</span></span>  
  
    -   <span data-ttu-id="f22ff-111">トランザクションに基づく単一グループ内のトランザクションの種類の検証の設定グループ マッピングは設定されている X12 で提供されている標準です。</span><span class="sxs-lookup"><span data-stu-id="f22ff-111">Validation of the types of transaction sets within a single group based on the transaction set -group mapping provided by X12 standards.</span></span>  
  
-   <span data-ttu-id="f22ff-112">**有効になっている場合にのみ実行される検証は**:</span><span class="sxs-lookup"><span data-stu-id="f22ff-112">**The validations that are performed only if enabled are**:</span></span>  
  
    -   <span data-ttu-id="f22ff-113">トランザクション セット データ要素に対して EDI の検証が実行されます。</span><span class="sxs-lookup"><span data-stu-id="f22ff-113">EDI validation performed on transaction-set data elements.</span></span> <span data-ttu-id="f22ff-114">これは、アグリーメントのプロパティで有効になっている場合に実行されます。</span><span class="sxs-lookup"><span data-stu-id="f22ff-114">This is performed if enabled in the agreement properties.</span></span>  
  
    -   <span data-ttu-id="f22ff-115">トランザクション セット データ要素に対して実行される拡張検証。</span><span class="sxs-lookup"><span data-stu-id="f22ff-115">Extended validation performed on transaction-set data elements.</span></span> <span data-ttu-id="f22ff-116">これは、アグリーメントのプロパティで有効になっている場合に実行されます。</span><span class="sxs-lookup"><span data-stu-id="f22ff-116">This is performed if enabled in the agreement properties.</span></span>  
  
    -   <span data-ttu-id="f22ff-117">クロス フィールド検証トランザクションでは、データ要素 (X12 でエンコードされたメッセージのみ) を設定します。</span><span class="sxs-lookup"><span data-stu-id="f22ff-117">Cross-field validation on transaction set data elements (X12-encoded messages only).</span></span> <span data-ttu-id="f22ff-118">これは、メッセージのスキーマで有効になっている場合に実行されます。</span><span class="sxs-lookup"><span data-stu-id="f22ff-118">This is performed if enabled in the message schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f22ff-119">参照</span><span class="sxs-lookup"><span data-stu-id="f22ff-119">See Also</span></span>  
 <span data-ttu-id="f22ff-120">[EDI 構造検証](../core/edi-structural-validation.md) </span><span class="sxs-lookup"><span data-stu-id="f22ff-120">[EDI Structural Validation](../core/edi-structural-validation.md) </span></span>  
 <span data-ttu-id="f22ff-121">[アグリーメントのプロパティの検証](../core/agreement-properties-validation.md) </span><span class="sxs-lookup"><span data-stu-id="f22ff-121">[Agreement Properties Validation](../core/agreement-properties-validation.md) </span></span>  
 <span data-ttu-id="f22ff-122">[EDI の種類 (データ要素) 検証](../core/edi-type-data-element-validation.md) </span><span class="sxs-lookup"><span data-stu-id="f22ff-122">[EDI Type (Data Element) Validation](../core/edi-type-data-element-validation.md) </span></span>  
 <span data-ttu-id="f22ff-123">[拡張された (BTS-XSD) 検証](../core/extended-bts-xsd-validation.md) </span><span class="sxs-lookup"><span data-stu-id="f22ff-123">[Extended (BTS-XSD) Validation](../core/extended-bts-xsd-validation.md) </span></span>  
 <span data-ttu-id="f22ff-124">[スキーマの検証](../core/schema-validation2.md) </span><span class="sxs-lookup"><span data-stu-id="f22ff-124">[Schema Validation](../core/schema-validation2.md) </span></span>  
 [<span data-ttu-id="f22ff-125">クロスフィールド/セグメント検証</span><span class="sxs-lookup"><span data-stu-id="f22ff-125">Cross Field-Segment Validation</span></span>](../core/cross-field-segment-validation.md)
---
title: 送信 EDI メッセージの検証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 491303c0-b585-409e-a289-a2f6f9f82469
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01e0afed109f3ea03e863e2813ca4f58d289eaa0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295654"
---
# <a name="validation-of-outgoing-edi-messages"></a><span data-ttu-id="9f8ae-102">送信 EDI メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="9f8ae-102">Validation of Outgoing EDI Messages</span></span>
<span data-ttu-id="9f8ae-103">EDI 送信パイプラインが送信されるメッセージを処理するとき、エンベロープとメッセージ データに対して一連の検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="9f8ae-103">When the EDI send pipeline processes a message to be sent, it performs a series of validations on the envelope and message data.</span></span> <span data-ttu-id="9f8ae-104">これらのプロセスの一部は常に実行します。一部は、それらを有効にした場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="9f8ae-104">Some of these processes are always performed; some are performed only if you enable them.</span></span> <span data-ttu-id="9f8ae-105">これらの検証を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="9f8ae-105">These validations include the following:</span></span>  
  
-   <span data-ttu-id="9f8ae-106">メッセージ スキーマと照らし合わせたトランザクション セット データ要素のスキーマの検証。</span><span class="sxs-lookup"><span data-stu-id="9f8ae-106">Schema validation of the transaction-set data elements against the message schema.</span></span> <span data-ttu-id="9f8ae-107">これは常に実行します。</span><span class="sxs-lookup"><span data-stu-id="9f8ae-107">This is always performed.</span></span>  
  
-   <span data-ttu-id="9f8ae-108">クロス フィールド検証トランザクションでは、データ要素 (X12 でエンコードされたメッセージのみ) を設定します。</span><span class="sxs-lookup"><span data-stu-id="9f8ae-108">Cross-field validation on transaction set data elements (X12-encoded messages only).</span></span> <span data-ttu-id="9f8ae-109">これは、メッセージのスキーマで有効になっている場合に実行されます。</span><span class="sxs-lookup"><span data-stu-id="9f8ae-109">This is performed if it is enabled in the message schema.</span></span>  
  
-   <span data-ttu-id="9f8ae-110">トランザクション セット データ要素に対して EDI の検証が実行されます。</span><span class="sxs-lookup"><span data-stu-id="9f8ae-110">EDI validation performed on transaction-set data elements.</span></span> <span data-ttu-id="9f8ae-111">これは、アグリーメントでプロパティを有効にした場合に実行されます。</span><span class="sxs-lookup"><span data-stu-id="9f8ae-111">This is performed if enabled in agreement properties.</span></span>  
  
-   <span data-ttu-id="9f8ae-112">トランザクション セット データ要素に対して実行される拡張検証。</span><span class="sxs-lookup"><span data-stu-id="9f8ae-112">Extended validation performed on transaction-set data elements.</span></span> <span data-ttu-id="9f8ae-113">これは、アグリーメントでプロパティを有効にした場合に実行されます。</span><span class="sxs-lookup"><span data-stu-id="9f8ae-113">This is performed if enabled in agreement properties.</span></span>  
  
-   <span data-ttu-id="9f8ae-114">トランザクションの検証の設定グループのマッピングに x12 トランザクション セットに基づく単一グループ内の標準です。</span><span class="sxs-lookup"><span data-stu-id="9f8ae-114">Validation of the transaction sets within a single group based on the transaction set – group mapping, according to X12 standards.</span></span> <span data-ttu-id="9f8ae-115">これを行う場合にのみ、**受信バッチ処理オプション**プロパティに設定されて**インターチェンジの保存 - エラーでインターチェンジを中断**または**インターチェンジの保存 - トランザクションを中断エラーの設定**します。</span><span class="sxs-lookup"><span data-stu-id="9f8ae-115">This is performed only when the **Inbound batch processing option** property is set to **Preserve Interchange - suspend Interchange on Error** or **Preserve Interchange - suspend Transaction Sets on Error**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f8ae-116">参照</span><span class="sxs-lookup"><span data-stu-id="9f8ae-116">See Also</span></span>  
 <span data-ttu-id="9f8ae-117">[EDI 構造検証](../core/edi-structural-validation.md) </span><span class="sxs-lookup"><span data-stu-id="9f8ae-117">[EDI Structural Validation](../core/edi-structural-validation.md) </span></span>  
 <span data-ttu-id="9f8ae-118">[アグリーメントのプロパティの検証](../core/agreement-properties-validation.md) </span><span class="sxs-lookup"><span data-stu-id="9f8ae-118">[Agreement Properties Validation](../core/agreement-properties-validation.md) </span></span>  
 <span data-ttu-id="9f8ae-119">[EDI の種類 (データ要素) 検証](../core/edi-type-data-element-validation.md) </span><span class="sxs-lookup"><span data-stu-id="9f8ae-119">[EDI Type (Data Element) Validation](../core/edi-type-data-element-validation.md) </span></span>  
 <span data-ttu-id="9f8ae-120">[拡張された (BTS-XSD) 検証](../core/extended-bts-xsd-validation.md) </span><span class="sxs-lookup"><span data-stu-id="9f8ae-120">[Extended (BTS-XSD) Validation](../core/extended-bts-xsd-validation.md) </span></span>  
 <span data-ttu-id="9f8ae-121">[スキーマの検証](../core/schema-validation2.md) </span><span class="sxs-lookup"><span data-stu-id="9f8ae-121">[Schema Validation](../core/schema-validation2.md) </span></span>  
 [<span data-ttu-id="9f8ae-122">クロスフィールド/セグメント検証</span><span class="sxs-lookup"><span data-stu-id="9f8ae-122">Cross Field-Segment Validation</span></span>](../core/cross-field-segment-validation.md)
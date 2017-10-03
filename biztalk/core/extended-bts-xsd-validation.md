---
title: "拡張された (BTS-XSD) 検証 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f225115d-8890-4149-8e46-d1bc8af17e62
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed147515b48a23c55e552710d6a76d6df981edd7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="extended-bts-xsd-validation"></a><span data-ttu-id="58982-102">拡張された (BTS-XSD) 検証</span><span class="sxs-lookup"><span data-stu-id="58982-102">Extended (BTS-XSD) Validation</span></span>
<span data-ttu-id="58982-103">EDI 受信パイプラインと EDI 送信パイプラインは、データ型が EDI データ型ではない要素を使用してスキーマがカスタマイズされている場合にのみ、拡張された検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="58982-103">The EDI receive pipeline and EDI send pipeline perform extended validation only if the schema has been customized with elements whose data type is not an EDI data type.</span></span> <span data-ttu-id="58982-104">これらの追加された要素は、EDI 検証では検証されず、拡張された検証の対象にもなりません。</span><span class="sxs-lookup"><span data-stu-id="58982-104">These added elements would not be validated by EDI validation, so will be covered by extended validation.</span></span> <span data-ttu-id="58982-105">拡張された検証には `System.Xml.XmlValidatingReader` が使用され、標準 XSD に定義可能なすべてのチェックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="58982-105">Extended validation uses `System.Xml.XmlValidatingReader` and includes all checks that can be defined in a standard XSD.</span></span>  
  
 <span data-ttu-id="58982-106">拡張された検証は、パーティに対して送受信するすべてのメッセージに構成できます。</span><span class="sxs-lookup"><span data-stu-id="58982-106">You configure extended validation for all messages to or from a party.</span></span> <span data-ttu-id="58982-107">選択してこれを行う、 **Extended Validation**のチェック ボックス、**検証**ページ (下にある、**トランザクション セットの設定**X12 または EDIFACT のいずれかのセクション) で、一方向アグリーメント タブで、**アグリーメントのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="58982-107">You do so by selecting the **Extended Validation** checkbox in the **Validation** page (under the **Transaction Set Settings** section for either X12 or EDIFACT), on the one-way agreement tab in the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="58982-108">拡張された検証を有効にするために、EDI 検証を有効にする必要はありません。同様に、EDI 検証を有効にするために、拡張された検証を有効にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="58982-108">You can enable extension validation without enabling EDI validation, or vice versa.</span></span>  
  
 <span data-ttu-id="58982-109">拡張された検証では、次のチェックが行われます。</span><span class="sxs-lookup"><span data-stu-id="58982-109">Extended validation consists of the following checks:</span></span>  
  
-   <span data-ttu-id="58982-110">データ要素要件および使用可能な繰り返し</span><span class="sxs-lookup"><span data-stu-id="58982-110">Data element requirement and allowed repetition</span></span>  
  
-   <span data-ttu-id="58982-111">列挙型</span><span class="sxs-lookup"><span data-stu-id="58982-111">Enumerations</span></span>  
  
-   <span data-ttu-id="58982-112">データ要素の長さの検証 (最小/最大)</span><span class="sxs-lookup"><span data-stu-id="58982-112">Data element length validation (min/max).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="58982-113">EDI 送信側のバッチ メッセージの Extended Validation はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="58982-113">Extended Validation for batched messages on the EDI send side is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58982-114">参照</span><span class="sxs-lookup"><span data-stu-id="58982-114">See Also</span></span>  
 [<span data-ttu-id="58982-115">EDI メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="58982-115">EDI Message Validation</span></span>](../core/edi-message-validation.md)
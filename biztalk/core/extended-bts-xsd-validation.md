---
title: 拡張された (BTS-XSD) 検証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f225115d-8890-4149-8e46-d1bc8af17e62
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65f102e1d5a182b729af164a83efa8f20be49ba7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345920"
---
# <a name="extended-bts-xsd-validation"></a><span data-ttu-id="3342f-102">拡張された (BTS-XSD) 検証</span><span class="sxs-lookup"><span data-stu-id="3342f-102">Extended (BTS-XSD) Validation</span></span>
<span data-ttu-id="3342f-103">EDI 受信パイプラインと EDI 送信パイプラインがデータ型が EDI データ型ではない要素を持つスキーマがカスタマイズされている場合にのみ、拡張された検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="3342f-103">The EDI receive pipeline and EDI send pipeline perform extended validation only if the schema has been customized with elements whose data type is not an EDI data type.</span></span> <span data-ttu-id="3342f-104">これらの追加要素は、拡張された検証の対象に、EDI 検証では検証されません。</span><span class="sxs-lookup"><span data-stu-id="3342f-104">These added elements would not be validated by EDI validation, so will be covered by extended validation.</span></span> <span data-ttu-id="3342f-105">検証の使用を拡張`System.Xml.XmlValidatingReader`標準 XSD に定義できるすべてのチェックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3342f-105">Extended validation uses `System.Xml.XmlValidatingReader` and includes all checks that can be defined in a standard XSD.</span></span>  
  
 <span data-ttu-id="3342f-106">パーティとの間のすべてのメッセージの extended validation を構成します。</span><span class="sxs-lookup"><span data-stu-id="3342f-106">You configure extended validation for all messages to or from a party.</span></span> <span data-ttu-id="3342f-107">選択してこれを行う、 **Extended Validation**でチェック ボックスをオン、**検証**ページ (下、**トランザクション セットの設定**X12 または EDIFACT のいずれかのセクション) で、一方向アグリーメント タブで、**アグリーメントのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="3342f-107">You do so by selecting the **Extended Validation** checkbox in the **Validation** page (under the **Transaction Set Settings** section for either X12 or EDIFACT), on the one-way agreement tab in the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="3342f-108">EDI の検証を有効にしなくても拡張機能の検証を有効にすることができますまたはその逆です。</span><span class="sxs-lookup"><span data-stu-id="3342f-108">You can enable extension validation without enabling EDI validation, or vice versa.</span></span>  
  
 <span data-ttu-id="3342f-109">拡張された検証は、次のチェックで構成されます。</span><span class="sxs-lookup"><span data-stu-id="3342f-109">Extended validation consists of the following checks:</span></span>  
  
-   <span data-ttu-id="3342f-110">データ要素の要件と使用可能な繰り返し</span><span class="sxs-lookup"><span data-stu-id="3342f-110">Data element requirement and allowed repetition</span></span>  
  
-   <span data-ttu-id="3342f-111">列挙</span><span class="sxs-lookup"><span data-stu-id="3342f-111">Enumerations</span></span>  
  
-   <span data-ttu-id="3342f-112">データ要素の長さの検証 (最小/最大)。</span><span class="sxs-lookup"><span data-stu-id="3342f-112">Data element length validation (min/max).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3342f-113">EDI 送信側バッチ処理されたメッセージの extended Validation はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3342f-113">Extended Validation for batched messages on the EDI send side is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3342f-114">参照</span><span class="sxs-lookup"><span data-stu-id="3342f-114">See Also</span></span>  
 [<span data-ttu-id="3342f-115">EDI メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="3342f-115">EDI Message Validation</span></span>](../core/edi-message-validation.md)
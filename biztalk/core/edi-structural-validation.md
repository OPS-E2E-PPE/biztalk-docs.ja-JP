---
title: EDI 構造検証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87086614-5616-441d-915c-2979c63c6e2f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 422449a9720b78a65b4934fbf17d255e84678613
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350223"
---
# <a name="edi-structural-validation"></a><span data-ttu-id="b1632-102">EDI 構造検証</span><span class="sxs-lookup"><span data-stu-id="b1632-102">EDI Structural Validation</span></span>
<span data-ttu-id="b1632-103">X12 と EDIFACT エンコードの両方の EDI 仕様では、特定の規則と EDI インターチェンジの構造に関する規則を定義します。</span><span class="sxs-lookup"><span data-stu-id="b1632-103">EDI specifications for both X12 and EDIFACT encoding define specific rules and conventions for the structure of EDI interchanges.</span></span> <span data-ttu-id="b1632-104">EDIReceivePipeline で EDI 逆アセンブラーは、各受信メッセージのエンベロープがこれらの構造上のルールに準拠しているかを確認します。</span><span class="sxs-lookup"><span data-stu-id="b1632-104">The EDI Disassembler in the EDIReceivePipeline verifies that the envelope of each received message complies with these structural rules.</span></span> <span data-ttu-id="b1632-105">EDISendPipeline は、これらの規則に従って送信するには、各メッセージを作成し、送信する前に、エンベロープを検証します。</span><span class="sxs-lookup"><span data-stu-id="b1632-105">The EDISendPipeline builds each message to be sent in accordance with these rules and validates the envelope before sending.</span></span>  
  
 <span data-ttu-id="b1632-106">構造の検証では、必要なヘッダーとトレーラーが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="b1632-106">The structural validation ensures that the required headers and trailers are present.</span></span> <span data-ttu-id="b1632-107">セグメントとループの順序を含めるし、数がチェックされます構造的整合性を確認します。</span><span class="sxs-lookup"><span data-stu-id="b1632-107">The structural integrity checks include segment and loop ordering and count checks.</span></span> <span data-ttu-id="b1632-108">これらのチェックは、ドキュメントの解析または正しくシリアル化することを確認して常に実行されます。</span><span class="sxs-lookup"><span data-stu-id="b1632-108">These checks are always performed to ensure that the document will parse or serialize correctly.</span></span> <span data-ttu-id="b1632-109">この検証が実行される場合でも、 **EDI 型の検証**や**Extended Validation**オプションが無効になります。</span><span class="sxs-lookup"><span data-stu-id="b1632-109">This validation is performed even if the **EDI Type Validation** and/or **Extended Validation** options are disabled.</span></span> <span data-ttu-id="b1632-110">基本的な構造検証に失敗したインターチェンジは中断される場合でも、 **EDI 型の検証**や**Extended Validation**オプションが無効になります。</span><span class="sxs-lookup"><span data-stu-id="b1632-110">An interchange that fails the basic structural validations will be suspended, even if the **EDI Type Validation** and/or **Extended Validation** options are disabled.</span></span>  
  
 <span data-ttu-id="b1632-111">ヘッダーとトレーラー、内のデータ要素およびヘッダー/トレーラとデータ要素を区切る方法の値は、契約によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="b1632-111">The values of the data elements within the headers and trailers, and how the headers/trailers and data elements are separated, are determined by the agreement.</span></span> <span data-ttu-id="b1632-112">スキーマの検証によって検証されます。</span><span class="sxs-lookup"><span data-stu-id="b1632-112">These are validated through schema validation.</span></span>  
  
 <span data-ttu-id="b1632-113">エンベロープとヘッダーとトレーラーの各セット内の内容の詳細については、次を参照してください。 [EDI メッセージの構造](../core/edi-message-structure.md)します。</span><span class="sxs-lookup"><span data-stu-id="b1632-113">For more information about the envelope and the contents within each set of headers and trailers, see [EDI Message Structure](../core/edi-message-structure.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1632-114">参照</span><span class="sxs-lookup"><span data-stu-id="b1632-114">See Also</span></span>  
 [<span data-ttu-id="b1632-115">EDI メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="b1632-115">EDI Message Validation</span></span>](../core/edi-message-validation.md)
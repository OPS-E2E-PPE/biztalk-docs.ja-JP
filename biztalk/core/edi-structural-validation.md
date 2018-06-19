---
title: EDI 構造検証 |Microsoft ドキュメント
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
ms.openlocfilehash: 505b9ac55eff0b6adb249d11788308f03902f1d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239594"
---
# <a name="edi-structural-validation"></a><span data-ttu-id="1da0e-102">EDI 構造の検証</span><span class="sxs-lookup"><span data-stu-id="1da0e-102">EDI Structural Validation</span></span>
<span data-ttu-id="1da0e-103">X12 エンコードと EDIFACT エンコードのどちらの EDI 仕様にも、EDI インターチェンジの構造に固有の規則と規約が定義されています。</span><span class="sxs-lookup"><span data-stu-id="1da0e-103">EDI specifications for both X12 and EDIFACT encoding define specific rules and conventions for the structure of EDI interchanges.</span></span> <span data-ttu-id="1da0e-104">EDIReceivePipeline で EDI 逆アセンブラーでは、各受信したメッセージのエンベロープがこれらの構造の規則に準拠していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1da0e-104">The EDI Disassembler in the EDIReceivePipeline verifies that the envelope of each received message complies with these structural rules.</span></span> <span data-ttu-id="1da0e-105">EDISendPipeline は、送信する各メッセージをこれらの規則に基づいて構築し、送信前にエンベロープを検証します。</span><span class="sxs-lookup"><span data-stu-id="1da0e-105">The EDISendPipeline builds each message to be sent in accordance with these rules and validates the envelope before sending.</span></span>  
  
 <span data-ttu-id="1da0e-106">この構造検証では、必要なヘッダーとトレーラーが含まれているかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="1da0e-106">The structural validation ensures that the required headers and trailers are present.</span></span> <span data-ttu-id="1da0e-107">構造的整合性チェックでは、セグメントとループの順序と数がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="1da0e-107">The structural integrity checks include segment and loop ordering and count checks.</span></span> <span data-ttu-id="1da0e-108">これらのチェックは、ドキュメントの解析またはシリアル化が正しく行われるようにするために、必ず実行されます。</span><span class="sxs-lookup"><span data-stu-id="1da0e-108">These checks are always performed to ensure that the document will parse or serialize correctly.</span></span> <span data-ttu-id="1da0e-109">この検証が実行される場合でも、 **EDI 型の検証**や**Extended Validation**オプションが無効になります。</span><span class="sxs-lookup"><span data-stu-id="1da0e-109">This validation is performed even if the **EDI Type Validation** and/or **Extended Validation** options are disabled.</span></span> <span data-ttu-id="1da0e-110">基本的な構造検証に失敗したインターチェンジは中断される場合でも、 **EDI 型の検証**や**Extended Validation**オプションが無効になります。</span><span class="sxs-lookup"><span data-stu-id="1da0e-110">An interchange that fails the basic structural validations will be suspended, even if the **EDI Type Validation** and/or **Extended Validation** options are disabled.</span></span>  
  
 <span data-ttu-id="1da0e-111">ヘッダーとトレーラー内のデータ要素の値、およびヘッダー/トレーラーとデータ要素をどのように分離するかは、アグリーメントによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="1da0e-111">The values of the data elements within the headers and trailers, and how the headers/trailers and data elements are separated, are determined by the agreement.</span></span> <span data-ttu-id="1da0e-112">スキーマ検証によって検証されます。</span><span class="sxs-lookup"><span data-stu-id="1da0e-112">These are validated through schema validation.</span></span>  
  
 <span data-ttu-id="1da0e-113">エンベロープとヘッダーとトレーラーの各セット内の内容の詳細については、次を参照してください。 [EDI メッセージの構造体](../core/edi-message-structure.md)です。</span><span class="sxs-lookup"><span data-stu-id="1da0e-113">For more information about the envelope and the contents within each set of headers and trailers, see [EDI Message Structure](../core/edi-message-structure.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1da0e-114">参照</span><span class="sxs-lookup"><span data-stu-id="1da0e-114">See Also</span></span>  
 [<span data-ttu-id="1da0e-115">EDI メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="1da0e-115">EDI Message Validation</span></span>](../core/edi-message-validation.md)
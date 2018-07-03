---
title: 区切り記号の既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- known issues, delimiters
- delimiters
ms.assetid: 4eaacb3c-9d8d-43da-91dd-8bb25dec70e1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6de686d136d0158315dfd00eba9690b8ffcbdccc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985651"
---
# <a name="delimiters-known-issues"></a><span data-ttu-id="9a305-102">区切り記号の既知の問題</span><span class="sxs-lookup"><span data-stu-id="9a305-102">Delimiters Known Issues</span></span>
<span data-ttu-id="9a305-103">このセクションには、区切り記号のエラーを回避するために役立つ有用な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9a305-103">This section contains useful information that may help you avoid delimiter errors.</span></span>  
  
## <a name="characters-not-recommended-to-be-used-as-delimiters"></a><span data-ttu-id="9a305-104">文字が区切り記号として使用することをお勧めしません</span><span class="sxs-lookup"><span data-stu-id="9a305-104">Characters not recommended to be used as delimiters</span></span>  
 <span data-ttu-id="9a305-105">使用することはない、次の文字区切り記号としてエラーが発生する可能性がありますをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9a305-105">It is recommended that you do not use the following characters as delimiters as they might cause errors:</span></span>  
  
-   <span data-ttu-id="9a305-106">Null 文字</span><span class="sxs-lookup"><span data-stu-id="9a305-106">Null characters</span></span>  
  
-   <span data-ttu-id="9a305-107">スペース</span><span class="sxs-lookup"><span data-stu-id="9a305-107">Spaces</span></span>  
  
## <a name="extra-delimiters-in-a-header-or-body-field-cause-multiple-errors"></a><span data-ttu-id="9a305-108">複数のエラーが発生する、ヘッダーまたは本文フィールド内の余分な区切り記号</span><span class="sxs-lookup"><span data-stu-id="9a305-108">Extra delimiters in a header or body field cause multiple errors</span></span>  
 <span data-ttu-id="9a305-109">HL7 V2 を内のフィールドに追加の区切り記号がある場合は。X のメッセージ、Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) パーサーは 2 つのエラー メッセージを生成可能性があります XML 検証に関連する 1 つと、構造の検証に関連する他のです。</span><span class="sxs-lookup"><span data-stu-id="9a305-109">When you have an extra delimiter in a field in an HL7 V2.X message, the Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) parser might generate two error messages, one related to XML validation and the other related to structural validation.</span></span>  
  
## <a name="trailing-delimiters-permitted-in-hl7-batch-segments"></a><span data-ttu-id="9a305-110">HL7 バッチ セグメントで許可されている末尾の区切り記号</span><span class="sxs-lookup"><span data-stu-id="9a305-110">Trailing delimiters permitted in HL7 batch segments</span></span>  
 <span data-ttu-id="9a305-111">HL7 のために末尾の区切り記号があることができ、末尾の区切り記号フラグでは、必ずしも FHS、BHS、BTS、および FTS など batch セグメントを定義した[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]セグメントをバッチ処理の末尾の区切り記号を検証しません。</span><span class="sxs-lookup"><span data-stu-id="9a305-111">HL7 defined batch segments such as FHS, BHS, BTS, and FTS can have trailing delimiters and are not constrained by the trailing delimiter flag, because [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does not validate trailing delimiters for batching segments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a305-112">参照</span><span class="sxs-lookup"><span data-stu-id="9a305-112">See Also</span></span>  
 [<span data-ttu-id="9a305-113">既知の問題</span><span class="sxs-lookup"><span data-stu-id="9a305-113">Known Issues</span></span>](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)
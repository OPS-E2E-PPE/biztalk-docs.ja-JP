---
title: "宣言されていないカスタマイズ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- undeclared customizations
- Z objects, undeclared customizations
- customizing, Z objects
- customizing, undeclared customizations
ms.assetid: f062dbb7-2c78-47ea-a927-99e1fba4854b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77f688e4cf6a4bbb55243d9f5f6f60e144bad862
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="undeclared-customizations"></a><span data-ttu-id="f646b-102">宣言されていないカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="f646b-102">Undeclared Customizations</span></span>
<span data-ttu-id="f646b-103">形式またはデータの特性を定義することがなく、メッセージにデータを追加できます。</span><span class="sxs-lookup"><span data-stu-id="f646b-103">You can add data to a message without defining the format or nature of the data.</span></span> <span data-ttu-id="f646b-104">宣言されていない Z セグメントを使用してこれを行います。</span><span class="sxs-lookup"><span data-stu-id="f646b-104">You do so by using undeclared Z segments.</span></span> <span data-ttu-id="f646b-105">宣言されていない Z セグメントは、メッセージの最後に予期しないインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="f646b-105">Undeclared Z segments are unexpected instances at the end of a message.</span></span> <span data-ttu-id="f646b-106">パーサー/XML 検証では、セグメントは検証しません。</span><span class="sxs-lookup"><span data-stu-id="f646b-106">The parser/XML validator does not validate the segment.</span></span> <span data-ttu-id="f646b-107">任意のスキーマで定義されていません。</span><span class="sxs-lookup"><span data-stu-id="f646b-107">It is not defined by any schema.</span></span> [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="f646b-108">BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) セグメントをバイナリ ラージ オブジェクト (BLOB) として扱われます。</span><span class="sxs-lookup"><span data-stu-id="f646b-108"> BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) treats the segment as a binary large object (BLOB).</span></span>  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="f646b-109">3 つの部分のメッセージの 3 番目の部分としてを通じて Z 宣言されていないデータのセグメントを渡します。</span><span class="sxs-lookup"><span data-stu-id="f646b-109"> passes undeclared Z segment data through as the third part of a three-part message.</span></span> <span data-ttu-id="f646b-110">3 つの部分は、ヘッダー、本文、および宣言されていない Z セグメント、Z の一部とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="f646b-110">The three parts are the header, the body, and the undeclared Z segment, also called the Z part.</span></span> <span data-ttu-id="f646b-111">セグメント ID、文字で始まる"Z"、たとえば、"ZPD"カスタム患者人口統計については、Z の一部を識別します。</span><span class="sxs-lookup"><span data-stu-id="f646b-111">A segment ID beginning with the letter "Z", for instance, "ZPD" for custom patient demographics information, identifies the Z part.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f646b-112">参照</span><span class="sxs-lookup"><span data-stu-id="f646b-112">See Also</span></span>  
 <span data-ttu-id="f646b-113">[宣言のカスタマイズ](../../adapters-and-accelerators/accelerator-hl7/declared-customizations.md) </span><span class="sxs-lookup"><span data-stu-id="f646b-113">[Declared Customizations](../../adapters-and-accelerators/accelerator-hl7/declared-customizations.md) </span></span>  
 <span data-ttu-id="f646b-114">[Z オブジェクトと HL7 2.X スキーマを拡張します。](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span><span class="sxs-lookup"><span data-stu-id="f646b-114">[Extending HL7 2.X Schemas with Z Objects](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span></span>  
 <span data-ttu-id="f646b-115">[HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="f646b-115">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="f646b-116">[メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="f646b-116">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="f646b-117">HL7 2.X スキーマの使用</span><span class="sxs-lookup"><span data-stu-id="f646b-117">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)
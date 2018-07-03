---
title: 未宣言のカスタマイズ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- undeclared customizations
- Z objects, undeclared customizations
- customizing, Z objects
- customizing, undeclared customizations
ms.assetid: f062dbb7-2c78-47ea-a927-99e1fba4854b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05a33abb76d49cfa5db640b1d15d9fde420f19c6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974227"
---
# <a name="undeclared-customizations"></a><span data-ttu-id="3d81a-102">未宣言のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="3d81a-102">Undeclared Customizations</span></span>
<span data-ttu-id="3d81a-103">形式またはデータの性質を定義することがなく、メッセージにデータを追加できます。</span><span class="sxs-lookup"><span data-stu-id="3d81a-103">You can add data to a message without defining the format or nature of the data.</span></span> <span data-ttu-id="3d81a-104">未宣言の Z セグメントを使用してこれを行います。</span><span class="sxs-lookup"><span data-stu-id="3d81a-104">You do so by using undeclared Z segments.</span></span> <span data-ttu-id="3d81a-105">未宣言の Z セグメントは、メッセージの最後の予期しないインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="3d81a-105">Undeclared Z segments are unexpected instances at the end of a message.</span></span> <span data-ttu-id="3d81a-106">パーサー/XML 検証では、セグメントは検証されません。</span><span class="sxs-lookup"><span data-stu-id="3d81a-106">The parser/XML validator does not validate the segment.</span></span> <span data-ttu-id="3d81a-107">任意のスキーマでは定義されません。</span><span class="sxs-lookup"><span data-stu-id="3d81a-107">It is not defined by any schema.</span></span> <span data-ttu-id="3d81a-108">Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) セグメントをバイナリ ラージ オブジェクト (BLOB) として扱われます。</span><span class="sxs-lookup"><span data-stu-id="3d81a-108">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) treats the segment as a binary large object (BLOB).</span></span>  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="3d81a-109"> 3 つの部分のメッセージの 3 番目の部分として宣言されていない経由の Z セグメントのデータを渡します。</span><span class="sxs-lookup"><span data-stu-id="3d81a-109"> passes undeclared Z segment data through as the third part of a three-part message.</span></span> <span data-ttu-id="3d81a-110">3 つの部分は、ヘッダー、本文、および Z の一部とも呼ばれる、宣言されていない Z セグメントです。</span><span class="sxs-lookup"><span data-stu-id="3d81a-110">The three parts are the header, the body, and the undeclared Z segment, also called the Z part.</span></span> <span data-ttu-id="3d81a-111">文字"Z"、たとえば、"ZPD"カスタム患者の人口統計については、セグメント ID の先頭では、Z の一部を識別します。</span><span class="sxs-lookup"><span data-stu-id="3d81a-111">A segment ID beginning with the letter "Z", for instance, "ZPD" for custom patient demographics information, identifies the Z part.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d81a-112">参照</span><span class="sxs-lookup"><span data-stu-id="3d81a-112">See Also</span></span>  
 <span data-ttu-id="3d81a-113">[宣言済みのカスタマイズ](../../adapters-and-accelerators/accelerator-hl7/declared-customizations.md) </span><span class="sxs-lookup"><span data-stu-id="3d81a-113">[Declared Customizations](../../adapters-and-accelerators/accelerator-hl7/declared-customizations.md) </span></span>  
 <span data-ttu-id="3d81a-114">[Z オブジェクト HL7 2.X スキーマの拡張](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span><span class="sxs-lookup"><span data-stu-id="3d81a-114">[Extending HL7 2.X Schemas with Z Objects](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span></span>  
 <span data-ttu-id="3d81a-115">[HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="3d81a-115">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="3d81a-116">[メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="3d81a-116">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="3d81a-117">HL7 2.X スキーマの使用</span><span class="sxs-lookup"><span data-stu-id="3d81a-117">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)
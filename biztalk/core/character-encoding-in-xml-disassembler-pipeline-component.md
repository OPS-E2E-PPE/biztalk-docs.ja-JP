---
title: XML 逆アセンブラー パイプライン コンポーネントにおける文字エンコーディング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IBaseMessagePart.Charset property
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component], character encoding
- XMLNorm.SourceCharset property
ms.assetid: 37962bdc-cbcb-4559-9ae8-6c4be49b4822
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6fee26bdab8566010981e72585358b060009785f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977579"
---
# <a name="character-encoding-in-xml-disassembler-pipeline-component"></a><span data-ttu-id="d2680-102">XML 逆アセンブラー パイプライン コンポーネントでの文字エン コード</span><span class="sxs-lookup"><span data-stu-id="d2680-102">Character Encoding in XML Disassembler Pipeline Component</span></span>
<span data-ttu-id="d2680-103">XML 逆アセンブラーでは、次のアルゴリズムに基づいて、受信メッセージを処理するためのエンコードを決定します。</span><span class="sxs-lookup"><span data-stu-id="d2680-103">The XML Disassembler uses the following algorithm to determine which encoding to use for processing incoming messages:</span></span>  
  
1. <span data-ttu-id="d2680-104">バイト順マークがデータ内に存在する場合、これによってエンコード情報が決定されます。</span><span class="sxs-lookup"><span data-stu-id="d2680-104">If a byte order mark exists in the data, encoding information is determined from it.</span></span>  
  
2. <span data-ttu-id="d2680-105">の場合、 **IBaseMessagePart.Charset**プロパティが設定されて、が指定されてエンコードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d2680-105">Otherwise, if the **IBaseMessagePart.Charset** property is set, the encoding specified there is used.</span></span>  
  
3. <span data-ttu-id="d2680-106">上記のいずれにも該当せず、XML ドキュメント内に ANSI を指定する XML 宣言が存在する場合は、その宣言に指定されているエンコードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d2680-106">Otherwise if the XML declaration is present in the XML document, the encoding specified there is used, provided the XML declaration is ANSI.</span></span>  
  
4. <span data-ttu-id="d2680-107">上記のいずれにも該当しない場合は、UTF-8 エンコードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d2680-107">Otherwise, UTF-8 encoding is used.</span></span>  
  
   <span data-ttu-id="d2680-108">メッセージ コンテキストに保存、上記の場合に 2、3、および 4、エンコーディング、XML 逆アセンブラーが決定した後の**XMLNorm.SourceCharset**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d2680-108">For the preceding cases 2, 3, and 4, after the XML Disassembler determines the encoding, it saves it on the message context in **XMLNorm.SourceCharset** property.</span></span> <span data-ttu-id="d2680-109">XML 逆アセンブラー パイプライン コンポーネントにより生成されるメッセージには、常に UTF-8 エンコードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d2680-109">Messages produced by the XML Disassembler pipeline component always use UTF-8 encoding.</span></span> <span data-ttu-id="d2680-110">バイト オーダー マークから取得されたエンコード (上記 1 のケース) は保持されません。</span><span class="sxs-lookup"><span data-stu-id="d2680-110">For case 1, encoding determined from the byte order mark is not preserved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2680-111">参照</span><span class="sxs-lookup"><span data-stu-id="d2680-111">See Also</span></span>  
 <span data-ttu-id="d2680-112">[XML 逆アセンブラー パイプライン コンポーネント](../core/xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="d2680-112">[XML Disassembler Pipeline Component](../core/xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="d2680-113">XML 逆アセンブラー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="d2680-113">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)
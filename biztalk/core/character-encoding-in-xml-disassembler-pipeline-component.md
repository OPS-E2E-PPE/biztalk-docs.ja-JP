---
title: XML 逆アセンブラー パイプライン コンポーネントにおける文字エンコーディング |Microsoft ドキュメント
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
ms.openlocfilehash: 2b0e307f2f608cde266e7a566fb3005bde048c31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231666"
---
# <a name="character-encoding-in-xml-disassembler-pipeline-component"></a><span data-ttu-id="43b81-102">XML 逆アセンブラー パイプライン コンポーネントでの文字エン コード</span><span class="sxs-lookup"><span data-stu-id="43b81-102">Character Encoding in XML Disassembler Pipeline Component</span></span>
<span data-ttu-id="43b81-103">XML 逆アセンブラーでは、次のアルゴリズムに基づいて、受信メッセージを処理するためのエンコードを決定します。</span><span class="sxs-lookup"><span data-stu-id="43b81-103">The XML Disassembler uses the following algorithm to determine which encoding to use for processing incoming messages:</span></span>  
  
1.  <span data-ttu-id="43b81-104">バイト順マークがデータ内に存在する場合、これによってエンコード情報が決定されます。</span><span class="sxs-lookup"><span data-stu-id="43b81-104">If a byte order mark exists in the data, encoding information is determined from it.</span></span>  
  
2.  <span data-ttu-id="43b81-105">それ以外の場合、 **IBaseMessagePart.Charset**プロパティが設定されてがあります指定されたエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="43b81-105">Otherwise, if the **IBaseMessagePart.Charset** property is set, the encoding specified there is used.</span></span>  
  
3.  <span data-ttu-id="43b81-106">上記のいずれにも該当せず、XML ドキュメント内に ANSI を指定する XML 宣言が存在する場合は、その宣言に指定されているエンコードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="43b81-106">Otherwise if the XML declaration is present in the XML document, the encoding specified there is used, provided the XML declaration is ANSI.</span></span>  
  
4.  <span data-ttu-id="43b81-107">上記のいずれにも該当しない場合は、UTF-8 エンコードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="43b81-107">Otherwise, UTF-8 encoding is used.</span></span>  
  
 <span data-ttu-id="43b81-108">メッセージ コンテキストに保存前、場合によっては 2、3、および 4 では、XML 逆アセンブラーは、エンコーディングを決定した後の**XMLNorm.SourceCharset**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="43b81-108">For the preceding cases 2, 3, and 4, after the XML Disassembler determines the encoding, it saves it on the message context in **XMLNorm.SourceCharset** property.</span></span> <span data-ttu-id="43b81-109">XML 逆アセンブラー パイプライン コンポーネントにより生成されるメッセージには、常に UTF-8 エンコードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="43b81-109">Messages produced by the XML Disassembler pipeline component always use UTF-8 encoding.</span></span> <span data-ttu-id="43b81-110">バイト オーダー マークから取得されたエンコード (上記 1 のケース) は保持されません。</span><span class="sxs-lookup"><span data-stu-id="43b81-110">For case 1, encoding determined from the byte order mark is not preserved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43b81-111">参照</span><span class="sxs-lookup"><span data-stu-id="43b81-111">See Also</span></span>  
 <span data-ttu-id="43b81-112">[XML 逆アセンブラー パイプライン コンポーネント](../core/xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="43b81-112">[XML Disassembler Pipeline Component](../core/xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="43b81-113">XML 逆アセンブラー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="43b81-113">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)
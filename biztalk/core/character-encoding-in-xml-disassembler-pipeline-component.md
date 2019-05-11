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
ms.openlocfilehash: d299ac6a1261160cbd3844c3f0201e55affa5655
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391673"
---
# <a name="character-encoding-in-xml-disassembler-pipeline-component"></a><span data-ttu-id="39b25-102">XML 逆アセンブラー パイプライン コンポーネントでの文字エン コード</span><span class="sxs-lookup"><span data-stu-id="39b25-102">Character Encoding in XML Disassembler Pipeline Component</span></span>
<span data-ttu-id="39b25-103">XML 逆アセンブラーは、受信メッセージを処理するために使用するのにエンコードを決定するのに、次のアルゴリズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="39b25-103">The XML Disassembler uses the following algorithm to determine which encoding to use for processing incoming messages:</span></span>  
  
1. <span data-ttu-id="39b25-104">データのバイト順マークが存在する場合、そこからはエンコード情報が判断されます。</span><span class="sxs-lookup"><span data-stu-id="39b25-104">If a byte order mark exists in the data, encoding information is determined from it.</span></span>  
  
2. <span data-ttu-id="39b25-105">の場合、 **IBaseMessagePart.Charset**プロパティが設定されて、が指定されてエンコードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="39b25-105">Otherwise, if the **IBaseMessagePart.Charset** property is set, the encoding specified there is used.</span></span>  
  
3. <span data-ttu-id="39b25-106">それ以外の場合、XML 宣言が XML ドキュメント内にある場合が指定されてエンコードされる、指定された XML 宣言が ANSI。</span><span class="sxs-lookup"><span data-stu-id="39b25-106">Otherwise if the XML declaration is present in the XML document, the encoding specified there is used, provided the XML declaration is ANSI.</span></span>  
  
4. <span data-ttu-id="39b25-107">それ以外の場合、utf-8 エンコードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="39b25-107">Otherwise, UTF-8 encoding is used.</span></span>  
  
   <span data-ttu-id="39b25-108">メッセージ コンテキストに保存、上記の場合に 2、3、および 4、エンコーディング、XML 逆アセンブラーが決定した後の**XMLNorm.SourceCharset**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="39b25-108">For the preceding cases 2, 3, and 4, after the XML Disassembler determines the encoding, it saves it on the message context in **XMLNorm.SourceCharset** property.</span></span> <span data-ttu-id="39b25-109">常に、XML 逆アセンブラー パイプライン コンポーネントによって生成されたメッセージは、utf-8 エンコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="39b25-109">Messages produced by the XML Disassembler pipeline component always use UTF-8 encoding.</span></span> <span data-ttu-id="39b25-110">1 の場合、バイト オーダー マークから取得されたエンコードは保持されません。</span><span class="sxs-lookup"><span data-stu-id="39b25-110">For case 1, encoding determined from the byte order mark is not preserved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39b25-111">参照</span><span class="sxs-lookup"><span data-stu-id="39b25-111">See Also</span></span>  
 <span data-ttu-id="39b25-112">[XML 逆アセンブラー パイプライン コンポーネント](../core/xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="39b25-112">[XML Disassembler Pipeline Component](../core/xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="39b25-113">XML 逆アセンブラー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="39b25-113">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)
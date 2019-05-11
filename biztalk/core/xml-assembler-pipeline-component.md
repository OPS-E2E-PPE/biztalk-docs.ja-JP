---
title: XML アセンブラー パイプライン コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Assembler [pipeline component]
- pipeline components, XML Assembler
ms.assetid: 3adfd603-0577-49c2-ae9d-445d62fed385
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ed0d334539ae013a87d8caa293b55288e24becd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295600"
---
# <a name="xml-assembler-pipeline-component"></a><span data-ttu-id="ad5b1-102">XML アセンブラー パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ad5b1-102">XML Assembler Pipeline Component</span></span>
<span data-ttu-id="ad5b1-103">XML アセンブラー パイプライン コンポーネントは、XML シリアル化して、1 つのコンポーネントにアセンブルを結合します。</span><span class="sxs-lookup"><span data-stu-id="ad5b1-103">The XML Assembler pipeline component combines XML serializing and assembling in one component.</span></span> <span data-ttu-id="ad5b1-104">その主な機能では、プロパティをメッセージ コンテキストからエンベロープおよびドキュメントに転送します。</span><span class="sxs-lookup"><span data-stu-id="ad5b1-104">Its primary function is to transfer properties from the message context back into envelopes and documents.</span></span>  
  
 <span data-ttu-id="ad5b1-105">次の操作は、メッセージをインターチェンジのバッチを受信した後、XML アセンブラー コンポーネントで発生します。</span><span class="sxs-lookup"><span data-stu-id="ad5b1-105">The following actions occur in the XML Assembler component after receiving a batch of messages to form an interchange:</span></span>  
  
1.  <span data-ttu-id="ad5b1-106">アセンブラーは、指定されたエンベロープ仕様を使用してエンベロープを作成します。</span><span class="sxs-lookup"><span data-stu-id="ad5b1-106">The assembler creates the envelope by using the specified envelope specification.</span></span>  
  
2.  <span data-ttu-id="ad5b1-107">コンポーネントは、メッセージに関連付けられている XSD スキーマに注釈としてコーディングされている、事前定義された Xpath を使用して、メッセージ インスタンスのコンテンツのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ad5b1-107">The component puts the content properties on the message instances by using the predefined XPaths coded as annotations in the XSD schemas associated with the message.</span></span>  
  
3.  <span data-ttu-id="ad5b1-108">コンポーネントは、メッセージをエンベロープに追加します。</span><span class="sxs-lookup"><span data-stu-id="ad5b1-108">The component appends the message to the envelope.</span></span>  
  
4.  <span data-ttu-id="ad5b1-109">コンポーネントは、エンベロープに関連付けられている XSD スキーマ内に注釈としてコーディングされている、事前定義された Xpath を使用して、エンベロープのコンテンツのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ad5b1-109">The component puts the content properties on the envelope by using the predefined XPaths coded as annotations in the XSD schemas associated with envelopes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad5b1-110">XML アセンブラー パイプライン コンポーネントは、不足している属性フィールドでは設定されませんが、フィールドは省略可能ですが、既定値はありませんまたは固定値と、空の要素のフィールドを設定は。</span><span class="sxs-lookup"><span data-stu-id="ad5b1-110">The XML Assembler pipeline component does not populate missing attribute fields, but does populate empty element fields when the fields are optional but do not have default or fixed values.</span></span>  
  
 <span data-ttu-id="ad5b1-111">XML アセンブラー パイプライン コンポーネントの構成方法の詳細については、次を参照してください。 [、XML アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-assembler-pipeline-component.md)します。</span><span class="sxs-lookup"><span data-stu-id="ad5b1-111">For information about configuring the XML Assembler pipeline component, see [How to Configure the XML Assembler Pipeline Component](../core/how-to-configure-the-xml-assembler-pipeline-component.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ad5b1-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ad5b1-112">In This Section</span></span>  
  
-   [<span data-ttu-id="ad5b1-113">XML アセンブラー パイプライン コンポーネントでの文字エンコード</span><span class="sxs-lookup"><span data-stu-id="ad5b1-113">Character Encoding in the XML Assembler Pipeline Component</span></span>](../core/character-encoding-in-the-xml-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="ad5b1-114">XML アセンブラー パイプライン コンポーネントの処理命令</span><span class="sxs-lookup"><span data-stu-id="ad5b1-114">Processing Instructions in the XML Assembler Pipeline Component</span></span>](../core/processing-instructions-in-the-xml-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="ad5b1-115">XML アセンブラー パイプライン コンポーネントで認識されないメッセージ</span><span class="sxs-lookup"><span data-stu-id="ad5b1-115">Unrecognized Messages in the XML Assembler Pipeline Component</span></span>](../core/unrecognized-messages-in-the-xml-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="ad5b1-116">XML アセンブラー パイプライン コンポーネントにおける XML 要素</span><span class="sxs-lookup"><span data-stu-id="ad5b1-116">XML Information Set Elements in the XML Assembler Pipeline Component</span></span>](../core/xml-information-set-elements-in-the-xml-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="ad5b1-117">XML アセンブラー パイプライン コンポーネントにおけるドキュメント構造の強化</span><span class="sxs-lookup"><span data-stu-id="ad5b1-117">Document Structure Enforcement in the XML Assembler Pipeline Component</span></span>](../core/document-structure-enforcement-in-the-xml-assembler-pipeline-component.md)
---
title: "XML アセンブラー パイプライン コンポーネント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML Assembler [pipeline component]
- pipeline components, XML Assembler
ms.assetid: 3adfd603-0577-49c2-ae9d-445d62fed385
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22348b61ca32567190fa99e103fe536f5199af58
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="xml-assembler-pipeline-component"></a><span data-ttu-id="a7bdb-102">XML アセンブラー パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a7bdb-102">XML Assembler Pipeline Component</span></span>
<span data-ttu-id="a7bdb-103">XML アセンブラー パイプライン コンポーネントは、XML のシリアル化とアセンブルを 1 つのコンポーネントで実行します。</span><span class="sxs-lookup"><span data-stu-id="a7bdb-103">The XML Assembler pipeline component combines XML serializing and assembling in one component.</span></span> <span data-ttu-id="a7bdb-104">XML アセンブラー パイプライン コンポーネントの主要な機能は、メッセージ コンテキストからエンベロープおよびドキュメントにプロパティを転送することです。</span><span class="sxs-lookup"><span data-stu-id="a7bdb-104">Its primary function is to transfer properties from the message context back into envelopes and documents.</span></span>  
  
 <span data-ttu-id="a7bdb-105">XML アセンブラー コンポーネントは、一連のメッセージを受け取った後で、次の処理を実行することによりデータ交換を実現します。</span><span class="sxs-lookup"><span data-stu-id="a7bdb-105">The following actions occur in the XML Assembler component after receiving a batch of messages to form an interchange:</span></span>  
  
1.  <span data-ttu-id="a7bdb-106">指定されたエンベロープ仕様に基づいてエンベロープを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7bdb-106">The assembler creates the envelope by using the specified envelope specification.</span></span>  
  
2.  <span data-ttu-id="a7bdb-107">メッセージに関連付けられている XSD スキーマ内に注釈としてコーディングされている、定義済みの XPath を使用して、メッセージ インスタンスのコンテンツ プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="a7bdb-107">The component puts the content properties on the message instances by using the predefined XPaths coded as annotations in the XSD schemas associated with the message.</span></span>  
  
3.  <span data-ttu-id="a7bdb-108">メッセージをエンベロープに追加します。</span><span class="sxs-lookup"><span data-stu-id="a7bdb-108">The component appends the message to the envelope.</span></span>  
  
4.  <span data-ttu-id="a7bdb-109">エンベロープに関連付けられている XSD スキーマ内に注釈としてコーディングされている、定義済みの XPath を使用して、エンベロープのコンテンツ プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="a7bdb-109">The component puts the content properties on the envelope by using the predefined XPaths coded as annotations in the XSD schemas associated with envelopes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7bdb-110">XML アセンブラー パイプライン コンポーネントでは、欠落している属性フィールドに値を設定することはありません。ただし、空の要素フィールドについては、既定値や固定値の割り当てられていない省略可能なフィールドの場合にのみ値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="a7bdb-110">The XML Assembler pipeline component does not populate missing attribute fields, but does populate empty element fields when the fields are optional but do not have default or fixed values.</span></span>  
  
 <span data-ttu-id="a7bdb-111">XML アセンブラー パイプライン コンポーネントの構成方法の詳細については、次を参照してください。 [、XML アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-assembler-pipeline-component.md)です。</span><span class="sxs-lookup"><span data-stu-id="a7bdb-111">For information about configuring the XML Assembler pipeline component, see [How to Configure the XML Assembler Pipeline Component](../core/how-to-configure-the-xml-assembler-pipeline-component.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a7bdb-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a7bdb-112">In This Section</span></span>  
  
-   [<span data-ttu-id="a7bdb-113">XML アセンブラー パイプライン コンポーネントでの文字エン コード</span><span class="sxs-lookup"><span data-stu-id="a7bdb-113">Character Encoding in the XML Assembler Pipeline Component</span></span>](../core/character-encoding-in-the-xml-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="a7bdb-114">XML アセンブラー パイプライン コンポーネントで処理命令</span><span class="sxs-lookup"><span data-stu-id="a7bdb-114">Processing Instructions in the XML Assembler Pipeline Component</span></span>](../core/processing-instructions-in-the-xml-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="a7bdb-115">XML アセンブラー パイプライン コンポーネントで認識されないメッセージ</span><span class="sxs-lookup"><span data-stu-id="a7bdb-115">Unrecognized Messages in the XML Assembler Pipeline Component</span></span>](../core/unrecognized-messages-in-the-xml-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="a7bdb-116">XML 情報は、XML アセンブラー パイプライン コンポーネントで要素を設定</span><span class="sxs-lookup"><span data-stu-id="a7bdb-116">XML Information Set Elements in the XML Assembler Pipeline Component</span></span>](../core/xml-information-set-elements-in-the-xml-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="a7bdb-117">XML アセンブラー パイプライン コンポーネントにおけるドキュメント構造の強化</span><span class="sxs-lookup"><span data-stu-id="a7bdb-117">Document Structure Enforcement in the XML Assembler Pipeline Component</span></span>](../core/document-structure-enforcement-in-the-xml-assembler-pipeline-component.md)
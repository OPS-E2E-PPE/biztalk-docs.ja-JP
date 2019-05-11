---
title: XML 逆アセンブラー パイプライン コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Disassembler [pipeline component], about XML Disassembler
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component]
ms.assetid: ef39b695-6ae7-401d-be1e-b066048c34e9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 634d007e2545dfd89457239fe4d05f86a1c90aeb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65246382"
---
# <a name="xml-disassembler-pipeline-component"></a><span data-ttu-id="ce5e2-102">XML 逆アセンブラー パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ce5e2-102">XML Disassembler Pipeline Component</span></span>
<span data-ttu-id="ce5e2-103">XML 逆アセンブラー パイプライン コンポーネントは、XML 解析および XML 逆アセンブラーを 1 つのコンポーネントに組み込んでいます。</span><span class="sxs-lookup"><span data-stu-id="ce5e2-103">The XML Disassembler pipeline component combines XML parsing and disassembling into one component.</span></span> <span data-ttu-id="ce5e2-104">主要な機能を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ce5e2-104">Its primary functions are:</span></span>  
  
- <span data-ttu-id="ce5e2-105">エンベロープの削除。</span><span class="sxs-lookup"><span data-stu-id="ce5e2-105">Removing envelopes.</span></span>  
  
- <span data-ttu-id="ce5e2-106">インターチェンジの逆アセンブル。</span><span class="sxs-lookup"><span data-stu-id="ce5e2-106">Disassembling the interchange.</span></span>  
  
- <span data-ttu-id="ce5e2-107">インターチェンジ レベルおよび個別のドキュメント レベルからメッセージ コンテキストにコンテンツ プロパティを昇格する。</span><span class="sxs-lookup"><span data-stu-id="ce5e2-107">Promoting the content properties from interchange and individual document levels on to the message context.</span></span>  
  
  <span data-ttu-id="ce5e2-108">エンベロープを受け取った後、XML 逆アセンブラー コンポーネントで次の操作が行われます。</span><span class="sxs-lookup"><span data-stu-id="ce5e2-108">The following actions occur in the XML Disassembler component after receiving an envelope:</span></span>  
  
1. <span data-ttu-id="ce5e2-109">逆アセンブラーは、設計時にコンポーネントに静的に関連付けられたエンベロープ スキーマを使用するか、実行時にメッセージの種類からエンベロープ スキーマを動的に決定して、エンベロープを解析します。</span><span class="sxs-lookup"><span data-stu-id="ce5e2-109">The disassembler parses the envelope by using the envelope schemas statically associated with the component at design time or dynamically by determining envelope schemas from the message type at run time.</span></span> <span data-ttu-id="ce5e2-110">スキーマを使用すると、エンベロープの解析中にエンベロープの構造を確認できます。</span><span class="sxs-lookup"><span data-stu-id="ce5e2-110">The schema is used to verify the structure of the envelope during envelope parsing.</span></span> <span data-ttu-id="ce5e2-111">エンベロープの構造が定義されていない場合、ルート ノードの名前空間およびベース名を使用してスキーマを参照することで、エンベロープの構造が再帰的に検索されます。</span><span class="sxs-lookup"><span data-stu-id="ce5e2-111">If envelope structure is not defined, it is found recursively by using the root node's namespace and base name to look up the schemas.</span></span>  
  
2. <span data-ttu-id="ce5e2-112">逆アセンブラー コンポーネントは、エンベロープの各ドキュメントを解析します。</span><span class="sxs-lookup"><span data-stu-id="ce5e2-112">The disassembler component parses each document within the envelope.</span></span> <span data-ttu-id="ce5e2-113">各ドキュメントに対し、独自のコンテキストを持つ BizTalk メッセージ オブジェクトが作成されます。ここで、エンベロープおよびドキュメントから昇格されたすべてのプロパティがコピーされます。</span><span class="sxs-lookup"><span data-stu-id="ce5e2-113">For each document, the BizTalk message object is created with its own context where all the properties promoted from the envelope and from the document itself get copied.</span></span> <span data-ttu-id="ce5e2-114">定義済みの XPath (エンベロープおよびメッセージの XSD スキーマに注釈としてコーディングされている) を使用すると、エンベロープ インスタンスおよびメッセージ インスタンスのコンテンツ プロパティが抽出されます。</span><span class="sxs-lookup"><span data-stu-id="ce5e2-114">The component pulls the content properties from the envelope and message instances by using the predefined XPaths coded as annotations in the XSD schemas associated with the envelope and message.</span></span> <span data-ttu-id="ce5e2-115">個別のドキュメント スキーマとエンベロープ スキーマは、パイプライン デザイナーの逆アセンブラー コンポーネントに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="ce5e2-115">The envelope schemas as well as the individual document schemas are associated with the disassembler component in Pipeline Designer.</span></span>  
  
   <span data-ttu-id="ce5e2-116">XML 逆アセンブラーは、メッセージのボディ部分のデータのみ処理します。</span><span class="sxs-lookup"><span data-stu-id="ce5e2-116">The XML Disassembler only processes data in the body part of the message.</span></span> <span data-ttu-id="ce5e2-117">このため、ボディ部分のプロパティのみ昇格できます。</span><span class="sxs-lookup"><span data-stu-id="ce5e2-117">Thus, only properties from body part can be promoted.</span></span> <span data-ttu-id="ce5e2-118">昇格できるプロパティに関連付けられているフィールドの datetime 値は、プロパティの昇格が発生すると、UTC に変換されます。</span><span class="sxs-lookup"><span data-stu-id="ce5e2-118">Datetime values from the fields associated with the promotable properties get converted to UTC when property promotion occurs.</span></span> <span data-ttu-id="ce5e2-119">ボディ部分以外は、そのまま出力メッセージにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="ce5e2-119">Non-body parts are copied to the output message unchanged.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce5e2-120">XML 逆アセンブラー パイプライン コンポーネントは、メッセージ ストアに達する前に、すべての日時プロパティを UTC に強制的に変換します。</span><span class="sxs-lookup"><span data-stu-id="ce5e2-120">The XML Disassembler pipeline component currently forces conversion of all datetime properties to UTC before they reach the message store.</span></span> <span data-ttu-id="ce5e2-121">BizTalk Server は、内部的に SQL datetime (タイム ゾーンの情報は含まれない) を使用します。</span><span class="sxs-lookup"><span data-stu-id="ce5e2-121">BizTalk Server uses an SQL datetime type internally, which does not have information about the time zone.</span></span> <span data-ttu-id="ce5e2-122">オーケストレーションで日時プロパティを生成し、生成したプロパティを後続のメッセージと相互に関連付けようとすると、正しく機能しない場合があります。XML 逆アセンブラー パイプライン コンポーネントにより応答時に日時プロパティが UTC に変換され、Microsoft SQL Server で元の日時プロパティと応答時間フィールドを同一のものとして認識できなくなるためです。</span><span class="sxs-lookup"><span data-stu-id="ce5e2-122">If you generate a datetime property in an orchestration, and then try to use it for correlation with subsequent messages, it may not work correctly, because the XML Disassembler pipeline component will convert it on response into UTC, and Microsoft SQL Server will have no way to identify the original and response time fields as identical.</span></span> <span data-ttu-id="ce5e2-123">同様に、メッセージ イベントおよびサービス インスタンスの追跡データの表示で不整合が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="ce5e2-123">Similarly, you may encounter discrepancies when viewing message event and service instance tracking data.</span></span>  
  
 <span data-ttu-id="ce5e2-124">XML 逆アセンブラー パイプライン コンポーネントの構成方法の詳細については、次を参照してください。 [XML 逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)します。</span><span class="sxs-lookup"><span data-stu-id="ce5e2-124">For information about configuring the XML Disassembler pipeline component, see [How to Configure the XML Disassembler Pipeline Component](../core/how-to-configure-the-xml-disassembler-pipeline-component.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ce5e2-125">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ce5e2-125">In This Section</span></span>  
  
-   [<span data-ttu-id="ce5e2-126">XML 逆アセンブラー パイプライン コンポーネントにおける XML 要素</span><span class="sxs-lookup"><span data-stu-id="ce5e2-126">XML Information Set Elements in the XML Disassembler Pipeline Component</span></span>](../core/xml-information-set-elements-in-the-xml-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="ce5e2-127">XML 逆アセンブラー パイプライン コンポーネントで認識されないメッセージ</span><span class="sxs-lookup"><span data-stu-id="ce5e2-127">Unrecognized Messages in the XML Disassembler Pipeline Component</span></span>](../core/unrecognized-messages-in-the-xml-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="ce5e2-128">XML 逆アセンブラー パイプライン コンポーネントのドキュメント検証</span><span class="sxs-lookup"><span data-stu-id="ce5e2-128">Document Validation in the XML Disassembler Pipeline Component</span></span>](../core/document-validation-in-the-xml-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="ce5e2-129">XML 逆アセンブラー パイプライン コンポーネントにおけるドキュメント構造の強化</span><span class="sxs-lookup"><span data-stu-id="ce5e2-129">Document Structure Enforcement in the XML Disassembler Pipeline Component</span></span>](../core/document-structure-enforcement-in-the-xml-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="ce5e2-130">XML 逆アセンブラー パイプライン コンポーネントでの文字エンコード</span><span class="sxs-lookup"><span data-stu-id="ce5e2-130">Character Encoding in XML Disassembler Pipeline Component</span></span>](../core/character-encoding-in-xml-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="ce5e2-131">チュートリアル: XML エンベロープ (Basic) の使用</span><span class="sxs-lookup"><span data-stu-id="ce5e2-131">Walkthrough: Using XML Envelopes (Basic)</span></span>](../core/walkthrough-using-xml-envelopes-basic.md)
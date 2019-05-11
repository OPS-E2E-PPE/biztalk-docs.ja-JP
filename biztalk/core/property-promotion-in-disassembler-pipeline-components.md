---
title: 逆アセンブラー パイプライン コンポーネントのプロパティの昇格 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, promoting properties
- XML Disassembler [pipeline component], properties
- pipeline components, properties
- promoting properties, disassembler pipeline components
- BizTalk Framework Assembler [pipeline component], properties
- Flat File Disassembler [pipeline component], properties
ms.assetid: aa37b308-8aa2-45f4-9383-aca4f2c925ce
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26e8b358b70c12ecf5567c19377fa8419f5bea83
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398463"
---
# <a name="property-promotion-in-disassembler-pipeline-components"></a><span data-ttu-id="7bec1-102">逆アセンブラー パイプライン コンポーネントのプロパティの昇格</span><span class="sxs-lookup"><span data-stu-id="7bec1-102">Property Promotion in Disassembler Pipeline Components</span></span>
<span data-ttu-id="7bec1-103">プロパティの昇格は、プロパティ値を XPath 式を使用して XML ドキュメントから抽出してメッセージのルーティングのために使用できるように、メッセージ コンテキストに配置するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="7bec1-103">Property promotion is a process by which a property value is extracted from an XML document by using an XPath expression and placed on the message context so that it can be used for message routing.</span></span>  
  
 <span data-ttu-id="7bec1-104">昇格させたプロパティには、既定値はありません。 または値を修正するには、そのプロパティの XML フィールドが存在しないか、およびドキュメント構造の検証プロパティが場合**False**、プロパティは昇格されません。</span><span class="sxs-lookup"><span data-stu-id="7bec1-104">If a promoted property does not have a default or fixed value, the XML field for that property is missing, and the Validate Document Structure property is **False**, the property is not promoted.</span></span>  
  
 <span data-ttu-id="7bec1-105">カスタム パイプライン コンポーネントで昇格できる複数の値 (つまり、配列化された) プロパティ。</span><span class="sxs-lookup"><span data-stu-id="7bec1-105">A custom pipeline component can promote multivalued (that is, arrayed) properties.</span></span> <span data-ttu-id="7bec1-106">複数値プロパティを含むメッセージは、コンテンツ ベースのルーティング (CBR) シナリオでのみサポートします。オーケストレーションにルーティングすることはできません、または追跡の目的で使用します。</span><span class="sxs-lookup"><span data-stu-id="7bec1-106">Messages that contain multivalued properties are only supported in content-based routing (CBR) scenarios; they cannot be routed to orchestrations or be used for tracking purposes.</span></span>  
  
 <span data-ttu-id="7bec1-107">XML 逆アセンブラーは、既定値は昇格しませんまたは終了タグがある場合は、空の要素の値を修正しました。</span><span class="sxs-lookup"><span data-stu-id="7bec1-107">The XML Disassembler does not promote default or fixed values for an empty element if it has a closing tag.</span></span> <span data-ttu-id="7bec1-108">たとえば、 \<field1\>は、次の XML は昇格されません。</span><span class="sxs-lookup"><span data-stu-id="7bec1-108">For example, \<field1\> is not promoted in the following XML.</span></span>  
  
```  
<document>  
   <field1></field1>  
</document>  
```  
  
 <span data-ttu-id="7bec1-109">ただし、(次の例で示す) のように終了タグのない空の要素を昇格します。</span><span class="sxs-lookup"><span data-stu-id="7bec1-109">However, an empty element without a closing tag (as shown in the following example) is promoted.</span></span>  
  
```  
<document>  
   <field1/>  
</document>  
```  
  
 <span data-ttu-id="7bec1-110">ドキュメントとデータが UTC 形式である場合、コンテキスト プロパティに配置することから datetime データを読み取るときにその形式が維持されます。</span><span class="sxs-lookup"><span data-stu-id="7bec1-110">When reading datetime data from a document and placing it into the context property, if the data is in UTC format, that format is preserved.</span></span> <span data-ttu-id="7bec1-111">Datetime データがローカル + オフセット形式である場合は、BizTalk Server は、datetime 形式を現地時刻にオフセットを加算した結果を UTC 形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="7bec1-111">If the datetime data is in local+offset format, BizTalk Server converts the datetime format to the UTC format that results from adding the offset to the local time.</span></span> <span data-ttu-id="7bec1-112">Datetime 形式がタイム ゾーンまたは UTC 形式を指定しない場合、時刻はローカルと見なされ、現在のタイム ゾーンに基づいて UTC に変換されます。</span><span class="sxs-lookup"><span data-stu-id="7bec1-112">If the datetime format does not specify time zone or UTC format, the time is assumed to be local and is converted to UTC based on the current time zone.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bec1-113">参照</span><span class="sxs-lookup"><span data-stu-id="7bec1-113">See Also</span></span>  
 <span data-ttu-id="7bec1-114">[XML 逆アセンブラー パイプライン コンポーネント](../core/xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="7bec1-114">[XML Disassembler Pipeline Component](../core/xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="7bec1-115">XML 逆アセンブラー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="7bec1-115">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)
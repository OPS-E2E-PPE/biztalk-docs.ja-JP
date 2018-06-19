---
title: 逆アセンブラー パイプライン コンポーネントのプロパティの昇格 |Microsoft ドキュメント
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
ms.openlocfilehash: d6c95c58dafe1f7f875232c5b65962e731334f16
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971840"
---
# <a name="property-promotion-in-disassembler-pipeline-components"></a><span data-ttu-id="abf0a-102">逆アセンブラー パイプライン コンポーネントのプロパティの昇格</span><span class="sxs-lookup"><span data-stu-id="abf0a-102">Property Promotion in Disassembler Pipeline Components</span></span>
<span data-ttu-id="abf0a-103">プロパティの昇格とは、XML ドキュメントから XPath 式を使ってプロパティ値を抽出し、メッセージ コンテキストに設定することによって、プロパティ値に基づくメッセージのルーティングを可能にするプロセスです。</span><span class="sxs-lookup"><span data-stu-id="abf0a-103">Property promotion is a process by which a property value is extracted from an XML document by using an XPath expression and placed on the message context so that it can be used for message routing.</span></span>  
  
 <span data-ttu-id="abf0a-104">昇格させたプロパティには、既定値はありません。 または値を修正するには、そのプロパティの XML フィールドが存在し、ドキュメント構造の検証プロパティは場合**False**、プロパティは昇格されません。</span><span class="sxs-lookup"><span data-stu-id="abf0a-104">If a promoted property does not have a default or fixed value, the XML field for that property is missing, and the Validate Document Structure property is **False**, the property is not promoted.</span></span>  
  
 <span data-ttu-id="abf0a-105">カスタム パイプライン コンポーネントでは、複数値 (つまり、配列化された) プロパティを昇格させることができます。</span><span class="sxs-lookup"><span data-stu-id="abf0a-105">A custom pipeline component can promote multivalued (that is, arrayed) properties.</span></span> <span data-ttu-id="abf0a-106">複数値プロパティを含むメッセージは、コンテンツ ベースのルーティング (CBR) シナリオでのみサポートされます。オーケストレーションにルーティングしたり、追跡目的で使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="abf0a-106">Messages that contain multivalued properties are only supported in content-based routing (CBR) scenarios; they cannot be routed to orchestrations or be used for tracking purposes.</span></span>  
  
 <span data-ttu-id="abf0a-107">終了タグが存在する空要素では、既定値や固定値は昇格されません。</span><span class="sxs-lookup"><span data-stu-id="abf0a-107">The XML Disassembler does not promote default or fixed values for an empty element if it has a closing tag.</span></span> <span data-ttu-id="abf0a-108">たとえば、 \<field1\>次の XML では昇格されません。</span><span class="sxs-lookup"><span data-stu-id="abf0a-108">For example, \<field1\> is not promoted in the following XML.</span></span>  
  
```  
<document>  
   <field1></field1>  
</document>  
```  
  
 <span data-ttu-id="abf0a-109">ただし、次の例のように、終了タグのない空要素は昇格されます。</span><span class="sxs-lookup"><span data-stu-id="abf0a-109">However, an empty element without a closing tag (as shown in the following example) is promoted.</span></span>  
  
```  
<document>  
   <field1/>  
</document>  
```  
  
 <span data-ttu-id="abf0a-110">ドキュメントから datetime データを読み取り、それをコンテキスト プロパティに設定するとき、データが UTC 形式であった場合、その形式が維持されます。</span><span class="sxs-lookup"><span data-stu-id="abf0a-110">When reading datetime data from a document and placing it into the context property, if the data is in UTC format, that format is preserved.</span></span> <span data-ttu-id="abf0a-111">datetime データがローカル時刻にオフセット値を加えた形式になっている場合、BizTalk Server によって、datetime の形式が UTC 形式に変換されます。この UTC 形式は、ローカル時刻にオフセット値を加算することによって取得されます。</span><span class="sxs-lookup"><span data-stu-id="abf0a-111">If the datetime data is in local+offset format, BizTalk Server converts the datetime format to the UTC format that results from adding the offset to the local time.</span></span> <span data-ttu-id="abf0a-112">datetime 形式にタイム ゾーンも UTC 形式も指定されていなかった場合、ローカル時刻と見なされ、現在のタイム ゾーンに基づいて UTC に変換されます。</span><span class="sxs-lookup"><span data-stu-id="abf0a-112">If the datetime format does not specify time zone or UTC format, the time is assumed to be local and is converted to UTC based on the current time zone.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abf0a-113">参照</span><span class="sxs-lookup"><span data-stu-id="abf0a-113">See Also</span></span>  
 <span data-ttu-id="abf0a-114">[XML 逆アセンブラー パイプライン コンポーネント](../core/xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="abf0a-114">[XML Disassembler Pipeline Component](../core/xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="abf0a-115">XML 逆アセンブラー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="abf0a-115">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)
---
title: Namespace 管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4638c47c-3cdd-43af-aa00-da98e7293503
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa476034a578be24bf388c87f38f910565cd2548
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022472"
---
# <a name="namespace-management"></a><span data-ttu-id="55eb1-102">名前空間の管理</span><span class="sxs-lookup"><span data-stu-id="55eb1-102">Namespace Management</span></span>
<span data-ttu-id="55eb1-103">BizTalk エディターは名前空間をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="55eb1-103">BizTalk Editor provides support for namespaces.</span></span> <span data-ttu-id="55eb1-104">XML の名前空間は、XML メッセージにおける要素名または属性名として使用することのできる名前の集合です。</span><span class="sxs-lookup"><span data-stu-id="55eb1-104">An XML namespace is a collection of names that can be used as element or attribute names in an XML message.</span></span> <span data-ttu-id="55eb1-105">要素名や属性名を名前空間で修飾することにより、同じスキーマ内の別の部分で定義されている同じ要素名や同じ属性名の競合を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="55eb1-105">The namespace qualifies element and attribute names to avoid conflicts between the same element and attribute names that might be defined elsewhere within the same schema.</span></span>  
  
 <span data-ttu-id="55eb1-106">名前空間は、URI (Universal Resource Identifier) で識別されます (URI には、URL (Uniform Resource Locator) または URN (Uniform Resource Name) が使用される)。</span><span class="sxs-lookup"><span data-stu-id="55eb1-106">Namespaces are identified by a Universal Resource Identifier (URI), either as a Uniform Resource Locator (URL) or a Uniform Resource Name (URN).</span></span> <span data-ttu-id="55eb1-107">通常、名前空間には別名が割り当てられます。別名とは、要素名や属性名の前に付加される短いプレフィックスのことで、要素名や属性名との区切りとしてコロン (:) が付きます。</span><span class="sxs-lookup"><span data-stu-id="55eb1-107">They are also given a typically short prefix alias that is prepended with a separating colon (:) from the element or attribute name itself.</span></span> <span data-ttu-id="55eb1-108">たとえば、一般的に、次の名前空間宣言内では、**スキーマ**要素は、スキーマの XSD 表記でします。</span><span class="sxs-lookup"><span data-stu-id="55eb1-108">For example, it is common to see the following namespace declaration within the **schema** element in the XSD representation of the schema.</span></span>  
  
```  
xmlns:xs="http://www.w3.org/2001/XMLSchema"  
  
```  
  
 <span data-ttu-id="55eb1-109">プレフィックスは、xs など、要素として、XSD 全体を通じて表示されることが、**要素**要素 (xs:element) および**属性**要素 (xs:attribute))。</span><span class="sxs-lookup"><span data-stu-id="55eb1-109">The prefix is xs, which you see throughout the XSD representation, qualifying such elements as the **element** element (xs:element) and the **attribute** element (xs:attribute).</span></span>  
  
 <span data-ttu-id="55eb1-110">設定する必要が最初に、メッセージ スキーマと、プロパティ スキーマであるかに関係なく、新しいスキーマを作成するときに、 **Target Namespace**のプロパティ、**スキーマ**ノード適切です。</span><span class="sxs-lookup"><span data-stu-id="55eb1-110">When you first create a new schema, regardless of whether it is a message schema or a property schema, it is important to set the **Target Namespace** property of the **Schema** node properly.</span></span> <span data-ttu-id="55eb1-111">スキーマは、他のスキーマで、インポート/を含める/redefine メカニズムを使用して、上位変換が定義されている任意のプロパティの前に前に、ターゲットの名前空間を確立する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55eb1-111">You need to establish the target namespace before the schema is used by another schema with the import/include/redefine mechanisms, and before any property promotions are defined.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="55eb1-112">大文字と小文字のみが異なる 2 つの名前空間を使用する場合、大文字と小文字を区別する照合順序を指定して BizTalk データベースをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="55eb1-112">If you will be using two namespaces that vary only by case, the BizTalk database must be installed with a case-sensitive collation.</span></span> <span data-ttu-id="55eb1-113">大文字と小文字を区別する照合順序には、たとえば、大文字と小文字の区別を有効にしたバイナリと非バイナリの照合順序などがあります。</span><span class="sxs-lookup"><span data-stu-id="55eb1-113">Examples of case-sensitive collations include binary and non-binary collations with case-sensitivity enabled.</span></span> <span data-ttu-id="55eb1-114">XML は大文字と小文字を区別するので、大文字と小文字を区別する照合順序を指定しないと、スキーマ解決が失敗します。</span><span class="sxs-lookup"><span data-stu-id="55eb1-114">If this is not done, schema resolution will fail because XML is case-sensitive.</span></span>  
  
 <span data-ttu-id="55eb1-115">次の 2 つの名前空間は、スキーマの XSD (XML Schema Definition) 言語表記では、schema 要素に名前空間宣言として自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="55eb1-115">The following two namespaces are automatically added as namespace declarations to the schema element in the XML Schema definition (XSD) language representation of the schema:</span></span>  
  
- <span data-ttu-id="55eb1-116">xmlns:b ="<http://schemas.microsoft.com/BizTalk/2003>"</span><span class="sxs-lookup"><span data-stu-id="55eb1-116">xmlns:b="<http://schemas.microsoft.com/BizTalk/2003>"</span></span>  
  
- <span data-ttu-id="55eb1-117">xmlns:xs ="<http://www.w3.org/2001/XMLSchema>"</span><span class="sxs-lookup"><span data-stu-id="55eb1-117">xmlns:xs="<http://www.w3.org/2001/XMLSchema>"</span></span>  
  
  <span data-ttu-id="55eb1-118">作成中のスキーマから他のスキーマを使用する場合は、それに該当する名前空間を宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55eb1-118">In the course of using other schemas within the schema you are creating, other namespaces will be declared.</span></span> <span data-ttu-id="55eb1-119">これらの名前空間と、自動的に追加された名前空間を調べることができます、 **Imports**  ダイアログ ボックスを使用してアクセスできる、 **Imports**のプロパティ、 **スキーマ**ノード。</span><span class="sxs-lookup"><span data-stu-id="55eb1-119">You can examine these namespaces, as well as the automatically included namespaces, in the **Imports** dialog box that you can access by using the **Imports** property of the **Schema** node.</span></span> <span data-ttu-id="55eb1-120">作成して、スキーマ内の他のスキーマで宣言されているその他のデータ型の使用の詳細については、次を参照してください。[使用その他のスキーマを](../core/schemas-that-use-other-schemas.md)と[スキーマを使用して他のスキーマ作成](../core/how-to-create-schemas-that-use-other-schemas.md)です。</span><span class="sxs-lookup"><span data-stu-id="55eb1-120">For more information about using other data types declared in other schemas within the schema you are creating, see [Schemas That Use Other Schemas](../core/schemas-that-use-other-schemas.md) and [Creating Schemas That Use Other Schemas](../core/how-to-create-schemas-that-use-other-schemas.md).</span></span>  
  
  <span data-ttu-id="55eb1-121">プロパティ スキーマに関連付けられている名前空間で調べることができます、**プロパティの昇格** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="55eb1-121">Namespaces associated with property schemas can be examined in the **Promote Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55eb1-122">参照</span><span class="sxs-lookup"><span data-stu-id="55eb1-122">See Also</span></span>  
 [<span data-ttu-id="55eb1-123">スキーマを作成する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="55eb1-123">Considerations When Creating Schemas</span></span>](../core/considerations-when-creating-schemas.md)
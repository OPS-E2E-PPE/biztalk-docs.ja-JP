---
title: "再利用と派生型 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 240145ea-be41-40ce-8edd-3d4d00e2baec
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2982fdf5e46f813669ff74b513615637aa699bd4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="type-reuse-and-derivations"></a><span data-ttu-id="f65bc-102">型の再利用と派生</span><span class="sxs-lookup"><span data-stu-id="f65bc-102">Type Reuse and Derivations</span></span>
<span data-ttu-id="f65bc-103">XSD (XML Schema Definition) 言語では、複雑なグローバル型を使用することにより、スキーマ内のさまざまな場所で、再利用や再定義が可能な構造化されたデータ型を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="f65bc-103">Within XML Schema definition (XSD) language, complex global types provide a mechanism for defining a structured data type that can be reused, and potentially redefined, at various locations within your schema.</span></span> <span data-ttu-id="f65bc-104">最も典型的な例として、名前、番地、市区町村、都道府県などを含む住所の構造があります。</span><span class="sxs-lookup"><span data-stu-id="f65bc-104">Perhaps the most classic example is an address structure that includes a name, street, city, state, and so on.</span></span> <span data-ttu-id="f65bc-105">また、名前は、姓、ミドル ネーム、および名の文字列を含む構造になります。</span><span class="sxs-lookup"><span data-stu-id="f65bc-105">Further, the name itself might be a structure that includes first, middle, and last name strings.</span></span> <span data-ttu-id="f65bc-106">この複雑な構造がグローバルに定義されると、スキーマ内の複数の場所 (出荷先住所や請求先住所など) でこの構造を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f65bc-106">If this complex structure is defined globally, you can use it in multiple locations within your schema, such as for both a shipping address and a billing address.</span></span>  
  
 <span data-ttu-id="f65bc-107">XSD は、別の型から型を派生するメカニズムも提供します。</span><span class="sxs-lookup"><span data-stu-id="f65bc-107">XSD also provides mechanisms for deriving one type from another.</span></span> <span data-ttu-id="f65bc-108">このメカニズムには、単純コンテンツ型と複合コンテンツ型が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f65bc-108">This includes both simple content types and complex content types.</span></span> <span data-ttu-id="f65bc-109">たとえば、いくつかの特定の文字列だけを有効な値として許可する新しい型を単純な文字列型 (xs:string など) から派生できます。</span><span class="sxs-lookup"><span data-stu-id="f65bc-109">For example, a new type can be derived from a simple string type (such as, xs:string) such that the new type allows only a few particular strings as legal values.</span></span> <span data-ttu-id="f65bc-110">この派生は、制約による派生として XSD 内で認識されます。派生された型で許可される値は、基本型で許可される値よりも制約が多いためです。</span><span class="sxs-lookup"><span data-stu-id="f65bc-110">This type of derivation is known within XSD as derivation by restriction because the values allowed by the derived type are more restrictive than the values allowed by the base type.</span></span>  
  
 <span data-ttu-id="f65bc-111">複合型を含む派生の例として、前述の住所の型があります。</span><span class="sxs-lookup"><span data-stu-id="f65bc-111">An example of a derivation involving a complex type can be seen in the address type previously suggested.</span></span> <span data-ttu-id="f65bc-112">国/地域を住所に使用して、特定の国/地域の住所に対応する住所の型を使用する場合を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="f65bc-112">Suppose that the address type is designed to accommodate the addresses within a particular country/region, where the country/region itself is assumed in the address.</span></span> <span data-ttu-id="f65bc-113">このような住所の型を拡張して国際住所を扱うには、元の住所の型から新しい型を派生し、国/地域などの追加情報を派生された型に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f65bc-113">To extend such an address type to handle international addresses, you can derive a new type from the original address type and then include additional information in the derived type, such as the country/region.</span></span> <span data-ttu-id="f65bc-114">この派生は、基本型を拡張して型を派生するため、拡張による派生として XSD 内で認識されます。</span><span class="sxs-lookup"><span data-stu-id="f65bc-114">This type of derivation is known within XSD as derivation by extension because the derived type has extended the base type.</span></span>  
  
 <span data-ttu-id="f65bc-115">このセクションでは、型の再利用方法、および型が再利用される際に派生を使用して型を再定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f65bc-115">This section describes type reuse and the ways in which you can use derivation to redefine types as they are reused.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f65bc-116">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f65bc-116">In This Section</span></span>  
  
-   [<span data-ttu-id="f65bc-117">複合グローバル型の定義と名前付け</span><span class="sxs-lookup"><span data-stu-id="f65bc-117">Complex Global Type Definition and Naming</span></span>](../core/complex-global-type-definition-and-naming.md)  
  
-   [<span data-ttu-id="f65bc-118">複合グローバル型を使用する方法</span><span class="sxs-lookup"><span data-stu-id="f65bc-118">Ways to Use Complex Global Types</span></span>](../core/ways-to-use-complex-global-types.md)  
  
-   [<span data-ttu-id="f65bc-119">単純型の派生</span><span class="sxs-lookup"><span data-stu-id="f65bc-119">Simple Type Derivation</span></span>](../core/simple-type-derivation.md)
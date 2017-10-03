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
# <a name="type-reuse-and-derivations"></a>型の再利用と派生
XSD (XML Schema Definition) 言語では、複雑なグローバル型を使用することにより、スキーマ内のさまざまな場所で、再利用や再定義が可能な構造化されたデータ型を定義することができます。 最も典型的な例として、名前、番地、市区町村、都道府県などを含む住所の構造があります。 また、名前は、姓、ミドル ネーム、および名の文字列を含む構造になります。 この複雑な構造がグローバルに定義されると、スキーマ内の複数の場所 (出荷先住所や請求先住所など) でこの構造を使用できます。  
  
 XSD は、別の型から型を派生するメカニズムも提供します。 このメカニズムには、単純コンテンツ型と複合コンテンツ型が含まれます。 たとえば、いくつかの特定の文字列だけを有効な値として許可する新しい型を単純な文字列型 (xs:string など) から派生できます。 この派生は、制約による派生として XSD 内で認識されます。派生された型で許可される値は、基本型で許可される値よりも制約が多いためです。  
  
 複合型を含む派生の例として、前述の住所の型があります。 国/地域を住所に使用して、特定の国/地域の住所に対応する住所の型を使用する場合を考えてみます。 このような住所の型を拡張して国際住所を扱うには、元の住所の型から新しい型を派生し、国/地域などの追加情報を派生された型に含めることができます。 この派生は、基本型を拡張して型を派生するため、拡張による派生として XSD 内で認識されます。  
  
 このセクションでは、型の再利用方法、および型が再利用される際に派生を使用して型を再定義する方法について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [複合グローバル型の定義と名前付け](../core/complex-global-type-definition-and-naming.md)  
  
-   [複合グローバル型を使用する方法](../core/ways-to-use-complex-global-types.md)  
  
-   [単純型の派生](../core/simple-type-derivation.md)
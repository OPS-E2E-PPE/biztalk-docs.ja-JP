---
title: "フィールド要素 ノードとフィールド属性 ノード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a1fffbca-8886-42c0-9214-cd0c5314850c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d90f622e20bbdbace6804b2418cb68fd2ad60da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="field-element-nodes-vs-field-attribute-nodes"></a>[フィールド要素] ノードと[フィールド属性] ノード

## <a name="overview"></a>概要
フラット ファイル スキーマは、フラット ファイル逆アセンブラーが受信フラット ファイル インスタンス メッセージを、それと等価な XML 形式に変換するとき、および、フラット ファイル アセンブラーが送信 XML メッセージを、それと等価なフラット ファイル インスタンス メッセージに変換するときに使用されます。 いずれかを使用するこのようなスキーマを構築するときに、**フィールド要素**ノードまたは**フィールド属性**ノード具体的には配置を制御スキーマ内で、フラット ファイル インスタンスの特定のフィールドかどうかメッセージは、XML 要素をまたは同等の XML 形式のメッセージ内の XML 属性に対応しています。  

## <a name="example"></a>例  
 たとえば、左揃え、アスタリスクが埋め込まれたフィールド値"`red*****`"フラット ファイル インスタンス メッセージ変換できるを同等の XML 表現にスキーマ内のフィールドがかどうかに応じて 2 つの異なる方法で、**フィールド要素**ノードまたは**フィールド属性**ノード。 により、スキーマでそのフィールドを表現するときに、**フィールド要素**ノードをその**ノード名**プロパティ"color"と、親に設定する**レコード**ノードがその**ノード名**プロパティが"shirt"、同等の XML は、(太字で表示)、フラット ファイル フィールドに設定します。  
  
```  
<shirt>  
    <color>red</color>  
</shirt>  
```  
  
 により、スキーマで同じフラット ファイル フィールドを表現するときに、**フィールド属性**ノードをその**ノード名**プロパティを設定する色、および含まれている**レコード**ノードには、**ノード名**プロパティが (太字で表示)、フラット ファイル フィールドの同等の XML のシャツに設定します。  
  
```  
<color shirt="red"/>  
```  
  
> [!NOTE]
>  フラット ファイル スキーマがさらに制限がある内を指定された**レコード**ノードで下位**フィールド属性**ノードで下位図形の前になければなりません**レコード**ノードまたは**フィールド要素**ノード。  
  
## <a name="see-also"></a>参照  
-  [フィールドに関する考慮事項](../core/field-considerations.md)
-  **ノード名**プロパティ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
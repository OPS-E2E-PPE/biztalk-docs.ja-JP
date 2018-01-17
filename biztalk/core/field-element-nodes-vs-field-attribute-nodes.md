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
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="field-element-nodes-vs-field-attribute-nodes"></a>[フィールド要素] ノードと[フィールド属性] ノード

## <a name="overview"></a>概要
フラット ファイル スキーマは、フラット ファイル逆アセンブラーが受信フラット ファイル インスタンス メッセージを、それと等価な XML 形式に変換するとき、および、フラット ファイル アセンブラーが送信 XML メッセージを、それと等価なフラット ファイル インスタンス メッセージに変換するときに使用されます。 このようなスキーマを作成するときに使用するか、 **フィールド要素** ノードまたは **フィールド属性** ノード具体的には配置を制御スキーマ内でフラット ファイル インスタンス メッセージの特定のフィールドは、XML 要素をまたは同等の XML 形式のメッセージ内の XML 属性に対応しているかどうか。  

## <a name="example"></a>例  
 左揃え、アスタリスクが埋め込まれたフィールドの値などの"`red*****`"フラット ファイル インスタンス メッセージに変換できる等価な XML 表現が、スキーマ内のフィールドであるかに応じて 2 つの異なる方法で、 **フィールド要素** ノードまたは **フィールド属性** ノードです。 により、スキーマでそのフィールドを表現するときに、**フィールド要素**ノードをその**ノード名**プロパティ"color"と、親に設定する**レコード**ノードがその**ノード名**プロパティが"shirt"、同等の XML は、(太字で表示)、フラット ファイル フィールドに設定します。  
  
```  
<shirt>  
    <color>red</color>  
</shirt>  
```  
  
 スキーマで同じフラット ファイル フィールドを表現するときに、 **フィールド属性** を持つノードの **ノード名** プロパティには、色、および格納している設定 **レコード** ノードには、 **ノード名** プロパティは、(太字で表示)、フラット ファイル フィールドに相当する XML のシャツに設定。  
  
```  
<color shirt="red"/>  
```  
  
> [!NOTE]
>  フラット ファイル スキーマにさらに制限がある内を指定された **レコード** ノードの下位 **フィールド属性** ノードは、下位の前にする必要があります **レコード** ノードまたは **フィールド要素** ノードです。  
  
## <a name="see-also"></a>参照  
-  [フィールドに関する注意](../core/field-considerations.md)
-  **ノード名**プロパティ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
---
title: フィールド要素 ノードとフィールド属性 ノード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1fffbca-8886-42c0-9214-cd0c5314850c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6c56aae4e681632ef056a7ed3b85aa5c4f88f89
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974163"
---
# <a name="field-element-nodes-vs-field-attribute-nodes"></a>[フィールド要素] ノードと[フィールド属性] ノード

## <a name="overview"></a>概要
フラット ファイル スキーマは、フラット ファイル逆アセンブラーが受信フラット ファイル インスタンス メッセージを、それと等価な XML 形式に変換するとき、および、フラット ファイル アセンブラーが送信 XML メッセージを、それと等価なフラット ファイル インスタンス メッセージに変換するときに使用されます。 いずれかを使用するこのようなスキーマを作成するときに、**フィールド要素**ノードまたは**フィールド属性**ノード具体的には配置を制御するスキーマ内でかどうか、フラット ファイル インスタンスの特定のフィールドメッセージは、XML 要素をまたは同等の XML 形式のメッセージ内の XML 属性に対応しています。  

## <a name="example"></a>例  
 左揃え、アスタリスクが埋め込まれたフィールドの値ではたとえば、"`red*****`"フラット ファイル インスタンス メッセージに変換できる同等の XML 表現、スキーマ内のフィールドは、かどうかに応じて 2 つの異なる方法で、**フィールド要素**ノードまたは**フィールド属性**ノード。 ときにそのフィールドは、スキーマ内に表されます、**フィールド要素**ノードとその**ノード名**プロパティが"color"、および格納オブジェクトに設定**レコード**ノードがその**ノード名**プロパティが"shirt"、同等の XML は (太字で表示)、フラット ファイル フィールドに設定します。  

```  
<shirt>  
    <color>red</color>  
</shirt>  
```  

 同じフラット ファイル フィールドは、スキーマ内に表されます、**フィールド属性**ノードでその**ノード名**プロパティには、色、および格納している設定**レコード**ノードがその**ノード名**プロパティは (太字で表示)、フラット ファイル フィールドに相当する XML のシャツに設定します。  

```  
<color shirt="red"/>  
```  

> [!NOTE]
>  フラット ファイル スキーマがさらに制限がある内を指定された**レコード**ノードの下位**フィールド属性**ノードは、下位のより前に、でなければなりません**レコード**ノードまたは**フィールド要素**ノード。  

## <a name="see-also"></a>参照  
- [フィールドに関する注意](../core/field-considerations.md)
- **ノード名**プロパティ [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]

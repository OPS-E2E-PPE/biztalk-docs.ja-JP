---
title: 等価のノードとその子ノード |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a85c6a1-6121-4849-b958-7c4bd1c7c552
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05c5603cf1882aa7b262ecc5393a9d91dc93da10
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970808"
---
# <a name="equivalent-nodes-and-their-child-nodes"></a>等価のノードとその子ノード

## <a name="overview"></a>概要
**\<等価\>** ノードとその子で使用、スキーマ ツリーを複雑なデータの種類のポリモーフィズムの出現を表示します。 ある複合データ型から別の複合データ型を派生させた場合、XSD における多態性により、ベースとなる複合データ型が指定されているインスタンス メッセージ内の対応位置には、この 2 つのデータ型のどちらでも出現できるようになります。 スキーマの検証中に特定の場所に複数の複合データ型の 1 つは許可されているという事実によって表される暗黙的に関連付けられている基本の複雑なデータ型の名前、**基本**の属性**拡張子**または**制限**派生複合データ型の要素。 スキーマ ツリーで、この多態性をより明確にする、 **\<等価\>** ノードとその子ノードが明示的に表示されます。  
  
 **\<等価\>** 発生インスタンス内の位置で発生する可能性があります複数の複合データ型があることを示す、ベース複合データ型の子ノードとしてノードが表示されますメッセージ。 子ノード、 **\<等価\>** ノードの値として表示されます、**名前**の対応する属性**complexType**山かっこ内に表示される、ポリモーフィズムの XSD 表記内の要素 (\<名前\>)。  
  
 **\<等価\>** ノードとその子の各それらに関連付けられている 2 つのプロパティがあります。  
  
-   **\<等価\>** ノード:**ノード名**と**基本データ型**
  
-   子ノード:**ノード名**と**派生型**

これらのプロパティの詳細について[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
## <a name="xsd-representation"></a>XSD 表記  
 直接の XSD 表記ではありません、 **\<等価\>** ノードとその子。 このノードは、スキーマ ツリー内で複合データ型の多態性を一見してわかるようにするために使用されるノードです。  
  
## <a name="see-also"></a>参照  
-  [スキーマの BizTalk 表記](../core/biztalk-representation-of-schemas.md)   
-  [ノードのプロパティ](../core/node-properties.md)   
-  **シーケンス グループ ノードのプロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  
-  [ノードのプロパティを設定する方法](../core/how-to-set-node-properties.md)
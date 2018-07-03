---
title: 等価のノードとその子ノード |Microsoft Docs
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
ms.openlocfilehash: 82c58b477130431ce2b115cb141af759b6614b57
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012051"
---
# <a name="equivalent-nodes-and-their-child-nodes"></a>等価のノードとその子ノード

## <a name="overview"></a>概要
**\<同等\>** ノードとその子を使ってスキーマ ツリーで複雑なデータの種類のポリモーフィズムの出現回数を表示します。 ある複合データ型から別の複合データ型を派生させた場合、XSD における多態性により、ベースとなる複合データ型が指定されているインスタンス メッセージ内の対応位置には、この 2 つのデータ型のどちらでも出現できるようになります。 スキーマの検証中に特定の場所で複数の複雑なデータ型のいずれかが許可されているという事実によって表される暗黙的に関連付けられている基本の複雑なデータ型の名前、**基本**属性、の**拡張子**または**制限**派生複合データ型の要素。 スキーマ ツリーで、このポリモーフィズムをより明確に、 **\<同等\>** ノードとその子ノードが明示的に表示されます。  

 **\<同等\>** ノードが出現するインスタンスでは、その位置で発生する可能性が複数の複合データ型があることを示す、基本の複雑なデータ型の子ノードとして表示されますメッセージ。 子ノード、 **\<同等\>** ノードは、の値として表示されます、**名前**属性に対応する**complexType**山かっこ内に表示される、ポリモーフィズムの XSD 表記内の要素 (\<名前\>)。  

 **\<同等\>** ノードとその子はそれらに関連付けられている 2 つのプロパティがあります。  

-   **\<等価\>** ノード:**ノード名**と**基本データ型**

-   子ノード:**ノード名**と**派生型**

これらのプロパティについて詳しく[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。

## <a name="xsd-representation"></a>XSD 表記  
 直接表す XSD 表記ではありません、 **\<同等\>** ノードとその子。 このノードは、スキーマ ツリー内で複合データ型の多態性を一見してわかるようにするために使用されるノードです。  

## <a name="see-also"></a>参照  
- [スキーマの BizTalk 表記](../core/biztalk-representation-of-schemas.md)   
- [ノードのプロパティ](../core/node-properties.md)   
- **シーケンス グループ ノードのプロパティ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  
- [ノードのプロパティを設定する方法](../core/how-to-set-node-properties.md)

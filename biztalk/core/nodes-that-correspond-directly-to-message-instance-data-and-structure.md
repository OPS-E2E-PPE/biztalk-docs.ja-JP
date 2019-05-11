---
title: メッセージに直接対応しているノード インスタンスのデータおよび構造体 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 18cf721c-2972-43c6-8ae4-f2f8f83ba2c5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eef4c9c8ae710aa75b1cb05ad8f5b4732f06bd30
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323628"
---
# <a name="nodes-that-correspond-directly-to-message-instance-data-and-structure"></a>メッセージ インスタンス データおよび構造に直接対応しているノード
スキーマによって管理するインスタンス メッセージの XML 表現の要素と属性に直接対応して一部の BizTalk エディターでスキーマを作成するために使用するノードの種類 (その他のインスタンス メッセージの書式設定、フラット ファイル形式などこれ対応のみ存在して、その他の形式に変換する前に他の形式から変換後)。 これらのノード型は**レコード**ノード (ルートを含む**レコード**ノード)、**フィールド要素**ノード、および**フィールド属性**ノード。  
  
 値に、**ノード名**のプロパティ**レコード**と**フィールド要素**ノードが準拠するもの、XML インスタンス メッセージ内の対応する要素の名前を指定しますスキーマです。 同様に、値に付ける、**ノード名**プロパティの**フィールド属性**ノードが XML インスタンス メッセージのスキーマ準拠するもので、対応する属性の名前を指定します。 このプロパティについて詳しく[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
  
 このセクションの残りの部分は、このクラスでは、ルート ノードの詳細情報を提供**レコード**ノードのスキーマで個別に扱うための特別な役割のを受信します。  
  
## <a name="next-steps"></a>次のステップ 
  
-   [ルート ノード](../core/root-nodes.md)  
  
-   [[レコード] ノード](../core/record-nodes.md)  
  
-   [[フィールド要素] ノード](../core/field-element-nodes.md)  
  
-   [[フィールド属性] ノード](../core/field-attribute-nodes.md)
---
title: 識別フィールドのデータとしてメッセージ コンテキストにコピーする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 004a13ca-a162-4a5e-9f72-8a5c55bbb7a6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fd5708fb972c21c84ae70f258c46e2d4cbcced9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340122"
---
# <a name="how-to-copy-data-to-the-message-context-as-distinguished-fields"></a>識別フィールドとしてメッセージ コンテキストにデータをコピーする方法
このトピックではプロパティとして昇格させる手順、**識別フィールド**します。  
  
 選択した可能性があります**識別フィールド**経由での昇格**プロパティ フィールド**次の理由の上位変換。  
  
-   **プロパティ フィールド**値は、長さが 255 文字に制限されています。  
  
-   **プロパティ フィールド**値がデータベースに格納されよりも多くのオーバーヘッドがあるため**識別フィールド**します。 **識別フィールド**追加のストレージが必要としないのエイリアスでは基本的には、 **XPath**を可能にするために複数のオーケストレーションがメッセージから直接、関連する値に簡単にアクセスします。  
  
### <a name="to-promote-a-property-as-a-distinguished-field"></a>プロパティを識別フィールドとして昇格させる  
  
1.  BizTalk エディターでは、1 つまたは複数のプロパティを昇格するスキーマを開き、(最初の) を選択**フィールド要素**、**フィールド属性**、または**レコード**ノードとして昇格する、**識別フィールド**します。  
  
    > [!NOTE]
    >  [レコード] ノードは、としては昇格されません**識別フィールド**が含まれているコンテンツの種類に関係なく、します。  
  
2.  選択したノードを右クリックし、をクリックして**昇格**、] をクリックし、 **[昇格の表示**します。  
  
     **プロパティの昇格**] ダイアログ ボックスの左側にあるスキーマ ツリーで選択した [選択したノードが表示されたダイアログ ボックスが開きます。  
  
3.  **プロパティの昇格**ダイアログ ボックスで、**識別フィールド**タブ。  
  
4.  左側にあるスキーマ ツリーで選択されている昇格するノードで、**プロパティの昇格**ダイアログ ボックスで、をクリックして**追加**します。  
  
     選択したノードを一覧に追加が許可されている場合、**識別フィールド**タブ。昇格できない場合は、その説明を示すメッセージ ボックスが表示されます。  
  
5.  プロモーションの追加のノードを選択するをクリックすると、ダイアログ ボックスの左側にあるスキーマ ツリーで**追加**選択後します。  
  
6.  完了したら、クリックして**OK**します。  
  
     昇格対象として選択したノードになった**識別フィールド**します。  
  
## <a name="see-also"></a>参照  
 [プロパティの昇格](../core/promoting-properties.md)   
 [プロパティ スキーマを作成する方法](../core/how-to-create-property-schemas.md)   
 [メッセージ処理を管理するためのメッセージの内容の使用方法](../core/ways-to-use-message-content-to-control-message-processing.md)
---
title: 識別フィールドのデータとしてメッセージ コンテキストにコピーする方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 2ea68bc0b83c5a8f886416107e1dc98ea8ad8d30
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248970"
---
# <a name="how-to-copy-data-to-the-message-context-as-distinguished-fields"></a>識別フィールドとしてメッセージ コンテキストにデータをコピーする方法
このトピックでは、プロパティとして昇格させる手順について、**識別フィールド**です。  
  
 できます**識別フィールド**経由で昇格**プロパティ フィールド**次の理由で昇格します。  
  
-   **プロパティ フィールド**値は 255 文字の長さに制限されます。  
  
-   **プロパティ フィールド**値、データベースに格納されていて、したがってよりもオーバーヘッドが大きく**識別フィールド**です。 **識別フィールド**; 追加のストレージを必要としないのエイリアスでは基本的には、 **XPath**ことのできるので、オーケストレーションをより簡単に、メッセージから直接、関連する値にアクセスします。  
  
### <a name="to-promote-a-property-as-a-distinguished-field"></a>プロパティを識別フィールドとして昇格させるには  
  
1.  BizTalk エディターで、1 つ以上のプロパティを昇格させるスキーマを開き (最初の) を選択し、**フィールド要素**、**フィールド属性**、または**レコード**ノードとして昇格する、**識別フィールド**です。  
  
    > [!NOTE]
    >  レコード ノードは、としては昇格されません**識別フィールド**が含まれているコンテンツの種類に関係なく、します。  
  
2.  選択したノードを右クリックし、をクリックして**昇格**、クリックして**昇格の**します。  
  
     **プロパティの昇格**] ダイアログ ボックスの左側にあるスキーマ ツリーで選択した [選択したノードを示すダイアログ ボックスが開きます。  
  
3.  **プロパティの昇格**ダイアログ ボックスで、**識別フィールド**タブです。  
  
4.  左側にあるスキーマ ツリーで選択されている昇格するノードで、**プロパティの昇格**ダイアログ ボックスで、をクリックして**追加**です。  
  
     許可された場合、選択したノードが一覧に追加、**識別フィールド**タブです。昇格できない場合は、その説明を示すメッセージ ボックスが表示されます。  
  
5.  プロモーションの追加のノードをクリックすると、ダイアログ ボックスの左側にあるスキーマ ツリーで選択できる**追加**選択するたびにします。  
  
6.  完了したら、クリックして**OK**です。  
  
     昇格対象として選択したノードは、今すぐ**識別フィールド**です。  
  
## <a name="see-also"></a>参照  
 [プロパティの昇格](../core/promoting-properties.md)   
 [プロパティ スキーマを作成する方法](../core/how-to-create-property-schemas.md)   
 [メッセージ処理を制御するメッセージの内容を使用する方法](../core/ways-to-use-message-content-to-control-message-processing.md)
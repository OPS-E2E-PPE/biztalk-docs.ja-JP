---
title: "識別フィールドを使用してインスタンス メッセージの処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b8f3f77-5385-4294-b441-bcb28bdc51b4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4dca22ff1b09a0d1cfb261a9d5726da8b1b17b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="instance-message-processing-using-distinguished-fields"></a>識別フィールドを使用したインスタンス メッセージの処理
使用してプロパティの昇格、**識別フィールド**メカニズムでは、プロパティ スキーマの作成は必要ありません。 すべてのプロパティの昇格を使用すると、**プロパティの昇格**を使用してアクセスされる ダイアログ ボックス、**プロパティの昇格**のプロパティ、**スキーマ**内のノードメッセージ スキーマ、またはを使用して、**昇格 & #124 です。プロモーションを表示する**コマンドを**BizTalk**またはショートカット メニュー。  
  
 **プロパティの昇格** ダイアログ ボックスで、確認、**識別フィールド** ダイアログ ボックスの右側にあるタブが選択されています。 検索して選択 ダイアログ ボックスの左側にあるスキーマ ツリーのノードを展開し、**フィールド要素**ノードまたは**フィールド属性**識別フィールドとして昇格するノードし、をクリックして**追加**です。 操作手順については、プロパティを昇格させる**識別フィールド**を使用して、**プロパティの昇格**ダイアログ ボックスを参照してください[Distinguished としてメッセージ コンテキストへのデータのコピーフィールド](../core/how-to-copy-data-to-the-message-context-as-distinguished-fields.md)です。  
  
> [!NOTE]
>  昇格することも、**レコード**場合に限り、プロパティ スキーマで、[フィールド要素] ノードにノード、**コンテンツ タイプ**のプロパティ、**レコード**に設定されているノード**SimpleContent**です。  
  
 識別フィールドとして昇格されるプロパティのセットからノードを削除するには、上、昇格させたプロパティを選択、**識別フィールド**タブをクリックし、をクリックして**削除**です。  
  
 識別フィールドのメカニズムを使ってプロパティを昇格させると、ルート要素の注釈サブ要素内に、XSD (XML Schema Definition) 言語のコードが追加されます。 次の例は、識別フィールドのメカニズムを使って昇格させた 2 つのプロパティのコードを示しています。  
  
```  
<b:properties>  
    <b:property distinguished="true"  
        xpath="/*[local-name()='Record' and namespace-  
         uri()='http://BizTalk_Server_Project1.Schema11']/*[local-  
         name()='test']/*[local-name()='Field1']" />  
    <b:property distinguished="true"  
        xpath="/*[local-name()='Record' and namespace-  
         uri()='http://BizTalk_Server_Project1.Schema11']/*[local-  
         name()='test']/*[local-name()='Field5' and position()='1']" />  
</b:properties>  
```  
  
## <a name="see-also"></a>参照  
 [メッセージ処理を制御するメッセージの内容を使用する方法](../core/ways-to-use-message-content-to-control-message-processing.md)   
 [識別フィールドとしてメッセージ コンテキストにデータをコピーする方法](../core/how-to-copy-data-to-the-message-context-as-distinguished-fields.md)
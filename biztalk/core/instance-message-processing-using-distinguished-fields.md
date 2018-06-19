---
title: 識別フィールドを使用してインスタンス メッセージの処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b8f3f77-5385-4294-b441-bcb28bdc51b4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4dca22ff1b09a0d1cfb261a9d5726da8b1b17b1
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
ms.locfileid: "22257514"
---
# <a name="instance-message-processing-using-distinguished-fields"></a>識別フィールドを使用したインスタンス メッセージの処理
使用してプロパティの昇格、 **識別フィールド** メカニズムには、プロパティ スキーマの作成は不要です。 すべてのプロパティの昇格では使用すると、 **プロパティの昇格** を使用してアクセス可能なダイアログ ボックス、 **プロパティの昇格** のプロパティ、 **スキーマ** ノード メッセージ スキーマでまたはを使用して、 **昇格と &#124; 文字です。プロモーションを表示する** コマンドを **BizTalk** またはショートカット メニュー。  
  
 **プロパティの昇格**  ダイアログ ボックスで、確認、 **識別フィールド**  ダイアログ ボックスの右側にタブを選択します。 検索して選択 ダイアログ ボックスの左側にあるスキーマ ツリーのノードを展開し、 **フィールド要素** ノードまたは **フィールド属性** クリックして、識別フィールドとして昇格するノードを **追加**します。 操作手順については、プロパティを昇格させる**識別フィールド**を使用して、**プロパティの昇格**ダイアログ ボックスを参照してください[Distinguished としてメッセージ コンテキストへのデータのコピーフィールド](../core/how-to-copy-data-to-the-message-context-as-distinguished-fields.md)です。  
  
> [!NOTE]
>  昇格することも、 **レコード** ノードの場合に限り、プロパティ スキーマ フィールド要素 ノードを **コンテンツ タイプ** のプロパティ、 **レコード** にノードが設定されている **SimpleContent**します。  
  
 識別フィールドとして昇格されるプロパティのセットからノードを削除するには、昇格させたプロパティを選択、 **識別フィールド** タブをクリックし、クリックして **削除**します。  
  
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
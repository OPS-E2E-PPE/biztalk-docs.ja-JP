---
title: 識別フィールドを使用して、インスタンス メッセージの処理 |Microsoft Docs
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
ms.openlocfilehash: db91474677843963dc578ee617ac238df5f13368
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382110"
---
# <a name="instance-message-processing-using-distinguished-fields"></a>識別フィールドを使用して、インスタンス メッセージの処理
プロパティの昇格を使用して、**識別フィールド**メカニズムでは、プロパティ スキーマの作成は必要ありません。 すべてのプロパティの昇格では使用すると、 **プロパティの昇格** を使用してアクセス可能なダイアログ ボックス、 **プロパティの昇格** のプロパティ、 **スキーマ** ノード メッセージ スキーマでまたはを使用して、 **昇格と &#124; 文字です。プロモーションを表示する** コマンドを **BizTalk** またはショートカット メニュー。  
  
 **プロパティの昇格** ダイアログ ボックスを確認してください、**識別フィールド** ダイアログ ボックスの右側にあるタブが選択されています。 探して選択します ダイアログ ボックスの左側にあるスキーマ ツリー内のノードを展開し、**フィールド要素**ノードまたは**フィールド属性**、識別フィールドとして昇格するノードをクリックしクリックして**追加**します。 プロパティを昇格させる方法についてステップ バイ ステップの手順について**識別フィールド**を使用して、**プロパティの昇格**ダイアログ ボックスを参照してください[Distinguished としてメッセージ コンテキストへのデータのコピーフィールド](../core/how-to-copy-data-to-the-message-context-as-distinguished-fields.md)します。  
  
> [!NOTE]
>  昇格することも、**レコード**ノード プロパティのスキーマが場合にのみで、[フィールド要素] ノードを**コンテンツの種類**のプロパティ、**レコード**にノードが設定されている**SimpleContent**します。  
  
 識別フィールドとして昇格されるプロパティのセットからノードを削除するには、上、昇格させたプロパティを選択、**識別フィールド**タブをクリックし、をクリックして**削除**します。  
  
 識別フィールドのメカニズムを使用してプロパティを昇格するときに、XML スキーマ定義 (XSD) 言語のコードはルート要素の注釈サブ要素内で追加されます。 次の例では、フラグメントは、識別フィールドのメカニズムを使用して昇格させた 2 つのプロパティを示します。  
  
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
 [メッセージの内容をコントロール メッセージの処理を使用する方法](../core/ways-to-use-message-content-to-control-message-processing.md)   
 [識別フィールドとしてメッセージ コンテキストにデータをコピーする方法](../core/how-to-copy-data-to-the-message-context-as-distinguished-fields.md)
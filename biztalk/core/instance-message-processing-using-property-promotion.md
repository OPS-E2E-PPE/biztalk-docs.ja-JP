---
title: インスタンスのプロパティの昇格を使用してメッセージの処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 753571b8-4609-4ac4-a974-8bd6dfecb077
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df619a7e8ec48565d06f16f4f8acbc5ac81c524f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331867"
---
# <a name="instance-message-processing-using-property-promotion"></a>プロパティの昇格を使用してインスタンス メッセージの処理
プロパティの昇格を使用して、**プロパティ フィールド**メソッド、プロパティ スキーマの作成が必要です。 プロパティ スキーマの作成の詳細については、次を参照してください。[プロパティ スキーマを作成する方法](../core/how-to-create-property-schemas.md)します。 すべてのプロパティの昇格と同様、**プロパティの昇格** ダイアログ ボックスを使用してアクセスできますが、**プロパティの昇格**のプロパティ、**スキーマ**内のノードメッセージのスキーマです。  
  
> [!NOTE]
>  昇格プロパティを使用してアクセスするためにプロパティを昇格するパイプラインを選択する必要があります。 たとえば、PassthruReceive パイプラインを使用する場合のプロパティは昇格されない;その結果、コンテンツ ベースのルーティングおよびその他の機能が正しく機能しません。  
  
 **プロパティの昇格** ダイアログ ボックスに、ことを確認します、**プロパティ フィールド** ダイアログ ボックスの右側にあるタブが選択されています。 次に、プロパティ スキーマの一覧の上部で、適切なプロパティ スキーマが含まれていることを確認、**プロパティ フィールド**タブ。必要に応じて、使用して、適切なプロパティ スキーマを選択するフォルダー ボタンを使用して、 **BizTalk 型の選択** ダイアログ ボックス。 次を選択します ダイアログ ボックスの左側にあるスキーマ ツリー内のノードを展開し、**フィールド要素**ノードまたは**フィールド属性**プロパティ フィールドとして昇格をクリックするノード**追加**します。 ドロップダウン リストの最後に、使用、**プロパティ**の列、**プロパティ フィールド ディクショナリ**を選択するテーブルを**フィールド要素**に使用するプロパティ スキーマのノード昇格させたプロパティに関連付けます。 使用して、プロパティ フィールドにプロパティを昇格させる方法についてステップ バイ ステップの手順について、**プロパティの昇格** ダイアログ ボックスを参照してください[プロパティ フィールドとしてメッセージ コンテキストにデータをコピーする方法](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)します。  
  
> [!NOTE]
>  昇格することも、**レコード**にノードを**フィールド要素**ノード プロパティのスキーマが場合にのみ、**コンテンツの種類**のプロパティ、**レコード**にノードが設定されている**SimpleContent**します。  
  
> [!NOTE]
>  同じプロパティ昇格できます何度もスキーマ内でとして異なるルート ノードでこれらの昇格をすべて実行されます。 メッセージは単一のルート ノードに対して検証し、そのルート ノードで昇格したプロパティだけが実行時に評価されるためです。  
  
 削除する、**フィールド要素**ノードまたは**フィールド属性**プロパティ フィールドとして昇格されるプロパティのセットからのノードで昇格させたプロパティを選択する、**プロパティ フィールド ディクショナリ**テーブルに対して、**プロパティ フィールド**タブをクリックし、をクリックし、**削除**します。  
  
 **ノード パス**内の列、**プロパティ フィールド ディクショナリ**テーブルは、昇格させたプロパティに対応するスキーマ ノードの XPath を示します。 この値を使用して直接編集することができます、**インスタンス XPath の編集** ダイアログ ボックス。 省略記号をクリックして、このダイアログ ボックスを開くことができます (**.**) そのセルを選択すると、対応するセルの右端に表示されるボタン。 BizTalk エディターで解決できない Xpath が適切な検証操作を防ぐために、XPath の値を直接編集するとき、十分に注意してする必要があります。  
  
 BizTalk エディターを使用してプロパティを昇格できる便利なコマンドも提供します、**プロパティ フィールド**メカニズム。 このコマンドはクイック昇格と呼ばれ、使用して設定できることをお勧めします **昇格と &#124; 文字です。クイック昇格** コマンド、BizTalk メニューとショートカット メニューをします。 このコマンドは、選択した昇格**フィールド**ノード (または**レコード**ノード) で指定されたプロパティ スキーマが自動的に作成されるプロパティ フィールドに、**既定のプロパティ スキーマ名**プロパティ、**プロパティ ページ**含んでいるスキーマのダイアログ ボックス。 クイック昇格コマンドを使用して、プロパティ フィールドにプロパティを昇格させる方法についてステップ バイ ステップの手順については、次を参照してください。[プロパティ フィールドとしてメッセージ コンテキストにデータをコピーする方法](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)します。  
  
 プロパティ フィールドのメカニズムを使用してプロパティを昇格するときに、XML スキーマ定義 (XSD) 言語の 2 つのフラグメントは、メッセージ スキーマの XSD 表記に追加されます。 最初の XSD フラグメントは、関連付けられる注釈フラグメント、**スキーマ**要素を次の例のように、対応するプロパティ スキーマを識別します。  
  
```  
<xs:annotation>  
    <xs:appinfo>  
        <b:imports>  
            <b:namespace prefix="ns0"  
                uri="http://BizTalk_Server_Project1.PropertySchema1"  
                location=".\propertyschema1.xsd" />  
        </b:imports>  
    </xs:appinfo>  
</xs:annotation>  
```  
  
 2 番目の XSD フラグメントは、関連付けられる注釈フラグメント、**ルート**(かどうかが変更されています) に関係なく要素を識別する、**フィールド要素**ノードまたは**フィールド属性**プロパティを使用して昇格されたノードの値フィールドのメカニズムは、次の例のように。  
  
```  
<xs:annotation>  
    <xs:appinfo>  
        <b:properties>  
            <b:property name="ns0:PromProp1"  
                xpath="/*[local-name()='Root' and namespace-  
                 uri()='http://BizTalk_Server_Project1.Schema2']/  
                 *[local-name()='MyRec1']/@*[local-  
                 name()='Field_x0020_1']" />  
            <b:property name="ns0:PromProp2"  
                xpath="/*[local-name()='Root' and namespace-  
                 uri()='http://BizTalk_Server_Project1.Schema2']/  
                 *[local-name()='MyRec1']/*[local-  
                 name()='ProgramManager']/*[local-name()='Name']" />  
        </b:properties>  
    </xs:appinfo>  
</xs:annotation>  
```  
  
## <a name="see-also"></a>参照  
 [メッセージの内容をコントロール メッセージの処理を使用する方法](../core/ways-to-use-message-content-to-control-message-processing.md)   
 [プロパティ フィールドとしてメッセージ コンテキストにデータをコピーする方法](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)
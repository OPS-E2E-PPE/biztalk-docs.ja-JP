---
title: プロパティの昇格を使用してメッセージの処理をインスタンス化 |Microsoft ドキュメント
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
ms.openlocfilehash: 288657d43443582c5a05df5dd6e67059eca572e9
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="instance-message-processing-using-property-promotion"></a>プロパティの昇格を使用したインスタンス メッセージ処理
使用してプロパティの昇格、 **プロパティ フィールド** メソッド、プロパティ スキーマの作成が必要です。 プロパティ スキーマの作成の詳細については、次を参照してください。[プロパティ スキーマを作成する方法](../core/how-to-create-property-schemas.md)です。 すべてのプロパティの昇格では使用すると、 **プロパティの昇格** を使用してアクセス可能なダイアログ ボックス、 **プロパティの昇格** のプロパティ、 **スキーマ** メッセージ スキーマ内のノードです。  
  
> [!NOTE]
>  昇格プロパティにアクセスして使用するには、プロパティを昇格するパイプラインを選択する必要があります。 たとえば、PassthruReceive パイプラインを使用する場合はプロパティは昇格されないため、コンテンツ ベースのルーティングおよびその他の機能は正常に機能しません。  
  
 **プロパティの昇格**  ダイアログ ボックスで確認、 **プロパティ フィールド**  ダイアログ ボックスの右側にタブを選択します。 次に、プロパティ スキーマの一覧の上部で、適切なプロパティ スキーマが含まれていることを確認、 **プロパティ フィールド**  タブをクリックします。必要に応じて、使用してフォルダー ボタンを使用して、適切なプロパティ スキーマを選択する、 **BizTalk 型の選択** ダイアログ ボックス。 次に、[を検索して選択] ダイアログ ボックスの左側にあるスキーマ ツリーでノードを展開して、 **フィールド要素** ノードまたは **フィールド属性** クリックして、プロパティ フィールドとして昇格するノードを **追加**します。 ドロップ ダウン リストの最後に、使用、 **プロパティ** の列、 **プロパティ フィールド ディクショナリ** を選択するテーブル、 **フィールド要素** に昇格させたプロパティを関連付けるプロパティ スキーマのノードです。 操作手順については、プロパティ フィールドを使用するプロパティの昇格、**プロパティの昇格** ダイアログ ボックスを参照してください[プロパティ フィールドとしてメッセージ コンテキストにデータをコピーする方法](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)です。  
  
> [!NOTE]
>  昇格することも、 **レコード** ノードを **フィールド要素** 場合に限り、プロパティ スキーマ内のノード、 **コンテンツ タイプ** のプロパティ、 **レコード** にノードが設定されている **SimpleContent**します。  
  
> [!NOTE]
>  同じプロパティをスキーマ内で複数回昇格できます。ただし、これらの昇格が、それぞれ異なるルート ノードについて行われる場合に限ります。 これは、メッセージの検証は単一のルート ノードに対して行われ、そのルート ノードで昇格したプロパティだけが実行時に評価されるためです。  
  
 削除する、 **フィールド要素** ノードまたは **フィールド属性** プロパティ フィールドとして昇格するプロパティのセットからのノードで昇格させたプロパティを選択して、 **プロパティ フィールド ディクショナリ** テーブルに、 **プロパティ フィールド** タブをクリックし、をクリックし、 **削除**します。  
  
 **ノード パス** 内の列、 **プロパティ フィールド ディクショナリ** テーブルは、昇格させたプロパティに対応するスキーマ ノードの XPath を示します。 この値を編集するにを使用して直接、 **インスタンス XPath の編集**  ダイアログ ボックス。 省略記号ボタンをクリックして、このダイアログ ボックスを開くことができます (**...**) そのセルを選択すると、対応するセルの右端に表示されるボタンをクリックします。 ただし、BizTalk エディターで解決できない XPath が適切な検証操作の妨げとなる場合があるので、XPath の値を直接編集するときは注意してください。  
  
 BizTalk エディターを使用してプロパティを昇格する場合に効率化されたコマンドもでは、 **プロパティ フィールド** メカニズムです。 このコマンドはクイック昇格と呼ばれ、使用して設定できることをお勧めします **昇格と #124 文字です。クイック昇格** コマンド、BizTalk メニューとショートカット メニューをします。 このコマンドは、選択した昇格 **フィールド** ノード (または **レコード** ノード) で指定されたプロパティ スキーマに自動的に作成されるプロパティ フィールドに、 **プロパティ スキーマ名の既定の** プロパティに、 **プロパティ ページ** を含むスキーマのダイアログ ボックス。 クイック昇格 コマンドを使用して、プロパティ フィールドにプロパティを昇格させる方法の詳細な手順については、次を参照してください。[プロパティ フィールドとしてメッセージ コンテキストにデータをコピーする方法](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)です。  
  
 プロパティ フィールドのメカニズムを使用してプロパティを昇格させると、XSD (XML Schema Definition) 言語による 2 つのフラグメントが、XSD 表記のメッセージ スキーマに追加されます。 最初の XSD フラグメントは、関連付けられる注釈フラグメント、 **スキーマ** 要素を次の例に示すように、対応するプロパティ スキーマを識別します。  
  
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
  
 2 番目の XSD フラグメントは、関連付けられる注釈フラグメント、 **ルート** (かどうか、名前が変更されました) に関係なく要素を識別する、 **フィールド要素** ノードまたは **フィールド属性** プロパティを使用して昇格されたノードの値フィールドのメカニズムは、例を次に示します。  
  
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
 [メッセージ処理を制御するメッセージの内容を使用する方法](../core/ways-to-use-message-content-to-control-message-processing.md)   
 [プロパティ フィールドとしてメッセージ コンテキストにデータをコピーする方法](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)
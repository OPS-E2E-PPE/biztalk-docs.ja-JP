---
title: BPEL4WS をインポートする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BPEL4WS, restrictions
- BPEL4WS, importing
- BPEL4WS, orchestrations
- orchestrations, BPEL4WS
ms.assetid: 3626fcb9-8e7d-4812-a0c9-bde6e7954ec8
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b32a0044321ce6ac57d7bd49c14b40ba17430db
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-import-bpel4ws"></a>BPEL4WS をインポートする方法
既存の BPEL4WS をインポートすることによってオーケストレーションを作成することができます。  
  
> [!IMPORTANT]
>  このリリースの BizTalk Server では、BPEL4WS 1.1 をサポートします。 BPEL4WS 1.0 をインポートまたはエクスポートすることはできません。  
  
 BPEL4WS をインポートする方法の例は、次を参照してください。 [BPEL インポート (BizTalk Server サンプル)](../core/bpel-import-biztalk-server-sample.md)です。  
  
### <a name="to-import-bpel4ws-into-an-orchestration"></a>BPEL4WS をオーケストレーションにインポートするには  
  
1.  新しいプロジェクトを作成します。  
  
2.  BizTalk プロジェクトの種類から、[BizTalk Server BPEL インポート プロジェクト] をダブルクリックするか、[BizTalk Server BPEL インポート プロジェクト] を選択して [OK] をクリックします。  
  
3.  ウィザードで、新しい BizTalk プロジェクトにインポートする BPEL ファイル、WSDL ファイル、および XSD ファイルを選択します。 import ステートメントと include ステートメントで参照するすべてのファイルを追加してください。  
  
4.  呼び出す Web サービスに対応した WSDL ファイルを選択します。  
  
     これで新しいオーケストレーションが作成されました。必要に応じて修正するか、そのまま展開できます。  
  
 **BPEL4WS のインポートに関する制限事項**  
  
-   BPEL および WSDL をインポートする際は、WSDL 定義ノードおよび BPEL プロセス ノードの Name プロパティが重複しないようにしてください。  
  
-   インポートする BPEL4WS に XLANG/s の予約語は使用できません。 完全な一覧についてを参照してください。 [xlang/s の予約語](../core/xlang-s-reserved-words.md)です。  
  
-   XSD で定義された単純な型のみサポートされます。  
  
-   xsd:QName はサポートされません。System.String としてインポートされます。 代わりに xsd:string を使用してください。  
  
-   BPEL4WS をインポートする際は、正規 (Canonical) XPaths を使用してください。  
  
     最適なパフォーマンスを得るため、正規 XPaths だけをインポートすることをお勧めします。 '/*[local-name()="someName" and namespace-uri()="someUri"]' のように、ルートを起点とする、昇格されたノードまでのパスを省略せずに記述する必要があります。  
  
     非正規 XPath をインポートする場合は、昇格を削除し、同じフィールドを再度昇格させることによって、正しい正規 XPath をスキーマ エディターに作成させることができます。  
  
     例: (targetNamespace = http://BizTalk_Server_Project3.Schema1)  
  
    ```  
    <element name=Root type=complexType>  
                <sequence>  
                            <element name=promotedField/>  
                </sequence>  
    </element>  
    ```  
  
     XPath - /*[local-name()='Root' and namespace-uri()='http://BizTalk_Server_Project3.Schema1']/\*[local-name()='promotedField' and namespace-uri()='']  
  
    |正規 XPath|非正規 XPath|  
    |---------------------|--------------------------|  
    |BizTalk エディターには、特別なアイコンが表示されます (![](../core/media/ebiz-orch-promotedprop.gif "ebiz_orch_promotedprop")) フィールドを昇格されていることを示すためにします。 正規 XPath 式を使用してフィールドを昇格させることにより、XML のトラバースを効率よく行うことができ、パフォーマンスが向上します。|BizTalk エディターには、特殊なアイコンが表示されません。 コンパイラおよび昇格ダイアログの両方で警告が発生します。 メッセージ サイズが肥大化するなど、単純な影響が発生しますが、これはパフォーマンス上は無視できない影響です。|  
  
## <a name="see-also"></a>参照  
 [BPEL4WS にエクスポートする方法](../core/how-to-export-bpel4ws.md)   
 [XLANG-s から BPEL4WS への種類の変換](../core/xlang-s-to-bpel4ws-type-conversions.md)
---
title: "BPEL4WS にエクスポートする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BPEL4WS, exporting
- BPEL4WS, restrictions
- orchestrations, BPEL4WS
ms.assetid: 4648dfcf-cf48-4471-b088-07252c080fb8
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b16c2e34b498a9fb8d5fd3f6e69f022c2876a763
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-export-bpel4ws"></a>BPEL4WS にエクスポートする方法
既存の BizTalk オーケストレーションを BPEL4WS にエクスポートできます。  
  
> [!IMPORTANT]
>  BizTalk Server のこのリリースでは、BPEL4WS 1.1 をサポートします。 BPEL4WS 1.0 をインポートまたはエクスポートすることはできません。  
  
 オーケストレーションをエクスポートする場合、コンパイルにおける BPEL4WS 準拠の関係上、そのオーケストレーションには、XLANG/s と BPEL4WS 間で共通の機能だけ、または、動作に影響することなく BPEL4WS に変換することのできる機能だけが含まれている必要があります。  
  
## <a name="export-restrictions-on-orchestrations-for-bpel4ws-compliance"></a>オーケストレーションをエクスポートする際の制約 (BPEL4WS 準拠)  
  
-   オーケストレーションの呼び出し図形とオーケストレーションの開始図形は使用できません。  
  
-   変換図形は使用できません。  
  
-   カスタム .NET コンポーネントのメソッドを呼び出すことはできません。  
  
-   長時間実行されるトランザクションにはタイムアウトを適用できません。  
  
-   パラメーターを受け取るオーケストレーションはエクスポートできません。  
  
-   呼び出し可能な補正ハンドラーにパラメーターを割り当てることはできません。  
  
-   変数の型が XPATH でサポートされている必要があります。  
  
-   中断図形は使用できません。  
  
-   リテラル値は、次のいずれかの型である必要があります。  
  
     boolean、char、byte、sbyte、int32、uint32、int64、uint64、single、double、string  
  
-   算術演算子では、次の数値型のオペランドのみサポートされます。  
  
     byte、sbyte、int32、uint32、int64、uint64、single、double  
  
-   関係演算子を char 型には適用できません。  
  
-   式の中では servicelink プロパティを参照できません。  
  
-   間のすべてのアクションを実行することはできません、**送信**図形および**受信**同じ要求-応答の送信ポートを使用する図形です。  
  
-   特定の参照を保持する別のプロジェクトを参照するなどして、Web サービスを間接的に参照することはできません。 プロジェクト内で Web サービスを明示的に参照する必要があります。  
  
-   定数 DateTime や TimeSpan を指定して遅延を定義できません。 System.Xml 名前空間のいずれかの変換クラスを使用する必要があります。  
  
     定数 DateTime の場合: System.Xml.XmlConvert.ToDateTime、System.Xml.XmlConvert.ToDateTime("2004-04-15") 例。  
  
     定数 TimeSpan の場合: System.Xml.XmlConvert.ToTimeSpan System.Xml.XmlConvert.ToTimeSpan("2004-04-15") 例。  
  
> [!NOTE]
>  文字リテラルは、符号なし整数としてエクスポートされます。 たとえば、'a' は 97 のように、'b' は 98 のようにエクスポートされます。  
  
> [!CAUTION]
>  識別子の名前は、W3C Extensible Markup Language (XML) 1.0 仕様に準拠している必要があります。  
  
#### <a name="to-export-an-orchestration-to-bpel4ws"></a>オーケストレーションを BPEL4WS にエクスポートするには  
  
1.  プロジェクトに新しい項目 (BizTalk オーケストレーション) を追加します。  
  
2.  デザイン画面をクリックして、[オーケストレーションのプロパティ] ウィンドウを開きます。  
  
3.  設定**モジュールがエクスポート可能**True に設定します。  
  
4.  名前空間の型**モジュール XML ターゲットの Namespace**です。  
  
5.  設定**エクスポート可能なオーケストレーション**True に設定します。  
  
6.  名前空間の型**オーケストレーション XML Target Namespace**です。  
  
7.  ソリューション エクスプ ローラーで右クリックします。オーケストレーションの ODX ファイルです。  
  
8.  選択**BPEL にエクスポート**です。  
  
     オーケストレーションが BPEL4WS にエクスポートされます。 出力ウィンドウとタスク一覧を調べて、処理が正常に行われたかどうかを確認し、必要に応じて問題を診断します。 エクスポートに成功すると、プロジェクト ディレクトリに .WSDL ファイルおよび .BPEL ファイルが作成されます。  
  
> [!NOTE]
>  オーケストレーションにロール リンク (サービス リンク) に対する割り当てや、動的ポートへのリテラル割り当てが含まれる場合、BizTalk により、ダミーの BPEL4WS エンドポイント参照が生成され、警告が発生します。  
  
## <a name="see-also"></a>参照  
 [BPEL4WS をインポートする方法](../core/how-to-import-bpel4ws.md)   
 [XLANG-s BPEL4WS 型への変換から](../core/xlang-s-to-bpel4ws-type-conversions.md)
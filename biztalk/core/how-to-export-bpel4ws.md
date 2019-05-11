---
title: BPEL4WS にエクスポートする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BPEL4WS, exporting
- BPEL4WS, restrictions
- orchestrations, BPEL4WS
ms.assetid: 4648dfcf-cf48-4471-b088-07252c080fb8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 655c3947283b5cd4cb45d863c416051d08a37a98
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385057"
---
# <a name="how-to-export-bpel4ws"></a>BPEL4WS にエクスポートする方法
既存の BizTalk オーケストレーションを BPEL4WS にエクスポートできます。  
  
> [!IMPORTANT]
>  このリリースの BizTalk Server では、BPEL4WS 1.1 をサポートします。 BPEL4WS 1.0 をインポートまたはエクスポートすることはできません。  
  
 エクスポートする場合コンパイル BPEL4WS 準拠では、オーケストレーションには、xlang/s と BPEL4WS、間に共通の機能または動作に影響を与えることがなく BPEL4WS に変換できる機能のみが含まれている必要があります。  
  
## <a name="export-restrictions-on-orchestrations-for-bpel4ws-compliance"></a>BPEL4WS 準拠するためのオーケストレーションの制限をエクスポートします。  
  
-   オーケストレーションの呼び出し図形またはオーケストレーションの開始図形を使用することはできません。  
  
-   変換図形を使用することはできません。  
  
-   カスタム .NET コンポーネントのメソッドを呼び出すことはできません。  
  
-   実行時間の長いトランザクションにタイムアウトを適用することはできません。  
  
-   オーケストレーションでは、パラメーターを受け取ることはできません。  
  
-   呼び出し可能な補正ハンドラーは、パラメーターを含めることはできません。  
  
-   変数の型は、XPATH でサポート可能なである必要があります。  
  
-   中断図形を使用することはできません。  
  
-   リテラル値には、次の種類のいずれかを指定する必要があります。  
  
     boolean、char、byte、sbyte、int32、uint32、int64、uint64、single、double、文字列  
  
-   算術演算子は、次の数値型のオペランドに対してのみ許可されます。  
  
     byte、sbyte、int32、uint32、int64、uint64、single、double  
  
-   関係演算子は、char 型に適用できません。  
  
-   式では servicelink プロパティへの参照を行うことはできません。  
  
-   間で任意の操作を実行することはできません、**送信**図形と**受信**同じ要求-応答の送信ポートを使用する図形。  
  
-   参照を格納している別のプロジェクトに参照を使用して、web サービスでは、間接的に参照できません。 プロジェクトで web サービスを明示的に参照する必要があります。  
  
-   遅延定数 DateTime や TimeSpan を指定することはできません。 代わりに、System.Xml 名前空間では、変換クラスのいずれかを使用します。  
  
     定数 datetime の場合。System.Xml.XmlConvert.ToDateTime, e.g System.Xml.XmlConvert.ToDateTime("2004-04-15")  
  
     定数 timespan の場合。System.Xml.XmlConvert.ToTimeSpan, e.g System.Xml.XmlConvert.ToTimeSpan("2004-04-15")  
  
> [!NOTE]
>  文字リテラルは、符号なし整数としてエクスポートされます。 たとえば、97 としてエクスポートされます。 'a'、'b' は 98、およびなどとしてエクスポートされます。  
  
> [!CAUTION]
>  識別子名は、W3C Extensible Markup Language (XML) 1.0 仕様に準拠する必要があります。  
  
#### <a name="to-export-an-orchestration-to-bpel4ws"></a>オーケストレーションを BPEL4WS にエクスポートするには  
  
1.  BizTalk オーケストレーションの種類の新しい項目をプロジェクトに追加します。  
  
2.  オーケストレーションのプロパティ ウィンドウを表示し、デザイン画面をクリックします。  
  
3.  設定**エクスポート可能なモジュール**を True にします。  
  
4.  型の名前空間で**モジュール XML ターゲットの Namespace**します。  
  
5.  設定**エクスポート可能なオーケストレーション**を True にします。  
  
6.  型の名前空間で**オーケストレーションの XML ターゲットの Namespace**します。  
  
7.  ソリューション エクスプ ローラーで右クリックします。オーケストレーションの ODX ファイルです。  
  
8.  選択**BPEL にエクスポート**します。  
  
     オーケストレーションが BPEL4WS にエクスポートされます。 成功を確認または問題を診断するには、出力ウィンドウとタスクの一覧を参照してください。 エクスポートが完了すると、します。WSDL ファイルとします。BPEL ファイルがプロジェクト ディレクトリに作成されます。  
  
> [!NOTE]
>  ロール リンク (リンク) への代入または動的なポートへのリテラル割り当てが、オーケストレーションが含まれる場合、BizTalk は、ダミーの BPEL4WS エンドポイント参照を生成し、警告を生成します。  
  
## <a name="see-also"></a>参照  
 [BPEL4WS をインポートする方法](../core/how-to-import-bpel4ws.md)   
 [XLANG-s から BPEL4WS への種類の変換](../core/xlang-s-to-bpel4ws-type-conversions.md)
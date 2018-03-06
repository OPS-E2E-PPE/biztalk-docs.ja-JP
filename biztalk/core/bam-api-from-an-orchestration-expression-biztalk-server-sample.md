---
title: "オーケストレーションの式のサンプルから BAM API を |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 341bc333-9bfc-484c-b431-9a71f9188792
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5413940eaba97e6f68d5e068e26625f320e6e817
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2018
---
# <a name="bam-api-from-an-orchestration-expression-biztalk-server-sample"></a>オーケストレーション式からの BAM API (BizTalk Server サンプル)
このサンプルで示す方法。  
  
-   BizTalk Server オーケストレーションの式から BAM API を使用します。  
  
-   メッセージ内の繰り返し項目を個別のアクティビティ インスタンスとして追跡する。  
  
-   追跡プロファイルを使用して追跡される BAM データと、BAM API を使用して追跡される BAM データの間の関係を作成する。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルを見つけることができます*\<サンプル パス\>*\BAM\BamFromExpression です。  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|----------|-----------------|  
|BamDefinition.xls|BAM 定義スタイル シート。|  
|BamDefinition.xml|BAM 定義。|  
|BamFromExpression.btproj|Visual Studio プロジェクトのファイルを追跡します。|  
|BamFromExpression.sln|Visual Studio のソリューションです。|  
|Cleanup.bat|サンプルの展開解除を行うバッチ ファイル。|  
|InputMessage.xml|入力メッセージ。|  
|Orchestration1.odx|オーケストレーション。|  
|PoSchema.xsd|注文書スキーマ。|  
|PropertySchema.xsd|プロパティ スキーマ :|  
|Setup.bat|サンプルをコンパイルし、展開するバッチ ファイル。|  
|QueryBam.sql|SQL スクリプト。|  
  
## <a name="create-the-tracking-profile"></a>追跡プロファイルを作成します。  
  
1.  管理者は、コマンド プロンプトを開き、実行*\<サンプル パス\>*\BAM\BAMFromExpression\Setup.bat です。 Setup.bat はこのサンプル用に BAM インフラストラクチャを初期化し、BAM アクティビティを展開します。  
  
2.  **プログラム** > **Microsoft BizTalk Server**を右クリックして**追跡プロファイル エディター**、および**を管理者として実行**.
  
3.  左側のウィンドウで、 **追跡プロファイル エディター** ウィンドウで、をクリックして **ここをクリックして BAM アクティビティ定義をインポートする**です。  
  
4.  **BAM アクティビティ定義名** のセクション、 **BAM アクティビティ定義のインポート** ダイアログ ボックスで、 **FromExpressionPo**, 、 をクリックし、 **OK**します。  
  
5.  右側のウィンドウで、 **追跡プロファイル エディター** ウィンドウで、をクリックして **ここをクリックすると、イベント ソースを選択する**です。  
  
6.  **アセンブリ名** のセクション、 **[イベント ソースの親アセンブリ** ダイアログ ボックスで、 **Microsoft.Samples.BizTalk.BamFromExpression**, 、] をクリックし、 **次**します。  
  
7.  **オーケストレーション名** のセクション、 **オーケストレーションの選択** ダイアログ ボックスで、 **BamFromExpression.Orchestration1**, 、 をクリックし、 **OK**します。  
  
8.  右クリックし、 **Receive_1** 図形をクリックして **メッセージ ペイロード スキーマ**します。  
  
9. 展開**\<スキーマ\>**、展開**PurchaseOrder**、展開**から**、し、ドラッグ**PoID**右のウィンドウ**ActivityID**左側のウィンドウでします。  
  
10. 右側のウィンドウから次の要素をドラッグし、左側のウィンドウの名前付きノードにドロップします。  
  
    |From|変換先|  
    |----------|--------|  
    |名前|From|  
    |状態|状態|  
    |City|City|  
    |Phone|Phone|  
    |Total|PoTotal|  
  
11. 矢印の付いたフォルダー アイコンをクリックして (![フォルダーとし、上のボタン &#45; 矢印](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4"))、オーケストレーションを表示します。  
  
12. ドラッグ、 **Receive_1** 右側のウィンドウに図形 **受信** 左側のウィンドウでします。  
  
13. ドラッグ、 **Send_1** 右側のウィンドウに図形 **送信** 左側のウィンドウでします。  
  
14. 追跡プロファイルを保存*\<サンプル パス\>*\BAM\BamFromExpression\ BamFromExpression.btt です。  
  
15. **ツール**  メニューのをクリックして **追跡プロファイルの適用**します。  
  
## <a name="build-and-initialize-this-sample"></a>ビルドおよび初期化するこのサンプル  
  
BamFromExpression.btt 追跡プロファイルを展開します。 参照してください[追跡を使用して追跡プロファイルを展開する方法のプロファイル管理ユーティリティ](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md)です。  
  
## <a name="run-this-sample"></a>このサンプルを実行します。  
  
ファイルをコピー *\<サンプル パス\>*に \BamFromExpression\InputMessage.xml *\<サンプル パス\>*\BamFromExpression\Input です。  
  
約 10 秒後に、出力メッセージが表示されます*\<サンプル パス\>*\BamFromExpression\Output です。  
  
## <a name="view-the-bam-data"></a>BAM データを表示します。  
  
1.  SQL Server Management Studio を開きます。  
  
2.  SQL Server Management Studio で、サーバーを展開し、 **データベース**, 、展開 **BAMPrimaryImport**, 、順に展開 **テーブル**します。  
  
3.  右クリック **dbo.bam_FromExpressionPo_Completed**, 、クリックして **テーブルを開く**します。 SQL Server を使用している場合はクリックして**上位 1000 行を選択して**です。  
  
     bam_FromExpressionPo_Completed テーブルの内容が、右側のウィンドウに表示されます。 アクティビティ ID が 123 の 1 行は、入力メッセージに含まれていた $345 の注文を表します。  
  
4.  右クリック **dbo.bam_FromExpressionPoItem_Completed**, 、クリックして **テーブルを開く**します。 SQL Server を使用している場合はクリックして**上位 1000 行を選択して**です。  
  
     bam_FromExpressionPoItem_Completed テーブルの内容が、右側のウィンドウに表示されます。 アクティビティ ID が 123_0 および 123_1 の 2 行は、注文のアイテム Flash MC と Infrared Decoder を表します。  
  
5.  右クリック **dbo.bam_FromExpressionPoItem_CompletedRelationships**, 、クリックして **テーブルを開く**します。 SQL Server を使用している場合はクリックして**上位 1000 行を選択して**です。  
  
     bam_FromExpressionPoItem_CompletedRelationships テーブルの内容が、右側のウィンドウに表示されます。 テーブルの各行は、FromExpressionPoItem アクティビティと FromExpressionPo アクティビティの関係を表します。 値、 **ActivityID** 列は、FromExpressionPoItem アクティビティのアクティビティ ID を示します。 値、 **ReferenceData** 列は、FromExpressionPo アクティビティのアクティビティ ID を示します。 この場合、2 つのレコードは、Flash MC アイテムと Infrared Decoder アイテムが $345 の注文で関連付けられていることを示します。  
  
## <a name="re-run-the-sample"></a>このサンプルを再実行します。  
  
1.  管理者は、コマンド プロンプトを開き、実行*\<サンプル パス\>*\BAM\BamFromExpression\Cleanup.bat 追跡プロファイルとその他の BAM インフラストラクチャを削除します。 
  
2.  実行*\<サンプル パス\>*\BAM\BamFromExpression\Setup.bat をサンプルをコンパイルして展開します。  
  
## <a name="see-also"></a>参照  
 [ビジネス アクティビティ監視 (BizTalk Server Samples フォルダ)](../core/business-activity-monitoring-biztalk-server-samples-folder.md)   
 [アクティビティ リレーションシップ](../core/activity-relationships.md)
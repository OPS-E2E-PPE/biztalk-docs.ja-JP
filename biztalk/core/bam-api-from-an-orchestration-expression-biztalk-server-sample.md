---
title: "オーケストレーションの式 (BizTalk Server サンプル) から BAM API を |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, BAM
- examples, orchestrations
- BAM, examples
ms.assetid: 341bc333-9bfc-484c-b431-9a71f9188792
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26b9cbc21eb93cad52a421b7df0912a37708978c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="bam-api-from-an-orchestration-expression-biztalk-server-sample"></a>オーケストレーション式からの BAM API (BizTalk Server サンプル)
このサンプルをする方法。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションの式から BAM API を使用する。  
  
-   メッセージ内の繰り返し項目を個別のアクティビティ インスタンスとして追跡する。  
  
-   追跡プロファイルを使用して追跡される BAM データと、BAM API を使用して追跡される BAM データの間の関係を作成する。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルを見つけることができます*\<サンプル パス >*\BAM\BamFromExpression です。  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|----------|-----------------|  
|BamDefinition.xls|BAM 定義スタイル シートです。|  
|BamDefinition.xml|BAM 定義。|  
|BamFromExpression.btproj|[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 追跡ファイル プロジェクト。|  
|BamFromExpression.sln|[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ソリューション。|  
|Cleanup.bat|サンプルの展開解除を行うバッチ ファイル。|  
|InputMessage.xml|入力メッセージ。|  
|Orchestration1.odx|オーケストレーション。|  
|PoSchema.xsd|注文書スキーマ。|  
|PropertySchema.xsd|プロパティ スキーマ : |  
|Setup.bat|サンプルをコンパイルし、展開するバッチ ファイル。|  
|QueryBam.sql|SQL スクリプト。|  
  
## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 次の手順を使用して追跡プロファイルを作成し、サンプルを実行して、結果を表示します。  
  
#### <a name="to-create-the-tracking-profile"></a>追跡プロファイルを作成するには  
  
1.  コマンド プロンプトを開き、実行*\<サンプル パス >*\BAM\BAMFromExpression\Setup.bat です。 [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] または [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] を使用している場合は、管理者としてコマンド プロンプトを開きます。 Setup.bat はこのサンプル用に BAM インフラストラクチャを初期化し、BAM アクティビティを展開します。  
  
2.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**追跡プロファイル エディター**です。 使用している場合[!INCLUDE[btsWinVista](../includes/btswinvista-md.md)]または[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]を右クリックして**追跡プロファイル エディター**  をクリックし、**管理者として実行**です。  
  
3.  左側のウィンドウで、**追跡プロファイル エディター**ウィンドウで、をクリックして**ここをクリックして、BAM アクティビティ定義をインポートする**です。  
  
4.  **BAM アクティビティ定義名**のセクションで、 **BAM アクティビティ定義のインポート**ダイアログ ボックスで、 **FromExpressionPo**、クリックして**[ok]**.  
  
5.  右側のペインで、**追跡プロファイル エディター**ウィンドウで、をクリックして**ここをクリックすると、イベント ソースを選択する**です。  
  
6.  **アセンブリ名**のセクションで、**イベント ソースの親アセンブリの選択**ダイアログ ボックスで、 **Microsoft.Samples.BizTalk.BamFromExpression**をクリックして**[次へ]**です。  
  
7.  **オーケストレーション名**のセクションで、**オーケストレーションの選択**ダイアログ ボックスで、 **BamFromExpression.Orchestration1**、クリックして**[ok]**.  
  
8.  右クリックし、 **Receive_1**図形をクリックして**メッセージ ペイロード スキーマ**です。  
  
9. 展開**\<スキーマ >**、展開**PurchaseOrder**、展開**から**、し、ドラッグ**PoID** の右側のウィンドウに**ActivityID**左側のウィンドウでします。  
  
10. 右側のウィンドウから次の要素をドラッグし、左側のウィンドウの名前付きノードにドロップします。  
  
    |From|変換先|  
    |----------|--------|  
    |名前|From|  
    |状態|状態|  
    |City|City|  
    |Phone|Phone|  
    |Total|PoTotal|  
  
11. 矢印の付いたフォルダー アイコンをクリックして (![フォルダーとし、上のボタン &#45; 矢印](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4"))、オーケストレーションを表示します。  
  
12. ドラッグ、 **Receive_1**図形を右側のペインで**Received**左側のウィンドウでします。  
  
13. ドラッグ、 **Send_1**図形を右側のペインで**送信**左側のウィンドウでします。  
  
14. 追跡プロファイルを保存*\<サンプル パス >*\BAM\BamFromExpression\ BamFromExpression.btt です。  
  
15. **ツール** メニューのをクリックして**追跡プロファイルの適用**です。  
  
#### <a name="to-build-and-initialize-this-sample"></a>このサンプルを作成および初期化するには  
  
-   BamFromExpression.btt 追跡プロファイルを展開します。 詳細については、次を参照してください。[追跡プロファイル管理ユーティリティを使って追跡プロファイルを展開する方法](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md)です。  
  
#### <a name="to-run-this-sample"></a>このサンプルを実行するには  
  
-   ファイルをコピー *\<サンプル パス >*に \BamFromExpression\InputMessage.xml *\<サンプル パス >*\BamFromExpression\Input です。  
  
     約 10 秒後に、出力メッセージが表示されます*\<サンプル パス >*\BamFromExpression\Output です。  
  
#### <a name="to-view-the-bam-data"></a>BAM データを表示するには  
  
1.  SQL Server Management Studio を開きます。  
  
2.  SQL Server Management Studio で、サーバーを展開し、**データベース**、展開**BAMPrimaryImport**の順に展開および**テーブル**です。  
  
3.  右クリック**dbo.bam_FromExpressionPo_Completed**、クリックして**テーブルを開く**です。 使用している場合[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]をクリックして**上位 1000 行を選択して**です。  
  
     bam_FromExpressionPo_Completed テーブルの内容が、右側のウィンドウに表示されます。 アクティビティ ID が 123 の 1 行は、入力メッセージに含まれていた $345 の注文を表します。  
  
4.  右クリック**dbo.bam_FromExpressionPoItem_Completed**、クリックして**テーブルを開く**です。 使用している場合[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]をクリックして**上位 1000 行を選択して**です。  
  
     bam_FromExpressionPoItem_Completed テーブルの内容が、右側のウィンドウに表示されます。 アクティビティ ID が 123_0 および 123_1 の 2 行は、注文のアイテム Flash MC と Infrared Decoder を表します。  
  
5.  右クリック**dbo.bam_FromExpressionPoItem_CompletedRelationships**、クリックして**テーブルを開く**です。 使用している場合[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]をクリックして**上位 1000 行を選択して**です。  
  
     bam_FromExpressionPoItem_CompletedRelationships テーブルの内容が、右側のウィンドウに表示されます。 テーブルの各行は、FromExpressionPoItem アクティビティと FromExpressionPo アクティビティの関係を表します。 値、 **ActivityID**列は、FromExpressionPoItem アクティビティのアクティビティ ID を示します。 値、 **ReferenceData**列は、FromExpressionPo アクティビティのアクティビティ ID を示します。 この場合、2 つのレコードは、Flash MC アイテムと Infrared Decoder アイテムが $345 の注文で関連付けられていることを示します。  
  
#### <a name="to-re-run-the-sample"></a>サンプルを再実行するには  
  
1.  コマンド プロンプトを開き、実行*\<サンプル パス >*\BAM\BamFromExpression\Cleanup.bat 追跡プロファイルとその他の BAM インフラストラクチャを削除します。 [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] または [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] を使用している場合は、管理者としてコマンド プロンプトを開きます。  
  
2.  実行*\<サンプル パス >*\BAM\BamFromExpression\Setup.bat をサンプルをコンパイルして展開します。  
  
## <a name="see-also"></a>参照  
 [ビジネス アクティビティ監視 (BizTalk Server Samples フォルダ)](../core/business-activity-monitoring-biztalk-server-samples-folder.md)   
 [アクティビティの関係](../core/activity-relationships.md)
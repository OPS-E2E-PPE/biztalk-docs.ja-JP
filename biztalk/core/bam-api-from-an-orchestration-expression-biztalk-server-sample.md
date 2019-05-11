---
title: BAM API サンプルのオーケストレーションの式から |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 341bc333-9bfc-484c-b431-9a71f9188792
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: acecbaff45eb7fd3e7197a27de5ae9911c174012
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358637"
---
# <a name="bam-api-from-an-orchestration-expression-biztalk-server-sample"></a>BAM API (BizTalk Server サンプル) オーケストレーション式から
このサンプルでは方法。  
  
-   BizTalk Server オーケストレーションの式から BAM API を使用します。  
  
-   個別のアクティビティ インスタンスとしてメッセージ内の項目を繰り返し追跡できます。  
  
-   追跡プロファイルを使用して追跡される BAM データ間のリレーションシップを作成し、BAM API を使用して BAM データを追跡します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルで*\<サンプル パス\>* \BAM\BamFromExpression します。  
  
 次の表では、このサンプルではファイルの一覧し、その目的について説明します。  
  
|ファイル|説明|  
|----------|-----------------|  
|BamDefinition.xls|BAM 定義スタイル シートです。|  
|BamDefinition.xml|BAM 定義します。|  
|BamFromExpression.btproj|Visual Studio プロジェクトのファイルを追跡します。|  
|BamFromExpression.sln|Visual Studio のソリューションです。|  
|Cleanup.bat|サンプルの展開解除するバッチ ファイルです。|  
|InputMessage.xml|入力メッセージ。|  
|Orchestration1.odx|オーケストレーションです。|  
|PoSchema.xsd|注文書スキーマ。|  
|PropertySchema.xsd|プロパティ スキーマ : |  
|Setup.bat|コンパイルして、サンプルを配置するバッチ ファイルです。|  
|QueryBam.sql|SQL スクリプトです。|  
  
## <a name="create-the-tracking-profile"></a>追跡プロファイルを作成します。  
  
1.  管理者は、コマンド プロンプトを開き、実行*\<サンプル パス\>* \BAM\BAMFromExpression\Setup.bat します。 Setup.bat は、このサンプルでは、BAM インフラストラクチャを初期化し、BAM アクティビティを展開します。  
  
2.  **プログラム** > **Microsoft BizTalk Server**、右クリックして**追跡プロファイル エディター**、および**を管理者として実行**.
  
3.  左側のウィンドウで、**追跡プロファイル エディター**ウィンドウで、をクリックして**ここをクリックすると、BAM アクティビティ定義をインポートする**します。  
  
4.  **BAM アクティビティ定義名**のセクション、 **BAM アクティビティ定義のインポート**ダイアログ ボックスで、 **FromExpressionPo**、 をクリックし、 **ok**.  
  
5.  右側のウィンドウで、**追跡プロファイル エディター**ウィンドウで、をクリックして**ここをクリックすると、イベント ソースを選択する**します。  
  
6.  **アセンブリ名**のセクション、 **イベント ソースの親アセンブリ**ダイアログ ボックスで、 **Microsoft.Samples.BizTalk.BamFromExpression**順にクリックします**次へ**します。  
  
7.  **オーケストレーション名**のセクション、**オーケストレーションの選択**ダイアログ ボックスで、 **BamFromExpression.Orchestration1**、 をクリックし、 **ok**.  
  
8.  右クリックし、 **Receive_1**図形をクリックして**メッセージ ペイロード スキーマ**します。  
  
9. 展開**\<スキーマ\>**、展開**PurchaseOrder**、展開**から**、し、ドラッグ**PoID**右にあります。ウィンドウ**ActivityID**左側のウィンドウでします。  
  
10. 右側のウィンドウから、次の要素をドラッグし、左側のウィンドウで名前付きノードにドロップします。  
  
    |From|目的|  
    |----------|--------|  
    |名前|From|  
    |状態|状態|  
    |City|City|  
    |Phone|Phone|  
    |Total|書|  
  
11. 矢印の付いたフォルダー アイコンをクリックします (![フォルダーでボタンをクリックし、セットアップ&#45;矢印](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4"))、オーケストレーションを表示します。  
  
12. ドラッグ、 **Receive_1**右側のウィンドウに図形**Received**左側のウィンドウでします。  
  
13. ドラッグ、 **Send_1**右側のウィンドウに図形**送信**左側のウィンドウでします。  
  
14. 追跡プロファイルを保存*\<サンプル パス\>* \BAM\BamFromExpression\ BamFromExpression.btt します。  
  
15. **ツール** メニューのをクリックして**追跡プロファイルの適用**します。  
  
## <a name="build-and-initialize-this-sample"></a>ビルドしてこのサンプルの初期化  
  
BamFromExpression.btt 追跡プロファイルを展開します。 参照してください[追跡を使用して追跡プロファイルを展開する方法のプロファイル管理ユーティリティ](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md)します。  
  
## <a name="run-this-sample"></a>このサンプルを実行します。  
  
ファイルをコピー *\<サンプル パス\>* に \BamFromExpression\InputMessage.xml *\<サンプル パス\>* \BamFromExpression\Input します。  
  
約 10 秒間には、出力メッセージに表示されます*\<サンプル パス\>* \BamFromExpression\Output します。  
  
## <a name="view-the-bam-data"></a>BAM データを表示します。  
  
1.  SQL Server Management Studio を開きます。  
  
2.  SQL Server Management studio で、サーバーを展開し、**データベース**、展開**BAMPrimaryImport**、順に展開**テーブル**します。  
  
3.  右クリックして**dbo.bam_FromExpressionPo_Completed**、 をクリックし、**テーブルを開く**します。 SQL Server を使用している場合はクリックして**上位 1000 行を選択する**します。  
  
     Bam_FromExpressionPo_Completed テーブルの内容は、右側のウィンドウに表示されます。 1 つの行は、アクティビティ ID が 123 には、入力メッセージに含まれていた $345 の注文書を表します。  
  
4.  右クリックして**dbo.bam_FromExpressionPoItem_Completed**、 をクリックし、**テーブルを開く**します。 SQL Server を使用している場合はクリックして**上位 1000 行を選択する**します。  
  
     Bam_FromExpressionPoItem_Completed テーブルの内容は、右側のウィンドウに表示されます。 アクティビティ Id 123_0 と 123_1 を持ち、2 つの行では、注文書内の項目を表します。MC と Infrared Decoder をフラッシュします。  
  
5.  右クリックして**dbo.bam_FromExpressionPoItem_CompletedRelationships**、 をクリックし、**テーブルを開く**します。 SQL Server を使用している場合はクリックして**上位 1000 行を選択する**します。  
  
     Bam_FromExpressionPoItem_CompletedRelationships テーブルの内容は、右側のウィンドウに表示されます。 テーブルの各行は、FromExpressionPoItem アクティビティと FromExpressionPo アクティビティ間のリレーションシップを表します。 値、 **ActivityID**列は、FromExpressionPoItem アクティビティのアクティビティ ID を参照します。 値、 **ReferenceData** FromExpressionPo アクティビティのアクティビティ ID を参照する列。 この場合、2 つのレコードは、Flash MC と Infrared Decoder アイテムが $345 の注文書に関連付けられたことを示します。  
  
## <a name="re-run-the-sample"></a>このサンプルを再実行します。  
  
1.  管理者は、コマンド プロンプトを開き、実行*\<サンプル パス\>* \BAM\BamFromExpression\Cleanup.bat を追跡プロファイルとその他の BAM インフラストラクチャを削除します。 
  
2.  実行*\<サンプル パス\>* \BAM\BamFromExpression\Setup.bat サンプルをコンパイルし、デプロイします。  
  
## <a name="see-also"></a>参照  
 [ビジネス アクティビティ監視 (BizTalk Server Samples フォルダー)](../core/business-activity-monitoring-biztalk-server-samples-folder.md)   
 [アクティビティ リレーションシップ](../core/activity-relationships.md)
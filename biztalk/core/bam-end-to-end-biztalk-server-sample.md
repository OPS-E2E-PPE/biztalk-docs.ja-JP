---
title: "BizTalk Server で BAM エンド ツー エンドのサンプル |Microsoft ドキュメント"
description: "BizTalk Server でビジネス アクティビティの監視を使用して複数のコンポーネントからイベントを関連付ける方法のシナリオ"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81406038-7f3f-499f-a003-12423d92c44b
caps.latest.revision: "35"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21cf3bcfae53d3204a1b4de23c1476591be2b453
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="bam-end-to-end-biztalk-server-sample"></a>BAM End-to-End (BizTalk Server サンプル)
エンド ツー エンドの例では、BAM を使用して、複数のコンポーネント (この場合は、3 つのオーケストレーションとパイプライン) からのイベントを関連付ける方法を示します。  
  
 BAM によって、パイプライン コンポーネントとオーケストレーションにまたがるビジネス アクティビティが再構築されます。 最下位のレベルへの呼び出しによって機能**EventStream.EnableContinuation**各実装コンポーネント、アクティビティの複数のイベントを受け取るからです。 呼び出し**EnableContinuation**明示的な Orchestration1 と Orchestration2 が 1 つのスケジュールとされるスケジュールを ContinuationID フォルダーに追跡プロファイルに Continuation フォルダーを追加することによって行われた呼び出し中にはです。  
  
 次の図は、このサンプルのワークフローを示します。  
  
 ![](../core/media/ebiz-sdk-samples-bam-endtoendwkflw.gif "ebiz_sdk_samples_bam_endtoendwkflw")  

  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 BAM End-to-End サンプルでは、BAM を使用し、1 つのパイプラインと複数のオーケストレーションから情報を収集して単一のアクティビティを更新する方法を示します。  
  
## <a name="how-this-sample-was-designed-and-why"></a>このサンプルをデザインした方法とその理由  
 BAM End-to-End サンプルは、次のアクティビティを示すようにデザインされています。  
  
-   パイプライン内の BAM の使用  
  
-   追跡プロファイル エディター (TPE) を使用したオーケストレーション内の図形とメッセージの要素へのアクティビティ項目のマップ  
  
-   複数のソリューションがアクティビティに関連する場合における、Continuation を使用したアクティビティのアクティブ状態の維持  
  

このサンプルの動作は次のとおりです。  
  
1.  入力メッセージを取得、 *\<サンプル パス >*\BamEndToEnd\Input フォルダーです。  
  
2.  パイプライン コンポーネントによって、一意の DocumentID がメッセージに割り当てられ、BAM API を使用して新しい BAM アクティビティが開始されます。 オーケストレーションで利用できるように、入力メッセージの個別の部分として DocumentID が添付されます。  
  
3.  入力メッセージが受信されると、サービス Orchestration1 がアクティブ化されます。  
  
4.  Orchestration1 によって入力メッセージが変更され、パラメーターとして Orchestration2 に渡されます。  
  
5.  Orchestration2 によって入力メッセージが変更され、Orchestration3 をアクティブ化するメッセージ ボックス データベースに送信されます。  
  
6.  Orchestration3 によってメッセージが変更され、フォルダーに書き込まれます*\<サンプル パス >*\BamEndToEnd\Output です。  
  
7.  各オーケストレーションによって BAM アクティビティ内のアクティビティ項目が更新されます。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルを見つけることができます*\<サンプル パス >*\BAM\BamEndToEnd です。  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|----|---|  
|BamEndToEnd.sln|BAM End-to-End サンプル ソリューション。|  
|BamEndToEnd.xls|BAM 定義スタイルシート。|  
|BamEndToEnd.xml|BAM 定義 XML。|  
|BAMEndToEndBinding.xml|BAM バインド。|  
|Cleanup.bat|サンプルの展開解除を行うバッチ ファイル。|  
|InputMessage.xml|入力メッセージ。|  
|Setup.bat|サンプルをコンパイルし、展開するバッチ ファイル。|  
|\Components\AssemblyInfo.cs|パイプライン コンポーネント コード。|  
|\Components\BAMMessagePartPLComponent.cs|パイプライン コンポーネント コード。|  
|\Components\Components.csproj|パイプライン コンポーネント プロジェクト。|  
|\Messages\InputMessage01.xml<br /><br /> [...]<br /><br /> \Messages\InputMessage10.xml|サンプル入力メッセージ。|  
|\Services\BAMInbound.btp|受信パイプライン ファイル。|  
|\Services\BAMPartSchema.xsd|BAM パート メッセージ スキーマ。|  
|\Services\Orchestration1.odx|オーケストレーション。|  
|\Services\Orchestration2.odx|オーケストレーション。|  
|\Services\Orchestration3.odx|オーケストレーション。|  
|\Services\PropertySchema.xsd|プロパティ スキーマ : |  
|\Services\Schema1.xsd|メッセージ スキーマ。|  
|\Services\Schema2.xsd|メッセージ スキーマ。|  
Services\Schema3.xsd|メッセージ スキーマ。|  
|\Services\Services.btproj|[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk ファイル プロジェクト。|  
|\Services\Transform_1.btm|マップ ファイル。|  
|\Services\Transform_2.btm|マップ ファイル。|  
|\Services\Transform_3.btm|マップ ファイル。|  
  
## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 次の手順を使用して、BAM End-to-End サンプルをビルドおよび実行します。  
  
-   [このサンプルをビルドして初期化](#To_Build_Sample)  
  
-   [このサンプルを実行するには](#To_Run_Sample)  
  
-   [BAM データを表示するには](#To_View_Data)  
  
##  <a name="To_Build_Sample"></a>ビルドおよび初期化するこのサンプル  
  
1.  管理者は、コマンド プロンプトを開き、実行*\<サンプル パス >*\BAM\BAMEndToEnd\Setup.bat です。 Setup.bat は、このサンプルの BAM インフラストラクチャをビルドして初期化します。 コマンド プロンプトは開いたままにします。  
  
2.  Orchestration1、Orchestration2、および Orchestration3 を BAM アクティビティにマップするための追跡プロファイルを作成します。 (という別の手順の方法の詳細については、追跡プロファイルの作成は複雑なプロセスなので**追跡プロファイルを作成する**です。 この手順については、このドキュメントの後半で説明します)。  
  
3.  前の手順で作成した追跡プロファイル BamEndToEnd.btt を展開します。  コマンド プロンプトでを変更、 *\<サンプル パス >*\BAM\BamEndToEnd ディレクトリ。 追跡プロファイルを展開する次の行を入力し、キーを押します**Enter**:  
  
    `“<BizTalkInstallationPath>\Tracking\bttdeploy” BamEndToEnd.btt`
  
     [追跡プロファイル管理ユーティリティを使って追跡プロファイルを展開する方法](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md)詳しく説明します。
  
    > [!IMPORTANT]
    >  ContinuationID Orch1_ に一致する Continuation がないことを示すメッセージは無視できます。 Orch1_ という名前の Continuation は追跡プロファイルではなくパイプライン コンポーネントで定義されているので、このメッセージが表示されます。  
  
##  <a name="To_Run_Sample"></a>このサンプルを実行します。  
  
ファイルをコピー *\<サンプル パス >*フォルダーに \BamEndToEnd\InputMessage.xml *\<サンプル パス >*\BamEndToEnd\Input です。 Input フォルダーから、数秒後に、メッセージが表示されなくなります、出力メッセージが表示されます、 *\<サンプル パス >*\BamEndToEnd\Output フォルダーです。  
  
##  <a name="To_View_Data"></a>BAM データを表示します。  
  
1.  SQL Server Management Studio を開きます。  
  
2.  SQL Server Management Studio で、サーバーを展開し、**データベース**、展開**BAMPrimaryImport**の順に展開および**テーブル**です。  
  
3.  右クリック**dbo.bam_EndToEndActivity_Completed**、クリックして**テーブルを開く**です。 使用している場合[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]をクリックして**上位 1000 行を選択して**です。  
  
     bam_EndToEndActivity_Completed テーブルの内容が右ペインに表示されます。 このテーブルの各行は、完了した EndToEndActivity アクティビティを表します。  
  
#### <a name="rerun-this-sample"></a>このサンプルを再実行します。  
  
1.  管理者は、コマンド プロンプトを開き、変更、 *\<サンプル パス >*\BAM\BamEndToEnd ディレクトリ。 次の行を入力します。  
  
    `“C:\Program Files\Microsoft BizTalk Server <version>\Tracking\bttdeploy” BamEndToEnd.btt /remove`  
  
    > [!NOTE]
    >  インストールしていない場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]C ドライブにインストールしたドライブ文字"C"を置き換えます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。  
  
2.  実行*\<サンプル パス >*\BAM\BAMEndToEnd\Cleanup.bat です。 Cleanup.bat は、このサンプルの BAM インフラストラクチャを削除します。  
  
3.  手順に従います**このサンプルをビルドして初期化**」セクションを参照します。  
  
##  <a name="TPE_procedure"></a>追跡プロファイルを作成します。  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]です。 右クリック**追跡プロファイル エディター**、および**管理者として実行**です。  
  
2.  左側のウィンドウで、**追跡プロファイル エディター**ウィンドウで、をクリックして**ここをクリックして、BAM アクティビティ定義をインポートする**です。  
  
3.  **BAM アクティビティ定義名**のセクションで、 **BAM アクティビティ定義のインポート**ダイアログ ボックスで、 **[endtoendactivity]**、クリックして**[ok]**.  
  
4.  右側のペインで、**追跡プロファイル エディター**ウィンドウで、をクリックして**ここをクリックすると、イベント ソースを選択する**です。  
  
5.  **アセンブリ名**のセクションで、**イベント ソースの親アセンブリの選択**ダイアログ ボックスで、 **Microsoft.Samples.BizTalk.BamEndToEnd.Services**をクリックし、**次**です。  
  
6.  **オーケストレーション名**のセクション、**オーケストレーションの選択**ダイアログ ボックスで、**で BamEndToEnd.Services.Orchestration1**、順にクリック**OK**.  
  
7.  左側のウィンドウで、**追跡プロファイル エディター**ウィンドウを右クリックして**endtoendactivity**、クリックして**新しい continuationid**です。 新しい continuation ID の名前を付けます**orch1 _**です。 2 つの continuation Id という名前を作成するには、この手順を繰り返します**orch2 _**と**orch3 _**です。  
  
8.  右クリック**[endtoendactivity]**、クリックして**新しい Continuation**です。 新しい continuation の名前**orch2 _**です。 という continuation も作成するには、この手順を繰り返します**orch3 _**です。  
  
9. 右クリックし、 **Receive1**図形をクリックして**コンテキスト プロパティ スキーマ**です。  
  
10. 末尾にスクロール、**コンテキスト プロパティ名**、一覧表示し、ダブルクリック**BAMEndToEnd.Services.PropertySchema.DocumentID**です。  
  
11. 展開**\<スキーマ >**、し、ドラッグ**DocumentID**を右側のウィンドウで**orch1 _**左側のウィンドウでします。  
  
12. 矢印の付いたフォルダー アイコンをクリックして (![フォルダーと上矢印ボタン](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4"))、オーケストレーションを表示するには、2 回クリックします。  
  
13. ドラッグ、 **Receive1**図形を右側のペインで**[sbegin1]**左側のウィンドウでします。  
  
14. ドラッグ、 **StartOrchestration_1**図形を右側のペインで**[send1]**左側のウィンドウでします。  
  
15. 右クリックし、 **StartOrchestration_1**図形をクリックして**メッセージ ペイロード スキーマ**です。  
  
16. 値"Message_2"を含む行をダブルクリックして、**メッセージ**列と値"MessageBody"で、**一部**列です。  
  
     ![TPE メッセージ ペイロード スキーマ メッセージ &#95; 2.](../core/media/77fbc444-46cf-4d45-8e9c-c330da7ba7d1.gif "77fbc444-46cf-4d45-8e9c-c330da7ba7d1")  
  
17. 展開**Schema2**、し、ドラッグ**Data2**を右側のウィンドウで**Data1**左側のウィンドウでします。  
  
18. をクリックして**イベント ソースの選択**、クリックして**コンテキスト プロパティの**します。  
  
19. 末尾にスクロール、**コンテキスト プロパティ名**、一覧表示し、ダブルクリック**BAMEndToEnd.Services.PropertySchema.DocumentID**です。  
  
20. 展開**\<スキーマ >**、し、ドラッグ**DocumentID**を**orch2 _**左側のウィンドウで継続します。  
  
    > [!NOTE]
    >  Orch2_ Continuation と Orch2_ Continuation ID を混同しないように注意してください。 Continuation ID を表すアイコンには、キーが含まれています (![continuation ID のアイコン](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))、continuation を表すアイコンには、キー (が含まれていません。![continuation のアイコン](../core/media/test.gif "テスト"))。  
  
21. をクリックして**イベント ソースの選択**、クリックして**オーケストレーション スケジュールの**します。  
  
22. **アセンブリ名**のセクションで、**イベント ソースの親アセンブリの選択**ダイアログ ボックスで、 **Microsoft.Samples.BizTalk.BamEndToEnd.Services**をクリックし、**次**です。  
  
23. **オーケストレーション名**のセクション、**オーケストレーションの選択**ダイアログ ボックスで、**で BamEndToEnd.Services.Orchestration2**、順にクリック**OK**.  
  
24. 右クリックし、 **ConstructMessage_1**図形をクリックして**メッセージ ペイロード スキーマ**です。  
  
25. 値"Message_3"を含む行をダブルクリックして、**メッセージ**列と値に"BAMPart"で、**一部**列です。  
  
26. 展開**BAMPart**、し、ドラッグ**DocumentID**を右側のウィンドウで、 **orch2 _**左側のウィンドウで continuation ID。  
  
    > [!NOTE]
    >  Orch2_ Continuation と Orch2_ Continuation ID を混同しないように注意してください。 Continuation ID を表すアイコンには、キーが含まれています (![continuation ID のアイコン](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))、continuation を表すアイコンには、キー (が含まれていません。![continuation のアイコン](../core/media/test.gif "テスト"))。  
  
27. 矢印の付いたフォルダー アイコンをクリックして (![フォルダーとし、上のボタン &#45; 矢印](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4"))、オーケストレーションを表示するには、2 回クリックします。  
  
28. ドラッグ、 **ConstructMessage_1**図形を右側のペインで**[sbegin2]**左側のウィンドウでします。  
  
29. ドラッグ、 **Send_1**図形を右側のペインで**[send2]**左側のウィンドウでします。  
  
30. 右クリックし、 **Send_1**図形をクリックして**メッセージ ペイロード スキーマ**です。  
  
31. 値"Message_3"を含む行をダブルクリックして、**メッセージ**列と値"MessageBody"で、**一部**列です。  
  
32. 展開**Schema3**、し、ドラッグ**Data3**を右側のウィンドウで**Data2**左側のウィンドウでします。  
  
33. 右側のペインの上にドロップ ダウン リストから選択**メッセージ ペイロード スキーマ**です。  
  
34. 値"Message_3"を含む行をダブルクリックして、**メッセージ**列と値に"BAMPart"で、**一部**列です。  
  
35. 展開**BAMPart**、し、ドラッグ**DocumentID**を右側のウィンドウで、 **orch3 _**左側のウィンドウで継続します。  
  
    > [!NOTE]
    >  Orch3_ Continuation と Orch3_ Continuation ID を混同しないように注意してください。 Continuation ID を表すアイコンには、キーが含まれています (![continuation ID のアイコン](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))、continuation を表すアイコンには、キー (が含まれていません。![continuation のアイコン](../core/media/test.gif "テスト"))。  
  
36. をクリックして**イベント ソースの選択**、クリックして**オーケストレーション スケジュールの**します。  
  
37. **アセンブリ名**のセクションで、**イベント ソースの親アセンブリの選択**ダイアログ ボックスで、 **Microsoft.Samples.BizTalk.BamEndToEnd.Services**をクリックし、**次**です。  
  
38. **オーケストレーション名**のセクション、**オーケストレーションの選択**ダイアログ ボックスで、**で BamEndToEnd.Services.Orchestration3**、順にクリック**OK**.  
  
39. 右クリックし、 **Receive1**図形をクリックして**メッセージ ペイロード スキーマ**です。  
  
40. 値"Message_3"を含む行をダブルクリックして、**メッセージ**列と値に"BAMPart"で、**一部**列です。  
  
41. 展開**BAMPart**、し、ドラッグ**DocumentID**を右側のウィンドウで、 **orch3 _**左側のウィンドウで continuation ID。  
  
    > [!NOTE]
    >  Orch3_ Continuation と Orch3_ Continuation ID を混同しないように注意してください。 Continuation ID を表すアイコンには、キーが含まれています (![continuation ID のアイコン](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))、continuation を表すアイコンには、キー (が含まれていません。![continuation のアイコン](../core/media/test.gif "テスト"))。  
  
42. 矢印の付いたフォルダー アイコンをクリックして (![フォルダーと上矢印ボタン](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4"))、オーケストレーションを表示するには、2 回クリックします。  
  
43. ドラッグ、 **Receive1**図形を右側のペインで**[sbegin3]**左側のウィンドウでします。  
  
44. ドラッグ、 **Send_1**図形を右側のペインで**[send3]**左側のウィンドウでします。  
  
45. 右クリックし、 **Send_1**図形をクリックして**メッセージ ペイロード スキーマ**です。  
  
46. 展開**Schema3**、し、ドラッグ**Data3**を右側のウィンドウで**Data3**左側のウィンドウでします。  
  
47. 右クリック**DocumentID**下、 **orch2 _**継続をクリックして**ポート マッピング**です。  
  
    > [!NOTE]
    >  Orch2_ Continuation と Orch2_ Continuation ID を混同しないように注意してください。 Continuation ID を表すアイコンには、キーが含まれています (![continuation ID のアイコン](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))、continuation を表すアイコンには、キー (が含まれていません。![continuation のアイコン](../core/media/test.gif "テスト"))。  
  
48. **ポートの選択**のセクションで、**ポートの選択**ダイアログ ボックスで、をクリックして**BamEndToEnd_ReceivePort**、大きい をクリックして-不等号 ( **>**)、をクリックして**OK**です。  
  
49. 追跡プロファイルを保存*\<サンプル パス >*\BAM\BamEndToEnd\BamEndToEnd.btt です。  
  
## <a name="important-details"></a>重要な詳細情報  
 追跡プロファイルは、パイプラインではサポートされていません。 ただしへの呼び出し**BeginActivity**パイプライン コンポーネントは、同じようにオーケストレーションで ActivityID を使用します。 呼び出し**EnableContinuation**オーケストレーションでの continuation の使用と同じです。  
  
## <a name="see-also"></a>参照  
 [ビジネス アクティビティ監視 (BizTalk Server Samples フォルダ)](../core/business-activity-monitoring-biztalk-server-samples-folder.md)
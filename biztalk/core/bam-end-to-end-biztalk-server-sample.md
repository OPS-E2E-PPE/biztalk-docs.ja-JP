---
title: BizTalk Server で BAM エンド ツー エンドのサンプル |Microsoft Docs
description: BizTalk Server でビジネス アクティビティの監視を使用して複数のコンポーネントからイベントを関連付ける方法のシナリオ
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81406038-7f3f-499f-a003-12423d92c44b
caps.latest.revision: 35
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17ba248941ef6351bd421b30bd0124073e20b791
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528636"
---
# <a name="bam-end-to-end-biztalk-server-sample"></a>BAM エンド ツー エンド (BizTalk Server サンプル)
エンド ツー エンドのサンプルでは、BAM を使用して (この場合、3 つのオーケストレーションおよびパイプライン) で複数のコンポーネントからのイベントを関連付ける方法を示します。  

 BAM には、パイプライン コンポーネントとオーケストレーションにまたがるビジネス アクティビティが再構築します。 最下位レベルでこの動作を呼び出して**EventStream.EnableContinuation**アクティビティの他のイベントが必要とする各実装コンポーネントから。 呼び出し**EnableContinuation**明示的な Orchestration1 と Orchestration2 が Continuation フォルダーを 1 つのスケジュールと後のスケジュールを ContinuationID フォルダーで追跡プロファイルに追加することで行われた呼び出し中にはです。  

 次の図は、このサンプルで使用されるワークフローを示しています。  

 ![](../core/media/ebiz-sdk-samples-bam-endtoendwkflw.gif "ebiz_sdk_samples_bam_endtoendwkflw")  


## <a name="what-this-sample-does"></a>このサンプルの処理  
 BAM のエンド ツー エンドのサンプルでは、BAM を使用するパイプラインと複数のオーケストレーションから情報を収集し、1 つのアクティビティを更新する方法を示します。  

## <a name="how-this-sample-was-designed-and-why"></a>このサンプルのデザイン方法とその理由  
 BAM のエンド ツー エンドのサンプルは、次のアクティビティを示すために設計されました。  

-   BAM を使用して、パイプライン内で。  

-   追跡プロファイル エディター (TPE) を使用して、アクティビティ項目をオーケストレーションとメッセージの要素内の図形にマップします。  

-   Continuation を使用して、ソリューションの複数の部分は、アクティビティを投稿するときは、アクティビティを維持します。  


このサンプルはように動作します。  

1.  入力メッセージがから取得した、 *\<サンプル パス\>* \BamEndToEnd\Input フォルダー。  

2.  パイプライン コンポーネントでは、メッセージに一意の DocumentID を割り当てるし、新しい BAM アクティビティを開始するために、BAM API を使用します。 オーケストレーションに使用できるようにする、入力メッセージの別の部分として DocumentID が添付されます。  

3.  入力メッセージを受信したときに、サービス Orchestration1 がアクティブになります。  

4.  Orchestration1 では、入力メッセージが変更され、パラメーターとして Orchestration2 に渡します。  

5.  Orchestration2 によって入力メッセージが変更され、Orchestration3 をアクティブ化するメッセージ ボックス データベースに送信します。  

6.  Orchestration3 のメッセージが変更され、フォルダーに書き込みます *\<サンプル パス\>* \BamEndToEnd\Output します。  

7.  各オーケストレーションでは、BAM アクティビティ内のアクティビティ項目を更新します。  

## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルで *\<サンプル パス\>* \BAM\BamEndToEnd します。  

 次の表は、このサンプルのファイルとその目的を示しています。  


|                                        ファイル                                        |                                         説明                                          |
|---------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------|
|                                    BamEndToEnd.sln                                    |                               BAM のエンド ツー エンドのサンプル ソリューションです。                                |
|                                    BamEndToEnd.xls                                    |                                 BAM 定義スタイル シートです。                                  |
|                                    BamEndToEnd.xml                                    |                                     BAM 定義 XML。                                      |
|                                BAMEndToEndBinding.xml                                 |                                         BAM バインド。                                         |
|                                      Cleanup.bat                                      |                              サンプルの展開解除するバッチ ファイルです。                              |
|                                   InputMessage.xml                                    |                                        入力メッセージ。                                        |
|                                       Setup.bat                                       |                         コンパイルして、サンプルを配置するバッチ ファイルです。                         |
|                              \Components\AssemblyInfo.cs                              |                                   パイプライン コンポーネント コード。                                   |
|                       \Components\BAMMessagePartPLComponent.cs                        |                                   パイプライン コンポーネント コード。                                   |
|                             \Components\Components.csproj                             |                                 パイプライン コンポーネントのプロジェクトです。                                  |
| \Messages\InputMessage01.xml<br /><br /> [...]<br /><br /> \Messages\InputMessage10.xml |                                    サンプル入力メッセージ。                                    |
|                               \Services\BAMInbound.btp                                |                                    受信パイプライン ファイルです。                                    |
|                              \Services\BAMPartSchema.xsd                              |                                   BAM パート メッセージ スキーマ。                                   |
|                             \Services\Orchestration1.odx                              |                                        オーケストレーションです。                                        |
|                             \Services\Orchestration2.odx                              |                                        オーケストレーションです。                                        |
|                             \Services\Orchestration3.odx                              |                                        オーケストレーションです。                                        |
|                             \Services\PropertySchema.xsd                              |                                       プロパティ スキーマ :                                       |
|                                 \Services\Schema1.xsd                                 |                                       メッセージ スキーマです。                                        |
|                                 \Services\Schema2.xsd                                 |                                       メッセージ スキーマです。                                        |
|                                 Services\Schema3.xsd                                  |                                       メッセージ スキーマです。                                        |
|                               \Services\Services.btproj                               | [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk ファイル プロジェクト。 |
|                               \Services\Transform_1.btm                               |                                          マップ ファイルです。                                           |
|                               \Services\Transform_2.btm                               |                                          マップ ファイルです。                                           |
|                               \Services\Transform_3.btm                               |                                          マップ ファイルです。                                           |

## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 ビルドして BAM エンド ツー エンドのサンプルを実行するには、次の手順を使用します。  

-   [このサンプルをビルドして初期化](#To_Build_Sample)  

-   [このサンプルを実行するには](#To_Run_Sample)  

-   [BAM データを表示するには](#To_View_Data)  

##  <a name="To_Build_Sample"></a>ビルドしてこのサンプルの初期化  

1.  管理者は、コマンド プロンプトを開き、実行 *\<サンプル パス\>* \BAM\BAMEndToEnd\Setup.bat します。 Setup.bat は、ビルドして、このサンプルの BAM インフラストラクチャを初期化します。 コマンド プロンプトは開いたままにしておきます。  

2.  Orchestration1、Orchestration2、および Orchestration3 を BAM アクティビティにマップする追跡プロファイルを作成します。 (詳細な手順がという別の手順では、追跡プロファイルの作成は複雑なプロセスなので**追跡プロファイルを作成する**します。 この手順が表示されますこのドキュメントで後述します。)  

3.  前の手順で作成した BamEndToEnd.btt 追跡プロファイルを展開します。  コマンド プロンプトでを変更、 *\<サンプル パス\>* \BAM\BamEndToEnd ディレクトリ。 追跡プロファイルを展開するには、次の行を入力し、キーを押します**Enter**:  

    `“<BizTalkInstallationPath>\Tracking\bttdeploy” BamEndToEnd.btt`

     [追跡プロファイル管理ユーティリティを使って追跡プロファイルを展開する方法](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md)詳細に説明します。

    > [!IMPORTANT]
    >  ContinuationID orch1 _ に一致する Continuation がないこと、メッセージを無視することができます。 パイプライン コンポーネントでは、追跡プロファイルではなく、orch1 _ という名前の continuation が定義されているため、このメッセージが必要です。  

##  <a name="To_Run_Sample"></a>このサンプルを実行します。  

ファイルをコピー *\<サンプル パス\>* フォルダーに \BamEndToEnd\InputMessage.xml *\<サンプル パス\>* \BamEndToEnd\Input します。 入力フォルダーから、数秒後に、メッセージが表示されなくなり、出力メッセージが表示されます、 *\<サンプル パス\>* \BamEndToEnd\Output フォルダー。  

##  <a name="To_View_Data"></a>BAM データを表示します。  

1.  SQL Server Management Studio を開きます。  

2.  SQL Server Management studio で、サーバーを展開し、**データベース**、展開**BAMPrimaryImport**、順に展開**テーブル**します。  

3.  右クリックして**dbo.bam_EndToEndActivity_Completed**、 をクリックし、**テーブルを開く**します。 SQL Server を使用している場合はクリックして**上位 1000 行を選択する**します。  

     Bam_EndToEndActivity_Completed テーブルの内容は、右側のウィンドウに表示されます。 テーブルの各行は、完了した EndToEndActivity アクティビティを表します。  

#### <a name="rerun-this-sample"></a>このサンプルを再実行します。  

1. 管理者は、コマンド プロンプトを開き、変更、 *\<サンプル パス\>* \BAM\BamEndToEnd ディレクトリ。 次の行を入力します。  

   `“C:\Program Files\Microsoft BizTalk Server <version>\Tracking\bttdeploy” BamEndToEnd.btt /remove`  

   > [!NOTE]
   >  インストールしなかった場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を C ドライブにインストールされている、ドライブ文字"C"を置き換えます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  

2. 実行 *\<サンプル パス\>* \BAM\BAMEndToEnd\Cleanup.bat します。 Cleanup.bat は、このサンプルの BAM インフラストラクチャを削除します。  

3. 手順に従います**このサンプルをビルドして初期化**このトピックの「します。  

##  <a name="TPE_procedure"></a>追跡プロファイルを作成します。  

1. クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]します。 右クリックして**追跡プロファイル エディター**、および**管理者として実行**します。  

2. 左側のウィンドウで、**追跡プロファイル エディター**ウィンドウで、をクリックして**ここをクリックすると、BAM アクティビティ定義をインポートする**します。  

3. **BAM アクティビティ定義名**のセクション、 **BAM アクティビティ定義のインポート**ダイアログ ボックスで、 **endtoendactivity**、 をクリックし、 **ok**.  

4. 右側のウィンドウで、**追跡プロファイル エディター**ウィンドウで、をクリックして**ここをクリックすると、イベント ソースを選択する**します。  

5. **アセンブリ名**のセクション、 **イベント ソースの親アセンブリ**ダイアログ ボックスで、 **Microsoft.Samples.BizTalk.BamEndToEnd.Services**、順にクリックします**次**します。  

6. **オーケストレーション名**のセクション、**オーケストレーションの選択**ダイアログ ボックスで、 **BamEndToEnd.Services.Orchestration1**、 をクリックし、 **ok**.  

7. 左側のウィンドウで、**追跡プロファイル エディター**ウィンドウで、右クリック **[endtoendactivity]** 、順にクリックします**新しい ContinuationID**します。 新しい continuation ID の名前を付けます**orch1 _** します。 2 つの continuation Id という名前を作成するには、この手順を繰り返します**orch2 _** と**orch3 _** します。  

8. 右クリックして**endtoendactivity**、 をクリックし、**新しい Continuation**します。 新しい continuation の名前**orch2 _** します。 という名前のもう 1 つの continuation を作成するには、この手順を繰り返します**orch3 _** します。  

9. 右クリックし、 **Receive1**図形をクリックして**コンテキスト プロパティ スキーマ**します。  

10. 最後までスクロール、**コンテキスト プロパティ名**、一覧表示し、ダブルクリック**BAMEndToEnd.Services.PropertySchema.DocumentID**します。  

11. 展開 **\<スキーマ\>** 、し、ドラッグ**DocumentID**を右側のウィンドウで**orch1 _** 左側のウィンドウでします。  

12. 矢印の付いたフォルダー アイコンをクリックします (![フォルダーと上矢印ボタン](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4"))、オーケストレーションを表示するには、2 回クリックします。  

13. ドラッグ、 **Receive1**右側のウィンドウに図形 **[sbegin1]** 左側のウィンドウでします。  

14. ドラッグ、 **StartOrchestration_1**右側のウィンドウに図形 **[send1]** 左側のウィンドウでします。  

15. 右クリックし、 **StartOrchestration_1**図形をクリックして**メッセージ ペイロード スキーマ**します。  

16. 値"Message_2"を含む行をダブルクリックして、**メッセージ**列と値"MessageBody"で、**一部**列。  

     ![TPE メッセージ ペイロード スキーマが表示されたメッセージ&#95;2](../core/media/77fbc444-46cf-4d45-8e9c-c330da7ba7d1.gif "77fbc444-46cf-4d45-8e9c-c330da7ba7d1")  

17. 展開**Schema2**、し、ドラッグ**Data2**を右側のウィンドウで**Data1**左側のウィンドウでします。  

18. をクリックして**イベント ソースの選択**、] をクリックし、 **[コンテキスト プロパティの**します。  

19. 最後までスクロール、**コンテキスト プロパティ名**、一覧表示し、ダブルクリック**BAMEndToEnd.Services.PropertySchema.DocumentID**します。  

20. 展開 **\<スキーマ\>** 、し、ドラッグ**DocumentID**を**orch2 _** 左側のウィンドウで継続します。  

    > [!NOTE]
    >  Orch2 _ continuation と orch2 _ continuation ID を混同しないでください。 Continuation ID を表すアイコンには、キーが含まれています (![continuation ID のアイコン](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))、continuation を表すアイコンにキー (が含まれていません![continuation のアイコン](../core/media/test.gif "テスト"))。  

21. をクリックして**イベント ソースの選択**、] をクリックし、 **[オーケストレーション スケジュールの**します。  

22. **アセンブリ名**のセクション、 **イベント ソースの親アセンブリ**ダイアログ ボックスで、 **Microsoft.Samples.BizTalk.BamEndToEnd.Services**、順にクリックします**次**します。  

23. **オーケストレーション名**のセクション、**オーケストレーションの選択**ダイアログ ボックスで、 **BamEndToEnd.Services.Orchestration2**、 をクリックし、 **ok**.  

24. 右クリックし、 **ConstructMessage_1**図形をクリックして**メッセージ ペイロード スキーマ**します。  

25. 値"Message_3"を含む行をダブルクリックして、**メッセージ**列と値に"BAMPart"で、**一部**列。  

26. 展開**BAMPart**、し、ドラッグ**DocumentID**を右側のウィンドウで、 **orch2 _** 左側のウィンドウで continuation ID。  

    > [!NOTE]
    >  Orch2 _ continuation と orch2 _ continuation ID を混同しないでください。 Continuation ID を表すアイコンには、キーが含まれています (![continuation ID のアイコン](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))、continuation を表すアイコンにキー (が含まれていません![continuation のアイコン](../core/media/test.gif "テスト"))。  

27. 矢印の付いたフォルダー アイコンをクリックします (![フォルダーでボタンをクリックし、セットアップ&#45;矢印](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4"))、オーケストレーションを表示するには、2 回です。  

28. ドラッグ、 **ConstructMessage_1**右側のウィンドウに図形 **[sbegin2]** 左側のウィンドウでします。  

29. ドラッグ、 **Send_1**右側のウィンドウに図形 **[send2]** 左側のウィンドウでします。  

30. 右クリックし、 **Send_1**図形をクリックして**メッセージ ペイロード スキーマ**します。  

31. 値"Message_3"を含む行をダブルクリックして、**メッセージ**列と値"MessageBody"で、**一部**列。  

32. 展開**Schema3**、し、ドラッグ**Data3**を右側のウィンドウで**Data2**左側のウィンドウでします。  

33. 右ペインの上のドロップダウン リストから選択**メッセージ ペイロード スキーマ**します。  

34. 値"Message_3"を含む行をダブルクリックして、**メッセージ**列と値に"BAMPart"で、**一部**列。  

35. 展開**BAMPart**、し、ドラッグ**DocumentID**を右側のウィンドウで、 **orch3 _** 左側のウィンドウで継続します。  

    > [!NOTE]
    >  Orch3 _ continuation と orch3 _ continuation ID を混同しないでください。 Continuation ID を表すアイコンには、キーが含まれています (![continuation ID のアイコン](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))、continuation を表すアイコンにキー (が含まれていません![continuation のアイコン](../core/media/test.gif "テスト"))。  

36. をクリックして**イベント ソースの選択**、] をクリックし、 **[オーケストレーション スケジュールの**します。  

37. **アセンブリ名**のセクション、 **イベント ソースの親アセンブリ**ダイアログ ボックスで、 **Microsoft.Samples.BizTalk.BamEndToEnd.Services**、順にクリックします**次**します。  

38. **オーケストレーション名**のセクション、**オーケストレーションの選択**ダイアログ ボックスで、 **BamEndToEnd.Services.Orchestration3**、 をクリックし、 **ok**.  

39. 右クリックし、 **Receive1**図形をクリックして**メッセージ ペイロード スキーマ**します。  

40. 値"Message_3"を含む行をダブルクリックして、**メッセージ**列と値に"BAMPart"で、**一部**列。  

41. 展開**BAMPart**、し、ドラッグ**DocumentID**を右側のウィンドウで、 **orch3 _** 左側のウィンドウで continuation ID。  

    > [!NOTE]
    >  Orch3 _ continuation と orch3 _ continuation ID を混同しないでください。 Continuation ID を表すアイコンには、キーが含まれています (![continuation ID のアイコン](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))、continuation を表すアイコンにキー (が含まれていません![continuation のアイコン](../core/media/test.gif "テスト"))。  

42. 矢印の付いたフォルダー アイコンをクリックします (![フォルダーと上矢印ボタン](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4"))、オーケストレーションを表示するには、2 回クリックします。  

43. ドラッグ、 **Receive1**右側のウィンドウに図形 **[sbegin3]** 左側のウィンドウでします。  

44. ドラッグ、 **Send_1**右側のウィンドウに図形 **[send3]** 左側のウィンドウでします。  

45. 右クリックし、 **Send_1**図形をクリックして**メッセージ ペイロード スキーマ**します。  

46. 展開**Schema3**、し、ドラッグ**Data3**を右側のウィンドウで**Data3**左側のウィンドウでします。  

47. 右クリック**DocumentID**下、 **orch2 _** クリックして、継続**ポート マッピングの設定**します。  

    > [!NOTE]
    >  Orch2 _ continuation と orch2 _ continuation ID を混同しないでください。 Continuation ID を表すアイコンには、キーが含まれています (![continuation ID のアイコン](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))、continuation を表すアイコンにキー (が含まれていません![continuation のアイコン](../core/media/test.gif "テスト"))。  

48. **ポートの選択**のセクション、**ポートの選択**ダイアログ ボックスで、 をクリックして**BamEndToEnd_ReceivePort**、クリックして-不等号 ( **>** )、をクリックし、 **OK**します。  

49. 追跡プロファイルを保存 *\<サンプル パス\>* \BAM\BamEndToEnd\BamEndToEnd.btt します。  

## <a name="important-details"></a>重要な詳細情報  
 パイプラインでは、追跡プロファイルはサポートされていません。 ただし、呼び出し**BeginActivity**パイプライン コンポーネントは、オーケストレーションで ActivityID の使用と同じです。 呼び出し**EnableContinuation**オーケストレーションでの continuation の使用と同じです。  

## <a name="see-also"></a>参照  
 [ビジネス アクティビティの監視 (BizTalk Server Samples フォルダー)](../core/business-activity-monitoring-biztalk-server-samples-folder.md)
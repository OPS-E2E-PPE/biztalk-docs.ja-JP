---
title: MQSSendPipelineComponent (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, MQSeries adapters
- pipelines, examples
- MQSeries adapters, examples
- examples, pipelines
ms.assetid: ac709e45-524b-45ab-9673-060790ecbed2
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3416b4a1ba58a1262e9ff27e3558a2532c839cd4
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752344"
---
# <a name="mqssendpipelinecomponent-biztalk-server-sample"></a>MQSSendPipelineComponent (BizTalk Server サンプル)
このサンプルでは、一連の MQSeries プロパティ値を XML ファイルから読み取って、メッセージに適用する、パイプライン コンポーネントの作成方法を示します。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルは、パイプライン コンポーネント プロジェクトおよびパイプライン コンポーネントを利用するパイプライン プロジェクトの 2 つの [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトで構成されています。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
  
- *\<SamplesPath\>* \AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent\SetMQSeriesHeaderPropertyComponent  
  
- *\<SamplesPath\>* \AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent\SetMQSeriesHeaderPropertyPipeline  
  
  次の表は、このサンプルのファイルとその目的を示しています。  
  
|                                                                              **[最近使ったファイル]**                                                                               |                                         **[説明]**                                          |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|
| SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent.sln、<br /><br /> SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent.csproj |                    パイプライン コンポーネントのプロジェクト ファイルとソリューション ファイルです。                    |
|                                              SetMQSeriesHeaderPropertyComponent\CSetMQSeriesHeaderPropertyComponent.cs                                              |                      パイプライン コンポーネントの Visual C#® ソース ファイルです。                      |
|                                                      SetMQSeriesHeaderPropertyComponent\SetMQSMQMDHdrProps.xml                                                      |                 パイプライン コンポーネントによって読み取られ、使用される MQSeries プロパティです。                 |
|   SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.btproj、<br /><br /> SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.sln   |                     BizTalk パイプラインのプロジェクト ファイルとソリューション ファイルです。                     |
|                                               SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.snk                                               |                   BizTalk パイプライン プロジェクトの厳密な名前のキー ファイルです。                   |
|                                               SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.btp                                               | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] パイプラインです。 |
  
## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 アプリケーションを作成するには、次の手順を実行します。  
  
1. アプリケーション用のフォルダーを作成します。  
  
2. パイプライン コンポーネント用に [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトを変更してコンパイルします。  
  
3. コンパイルしたアセンブリとヘッダー ファイルを適切なフォルダーにコピーします。  
  
4. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] パイプライン用に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトを変更します。  
  
5. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] パイプライン プロジェクトをコンパイルして展開します。  
  
6. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所を設定します。  
  
7. MQSeries キューを作成します。  
  
8. 送信ポートを設定します。  
  
9. 受信場所を有効にして送信ポートを開始します。  
  
## <a name="creating-the-folders-for-the-application"></a>アプリケーション用のフォルダーの作成  
 この手順では、アプリケーション用の適切なフォルダーを作成します。  
  
#### <a name="to-create-the-folders-for-the-application"></a>アプリケーション用のフォルダーを作成するには  
  
1.  という名前のフォルダーを作成する**temp** C:\ ドライブが既に存在しない場合にします。  
  
2.  下のフォルダーを作成、 **C:\temp**という名前のディレクトリ**Pickup3**します。  
  
## <a name="modifying-and-compiling-the-project-for-the-pipeline-component"></a>パイプライン コンポーネント用のプロジェクトの変更とコンパイル  
 この手順では、パイプライン コンポーネント用に [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトを変更してコンパイルします。  
  
#### <a name="to-modify-and-compile-the-project-for-the-pipeline-component"></a>パイプライン コンポーネント用にプロジェクトを変更およびコンパイルするには  
  
1. ソリューション ファイルをダブルクリックして **\setmqseriesheaderpropertycomponent.sln** でソリューションを開く[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。  
  
2. クラス ファイルをダブルクリックして **CSetMQSeriesHeaderPropertyComponent.cs** でクラス ファイルを開く[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。  
  
3. 変数を見つけて**samplesDir**、場所にこの変数が設定されていることを確認**C:\temp**します。  
  
4. ソリューション エクスプ ローラーでソリューションを右クリックし、をクリックして**ビルド**します。 これは、dll 内にある、プロジェクトのコンパイル、 **SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent\bin\Debug\\** ディレクトリ。  
  
## <a name="copying-the-assembly-and-header-file-to-appropriate-folders"></a>適切なフォルダーへのアセンブリとヘッダー ファイルのコピー  
 この手順では、コンパイルしたアセンブリとヘッダー ファイルを適切なフォルダーにコピーします。  
  
#### <a name="to-copy-the-compiled-assembly-and-header-file-to-the-appropriate-folders"></a>コンパイルしたアセンブリとヘッダー ファイルを適切なフォルダーにコピーするには  
  
1. コンパイル済みのアセンブリをコピー **SetMQSeriesHeaderPropertyComponent.dll** BizTalk パイプライン コンポーネント フォルダーにします。 BizTalk パイプライン コンポーネント フォルダーの既定の場所は [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Pipeline Components です。  
  
2. MQHeader プロパティ ファイルをコピー **SetMQSMQMDHdrProps.xml**を**C:\temp**ディレクトリ。  
  
## <a name="modifying-the-project-for-the-biztalk-server-pipeline"></a>BizTalk Server パイプライン用のプロジェクトの変更  
 この手順では、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] パイプライン用に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトを変更します。  
  
#### <a name="to-modify-the-project-for-the-biztalk-server-pipeline"></a>BizTalk Server パイプライン用にプロジェクトを変更するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、ソリューション ファイルをダブルクリックしてソリューションを開いて **\setmqseriesheaderpropertypipeline.sln** します。  
  
2. プロジェクトの厳密な名前キー ファイルを作成します。 この操作を行うには、次の手順を実行します。  
  
   1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] コマンド プロンプトを開きます。  
  
   2. ディレクトリに移動\<サンプル パス\>\AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent します。  
  
   3. 次のように入力します。  
  
       `sn -k MQSSendPipelineComponent.snk`  
  
   4. Enter キーを押します。 これにより、キー ファイルが作成されます。  
  
3. **ソリューション エクスプ ローラー**プロジェクトを右クリックし、クリックして、**プロパティ**プロジェクト デザイナー (中央のウィンドウ) でプロジェクトを起動します。  
  
   1.  プロジェクト デザイナーで、クリックして**署名**タブ。  
  
   2.  右側のウィンドウで、選択、**アセンブリに署名**オプション.  
  
   3.  ドロップダウン リストをクリックして、**厳密な名前キー ファイルを選択して** をクリックし、**参照**します。  
  
   4.  参照する\<サンプル パス\>\AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent\MQSSendPipelineComponent.snk、 をクリックして**オープン**します。  
  
4. 先ほど作成したパイプライン コンポーネントに既に追加されて、**プリアセンブル**このパイプライン プロジェクトのステージ。 このコンポーネントがまだ追加されていない場合は、次の手順に従って追加する必要があります。  
  
   1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] IDE、クリックして、**ツールボックス**左側にあるタブ。  
  
   2. 右クリックし、**ツールボックス**、 をクリック**アイテムの選択**します。  
  
   3. **ツールボックス アイテムの選択**ダイアログ ボックスで、をクリックして、 **BizTalk パイプライン コンポーネント**] タブで、[、 **MQseries ヘッダー プロパティを設定するカスタム コンポーネント**コンポーネント、およびクリックして**OK**します。  
  
   4. ドラッグ、 **MQseries ヘッダー プロパティを設定するカスタム コンポーネント**コンポーネントを**プリアセンブル**このパイプラインのステージ。  
  
## <a name="compiling-and-deploying-the-pipeline-project"></a>パイプライン プロジェクトのコンパイルと展開  
 この手順では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] パイプライン プロジェクトをコンパイルして展開します。  
  
#### <a name="to-compile-and-deploy-the-pipeline-project"></a>パイプライン プロジェクトをコンパイルおよび展開するには  
  
1.  ソリューション エクスプ ローラー ウィンドウで、ソリューションを右クリックし をクリックし、**ソリューションの配置**します。 これにより、ソリューションがビルドされ、アセンブリが BizTalk 管理データベースに展開されます。  
  
2.  次の手順に従って、アセンブリが BizTalk 管理データベースに展開されたことを確認します。  
  
    1.  BizTalk 管理コンソールを開きます。  
  
    2.  クリックして展開**BizTalk グループ [\<servername\>:\<管理データベース\>]** をクリックして展開し、**アセンブリ**フォルダー。  
  
         展開されたパイプライン アセンブリを下に表示されますが、**アセンブリ**フォルダー。  
  
## <a name="creating-the-receive-location"></a>作成、受信場所  
 この手順では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所を作成します。  
  
#### <a name="to-create-the-receive-location"></a>受信場所を作成するには  
  
1.  右クリックし、BizTalk Server 管理コンソールで**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**。  
  
2.  **一方向受信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに「MQReply」を入力し、 をクリック**OK**します。  
  
3.  左側のウィンドウで次のようにクリックします。**受信場所**タブをクリックし、[] をクリックし、**新規**します。  
  
4.  **受信場所のプロパティ** ダイアログ ボックスで、**名前**フィールドに「receivefile」と入力します。  
  
5.  **トランスポートの種類**ボックスで、**ファイル**します。  
  
6.  **受信ハンドラー**フィールドで、 **BizTalkServerApplication**します。  
  
7.  **受信パイプライン**フィールドで、 **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**します。  
  
8.  **受信フォルダー**フィールドに、"C:\temp\Pickup3"を入力します。  
  
9. **ファイル マスク**フィールドに「"\*.\*"。  
  
10. をクリックして**OK**、順にクリックします**OK**を終了するには、もう一度、**受信場所のプロパティ** ダイアログ ボックス。  
  
## <a name="creating-a-mqseries-queue-through-the-mqseries-explorer"></a>MQSeries エクスプローラーを使用した MQSeries キューの作成  
 MQSeries Server for Windows のインストールに必要なアクセス許可があればは、アダプターのダイアログ ボックスを使用して MQSeries キューを作成し、この次の手順を省略できます。  
  
 このようなアクセス許可を持っていない場合は、次の手順に従って、IBM WebSphere MQ エクスプローラーを使用してキューを作成できます。  
  
#### <a name="to-create-a-mqseries-queue-through-the-mqseries-explorer"></a>MQSeries エクスプローラーを使用して MQSeries キューを作成するには  
  
1.  クリックして**開始**、 をポイント**プログラム**、 をポイント**IBM WebSphere MQ**、順にクリックします**WebSphere MQ エクスプ ローラー**します。  
  
2.  ダブルクリック**キュー マネージャー**、し、既定のキュー マネージャーをダブルクリックします。 通常、既定のキュー マネージャーの名前**qm _**\<*machine_name* \>場所*machine_name*コンピューターの名前を指定します。  
  
3.  右クリック**キュー**、 をポイント**新規**、 をクリックし、**ローカル キュー**します。  
  
4.  **ローカル キューの作成** ダイアログ ボックスで**キュー名**、型**SETHEADER**、順にクリックします**OK**します。  
  
## <a name="creating-the-send-port-and-mqseries-queue"></a>送信ポートと MQSeries キューの作成  
 この手順では、出力メッセージ用の送信ポートを作成します。 MQSeries キューは、送信ポートがまだ作成されていない場合に送信ポートを作成したときにも作成されます。  
  
#### <a name="to-create-the-send-port-and-mqseries-queue"></a>送信ポートと MQSeries キューを作成するには  
  
1.  右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**します。  
  
2.  **送信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに「mqsolicitresponse」.  
  
3.  **トランスポートの種類**ボックスで、 **MQSeries**します。  
  
4.  **送信パイプライン**ボックスで、 **SetMQSeriesHeaderPropertyPipeline.SetMQSeriesHeadersSendPipeline**します。  
  
5.  **フィルター**、次の名前/値ペアを持つ新しいエントリを追加します。  
  
    -   設定**プロパティ**に"BTS します。ReceivePortName"。  
  
    -   設定**演算子**「= =」にします。  
  
    -   設定**値**を"ReceiveFile"。  
  
        > [!NOTE]
        >  これにより、ReceiveFile 受信ポートで受信したメッセージをサブスクライブするように送信ポートが設定されます。  
  
6.  クリックして**トランスポート**します。  
  
7.  **アドレス (URI)** フィールドで省略記号 (...) ボタンをクリックします。  
  
8.  **MQSeries トランスポートのプロパティ** ダイアログ ボックスで、**キュー定義**フィールドで省略記号 (...) ボタンをクリックします。  
  
9. **キュー定義** ダイアログ ボックスで、**サーバー名**フィールドに、コンピューター名を入力します。  
  
10. **キュー マネージャー**フィールドで、既定のキュー マネージャーを選択します。  
  
11. キュー フィールドに「SETHEADER」を入力し、、クリックして**エクスポート**します。  
  
12. **エクスポート**ダイアログ ボックスで、 をクリックして**キューの作成**、順にクリックします**ok**または**完了**すべてのダイアログを終了します。  
  
## <a name="enabling-the-receive-location-and-starting-the-send-port"></a>受信場所の有効化と送信ポートの開始  
 この手順では、受信場所を有効化し、送信ポートを開始します。  
  
#### <a name="to-enable-the-receive-location-and-start-the-send-port"></a>受信場所を有効にして送信ポートを開始するには  
  
1.  BizTalk Server 管理コンソールで、次のようにクリックします。**受信ポート**します。  
  
2.  詳細ペインで右クリックし、 **MQIn**受信場所とクリックして**を有効にする**します。  
  
3.  詳細ペインで右クリックし、 **SetMQHeader**送信ポートをクリックします**開始**します。  
  
## <a name="testing-the-application"></a>アプリケーションのテスト  
 この手順では、アプリケーションをテストします。  
  
#### <a name="to-test-the-application"></a>アプリケーションをテストするには  
  
1.  ファイルを配置、 **C:\Temp\Pickup3**フォルダー。  
  
2.  WebSphere MQ エクスプローラーを起動し、SETHEADER キューをダブルクリックして、SETHEADER キュー内のメッセージを検証します。  
  
     SETHEADER キュー内のメッセージのすべてのコンテキスト プロパティを表示するには、次の手順に従います。  
  
    1.  ダブルクリックして、 **SETHEADER**を表示するキュー、 **Message Browser**  ダイアログ ボックス。  
  
    2.  **Message Browser**ダイアログ ボックスで、をクリックして**列**を表示する、**のメッセージの表示/非表示列** ダイアログ ボックス。  
  
    3.  **使用可能な列**で表示されるようにするには、各エントリをダブルクリックして、 **Message Browser**クリックしてダイアログ ボックスで、 **ok**します。  
  
3.  各メッセージのメッセージ コンテキスト プロパティで表示するか、 **Message Browser**  ダイアログ ボックス。  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプタ サンプル](../core/mqseries-adapter-samples.md)
---
title: 'チュートリアル: ヘッダーとトレーラーを使用してフラット ファイル逆アセンブリ |Microsoft Docs'
description: フラット ファイル スキーマ ウィザードを使用してヘッダー スキーマ、トレーラー スキーマ、および本文のスキーマを作成し、BizTalk Server でのフラット ファイル逆アセンブル
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 715af9cc-d718-483d-b593-64462aa5a58b
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a3e2739b50d19c867fa05744ab98735ffc90646
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395335"
---
# <a name="walkthrough-flat-file-disassembly-using-a-header-and-trailer"></a>チュートリアル: ヘッダーとトレーラーを使用してフラット ファイル逆アセンブリ

## <a name="overview"></a>概要
このチュートリアルでは、フラット ファイル スキーマ ウィザードによって作成されたスキーマを使用して、ヘッダー、トレーラー、および繰り返しのメッセージ ボディを含んでいるファイルのフラット ファイル逆アセンブリを実行する方法を説明します。 このチュートリアルでは、次の要件を満たす架空のエラー追跡システムの一部を開発します。  
  
- エラー メッセージは社内のさまざまな物理的な場所でログに記録され、集中管理された場所に送信されて、さまざまなバックエンド システムに振り分けられます。  
  
- エラー メッセージは、場所を示すヘッダー、1 つ以上のエラー メッセージを含むボディ、およびバッチ数を示すトレーラーを含んだフラット ファイル形式で書き込まれます。  
  
- メッセージは、ヘッダー、ボディ、トレーラーを含んでいない場合、無効と見なされます。  
  
  このチュートリアルを完了すると、フラット ファイルを処理し、バックエンド システムで処理するために XML として出力する BizTalk Server アプリケーションが完成します。  
  
## <a name="prerequisites"></a>前提条件  
 この例では、BizTalk Server プロジェクトの作成、アセンブリへの署名、および BizTalk Server 管理コンソールでのアプリケーションとポートの表示に慣れている必要があります。 またはずで紹介したアイデアに[チュートリアル。基本的な BizTalk アプリケーション展開](../core/walkthrough-deploying-a-basic-biztalk-application.md)します。 フラット ファイル スキーマ ウィザードの基礎知識は役立ちますが、必須ではありません。  
  
## <a name="what-this-example-does"></a>この例の処理  
 この例では、受信フラット ファイルをカスタム パイプラインとフラット ファイル逆アセンブラー コンポーネントを使用して処理します。 ヘッダー スキーマ、トレーラー スキーマ、およびボディ スキーマを使用してメッセージを解析した後、バックエンドで処理するためにそれらのメッセージを送信場所に出力します。  
  
## <a name="example"></a>例  
 この例を作成するには、以下で概要を説明している手順を実行します。  
  
### <a name="create-a-new-biztalk-project"></a>新しい BizTalk プロジェクトの作成  
 BizTalk プロジェクトを作成する必要があるソリューションをビルドする前に、ソリューションに厳密な名前が付いていることを確認し、アプリケーション名をそのソリューションに割り当てます。 アプリケーション名を割り当てると、そのソリューションが BizTalk Server によって既定の BizTalk アプリケーションに配置されるのを防ぐことができます。  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して新しい BizTalk プロジェクトを作成します。 プロジェクトを呼び出す **[ffdisassemblerwalkthrough]** します。  
  
2. キー ファイルを作成してプロジェクトに割り当てます。 このタスクの詳細については、次を参照してください。[署名 Page, Project Designer](http://go.microsoft.com/fwlink/?LinkId=125876)します。  
  
3. プロジェクトの配置プロパティで、次のように設定します。**アプリケーション名**を"FlatFileExample"に設定し**ホスト インスタンスを再起動**に`True`します。 このフラグを設定すると、キャッシュされたアセンブリのインスタンスを消去するようにホストに通知されます。  
  
### <a name="create-the-sample-data-file"></a>サンプル データ ファイルの作成  
スキーマを生成する前に、テスト ファイルを作成する必要があります。   
  
1.  メモ帳または任意のテキスト エディターを起動します。  
  
2.  サンプル テスト ファイルを作成します。 このファイルは、エラーの報告元の場所を示すヘッダー、バッチの ID を含んだトレーラー、および 1 つ以上のエラー レコードで構成されたボディで構成されています。 ファイルの形式を次に示します。  
  
    ```  
    Location  
    ERRORid|type|priority|description|errorDateTime  
    …additional error records   
    BatchID  
    ```  
  
    エラー レコードのタグが付いたテキスト"ERROR"と区切り、"&#124;"文字 (位置指定)。 この ERROR レコードのデータ要素を次の表で説明します。  
  
    |要素|データ型|説明|  
    |---|---|---|  
    |ID|整数 (integer)|このエラーの ID。|  
    |型|整数 (integer)|エラーの種類。|  
    |[Priority]|string|優先度インジケーター:Low、Medium、または High。|  
    |説明|string|エラーの説明。|  
    |ErrorDateTime|DateTime|エラーが発生した日時です。|  
  
    ファイルには、1 つ以上の ERROR レコードを含めることができます。  
  
     * * - または-- * *
  
     新しいファイルに次のサンプル データをコピーします。 最後の行には、ラインフィードが含まれています。
  
    ```  
    East Coast Facility  
    ERROR102|0|High|Sprocket query fails.|1999-05-31T13:20:00.000-05:00  
    ERROR16502|2|Low|Time threshold exceeded.|1999-05-31T13:20:00.000-05:00  
    8675309  
  
    ```  
  
3.  新しいサンプル ファイルをプロジェクト ディレクトリに保存します。 簡単に見つけられるように、"ErrorFile.txt" などのわかりやすい名前を付けてください。  
  
### <a name="create-and-test-the-header-trailer-and-body-schemas"></a>ヘッダー スキーマ、トレーラー スキーマ、およびボディ スキーマの作成  
 サンプル データ ファイルを作成したら、ヘッダー スキーマ、トレーラー スキーマ、およびボディ スキーマを作成します。 これらのスキーマは、受信したメッセージを処理するためにフラット ファイル逆アセンブラー受信パイプライン コンポーネントで使用されます。  
  
##### <a name="use-the-flat-file-schema-wizard-to-create-the-header-schema"></a>フラット ファイル スキーマ ウィザードを使用して、ヘッダー スキーマを作成するには  
  
1.  新しいスキーマをプロジェクトに追加します。 ソリューション エクスプ ローラーで右クリック**ffdisassemblerwalkthrough**、 をポイント**追加**、 をクリックし、**新しい項目の**します。  
  
2.  **新しい項目の追加**ダイアログ ボックスで、をクリックして**スキーマ ファイル**選択と**フラット ファイル スキーマ ウィザード**します。 新しいスキーマ"Header.xsd"という名前をクリックして**追加**します。  
  
3.  **BizTalk フラット ファイル スキーマ ウィザードへようこそ**] ページで [**次**します。  
  
4.  **フラット ファイル スキーマ情報**] ページで [**参照**前に作成したサンプル データ ファイルを見つけます。 変更、**レコード名**"Header"に、コード ページを確認し、**次**します。  
  
    > [!NOTE]
    >  サンプル ファイルを Unicode 形式で保存した場合、コード ページはリトル エンディアン UTF16 (1200) になります。 これは、この例に影響しません。  
  
5.  次に、ドキュメント データを選択します。 **ドキュメント データを選択** ページで、改行文字 {CR} を含むデータの最初の行を強調表示と {LF} よう。  
  
     ![ヘッダー スキーマ用に選択されたデータ](../core/media/ffwiz-header-select-document-data.gif "ffwiz_header_select_document_data")  
  
     **[次へ]** をクリックします。  
  
6.  **レコード書式を** ページで  **次へ**既定値を受け入れます。 データ ファイルでは相対位置を使用していないので、既定の "区切り記号" を使用できます。  
  
7.  **区切られたレコード**] ページで [**次**します。  
  
8.  次に子要素を指定します。 次に示すように、ヘッダーには、"Location" という要素が 1 つ含まれています。  
  
     ![ヘッダーに定義された場所ノード](../core/media/ffwiz-header-child-elements.gif "ffwiz_header_child_elements")  
  
     **[次へ]** をクリックして次に進みます。  
  
9. **スキーマ ビュー**ページで、スキーマを確認します。  
  
     ![スキーマ ビューの表示が完了したヘッダー スキーマ](../core/media/ffwiz-header-schema-view.gif "ffwiz_header_schema_view")  
  
     問題がなければ、 をクリックして**完了**ウィザードを完了します。  
  
10. をクリックして、 **\<スキーマ\>** ヘッダー スキーマ ペインでノード。 プロパティ ペインで次のように変更します。 **Element FormDefault**に**Qualified**します。 これは、ローカルに宣言された要素を、ターゲットの名前空間を使用してインスタンス ドキュメント内で修飾する必要があることを示します。  
  
##### <a name="use-the-flat-file-schema-wizard-to-create-the-trailer-schema"></a>フラット ファイル スキーマ ウィザードを使用して、トレーラー スキーマを作成するには  
  
1.  新しいスキーマをプロジェクトに追加します。 ソリューション エクスプ ローラーで右クリック**ffdisassemblerwalkthrough**、 をポイント**追加**、 をクリックし、**新しい項目の**します。  
  
2.  **新しい項目の追加**ダイアログ ボックスで、をクリックして**スキーマ ファイル**選択と**フラット ファイル スキーマ ウィザード**します。 新しいスキーマ"Trailer.xsd"という名前をクリックして**追加**します。  
  
3.  **BizTalk フラット ファイル スキーマ ウィザードへようこそ**] ページで [**次**します。  
  
4.  **フラット ファイル スキーマ情報**] ページで [**参照**前に作成したサンプル データ ファイルを見つけます。 変更、**レコード名**を"Trailer"、コード ページを確認し、**次**します。  
  
    > [!NOTE]
    >  サンプル ファイルを Unicode 形式で保存した場合、コード ページはリトル エンディアン UTF16 (1200) になります。 これは、この例に影響しません。  
  
5.  次に、ドキュメント データを選択します。 **ドキュメント データを選択** ページで、改行文字 {CR} を含むデータの最後の行を強調表示と {LF} よう。  
  
     ![トレーラー スキーマ用に選択されたデータ](../core/media/ffwiz-trailer-select-document-data.gif "ffwiz_trailer_select_document_data")  
  
     **[次へ]** をクリックします。  
  
6.  **レコード書式を** ページで  **次へ**既定値を受け入れます。 データ ファイルでは相対位置を使用していないので、既定の "区切り記号" を使用できます。  
  
7.  **区切られたレコード**] ページで [**次**します。  
  
8.  次に子要素を指定します。 次に示すように、ヘッダーには、"BatchID" という要素が 1 つ含まれています。  
  
     ![トレーラー用に定義された場所ノード](../core/media/ffwiz-trailer-child-elements.gif "ffwiz_trailer_child_elements")  
  
     **[次へ]** をクリックして次に進みます。  
  
9. **スキーマ ビュー**ページで、スキーマを確認します。  
  
     ![スキーマ ビュー表示が完了したトレーラー スキーマ](../core/media/ffwiz-trailer-schema-view.gif "ffwiz_trailer_schema_view")  
  
     問題がなければ、 をクリックして**完了**ウィザードを完了します。  
  
10. をクリックして、 **\<スキーマ\>** トレーラー スキーマ ペイン内のノード。 プロパティ ペインで次のように変更します。 **elementFormDefault**に**Qualified**します。 これは、ローカルに宣言された要素を、ターゲットの名前空間を使用してインスタンス ドキュメント内で修飾する必要があることを示します。  
  
##### <a name="use-the-flat-file-schema-wizard-to-create-the-body-schema"></a>フラット ファイル スキーマ ウィザードを使用して、本文のスキーマを作成するには  
  
1.  新しいスキーマをプロジェクトに追加します。 ソリューション エクスプ ローラーで右クリック**ffdisassemblerwalkthrough**、 をポイント**追加**、 をクリックし、**新しい項目の**します。  
  
2.  **新しい項目の追加**ダイアログ ボックスで、をクリックして**スキーマ ファイル**選択と**フラット ファイル スキーマ ウィザード**します。 新しいスキーマ"Body.xsd"という名前をクリックして**追加**します。  
  
3.  **BizTalk フラット ファイル スキーマ ウィザードへようこそ**] ページで [**次**します。  
  
4.  **フラット ファイル スキーマ情報**] ページで [**参照**前に作成したサンプル データ ファイルを見つけます。 変更、**レコード名**"Body"に、コード ページを確認し、**次**します。  
  
    > [!NOTE]
    >  サンプル ファイルを Unicode 形式で保存した場合、コード ページはリトル エンディアン UTF16 (1200) になります。 これは、この例に影響しません。  
  
5.  次に、ドキュメント データを選択します。 **ドキュメント データを選択** ページで、改行文字 {CR} を含む、データの 2 と 3 つの行を強調表示と {LF} よう。  
  
     ![ボディ スキーマ用に選択されたデータ](../core/media/ffwiz-body-select-document-data.gif "ffwiz_body_select_document_data")  
  
     **[次へ]** をクリックします。  
  
6.  **レコード書式を** ページで  **次へ**既定値を受け入れます。 データ ファイルでは相対位置を使用していないので、既定の "区切り記号" を使用できます。  
  
7.  **区切られたレコード**] ページで、[**次**します。  
  
8.  ここでは、子要素を定義します。 変更**Body_Child1**に**エラー**に要素の型を設定および**繰り返しレコード**します。 設定、 **Body_Child2**要素レコードの種類を**無視**します。  
  
9. **スキーマ ビュー** ] ページで [**次**エラー レコードの子要素を定義します。  
  
10. **ドキュメント データを選択**] ページで [**次**します。 ウィザードによって、レコード定義データが適切に選択されます。  
  
11. **レコード書式を** ページで **次**します。 データは、区切り記号で書式設定されます。  
  
12. **区切られたレコード**] ページで、[ **&#124;** の**子区切り記号**します。 次に、選択、**レコードにタグ識別子** チェック ボックス**エラー**タグ値にします。  
  
     ![構成で区切られたレコードのタグ識別子](../core/media/ffwiz-bodyerror-delimited-record.gif "ffwiz_bodyerror_delimited_record")  
  
     **[次へ]** をクリックします。  
  
13. ここでは、Error レコードの子要素を定義します。  
  
     ![5 つの要素で定義されたエラー レコード](../core/media/ffwiz-bodyerror-child-elements.gif "ffwiz_bodyerror_child_elements")  
  
     **[次へ]** をクリックします。  
  
14. **スキーマ ビュー**ページで、スキーマを確認します。  
  
     ![スキーマ ビュー表示が完了したボディ スキーマ](../core/media/ffwiz-bodyerror-schema-view.gif "ffwiz_bodyerror_schema_view")  
  
     誤りを加えた場合にクリックします**戻る**し、必要に応じて修正します。 問題がなければ、 をクリックして**完了**ウィザードを完了します。  
  
15. をクリックして、 **\<スキーマ\>** Body スキーマ ペイン内のノード。 プロパティ ペインで次のように変更します。 **Element FormDefault**に**Qualified**します。 これは、ローカルに宣言された要素を、ターゲットの名前空間を使用してインスタンス ドキュメント内で修飾する必要があることを示します。  
  
16. をクリックして、 **\<エラー\>**  Body スキーマ ペイン上のノード。 プロパティ ペインで次のように変更します。 **Max Occurs**に**1**します。 これにより、フラット ファイル逆アセンブラーによって各エラーがそれぞれのメッセージに分割されます。  
  
##### <a name="test-the-schemas-using-ffdasm"></a>FFDasm を使用してスキーマをテストします。  
  
1.  コマンド プロンプトを開き、ディレクトリをプロジェクト ディレクトリに変更します。  
  
2.  コマンド プロンプトから、次に示すように FFDasm.exe を実行します。  
  
    ```  
    <Samples Path>\SDK\Utilities\PipelineTools\FFDasm ErrorFile.txt  -hs header.xsd -bs body.xsd -ts Trailer.xsd  
    ```  
  
     これと他のパイプライン ツールの場所については、次を参照してください。[パイプライン ツール](../core/pipeline-tools.md)します。  
  
3.  FFDasm.exe によって、テスト ファイル内の各 ERROR レコードに対応した {GUID}.xml という名前の出力ファイルが 2 つ生成されます。 優先度の高いエラー レコードは、次のようになります。  
  
    ```  
    <Body xmlns="http://FFDisassemblerWalkthrough.Body">  
      <Error>  
        <ID>102</ID>  
        <Type>0</Type>  
        <Priority>High</Priority>  
        <Description>Sprocket query fails.</Description>  
        <DateTime>1999-05-31T13:20:00.000-05:00</DateTime>  
      </Error>  
    </Body>  
    ```  
  
### <a name="create-a-custom-receive-pipeline"></a>カスタム受信パイプラインの作成  
 フラット ファイル スキーマを定義したので、次はフラット ファイル逆アセンブラー コンポーネントを使用するカスタム パイプラインを作成する必要があります。 その後で、フラット ファイル逆アセンブラー コンポーネントを、ヘッダー スキーマ、ボディ スキーマ、およびトレーラー スキーマを使用するように構成して、メッセージを分割できます。    
 
1.  新しい受信パイプラインをプロジェクトに追加します。 ソリューション エクスプ ローラーで右クリックし、 **ffdisassemblerwalkthrough**プロジェクトをポイントして、**追加**、 をクリックし、**新しい項目の**。  
  
2.  **新しい項目の追加** ダイアログ ボックスで、 をポイント**パイプライン ファイル** をクリックし、**受信パイプライン**します。 新しいパイプライン"FFReceivePipeline"という名前をクリックして**追加**します。  
  
3.  フラット ファイル逆アセンブラー コンポーネントを、[ツールボックス] ペインから逆アセンブル ステップへドラッグして新しいパイプラインを構成します。  
  
4.  プロパティ ウィンドウで、設定、**ドキュメント スキーマ**に**FFDisassemblerWalkthrough.Body**、**ヘッダー スキーマ**に**FFDisassemblerWalkthrough.Header**と**トレーラー スキーマ**に**FFDisassemblerWalkthrough.Trailer**します。  
  
### <a name="deploy-the-application-and-configure-the-send-and-receive-ports"></a>アプリケーションの展開および送信ポートと受信ポートの構成  
 スキーマとカスタム受信パイプラインを作成したら、次はプロジェクトをコンパイルして配置する必要があります。 プロジェクトを配置すると、BizTalk Server 管理コンソールを使用して、送信ポートと受信ポートを構成できます。  

##### <a name="deploy"></a>配置  
1. 内から[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、プロジェクトを右クリックし、をクリックして、ソリューションを配置**デプロイ**します。  
  
2. 展開し、BizTalk Server 管理コンソールを使用して、**アプリケーション**ことを確認するグループ **[flatfileexample]** がカスタム アプリケーションとして存在します。  
  
##### <a name="configure-the-receive-port"></a>受信ポートを構成します。  
  
1.  下の"Receive"という名前のディレクトリを作成する Windows エクスプ ローラーを使用して、 **[ffdisassemblerwalkthrough]** プロジェクト ディレクトリ。  
  
2.  BizTalk Server 管理コンソールで、 **flatfileexample**アプリケーションを右クリックして**受信ポート**、 をポイント**新規**順にクリックします**一方向受信ポート**します。  
  
3.  **受信ポートのプロパティ** ダイアログ ボックスで、ポートを"ReceiveError"の名前を設定します。  
  
4.  クリックして**受信場所**、 をクリックし、**新規**受信場所を追加します。 新しい受信場所に "ReceiveErrorLocation" という名前を付けます。 設定、**受信パイプライン**に**FFReceivePipeline**します。 **トランスポートの種類**を選択します**ファイル**、 をクリックし、**構成**します。 設定し、作成した受信ディレクトリを選択、**ファイル マスク***.txt にします。  
  
5.  **[OK]** をクリックします。 受信ポートが正しく構成されます。 クリックして**OK**を閉じます。  
  
##### <a name="configure-the-send-port"></a>送信ポートを構成します。  
  
1.  下の"Send"という名前のディレクトリを作成する Windows エクスプ ローラーを使用して、 **[ffdisassemblerwalkthrough]** プロジェクト ディレクトリ。  
  
2.  BizTalk Server 管理コンソールで、 **[flatfileexample]** 、アプリケーションを右クリックして**送信ポート**、 をポイント**新規**、順にクリックします**静的な一方向送信ポートしています**。  
  
3.  **送信ポートのプロパティ** ダイアログ ボックスで、「送信」をポートの名前を設定します。  
  
4.  トランスポートの種類を選択**ファイル**、 をクリックし、**構成**します。 送信先のフォルダーを、先ほど作成した送信ディレクトリに設定します。  
  
5.  次は、フィルターを構成します。 クリックして**フィルター**し、1 つの式を追加します。  
  
    -   BTS.MessageType == **http://FFDisassemblerWalkthrough.Body#Body**  
  
6.  クリックして**OK**送信ポートの構成を完了します。 送信ポートが正しく構成されます。  
  
### <a name="run-the-example"></a>例の実行  
 次に、例を実行します。 BizTalk Server 管理コンソールを使用すると、アプリケーションを起動、受信場所に、テスト ファイルをコピーし、送信場所に生成される内容を確認します。  
  
1.  右クリックし、BizTalk Server 管理コンソールで、 **[flatfileexample]** アプリケーション、およびクリック**開始**します。 送信を開始し、および受信ポートこれを参加させます。  
  
2.  サンプルの Errorfile.txt のコピーを受信ディレクトリに置きます。 2 つの出力ファイルが送信ディレクトリに書き込まれます。  
  

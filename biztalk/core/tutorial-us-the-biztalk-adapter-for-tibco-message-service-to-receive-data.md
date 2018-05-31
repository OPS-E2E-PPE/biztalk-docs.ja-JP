---
title: 'チュートリアル: BizTalk Adapter for TIBCO Enterprise Message Service を使用してデータを受信する |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc5a63ec-1897-4c9b-b37f-cdcec151b1c9
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ee9994861772be8fabe04a04e9bb30111cc1bc4
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008579"
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-enterprise-message-service-to-receive-data"></a>チュートリアル: BizTalk Adapter for TIBCO Enterprise Message Service を使用したデータの受信
BizTalk Adapter for TIBCO Enterprise Message Service (EMS) を使用して TIBCO システムからデータを受信できます。 このチュートリアルでは、これを示す SDK サンプルについて説明します。  
  
## <a name="prerequisites"></a>前提条件  
  
-   BizTalk Adapter for TIBCO Enterprise Message Service を使用するには、TIBCO EMS C# API の TIBCO.EMS.dll をグローバル アセンブリ キャッシュ (GAC) に追加する必要があります。 アセンブリのインストールの詳細については、次を参照してください。 [TIBCO Enterprise Message Service の要件と制限事項](../core/tibco-enterprise-message-service-requirements-and-limitations.md)です。  
  
-   このサンプルをビルドして展開するには、アダプターが実行されている [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールしてください。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、フォルダーから XML ファイルを取得し、そのファイルをオーケストレーションに送信し、BizTalk Adapter for TIBCO Enterprise Message Service を使用して TIBCO システムからデータを取得します。 結果は、XML ファイルに書き込まれます。  
  
## <a name="how-this-sample-is-designed-and-why"></a>このサンプルのデザイン方法とその理由  
 このサンプルは、Visual Studio でデザインでは、BizTalk オーケストレーションで TIBCO Enterprise Message Service の BizTalk アダプターを使用して基本的な機能を示しています。  
  
> [!NOTE]
>  このサンプルでは、処理するアプリケーション用の TIBCO からメッセージを送信する方法を理解していることを前提としています。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルの既定の場所は、次のとおりです。  
  
 C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Enterprise Message Service(TM)\Sdk\OneWayReceive  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|**ランタイム プロジェクト ファイル名**|**ランタイム プロジェクト ファイルの説明**|  
|----------------------------------|------------------------------------------|  
|OneWayReceive.btproj、<br /><br /> OneWayReceive.sln|アプリケーションのプロジェクトおよびソリューション ファイル。|  
|Schema.xsd、|アプリケーションのスキーマ ファイルです。|  
|Orchestration.odx|アプリケーションが使用するオーケストレーション。|  
|TIBCOEMSOneWaySend.snk|厳密な名前のキー ファイル。|  
  
## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
  
#### <a name="create-a-new-instance-of-the-biztalk-adapter-for-tibco-ems"></a>BizTalk Adapter for TIBCO EMS の新しいインスタンスを作成する  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを起動します。 をクリックして**開始**、**プログラム**、 **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、 **BizTalk Server 管理**です。  
  
2.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**プラットフォームの設定**をクリックして**アダプター**です。  
  
3.  右クリック**アダプター**を指す**新規**、**アダプター**を表示する、**アダプターのプロパティ**ダイアログ。  
  
4.  値を入力して、**名前**フィールド、たとえば**TIBCO EMS**です。  
  
5.  選択**TIBCO Enterprise Message System**で利用可能なアダプターの一覧から、**アダプター**ドロップダウン リスト をクリック**OK**です。  
  
#### <a name="create-a-biztalk-receive-port"></a>BizTalk 受信ポートを作成する  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**を展開して**BizTalk アプリケーション 1**、] をクリック**受信ポート**です。  
  
2.  受信ポート フォルダーを右クリックし、をクリックして**新規**、**一方向の受信ポート**受信ポートのプロパティ ダイアログを表示します。  
  
3.  値を入力、**名前**フィールド、たとえば**TIBCOEMSOneWayRP**、 をクリック**OK**です。  
  
#### <a name="create-a-biztalk-receive-location"></a>BizTalk の受信場所を作成する  
  
1.  右クリックし、新しい受信ポートをクリックし、**新規**、**受信場所の**を表示する、**受信場所のプロパティ**ダイアログ。  
  
2.  値を入力して、**名前**フィールド、たとえば**TIBCOEMSOneWayRL**です。  
  
3.  使用可能なアダプターの一覧から TIBCO EMS アダプターを選択して、**型**ドロップダウン リスト ボックスし、をクリックして、**構成**アダプターを表示するにはボタン**トランスポートのプロパティ**ダイアログ ボックス。  
  
    > [!NOTE]
    >  この値は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで TIBCO アダプターを作成したときに指定した名前です。  
  
4.  値を入力して、**サーバー接続の定義**:  
  
    |**プロパティ**|**値**|  
    |------------------|---------------|  
    |転送先|サーバーの送信先キューまたはトピック名。|  
    |[ポート番号]|TIBCO サーバーが待ち受けしているポート。 既定値は 7222 です。|  
    |[サーバー名]|TIBCO EMS サーバーの名前。|  
  
5.  値を入力して、**ユーザーの資格情報**:  
  
    |**プロパティ**|**値**|  
    |------------------|---------------|  
    |Password|TIBCO EMS サーバーのパスワード。|  
    |ユーザー名|TIBCO EMS サーバーのユーザー名。|  
  
     プロパティの詳細については、次を参照してください。 [TIBCO Enterprise メッセージ サービス受信ハンドラーの作成](../core/creating-tibco-enterprise-message-service-receive-handlers.md)です。  
  
6.  **[OK]** をクリックします。  
  
7.  選択 **[xmlreceive]** で使用可能なパイプラインの一覧から、**受信パイプライン**ドロップダウン リスト ボックスし、をクリックして**OK**です。  
  
8.  受信場所を右クリックし、をクリックして**を有効にする**です。  
  
#### <a name="create-a-one-way-file-send-port"></a>一方向 FILE 送信ポートを作成する  
  
1.  送信ポートが使用する送信先フォルダー (たとえば、C:\FilesOut) を作成します。  
  
2.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**を展開して**BizTalk アプリケーション 1**、] をクリック**送信ポート**です。  
  
3.  右クリック**送信ポート**を指す**新規**、**静的な一方向送信ポート**を表示する、**送信ポートのプロパティ**ダイアログ。  
  
4.  値を入力して、**名前**フィールド、たとえば**TIBCOEMSOneWayFileSP**です。  
  
5.  選択**ファイル**で使用可能なアダプターの一覧から、**型**ドロップダウン リスト ボックスし、をクリックして、**構成**アダプターを表示するにはボタン**トランスポートプロパティ** ダイアログ ボックス。  
  
6.  **コピー先フォルダー**プロパティ、先ほど作成したフォルダーの場所を入力し、をクリックして**OK**です。  
  
7.  選択、 **xmltransmit**パイプラインで使用可能なパイプラインの一覧から、**送信パイプライン**ドロップダウン リスト をクリック**OK**です。  
  
8.  送信ポートを右クリックし、をクリックして**開始**を参加させて、送信ポートを開始します。  
  
#### <a name="build-and-deploy-the-project"></a>プロジェクトのビルドと展開  
  
1.  ソリューション エクスプ ローラーで OneWayReceive プロジェクトを右クリックし、をクリックして**プロパティ**プロジェクトのプロジェクト デザイナーを起動します。  
  
2.  クリックして、**展開**タブです。  
  
3.  適切な値を入力、**サーバー**プロパティおよび**構成データベース**プロパティの  **BizTalk グループ**カテゴリ。  
  
4.  ソリューション エクスプ ローラーで OneWayReceive プロジェクトを右クリックし、をクリックして**展開**プロジェクトをビルドしてアセンブリを展開する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成データベース。  
  
#### <a name="bind-and-enlist-the-orchestration"></a>オーケストレーションをバインドして参加させる  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**を展開して**BizTalk アプリケーション 1**、] をクリック**オーケストレーション**です。  
  
2.  をクリックして、**更新**ボタンをクリックして、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール ツールバーまたはキーを押して、 **f5 キーを押して**を更新するキーボードのキー、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールの表示。  
  
3.  表示するオーケストレーションをダブルクリック、**オーケストレーションのプロパティ**ダイアログ。  
  
4.  をクリックして**バインド**オーケストレーションのバインド オプションを表示するダイアログ ボックスの左ペインでします。  
  
5.  バインド オプションに適切な値を指定します。次に例を示します。  
  
    |**パラメーター**|**値**|  
    |-------------------|---------------|  
    |Host|BizTalkServerApplication|  
    |FileSendPort|TIBCOEMSOneWayFileSP|  
    |TibcoEMSOneWayReceiveOperation|TIBCOEMSOneWayRP|  
  
6.  **[OK]** をクリックします。  
  
#### <a name="start-the-orchestration"></a>オーケストレーションを開始します。  
  
-   [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]管理コンソールでは、オーケストレーションを右クリックし、をクリックして**開始**を参加させて、オーケストレーションを開始します。  
  
#### <a name="verify-that-the-application-receives-a-message"></a>アプリケーションがメッセージを受信することの確認  
  
-   ファイル送信ポートの送信先として構成されているフォルダーを開いて、出力ドキュメントが生成されていることを確認します。 このファイルには、BizTalk Adapter for TIBCO Enterprise Message Service によって処理されたクエリの結果が含まれている必要があります。  
  
 ドキュメント インスタンスが正常に処理された場合、次の一連のイベントが発生します。  
  
1.  TIBCO EMS アダプターが TIBCO システムからメッセージを取得し、BizTalk メッセージとしてメッセージ ボックスに公開します。  
  
2.  オーケストレーションがこの公開されたメッセージをサブスクライブします。これにより、BizTalk メッセージング エンジンがオーケストレーションのインスタンスをアクティブ化し、オーケストレーション インスタンスにメッセージを送信できるようにします。  
  
3.  オーケストレーション インスタンスがメッセージ ボックスにメッセージを返します。  
  
4.  ファイル送信ポートがこのメッセージをサブスクライブし、BizTalk がメッセージをファイル アダプターに送信します。  
  
5.  ファイル アダプターが、結果セットを含むメッセージを指定の出力フォルダーに書き込みます。  
  
## <a name="see-also"></a>参照  
 [チュートリアル: BizTalk Adapter for TIBCO Enterprise Message Service を使用してデータを送信するには](../core/tutorial-use-tibco-enterprise-message-service-adapter-in-biztalk-to-send-data.md)   
 [チュートリアル: Microsoft BizTalk Adapter を使用して TIBCO Enterprise Message Service の](../core/tutorials-use-the-microsoft-biztalk-adapter-for-tibco-message-service.md)   
 [作業の開始](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)
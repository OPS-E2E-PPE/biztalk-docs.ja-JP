---
title: 'チュートリアル: BizTalk Adapter for TIBCO Enterprise Message Service を使用してデータを受信する |Microsoft Docs'
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
ms.openlocfilehash: 3d4f4ac08b979dfc959c6e2ea0aab68b8c07db67
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977523"
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-enterprise-message-service-to-receive-data"></a>チュートリアル: BizTalk Adapter for TIBCO Enterprise Message Service を使用したデータの受信
BizTalk Adapter for TIBCO Enterprise Message Service (EMS) を使用して TIBCO システムからデータを受信できます。 このチュートリアルでは、これを示す SDK サンプルについて説明します。  

## <a name="prerequisites"></a>前提条件  

- BizTalk Adapter for TIBCO Enterprise Message Service を使用するには、TIBCO EMS C# API の TIBCO.EMS.dll をグローバル アセンブリ キャッシュ (GAC) に追加する必要があります。 アセンブリのインストールの詳細については、[TIBCO Enterprise Message Service の要件と制限事項](../core/tibco-enterprise-message-service-requirements-and-limitations.md)を参照してください。  

- このサンプルをビルドして展開するには、アダプターが実行されている [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールしてください。  

## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、フォルダーから XML ファイルを取得し、そのファイルをオーケストレーションに送信し、BizTalk Adapter for TIBCO Enterprise Message Service を使用して TIBCO システムからデータを取得します。 結果は、XML ファイルに書き込まれます。  

## <a name="how-this-sample-is-designed-and-why"></a>このサンプルのデザイン方法とその理由  
 このサンプルは、Visual Studio でデザインでは、BizTalk オーケストレーションで TIBCO Enterprise Message Service の BizTalk アダプターを使用した基本機能を示しています。  

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

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを起動します。 クリックして**開始**、**プログラム**、 **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、 **BizTalk Server 管理**します。  

2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk Server 管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**順にクリックします**アダプター**します。  

3. 右クリック**アダプター**  をポイント**新規**、**アダプター**を表示する、**アダプター プロパティ**ダイアログ。  

4. 値を入力、**名前**フィールドに、たとえば**TIBCO EMS**します。  

5. 選択**TIBCO Enterprise Message System**で利用可能なアダプターの一覧から、**アダプター**ドロップダウンをクリック **[ok]**。  

#### <a name="create-a-biztalk-receive-port"></a>BizTalk 受信ポートを作成する  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、] をクリック**受信ポート**します。  

2. 受信ポート フォルダーを右クリックし、をクリックし、**新規**、**一方向の受信ポート**受信ポートのプロパティ ダイアログを表示します。  

3. 値を入力、**名前**フィールドに**TIBCOEMSOneWayRP**、 をクリック**OK**します。  

#### <a name="create-a-biztalk-receive-location"></a>BizTalk の受信場所を作成する  

1. 右クリックし、新しい受信ポート をクリックし、**新規**、**受信場所**を表示する、**受信場所のプロパティ**ダイアログ。  

2. 値を入力、**名前**フィールドに、たとえば**TIBCOEMSOneWayRL**します。  

3. 使用可能なアダプターの一覧から TIBCO EMS アダプターを選択、**型**ドロップダウン ボックス、をクリックし、**構成**アダプターを表示するボタン**トランスポートのプロパティ**ダイアログ ボックス。  

   > [!NOTE]
   >  この値は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで TIBCO アダプターを作成したときに指定した名前です。  

4. 値を入力、**サーバー接続の定義**:  


   | **プロパティ** |                                **[値]**                                |
   |--------------|-------------------------------------------------------------------------|
   | [Destination]  |               サーバーの送信先キューまたはトピック名。               |
   | [ポート番号]  | TIBCO サーバーが待ち受けしているポート。 既定値は 7222 です。 |
   | [サーバー名]  |                    TIBCO EMS サーバーの名前。                    |


5. 値を入力、**ユーザーの資格情報**:  

   |**プロパティ**|**[値]**|  
   |------------------|---------------|  
   |パスワード|TIBCO EMS サーバーのパスワード。|  
   |[ユーザー名]|TIBCO EMS サーバーのユーザー名。|  

    プロパティの詳細については、[作成 TIBCO Enterprise Message Service 受信ハンドラー](../core/creating-tibco-enterprise-message-service-receive-handlers.md)を参照してください。  

6. **[OK]** をクリックします。  

7. 選択**XMLReceive**で使用可能なパイプラインの一覧から、**受信パイプライン**ドロップダウン ボックスし、をクリックして**OK**。  

8. 受信場所を右クリックし、をクリックして**を有効にする**します。  

#### <a name="create-a-one-way-file-send-port"></a>一方向 FILE 送信ポートを作成する  

1. 送信ポートが使用する送信先フォルダー (たとえば、C:\FilesOut) を作成します。  

2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、] をクリック**送信ポート**します。  

3. 右クリックして**送信ポート** をポイント**新規**、**静的な一方向送信ポート**を表示する、**送信ポートのプロパティ**ダイアログ。  

4. 値を入力、**名前**フィールドに、たとえば**TIBCOEMSOneWayFileSP**します。  

5. 選択**ファイル**で使用可能なアダプターの一覧から、**型**ドロップダウン ボックス、をクリックし、**構成**アダプターを表示するボタン**トランスポートプロパティ** ダイアログ ボックス。  

6. **先フォルダー**プロパティは、先ほど作成したフォルダーの場所を入力しをクリックして**OK**します。  

7. 選択、 **XMLTransmit**で利用可能なパイプラインの一覧から、**送信パイプライン**ドロップダウン をクリック**ok**します。  

8. 送信ポートを右クリックし、をクリックして**開始**を参加させて、送信ポートを開始します。  

#### <a name="build-and-deploy-the-project"></a>プロジェクトのビルドと展開  

1. ソリューション エクスプ ローラーで OneWayReceive プロジェクトを右クリックし、をクリックして**プロパティ**をプロジェクトのプロジェクト デザイナーを起動します。  

2. をクリックして、**展開**タブ。  

3. 適切な値を入力、 **Server**プロパティおよび**構成データベース**のプロパティの  **BizTalk グループ**カテゴリ。  

4. ソリューション エクスプ ローラーで OneWayReceive プロジェクトを右クリックし、をクリックして**デプロイ**プロジェクトをビルドしてアセンブリを展開する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成データベース。  

#### <a name="bind-and-enlist-the-orchestration"></a>オーケストレーションをバインドして参加させる  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、] をクリック**オーケストレーション**します。  

2. をクリックして、**更新**ボタン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール ツールバーまたはキーを押して、 **F5**を更新するキーボードのキー、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール ビュー。  

3. 表示するオーケストレーションをダブルクリックして、**オーケストレーションのプロパティ**ダイアログ。  

4. クリックして**バインド**オーケストレーションのバインド オプションを表示するダイアログ ボックスの左側のウィンドウでします。  

5. バインド オプションに適切な値を指定します。次に例を示します。  


   |         **パラメーター**          |        **[値]**         |
   |--------------------------------|--------------------------|
   |              ホスト              | BizTalkServerApplication |
   |          FileSendPort          |   TIBCOEMSOneWayFileSP   |
   | TibcoEMSOneWayReceiveOperation |     TIBCOEMSOneWayRP     |


6. **[OK]** をクリックします。  

#### <a name="start-the-orchestration"></a>オーケストレーションを開始します  

- [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]管理コンソールでは、オーケストレーションを右クリックし、クリックして**開始**を参加させて、オーケストレーションを開始します。  

#### <a name="verify-that-the-application-receives-a-message"></a>アプリケーションがメッセージを受信することの確認  

- ファイル送信ポートの送信先として構成されているフォルダーを開いて、出力ドキュメントが生成されていることを確認します。 このファイルには、BizTalk Adapter for TIBCO Enterprise Message Service によって処理されたクエリの結果が含まれている必要があります。  

  ドキュメント インスタンスが正常に処理された場合、次の一連のイベントが発生します。  

1.  TIBCO EMS アダプターが TIBCO システムからメッセージを取得し、BizTalk メッセージとしてメッセージ ボックスに公開します。  

2.  オーケストレーションがこの公開されたメッセージをサブスクライブします。これにより、BizTalk メッセージング エンジンがオーケストレーションのインスタンスをアクティブ化し、オーケストレーション インスタンスにメッセージを送信できるようにします。  

3.  オーケストレーション インスタンスがメッセージ ボックスにメッセージを返します。  

4.  ファイル送信ポートがこのメッセージをサブスクライブし、BizTalk がメッセージをファイル アダプターに送信します。  

5.  ファイル アダプターが、結果セットを含むメッセージを指定の出力フォルダーに書き込みます。  

## <a name="see-also"></a>参照  
 [チュートリアル: BizTalk Adapter for TIBCO Enterprise Message Service を使用してデータを送信するには](../core/tutorial-use-tibco-enterprise-message-service-adapter-in-biztalk-to-send-data.md)   
 [チュートリアル: TIBCO Enterprise Message Service 用の Microsoft BizTalk Adapter の使用](../core/tutorials-use-the-microsoft-biztalk-adapter-for-tibco-message-service.md)   
 [作業の開始](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)
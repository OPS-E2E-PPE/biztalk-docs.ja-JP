---
title: 'チュートリアル: を使用して、TIBCO Rendezvous アダプター送信 |Microsoft ドキュメント'
description: BizTalk Server で TIBCO Rendezvous の BizTalk アダプターを使用して TIBCO システムにデータを送信するステップ バイ ステップ ガイド
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b761ce2d-3465-43e0-bd8d-4d68b523226a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a08987e92465358276df7936f39cfa7c449c0503
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014441"
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-send-data"></a>チュートリアル: BizTalk Adapter for TIBCO Rendezvous を使用したデータの送信
BizTalk Adapter for TIBCO Rendezvous を使用して TIBCO システムにデータを送信できます。 このチュートリアルでは、これを示す SDK サンプルについて説明します。  
  
## <a name="prerequisites"></a>前提条件  
  
-   このサンプルをビルドして展開するには、アダプターが実行されている [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールしてください。  
  
-   サンプルでは、メッセージ コンテキストのプロパティを含んでいる Microsoft.BizTalk.Adapters.TibRV.Properties.dll という DLL を使用します。 ソリューションからこのライブラリへの参照を更新する必要がある場合があります。 詳細については、次を参照してください。 [BizTalk Server のメッセージ コンテキスト プロパティ (送信ハンドラー)](../core/biztalk-server-message-context-properties-send-handlers.md)です。  
  
## <a name="about-the-sample"></a>サンプルについて 

- このサンプルでは、ファイル フォルダーから XML ファイルを取得し、そのファイルをオーケストレーションに送信し、BizTalk Adapter for TIBCO Rendezvous を使用して TIBCO システム内にレコードを作成します。  
  
- このサンプルは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] でデザインされたもので、BizTalk Adapter for TIBCO Rendezvous を BizTalk オーケストレーションと共に使用する場合の基本的な機能を示します。  
  
- サンプルの既定の場所は`C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWaySend`、次のファイルが含まれています。 
    
    |**ランタイム プロジェクト ファイル名**|**ランタイム プロジェクト ファイルの説明**|  
    |---|---|  
    |OneWaySend.btproj<br /><br /> OneWaySend.sln|アプリケーションのプロジェクトおよびソリューション ファイル。|  
    |Schema.xsd<br /><br /> PropertySchema.xsd|アプリケーションのスキーマおよびプロパティ スキーマ ファイル。|  
    |Orchestration.odx|アプリケーションが使用するオーケストレーション。|  
    |TIBCORendezvousOneWaySend.snk|厳密な名前のキー ファイル。|  
  
## <a name="step-1-add-the-adapter-to-biztalk-administration"></a>手順 1: アダプターを BizTalk 管理コンソールに追加します。
  
1.  **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**プラットフォームの設定**、順にクリック**アダプター**です。  
  
3.  右クリック**アダプター**を指す**新規**、**アダプターしています.** 表示する、**アダプター プロパティ**ダイアログ。  
  
4.  値を入力して、**名前**フィールドです。 たとえば、入力**TIBCO Rendezvous**です。  
  
5.  選択**TIBCO(r) Rendezvous(r)** で利用可能なアダプターの一覧から、**アダプター**ドロップダウン リスト をクリック**OK**です。  
  
## <a name="step-2-create-a-send-port"></a>手順 2: 送信ポートを作成します。  
  
1.  **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、 をクリック**送信ポート**です。  
  
2.  右クリック**送信ポート**を指す**新規**、**静的な一方向送信ポートしています.** 表示する、**送信ポートのプロパティ**ダイアログ。  
  
3.  値を入力して、**名前**フィールド、たとえば**TIBCORndOneWaySP**です。  
  
4.  使用可能なアダプターの一覧から TIBCO Rendezvous アダプターを選択して、**型**ドロップダウン リスト ボックスし、をクリックして、**構成**アダプターを表示するにはボタン**トランスポートのプロパティ**  ダイアログ ボックス。  
  
    > [!NOTE]
    >  この値は、TIBCO Enterprise Message System アダプターで作成したときに指定された名前、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
5.  値を入力して、**証明された送信者プロパティ**:  
  
    |**プロパティ**|**値**|  
    |------------------|---------------|  
    |台帳ファイル名|永続的な認証されたメッセージ配信に使用する台帳ファイル名。|  
    |再利用可能な名前|認証されたメッセージ配信に使用する再利用可能な送信者名です。 この名前は、ネットワーク上のすべての認証されたメッセージの送信者名の中で一意である必要があります。|  
  
6.  値を入力して、**資格情報**:  
  
    |**プロパティ**|**値**|  
    |------------------|---------------|  
    |Password|TIBCO Rendezvous サーバーのパスワード。|  
    |ユーザー名|TIBCO Rendezvous サーバーのユーザー名。|  
  
7.  値を入力して、 **RendezvousTransport**:  
  
    |**プロパティ**|**値**|  
    |------------------|---------------|  
    |デーモン|Rendezvous トランスポート デーモン パラメーター。|  
    |ネットワーク|Rendezvous トランスポート ネットワーク パラメーター。|  
    |サービス|Rendezvous トランスポート サービス パラメーター。|  
  
     プロパティの詳細については、次を参照してください。[送信成果物が作成](../core/creating-tibco-rendezvous-send-handlers.md)です。  
  
8.  **[OK]** をクリックします。  
  
9. 選択、 **XML Transmit**パイプラインで使用可能なパイプラインの一覧から、**送信パイプライン**ドロップダウン リスト をクリック**OK**です。  
  
10. 送信ポートを右クリックし、をクリックして**開始**を参加させて、送信ポートを開始します。  
  
## <a name="step-3-create-a-receive-port"></a>手順 3: 受信ポートを作成します。  
  
1.  **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、 をクリック**受信ポート**です。  
  
2.  受信ポート フォルダーを右クリックし、をクリックして**新規**、**一方向の受信ポートしています.** 受信ポートのプロパティ ダイアログを表示します。  
  
3.  値を入力、**名前**フィールド、たとえば**TIBCORndOneWayFileRP**、 をクリック**OK**です。  
  
## <a name="step-4-create-a-receive-location"></a>手順 4: 受信場所を作成します。  
  
1.  監視対象のファイル受信場所となるフォルダー (たとえば C:\Filesource) を作成します。  
  
2.  右クリックし、新しい受信ポートをクリックし、**新規**、**受信場所の追加.** 表示する、**受信場所のプロパティ**ダイアログ。  
  
3.  値を入力して、**名前**フィールド、たとえば**TIBCORndOneWayFileRL**です。  
  
4.  選択**ファイル**で使用可能なアダプターの一覧から、**型**ドロップダウン リスト ボックスし、をクリックして、**構成**アダプターを表示するにはボタン**トランスポートプロパティ** ダイアログ ボックス。  
  
5.  用に作成したフォルダーの場所を入力、**受信フォルダー**プロパティをクリック**OK**です。  
  
6.  選択 **[xmlreceive]** で使用可能なパイプラインの一覧から、**受信パイプライン**ドロップダウン リスト ボックスし、をクリックして**OK**です。  
  
7.  受信場所を右クリックし、をクリックして**を有効にする**です。  
  
## <a name="step-5-generate-a-document-instance-from-the-schema"></a>手順 5: スキーマからドキュメント インスタンスを生成します。  
  
1.  Visual Studio で、ソリューション エクスプ ローラーで、Schema.xsd を右クリックし、をクリックして**プロパティ**です。  
  
2.  プロパティ ウィンドウでクリックして選択、**出力インスタンス ファイル名**オプションで 、**全般**セクションです。  
  
3.  表示するには、省略記号ボタン (...) をクリックして、 **出力ファイルの**ダイアログ。  
  
4.  たとえば、フォルダーと出力ファイル インスタンスの名前を指定**C:\instance.xml**  をクリック**保存**です。  
  
    > [!NOTE]
    >  ファイル受信場所に指定したフォルダーの場所は、ここに指定しないでください。  
  
5.  ソリューション エクスプ ローラーで、Schema.xsd を右クリックし、をクリックして**インスタンスの生成**を指定した場所にドキュメント インスタンスを生成します。  
  
## <a name="step-6-update-the-generated-document-instance"></a>手順 6: 生成されたドキュメント インスタンスを更新します。  
  
1.  テキスト エディター (メモ帳 works) で生成されたドキュメント インスタンスを開き、データが TIBCO システムに一意なレコードを生成することを確認するドキュメント インスタンスの内容を編集します。 たとえば、次のコードは、データ ファイルの最初の部分を示しています。  
  
    ```  
    <ns0:Root xmlns:ns0="http://TibcoRendezvousOneWaySend.TibcoRendezvousOneWaySendSchema">  
        <Name>Punya Palit</Name>  
        <MailAddress>Prose Ware, Inc.</MailAddress>  
    </ns0:Root>  
    ```  
  
2.  変更したドキュメント インスタンスを保存します。  
  
## <a name="step-7-build-and-deploy-the-project"></a>手順 7: ビルドし、プロジェクトの配置  
  
1.  右クリックし、 **OneWaySend**ソリューション エクスプ ローラーでプロジェクトを**プロパティ**プロジェクトのプロジェクト デザイナーを起動します。  
  
2.  クリックして、**展開**タブです。  
  
3.  適切な値を入力、**サーバー**プロパティおよび**構成データベース**プロパティの  **BizTalk グループ**です。  
  
4.  ソリューション エクスプ ローラーで OneWaySend プロジェクトを右クリックし、をクリックして**展開**プロジェクトをビルドしてアセンブリを展開する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成データベース。  
  
## <a name="step-8-bind-enlist-and-start-the-orchestration"></a>手順 8: バインド、参加、およびオーケストレーションの開始  
  
1.  **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、 をクリック**オーケストレーション**です。  
  
2.  をクリックして、**更新**MMC ツールバーまたはキーを押してボタン、 **f5 キーを押して**を更新するキーボードのキー、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールの表示。  
  
3.  表示するオーケストレーションをダブルクリック、**オーケストレーションのプロパティ**ダイアログ。  
  
4.  をクリックして**バインド**オーケストレーションのバインド オプションを表示するダイアログ ボックスの左ペインでします。  
  
5.  バインド オプションに適切な値を指定します。次に例を示します。  
  
    |**パラメーター**|**値**|  
    |-------------------|---------------|  
    |Host|BizTalkServerApplication|  
    |FileReceivePort|TIBCORndOneWayFileRP|  
    |TibcoRendezvousSend|TIBCORndOneWaySP|  
  
6.  [OK] をクリックします。  
  
7. オーケストレーションを右クリックし、をクリックして**開始**を参加させて、オーケストレーションを開始します。  
  
## <a name="step-9-drop-a-document-and-check-the-tibco-system"></a>手順 9: は、ドキュメントを削除し、TIBCO システム チェック
  
-   先ほど作成したドキュメント インスタンスを、アプリケーションが監視するファイル受信フォルダーにコピーします。  
  
-   TIBCO Web インターフェイスを使用して、XML ファイルのデータからレコードが作成されたことを確認します。  
  

ドキュメント インスタンスが正常に処理された場合、次の一連のイベントが発生します。  
  
1.  ファイル アダプターがフォルダーからファイルを取得し、メッセージボックスに BizTalk メッセージとして公開します。  
  
2.  この公開されたメッセージをオーケストレーションがサブスクライブします。その結果、BizTalk メッセージング エンジンによってオーケストレーションのインスタンスがアクティブ化され、メッセージがオーケストレーション インスタンスに送信されます。  
  
3.  オーケストレーション インスタンスがオーケストレーションで指定されたロジックを使用してメッセージを処理し、メッセージ ボックスにメッセージを返します。  
  
4.  この公開されたメッセージを TIBCO 送信ポートがサブスクライブします。その結果、BizTalk メッセージング エンジンによってこのメッセージが TIBCO 送信ポートに送信されます。  
  
5.  送信ポートがメッセージを BizTalk Adapter for TIBCO Rendezvous に渡します。  
  
6.  BizTalk Adapter for TIBCO Rendezvous がメッセージを TIBCO システムに送信します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル: BizTalk Adapter for TIBCO Rendezvous を使用してデータを受信するには](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-receive-data.md)   
 [チュートリアル: Microsoft BizTalk Adapter を使用して TIBCO Rendezvous の](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md)   
 [作業の開始](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)
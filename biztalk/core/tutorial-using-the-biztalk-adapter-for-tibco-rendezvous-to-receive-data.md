---
title: チュートリアル:TIBCO Rendezvous アダプターを使用して受信 |Microsoft Docs
description: BizTalk Server で TIBCO Rendezvous の BizTalk アダプタを使用して TIBCO システムからデータを受信するステップ バイ ステップ ガイド
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58e7a739-701d-4085-a840-54f81c55e943
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce3d1e3737b56fc8a943d1fdee849a3eb2de5c6a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393827"
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-receive-data"></a>チュートリアル:BizTalk Adapter for TIBCO Rendezvous を使用してデータを受信するには
BizTalk Adapter for TIBCO Rendezvous を使用して TIBCO システムからデータを受信できます。 このチュートリアルでは、これを示す SDK サンプルについて説明します。  

## <a name="prerequisites"></a>前提条件  

このサンプルをビルドして展開するには、アダプターが実行されている [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールしてください。  

## <a name="about-the-sample"></a>サンプルについて 
- このサンプルでは、BizTalk Adapter for TIBCO Rendezvous を使用して TIBCO システムからデータを受信します。 オーケストレーションがメッセージを処理し、ファイル アダプターを使用して、指定されたフォルダーにデータを XML ファイルとして書き込みます。  

- このサンプルは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] でデザインされ、BizTalk Adapter for TIBCO Enterprise Message Service を BizTalk オーケストレーションと組み合わせて使用する基本的な機能を紹介する目的で作成されました。  

    > [!NOTE]
    >  このサンプルでは、処理するアプリケーション用の TIBCO からメッセージを送信する方法を理解していることを前提としています。  

- サンプルの既定の場所は`C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWayReceive`、次のファイルが含まれています。 

    |**ランタイム プロジェクト ファイル名**|**ランタイム プロジェクト ファイルの説明**|  
    |---|---|  
    |OneWayReceive.btproj、<br /><br /> OneWayReceive.sln|アプリケーションのプロジェクトおよびソリューション ファイル。|  
    |PureMessage.xsd|アプリケーションのスキーマ ファイルです。|  
    |TIBCORvOWR.odx|アプリケーションが使用するオーケストレーション。|  
    |TIBCORv.snk|厳密な名前のキー ファイル。|  


## <a name="step-1-add-the-adapter-to-biztalk-administration"></a>手順 1:アダプターを BizTalk 管理コンソールに追加します。

1.  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**、 をクリックし、**アダプター**します。  

3.  右クリックして**アダプター**  をポイント**新規**、**アダプター.** 表示する、**アダプター プロパティ**ダイアログ。  

4.  値を入力、**名前**フィールドに、たとえば**TIBCO Rendezvous**します。  

5.  選択**TIBCO(r) Rendezvous(r)** で利用可能なアダプターの一覧から、**アダプター**ドロップダウンをクリック **[ok]**。  

## <a name="step-2-create-a-receive-port"></a>手順 2:作成、受信ポート  

1.  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、 をクリック**受信ポート**します。  

2.  受信ポート フォルダーを右クリックし、をクリックし、**新規**、**一方向の受信ポート.** を表示する、**受信ポートのプロパティ**ダイアログ。  

3.  値を入力、**名前**フィールドに**TIBCORvOneWayRP**、 をクリック**OK**します。  

## <a name="step-3-create-a-receive-location"></a>手順 3:作成、受信場所  

1. 右クリックし、新しい受信ポート をクリックし、**新規**、**受信場所.** 表示する、**受信場所のプロパティ**ダイアログ。  

2. 値を入力、**名前**フィールド。 たとえば、入力**TIBCORvOneWayRL**します。  

3. 使用可能なアダプターの一覧から TIBCO Rendezvous アダプターを選択、**型**ドロップダウン ボックス、をクリックし、**構成**アダプターを表示するボタン**トランスポートのプロパティ**  ダイアログ ボックス。  

   > [!NOTE]
   >  この値は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで TIBCO アダプターを作成したときに指定した名前です。  

4. 値を入力、 **RendezvousSubjectName**下、 **AdapterRequiredProperties**します。  

5. 値を入力、**証明されたリスナーのプロパティ**:  


   |   **プロパティ**   |                                                                         **[値]**                                                                          |
   |------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | 台帳ファイル名 |                                             永続的な認証されたメッセージ配信に使用する台帳ファイル名。                                             |
   |  再利用可能な名前   | 認証されたメッセージ配信に使用する再利用可能な送信者名です。 この名前は、ネットワーク上のすべての認証されたメッセージの送信者名の中で一意である必要があります。 |


6. 値を入力、**資格情報**:  


   | **プロパティ** |                   **[値]**                    |
   |--------------|------------------------------------------------|
   |   パスワード   | TIBCO Rendezvous サーバーのパスワード。  |
   |  [ユーザー名]   | TIBCO Rendezvous サーバーのユーザー名。 |


7. 値を入力、 **RendezvousTransport**:  

   |**プロパティ**|**[値]**|  
   |------------------|---------------|  
   |デーモン|Rendezvous トランスポート デーモン パラメーター。|  
   |ネットワーク|Rendezvous トランスポート ネットワーク パラメーター。|  
   |サービス|Rendezvous トランスポート サービス パラメーター。|  

    プロパティの詳細については、次を参照してください。[成果物の作成が表示される](../core/creating-tibco-rendezvous-receive-handlers.md)します。  

8. **[OK]** をクリックします。  

9. 選択**XMLReceive**で使用可能なパイプラインの一覧から、**受信パイプライン**ドロップダウン ボックスし、をクリックして**OK**。  

10. 受信場所を右クリックし、をクリックして**を有効にする**します。  

## <a name="step-4-create-a-one-way-send-port"></a>手順 4:一方向の送信ポートを作成します。  

1. 送信ポートが使用する送信先フォルダー (たとえば、C:\FilesOut) を作成します。  

2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、] をクリック**送信ポート**します。  

3. 右クリックして**送信ポート** をポイント**新規**、**静的な一方向送信ポートしています.** 表示する、**送信ポートのプロパティ**ダイアログ。  

4. 値を入力、**名前**フィールドに、たとえば**TIBCORvOneWayFileSP**します。  

5. 選択**ファイル**で使用可能なアダプターの一覧から、**型**ドロップダウン ボックス、をクリックし、**構成**アダプターを表示するボタン**トランスポートプロパティ** ダイアログ ボックス。  

6. **先フォルダー**プロパティは、先ほど作成したフォルダーの場所を入力しをクリックして**OK**します。  

7. 選択、 **XMLTransmit**で利用可能なパイプラインの一覧から、**送信パイプライン**ドロップダウン をクリック**ok**します。  

8. 送信ポートを右クリックし、をクリックして**開始**を参加させて、送信ポートを開始します。  

## <a name="step-5-build-and-deploy-the-project"></a>手順 5:プロジェクトのビルドと展開  

1. ソリューション エクスプ ローラーで OneWayReceive プロジェクトを右クリックし、をクリックして**プロパティ**をプロジェクトのプロジェクト デザイナーを起動します。  

2. をクリックして、**展開**タブ。  

3. 適切な値を入力、 **Server**プロパティおよび**構成データベース**のプロパティの  **BizTalk グループ**カテゴリ。  

4. ソリューション エクスプ ローラーで OneWayReceive プロジェクトを右クリックし、をクリックして**デプロイ**プロジェクトをビルドしてアセンブリを展開する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成データベース。  

## <a name="step-6-bind-enlist-and-start-the-orchestration"></a>手順 6:バインド、参加、およびオーケストレーションを開始します  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[ **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、] をクリック**オーケストレーション**します。  

2. をクリックして、**更新**ボタン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール ツールバーまたはキーを押して、 **F5**を更新するキーボードのキー、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール ビュー。  

3. 表示するオーケストレーションをダブルクリックして、**オーケストレーションのプロパティ**ダイアログ。  

4. クリックして**バインド**オーケストレーションのバインド オプションを表示するダイアログ ボックスの左側のウィンドウでします。  

5. バインド オプションに適切な値を指定します。次に例を示します。  


   | **パラメーター** |        **[値]**         |
   |---------------|--------------------------|
   |     ホスト      | BizTalkServerApplication |
   |   SendPort    |   TIBCORvOneWayFileSP    |
   |  ReceivePort  |     TIBCORvOneWayRP      |


6. **[OK]** をクリックします。  

7. オーケストレーションを右クリックし、をクリックして**開始**を参加させて、オーケストレーションを開始します。  

## <a name="step-7-confirm-the-application-receives-a-message"></a>手順 7:アプリケーション メッセージを受信することを確認します。  

- File 送信ポートに送信し、出力ドキュメントが生成されたことを確認します。 構成されているフォルダーを開きます。  

  ドキュメント インスタンスが正常に処理された場合、次の一連のイベントが発生します。  

1.  TIBCO Rendezvous アダプターが TIBCO システムからメッセージを取得し、BizTalk メッセージとしてメッセージ ボックスに公開します。  

2.  オーケストレーションがこの公開されたメッセージをサブスクライブします。これにより、BizTalk メッセージング エンジンがオーケストレーションのインスタンスをアクティブ化し、オーケストレーション インスタンスにメッセージを送信できるようにします。  

3.  オーケストレーション インスタンスがメッセージ ボックスにメッセージを返します。  

4.  ファイル送信ポートがこのメッセージをサブスクライブし、BizTalk がメッセージをファイル アダプターに送信します。  

5.  ファイル アダプターが、結果セットを含むメッセージを指定の出力フォルダーに書き込みます。  

## <a name="see-also"></a>参照  
 [チュートリアル: BizTalk Adapter for TIBCO Rendezvous を使用してデータを送信するには](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-send-data.md)   
 [チュートリアル:TIBCO Rendezvous の Microsoft BizTalk Adapter の使用](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md)   
 [作業の開始](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)
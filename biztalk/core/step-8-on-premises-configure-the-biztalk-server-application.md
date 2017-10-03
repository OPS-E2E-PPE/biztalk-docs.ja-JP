---
title: "手順 8 (オンプレミス): BizTalk Server アプリケーションの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 2015-12-08
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5109fb54-8453-444f-bc9c-070a65053397
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47332edbf974b7e45d3ab65644f28d9d2bd6a623
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-8-on-premises-configure-the-biztalk-server-application"></a>手順 8 (オンプレミス): BizTalk Server アプリケーションを構成します。
前のステップでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションを作成しました。 このステップでは、アプリケーションをビルドし、展開し、構成します。  
  
## <a name="build-and-deploy-the-application"></a>アプリのビルドと配置  
  
1.  Visual Studio で、ソリューション エクスプ ローラーでソリューション名を右クリックし、をクリックして**ビルド**です。  
  
2.  展開プロセスでは、アセンブリが厳密に署名されている必要があります。  アセンブリに署名を行うには、厳密な名前のアセンブリ キー ファイルをプロジェクトに関連付ける必要があります。  
  
    1.  ソリューション エクスプ ローラーで右クリックし、 **OrderProcessingDemo**プロジェクトをクリックして**プロパティ**です。  
  
    2.  クリックして、**署名**タブをクリックし、選択、**アセンブリに署名**チェック ボックスをオンします。  
  
    3.  ドロップダウン リストから、**厳密な名前キー ファイルを選択して**ボックスで、 **\<新規作成 ...> >**です。  
  
    4.  **厳密な名前キーの作成** ダイアログ ボックスで、たとえば、キー ファイルの名前を入力`OrderProcessingDemo.snk`です。 パスワードでキー ファイルを保護するためのチェック ボックスをオフにし、をクリックして**OK**です。  
  
3.  クリックして、**展開** タブで、ボックスの右側に**アプリケーション名**、型`OrderProcessingDemo`です。  
  
4.  ボックスの右側にドロップダウン リストから**再展開** **True**です。  
  
5.  ソリューション エクスプ ローラーで右クリック**OrderProcessingDemo**、クリックして**展開**です。  出力ウィンドウが表示されます。  
  
    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ========== Deploy: 1 succeeded, 0 failed, 0 skipped ==========  
  
    ```  
  
## <a name="configure-the-application"></a>アプリケーションの構成  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]** 、順にクリック[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]です。  
  
2.  コンソール ツリーで、左側のウィンドウで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を右クリックして**BizTalk グループ**、クリックして**更新**です。  
  
3.  展開**BizTalk グループ**、展開**アプリケーション**、展開**OrderProcessingDemo**、順にクリック**オーケストレーション**です。 \Outputfromtestproviderdebugmode.txt、 **OrderProcessingDemo.OrderProcessing**オーケストレーションを展開します。  
  
4.  論理ポートを作成して、オーケストレーションで (**ReceiveSO**)、Service Bus キューからメッセージを受信します。 ここでは、この論理ポートにマップする物理受信ポートを作成します。  
  
    1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **OrderProcessingDemo**  ノードを右クリックして**受信ポート**、 をポイント**新規**をクリックして**一方向受信ポート**です。  
  
    2.  **[全般]** タブで、次の操作を行います。  
  
        |プロパティ|目的|  
        |--------------|----------------|  
        |**名前**|型**ReceiveSO**です。|  
        |**失敗したメッセージのルーティングを有効にします。**|(選択解除)|  
  
    3.  をクリックして**受信場所**、クリックして**新規**です。  
  
    4.  [Receive Location1 - 受信場所のプロパティ] ダイアログ ボックスで、次の操作を行います。  
  
        |プロパティ|目的|  
        |--------------|----------------|  
        |**名前**|型**ReceiveOrders_SO**です。|  
        |**型**|選択**Sb-messaging**です。|  
        |**受信ハンドラー**|[ **BizTalkServerApplication**] を選択します。|  
        |**受信パイプライン**|選択**XMLReceive**です。|  
  
    5.  をクリックして**構成**です。  
  
    6.  Sb-messaging トランスポートのプロパティ ダイアログ ボックスからの**全般** タブの**キューまたはサブスクリプション URL**、入力**sb://mynamespace.servicebus.appfabriclabs.com/queueordersedi**. ここでは、 *mynamespace*は、Service Bus 名前空間と*queueordersedi*で作成した Service Bus キューは、[手順 3 (Azure の): Service Bus キューの作成](../core/step-3-for-azure-create-a-service-bus-queue.md)です。  
  
    7.  Sb-messaging トランスポートのプロパティ ダイアログ ボックスからの**認証** タブで、次の値を指定します。  
  
        |プロパティ|目的|  
        |--------------|----------------|  
        |**アクセス制御サービス STS Uri**|「`https://mynamespace-sb.accesscontrol.appfabriclabs.com/`」と入力します。|  
        |**発行者名**|発行者名を指定します。 通常これに設定されている`owner`です。|  
        |**発行者キー**|発行者キーを指定します。|  
  
        > [!NOTE]
        >  名前とキーをキューの URL、ACS の URL、発行者の値を取得できます、 [Windows Azure CTP 管理ポータル](http://go.microsoft.com/fwlink/p/?LinkId=202886)です。  
  
    8.  をクリックして**OK**すべてのダイアログ ボックスを終了するまでです。  
  
5.  論理ポートを作成して、オーケストレーションで (**SendToSQL**) メッセージを送信する、 **SalesOrder**データベース テーブルです。 ここでは、この論理ポートにマップする物理送信ポートを作成します。  
  
    1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **OrderProcessingDemo**  ノードを右クリックして**送信ポート**、 をポイント**新規**をクリックして**静的な一方向送信ポート**です。  
  
    2.  [全般] タブには、次の操作を行います。  
  
        |プロパティ|目的|  
        |--------------|----------------|  
        |**名前**|型**SendToSQL**です。|  
        |**型**|選択**WCF-SQL**です。|  
        |**送信ハンドラー**|選択**BizTAlkServerApplication**です。|  
        |**送信パイプライン**|選択**PassThruTransmit**です。|  
  
    3.  をクリックして**構成**です。  
  
    4.  WCF-SQL トランスポートのプロパティ で、**全般** タブで、次の操作します。  
  
        |プロパティ|目的|  
        |--------------|----------------|  
        |**アドレス (URI)**|型**//computername/database_instance_name/databasename**です。 たとえばに接続するため、 **DemoDB**既定のデータベース インスタンスで実行されているローカル コンピューター上のデータベースを入力`mssql://.//DemoDB`<br /><br /> 詳細については、次を参照してください。 [SQL Server の接続 URI を作成する](../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。|  
        |**操作**|型**TableOp/挿入/dbo/SalesOrder**です。|  
  
    5.  [WCF-SQL トランスポートのプロパティ] で、**資格情報**] タブで [**シングル サインオンを使用しない**で指定したデータベースの SQL Server への接続に資格情報 (大文字小文字を区別) を指定し、接続文字列です。 Windows 認証を使用して接続する場合は、資格情報を空白のままにします。  
  
    6.  をクリックして**OK**すべてのダイアログ ボックスを終了するまでです。  
  
6.  論理ポートを作成して、オーケストレーションで (**SendToFile**) 共有ファイルの場所にメッセージを送信します。 ここでは、この論理ポートにマップする物理送信ポートを作成します。  
  
    1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **OrderProcessingDemo**  ノードを右クリックして**送信ポート**、 をポイント**新規**をクリックして**静的な一方向送信ポート**です。  
  
    2.  [全般] タブには、次の操作を行います。  
  
        |プロパティ|目的|  
        |--------------|----------------|  
        |**名前**|型**SendToFile**です。|  
        |**型**|選択**ファイル**です。|  
        |**送信ハンドラー**|選択**BizTAlkServerApplication**です。|  
        |**送信パイプライン**|選択**XML Transmit**です。|  
  
    3.  をクリックして**構成**です。  
  
    4.  [FILE トランスポートのプロパティ] で、次の操作を行います。  
  
        |プロパティ|目的|  
        |--------------|----------------|  
        |**受信フォルダー**|メッセージの送信先を指定します。|  
        |**ファイル名**|保持**%MessageID%.xml**です。|  
  
    5.  をクリックして**OK**すべてのダイアログ ボックスを終了するまでです。  
  
7.  次に、物理ポートと論理ポートを組み合わせてアプリケーションを構成する必要があります。  
  
    1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックして**OrderProcessingDemo**、クリックして**構成**です。  
  
    2.  アプリケーションの構成、左側のウィンドウでクリックして**OrderProcessing**です。  
  
    3.  次の表の値を使用してアプリケーションを構成します。  
  
        |プロパティ|目的|  
        |--------------|----------------|  
        |**ホスト**|選択**BizTalkServerApplication**|  
        |論理ポート**ReceiveSO**|物理ポートを選択して**ReceiveSO**|  
        |論理ポート**SendToSQL**|物理ポートを選択して**SendToSQL**|  
        |論理ポート**SendToFile**|物理ポートを選択して**SendToFile**|  
  
    4.  をクリックして**OK**構成を保存します。  
  
## <a name="start-the-application"></a>アプリケーションを開始します。  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックして**OrderProcessingDemo**、クリックして**開始**です。  
  
2.  ダイアログ ボックスで、をクリックして**開始**です。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 4: BizTalk Server 2013 を使用するハイブリッド アプリケーションを作成します。](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)
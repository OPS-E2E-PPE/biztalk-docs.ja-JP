---
title: "サイズの大きいメッセージを MSMQ に |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, examples
- examples, MSMQ adapters
ms.assetid: 1fb87b46-5656-42c0-be99-8ab66e51bb4d
caps.latest.revision: "35"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e6a3fda3082260338bd387dfe84fe48c7aed565
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="large-message-to-msmq"></a>MSMQ にサイズの大きいメッセージ
MSMQ のサンプル サイズの大きいメッセージは、.xml ドキュメント 4 メガバイト (MB) よりも大きいメッセージ キュー (MSMQ とも呼ばれます) から BizTalk MSMQ アダプターを使用して送信する方法を示します、 **MQSendLargeMessage** API によって実装されていませんMQRTLarge.dll です。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルの動作は次のとおりです。  
  
1.  ユーザーが SendLargeMessage.exe を使用して、サイズの大きい .xml ファイルをローカル コンピューター上のキューに送信します。  
  
2.  [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] はサイズの大きい .xml ファイルをキューから受信し、ローカル ディレクトリにコピーします。  
  
 メッセージ キューの多くの操作は非同期です。 多くは、MSMQ API 呼び出し (たとえば、 **MQSendLargeMessage**)、要求された操作が完全に完了する前に、呼び出し元に戻ります。  
  
 MSMQ には、操作完了後にアプリケーションにフィードバックを配信するメカニズムが用意されています。 このメカニズムでは、"管理キュー" を使用します。 MSMQ は管理キューにメッセージ形式でフィードバックを返します。 MSMQ がフィードバックを返す管理キューは、元の MSMQ API 呼び出しが行われたときに指定されます。 したがって、たとえばを使用してメッセージを送信するときに、 **MQSendLargeMessage** API アプリケーションを指定できます管理キューの名前を使用して、 **PROPID_M_ADMIN_QUEUE**メッセージのメッセージのプロパティ呼び出しで渡される**MQSendLargeMessage**です。 アプリケーションは、成功した場合のリターン コードを取得する可能性がある場合でも、 **MQSendLargeMessage**呼び出し、メッセージ送信操作に、後で失敗した場合、MSMQ メッセージを書き込みますそれを指定の管理キューにします。  
  
 メッセージが消失し、診断がキャプチャされませんで送信エラーの結果、アプリケーションでは、管理キューを指定しない場合、実際には、メッセージは証拠も残らない表示されなくなります。 MSMQ にはこの現象が発生するエラー状況が多数あります。たとえば、トランザクション キューにトランザクション以外の送信が行われる場合などです。  
  
 このサンプルのコンテキストでは、コードが呼び出しでは、トランザクションの種類を指定することが重要**MQSendLargeMessage**メッセージが送信キューの指定されたトランザクションのサポートと一貫性があるようにします。 この処理が行われない場合や、(このサンプルのように) 管理キューが指定されていない場合、MSMQ は何の通知もなく送信メッセージを破棄します (つまり、アプリケーションにエラー コードが返されたり、イベント ログに診断が書き込まれたりすることはありません)。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 \<サンプル パス > \AdaptersUsage\MSMQLarge  
  
> [!NOTE]
>  64 ビット バージョンの Windows を使用する場合と[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]、サンプルにインストールされる、 **C:\Program Files (x86) \Microsoft BizTalk Server\<バージョン > \SDK\Samples\AdaptersUsage\MSMQLarge**フォルダーです。  使用してこのドキュメントでその他の手順については、この変更に注意してください、 **C:\Program Files**フォルダーです。  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|**ファイル**|**Description**|  
|--------------|---------------------|  
|**MQRTLarge.dll**|ネイティブのメッセージ キュー用のアドオンを提供します。 公開、 **MQSendLargeMessage**と**MQReceiveLargeMessage** Api です。<br /><br /> 64 ビット版の MQRTLarge.dll にアクセスするために、64 ビット版の Windows に [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] をインストールする必要があります。<br /><br /> [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] を使用しない MSMQ ソリューションでは、MQRTLarge.dll が依然として正常に機能する場合があります。 ただし、これはマイクロソフトがサポートする推奨構成でなく、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 環境の外部で使用した場合は予期せぬ結果が生じることがあります。|  
|||  
|**Largemessages.sln という**|サンプルで使用する SendLargeMessage 実行可能ファイルを作成するための [!INCLUDE[vs2010](../includes/vs2010-md.md)] ソリューションを提供します。|  
|**XMLCreator.sln**|XMLCreator 実行可能ファイルを作成して SDK サンプルのテスト用 .xml ファイルを生成するための [!INCLUDE[vs2010](../includes/vs2010-md.md)] ソリューションを提供します。|  
  
## <a name="configuring-biztalk-server-and-creating-the-msmq-queue"></a>BizTalk Server の構成と MSMQ キューの作成  
 [!INCLUDE[vs2010](../includes/vs2010-md.md)]、Microsoft メッセージ キュー、および [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] がインストールされていることを確認します。  
  
#### <a name="to-configure-biztalk-server"></a>BizTalk Server を構成するには  
  
1.  [!INCLUDE[vs2010](../includes/vs2010-md.md)]を開き、 **C:\Program files \microsoft BizTalk Server\<バージョン > \SDK\Samples\AdaptersUsage\MSMQLarge\LargeMessages.sln**ソリューション ファイルです。  サンプルをビルドします。  
  
2.  作成、 **C:\Demo**ディレクトリ場所[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]MSMQ からのメッセージを配置します。  
  
3.  開く、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
4.  サンプルでメッセージを書き込む送信ポートを作成します。  
  
    -   展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**を右クリックして**送信ポート**をクリックして**新規**、クリックして**静的な一方向送信ポート**です。  
  
5.  **静的な一方向送信ポート プロパティ** ダイアログ ボックスで、ポートの名前を設定**MySendPort**です。  
  
6.  トランスポートの種類を設定**ファイル**です。  
  
7.  クリックして、**構成**を開く ボタン、 **File トランスポートのプロパティ**フォーム。 入力**C:\Demo**で**コピー先フォルダー**です。 ホスト インスタンス ID で C:\Demo フォルダーにアクセスできることを確認します。  
  
8.  いることを確認**ファイル名**に設定されている**%MessageID%.xml**です。 **[OK]**をクリックします。  
  
9. **[フィルター]**をクリックします。  
  
    1.  設定**プロパティ**に**BTS です。ReceivePortName**です。  
  
    2.  設定**演算子**に **=**です。  
  
    3.  設定**値**に**MyReceivePort**です。  
  
    4.  **[OK]**をクリックします。  
  
10. MSMQ からのメッセージを受け付ける受信ポートを作成します。  
  
    1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックして**受信ポート**です。  
  
    2.  をクリックして**新規**、クリックして**一方向の受信ポート**です。  
  
11. **受信ポートのプロパティ** ダイアログ ボックスで、ポートの名前を設定**MyReceivePort**、順にクリック**OK**です。  
  
12. サンプル用の受信ポートを作成したら、受信場所を作成します。  
  
    1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックして**受信場所**です。  
  
    2.  をクリックして**新規**、クリックして**一方向の受信場所**です。  
  
    3.  受信場所の名前を設定**MSMQReceiveLocation**です。  
  
    4.  **受信ポートの選択**ダイアログ ボックスで、 **MyReceivePort**です。  
  
    5.  **受信場所のプロパティ**ダイアログ ボックスで、セット**トランスポートの種類**に**MSMQ**です。  
  
    6.  **アドレス (URI)**セクションで、**構成**を開くには、 **MSMQ トランスポートのプロパティ**フォーム。 設定**キュー**に**localhost \private$ \test**です。  
  
    7.  設定**トランザクション**に`True`、順にクリック**OK**です。  
  
13. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、使用できるポートと受信場所を作成する必要があります。  
  
    1.  右クリック**MySendPort**、クリックして**Enlist**です。  
  
    2.  右クリック**MySendPort**、クリックして**開始**です。  
  
    3.  右クリック**MSMQReceiveLocation**、クリックして**を有効にする**です。  
  
#### <a name="to-create-the-msmq-queue-in-windows-server-2008-r2-or-windows-server-2008-sp2"></a>Windows Server 2008 R2 または Windows Server 2008 SP2 で MSMQ キューを作成するには  
  
1.  をクリックして**開始**を右クリックして**コンピューター**、順にクリック**管理**です。  
  
2.  展開して、**機能**ノード。  
  
3.  展開して、**メッセージ キュー**ノード。  
  
4.  右クリックし、**専用キュー**ノード、をクリックして**新規**、順にクリック**プライベート キュー**です。  
  
5.  **キュー名**、入力**テスト**です。 いることを確認、**トランザクション** チェック ボックスをオンします。  
  
6.  **[OK]**をクリックします。  
  
#### <a name="to-create-the-msmq-queue-in-windows-7-or-windows-vista-sp2"></a>Windows 7 または Windows Vista SP2 で MSMQ キューを作成するには  
  
1.  をクリックして**開始**を右クリックして**コンピューター**、順にクリック**管理**です。  
  
2.  展開**サービスとアプリケーション**の順に展開し、**メッセージ キュー**ノード。  
  
    > [!NOTE]
    >  場合**メッセージ キュー**がコンピューターにインストールされていないに移動して**コントロール パネル] > プログラム > プログラムと機能**、し、[ **Windows の機能のオンまたはオフ**です。 下のすべての機能を確認して**Microsoft メッセージ キュー (MSMQ) Server**、順にクリック**[ok]**です。  
  
3.  右クリックし、**専用キュー**ノード、をクリックして**新規**、順にクリック**プライベート キュー**です。  
  
4.  **キュー名**、入力**テスト**です。 いることを確認、**トランザクション** チェック ボックスをオンします。  
  
5.  **[OK]**をクリックします。  
  
## <a name="creating-a-test-file-and-running-the-sample"></a>テスト ファイルの作成とサンプルの実行  
  
#### <a name="to-create-a-large-test-file"></a>サイズの大きいテスト ファイルを作成するには  
  
1.  [!INCLUDE[vs2010](../includes/vs2010-md.md)]、ソリューションを開いて**C:\Program files \microsoft BizTalk Server\<バージョン > \SDK\Samples\AdaptersUsage\MSMQLarge\XMLCreator\XMLCreator.sln**です。  
  
2.  プロジェクトをビルドおよび実行します。  
  
3.  **XML 本文**、型**これは、テスト メッセージ**です。  
  
4.  **XML 本文をコピーする時期の #**、型`250000`です。  
  
5.  **XML ファイルの場所**、型`C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeFile.xml`です。  
  
6.  をクリックして**XML の作成**、順にクリック**OK**です。  
  
#### <a name="to-run-the-sample"></a>サンプルを実行するには  
  
1.  コマンド プロンプトを開き、ディレクトリに移動**C:\Program files \microsoft BizTalk Server\<バージョン > \SDK\Samples\AdaptersUsage\MSMQLarge\SendLargeMessage\bin\debug**です。  
  
2.  コマンド プロンプトで実行して**SendLargeMessage.exe**です。 SendLargeMessage 実行可能ファイルでは 2 つの変数を使用します。1 つ目の変数は MSMQ キューの場所を示し、2 つ目の変数は送信する .xml ファイルの場所を示します。  
  
    ```  
    DIRECT=OS:localhost\private$\Test  "C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeFile.xml"  
    ```  
  
3.  同じサイズのファイルが作成されたことを確認してください、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]内のコンピューター、 **C:\Demo**ディレクトリ。 これが MySendPort 送信ポートで識別されたディレクトリです。  
  
## <a name="comments"></a>コメント  
 SendLargeMessage.exe 参照、 **LargeMessages** API で、さらに、BizTalk メッセージ キュー大きいメッセージ用拡張機能 (MQRTLarge.dll) API を参照します。 メッセージ キューのサイズの大きいメッセージ用拡張機能 API はネイティブのメッセージ キュー用のアドオンで、ネイティブのメッセージ キューでは処理できない、4 MB の制限を超えるメッセージを処理できます。  
  
 このサンプルでは、 **MQSendLargeMessage** API API を公開、.NET framework を使用して、 **LargeMessages** API です。  
  
## <a name="see-also"></a>参照  
 [BizTalk メッセージ キューの大きいメッセージ用拡張機能](../core/biztalk-message-queuing-large-message-extension.md)   
 [アダプタ サンプル – 使用状況](../core/adapter-samples-usage.md)
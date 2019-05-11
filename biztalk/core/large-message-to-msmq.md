---
title: サイズの大きいメッセージを MSMQ に |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1fb87b46-5656-42c0-be99-8ab66e51bb4d
caps.latest.revision: 35
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d92428426b7032de36ab63cfd2be286ce3c67569
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329819"
---
# <a name="large-message-to-msmq"></a>MSMQ にサイズの大きいメッセージ
MSMQ のサンプル サイズの大きいメッセージが .xml ドキュメント 4 メガバイト (MB) よりも大きいメッセージ キュー (MSMQ とも呼ばれます) から BizTalk MSMQ アダプターを使用して送信する方法を示します、 **MQSendLargeMessage**によって実装される APIMQRTLarge.dll します。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルはように動作します。  
  
1. ユーザーは、サイズの大きい .xml ファイルをローカル コンピューター上のキューに送信するのに SendLargeMessage.exe を使用します。  
  
2. BizTalk Server では、キューからサイズの大きい .xml ファイルを受信し、ローカル ディレクトリにコピーします。  
  
   メッセージ キューの多くの操作は非同期です。 多くは、MSMQ API 呼び出し (たとえば、 **MQSendLargeMessage**)、要求された操作が完全に完了する前に、呼び出し元に戻ります。  
  
   MSMQ では、操作が完了した後、アプリケーションにフィードバックを配信するためのメカニズムを提供します。 このメカニズムでは、「管理キュー」の使用 MSMQ 管理キューにメッセージの形式でフィードバックを返します。 MSMQ がフィードバックを返す管理キューは、元の MSMQ API 呼び出しが行われたときに指定します。 そのため、たとえばを使用してメッセージを送信するときに、 **MQSendLargeMessage** API、アプリケーションを指定できます管理キューの名前を使用して、 **PROPID_M_ADMIN_QUEUE**メッセージのメッセージのプロパティ呼び出しで渡される**MQSendLargeMessage**します。 アプリケーションの成功を示すリターン コードが取得場合でも、 **MQSendLargeMessage**呼び出し、メッセージの送信操作後で失敗した場合、MSMQ メッセージを書き込みますそれに対応する指定の管理キューにします。  
  
   送信エラーによりメッセージが消失と診断がキャプチャされません、アプリケーションが管理キューを指定しない場合、実際には、メッセージは証拠も残らない表示されなくなります。 さまざまな MSMQ でのエラー状況可能性があります、この例では、トランザクション キューにトランザクション以外の送信を行います。  
  
   このサンプルのコンテキストでは、コードが呼び出しでトランザクションの種類を指定することが重要**MQSendLargeMessage**は、メッセージの送信先キューに指定されたトランザクションのサポートと一貫性があるようにします。 これを行わないし、管理キューが指定されていない場合 (このサンプルの場合と同様)、し、MSMQ 送信はメッセージを破棄することが示されない場合 (つまり、エラー コードが返さ、アプリケーションでは、診断がイベント ログに書き込まれたりするには、など)。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 \<パスのサンプル\>\AdaptersUsage\MSMQLarge  
  
> [!NOTE]
>  サンプルにインストールする場合は、Windows と BizTalk Server の 64 ビット バージョンを使用して、 **C:\Program Files (x86) \Microsoft BizTalk Server\<バージョン\>\SDK\Samples\AdaptersUsage\MSMQLarge**フォルダー。  使用してこのドキュメントでその他の手順については、この変更に注意してください、 **C:\Program Files**フォルダー。  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|**[最近使ったファイル]**|**[説明]**|  
|--------------|---------------------|  
|**MQRTLarge.dll**|ネイティブのメッセージ キューのアドオンを提供します。 公開、 **MQSendLargeMessage**と**MQReceiveLargeMessage** Api。<br /><br /> BizTalk Server は、64 ビット版の MQRTLarge.dll にアクセスするために Windows の 64 ビット バージョンをインストールする必要があります。<br /><br /> BizTalk Server なしの MSMQ ソリューションでは、可能性があります、まだ、MQRTLarge.dll から正常に機能します。 ただし、これは Microsoft がサポートしている推奨構成ではありませんし、BizTalk Server 環境の外部で使用されている場合に、予期しない結果が発生する可能性があります。|  
|||  
|**LargeMessages.sln**|このサンプルで使用される SendLargeMessage 実行可能ファイルを作成する Visual Studio ソリューションを提供します。|  
|**XMLCreator.sln**|XMLCreator の SDK サンプルのテストの .xml ファイルを生成する実行可能ファイルを作成する Visual Studio ソリューションを提供します。|  
  
## <a name="configure-biztalk-and-create-the-msmq-queue"></a>BizTalk の構成し、MSMQ キューを作成  
 Visual Studio、Microsoft メッセージ キュー、および BizTalk Server がインストールされていることを確認します。  
  
#### <a name="to-configure-biztalk-server"></a>BizTalk Server を構成するには  
  
1. Visual Studio で開く、 **C:\Program files \microsoft BizTalk Server\<バージョン\>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeMessages.sln**ソリューション ファイル。  サンプルをビルドします。  
  
2. 作成、 **C:\Demo**ディレクトリが BizTalk Server が MSMQ からのメッセージを配置する場所。  
  
3. 開く、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
4. メッセージを書き込む、サンプルの送信ポートを作成します。  
  
   -   展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、右クリック**送信ポート**をクリックします **。新規**、 をクリックし、**静的な一方向送信ポート**します。  
  
5. **静的な一方向送信ポート プロパティ** ダイアログ ボックスで、ポートの名前、設定**MySendPort**します。  
  
6. トランスポートの種類を設定**ファイル**します。  
  
7. をクリックして、**構成**ボタンをクリックする、 **File トランスポートのプロパティ**フォーム。 入力**C:\Demo**で**先フォルダー**します。 ホスト インスタンスの id に C:\Demo フォルダーにアクセスしてください。  
  
8. いることを確認**ファイル名**に設定されている **%MessageID%.xml**します。 **[OK]** をクリックします。  
  
9. **[フィルター]** をクリックします。  
  
    1.  設定**プロパティ**に**BTS します。ReceivePortName**します。  
  
    2.  設定**演算子**に **=** します。  
  
    3.  設定**値**に**MyReceivePort**します。  
  
    4.  **[OK]** をクリックします。  
  
10. MSMQ からのメッセージをそのまま使用する受信ポートを作成します。  
  
    1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックして**受信ポート**します。  
  
    2. クリックして**新規**、 をクリックし、**一方向の受信ポート**します。  
  
11. **受信ポートのプロパティ** ダイアログ ボックスで、ポートの名前、設定**MyReceivePort**、順にクリックします**OK**します。  
  
12. サンプル用の受信ポートを作成した後は、受信場所を作成する必要があります。  
  
    1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックして**受信場所**します。  
  
    2. クリックして**新規**、 をクリックし、**一方向の受信場所**します。  
  
    3. 受信場所の名前を設定**MSMQReceiveLocation**します。  
  
    4. **受信ポートの選択**ダイアログ ボックスで、 **MyReceivePort**します。  
  
    5. **受信場所のプロパティ**ダイアログ ボックスで、セット**トランスポートの種類**に**MSMQ**します。  
  
    6. **アドレス (URI)** セクションで、**構成**を開く、 **MSMQ トランスポートのプロパティ**フォーム。 設定**キュー**に**localhost \private$ \test**します。  
  
    7. 設定**トランザクション**に`True`、順にクリックします**OK**します。  
  
13. ポートを作成し、受信場所を通じて使用できる必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
    1.  右クリックして**MySendPort**、 をクリックし、**参加**します。  
  
    2.  右クリック**MySendPort**、 をクリックし、**開始**します。  
  
    3.  右クリックして**MSMQReceiveLocation**、 をクリックし、**を有効にする**します。  
  
#### <a name="to-create-the-msmq-queue-in-windows-server"></a>Windows Server の MSMQ キューを作成するには
  
1.  クリックして**開始**を右クリックして**コンピューター**、順にクリックします**管理**します。  
  
2.  展開、**機能**ノード。  
  
3.  展開、**メッセージ キュー**ノード。  
  
4.  右クリックし、**専用キュー**ノード、をクリックして**新規**、順にクリックします**プライベート キュー**します。  
  
5.  **キュー名**、入力**テスト**します。 いることを確認、**トランザクション** チェック ボックスをオンします。  
  
6.  **[OK]** をクリックします。  
  
#### <a name="to-create-the-msmq-queue-in-windows"></a>Windows で MSMQ キューを作成するには 
  
1.  クリックして**開始**を右クリックして**コンピューター**、順にクリックします**管理**します。  
  
2.  展開**サービスとアプリケーション**の順に展開し、**メッセージ キュー**ノード。  
  
    > [!NOTE]
    >  場合**メッセージ キュー** 、コンピューターにインストールされていないに移動して**コントロール パネル > プログラム > プログラムと機能**、し、**オンまたはオフにする Windows 機能**します。 すべての機能を確認**Microsoft メッセージ キュー (MSMQ) Server**、順にクリックします**OK**。  
  
3.  右クリックし、**専用キュー**ノード、をクリックして**新規**、順にクリックします**プライベート キュー**します。  
  
4.  **キュー名**、入力**テスト**します。 いることを確認、**トランザクション** チェック ボックスをオンします。  
  
5.  **[OK]** をクリックします。  
  
## <a name="creating-a-test-file-and-running-the-sample"></a>テスト ファイルを作成し、サンプルを実行します。  
  
#### <a name="to-create-a-large-test-file"></a>大規模なテスト ファイルを作成するには  
  
1.  Visual Studio でソリューションを開いて**C:\Program files \microsoft BizTalk Server\<バージョン\>\SDK\Samples\AdaptersUsage\MSMQLarge\XMLCreator\XMLCreator.sln**します。  
  
2.  プロジェクトをビルドして実行します。  
  
3.  **XML 本文**、型**これはテスト メッセージ**します。  
  
4.  **XML 本文をコピーする回数**、型`250000`します。  
  
5.  **XML ファイルの場所**、型`C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeFile.xml`します。  
  
6.  クリックして**XML の作成**、順にクリックします**OK**します。  
  
#### <a name="to-run-the-sample"></a>サンプルを実行するには  
  
1.  コマンド プロンプトを開き、ディレクトリに移動**C:\Program files \microsoft BizTalk Server\<バージョン\>\SDK\Samples\AdaptersUsage\MSMQLarge\SendLargeMessage\bin\debug**します。  
  
2.  コマンド プロンプトで次のように実行します。 **SendLargeMessage.exe**します。 SendLargeMessage 実行可能ファイルは、2 つの変数を受け入れる — 1 つは、MSMQ キューの場所と、2 つ目は、送信する .xml ファイルの場所。  
  
    ```  
    DIRECT=OS:localhost\private$\Test  "C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeFile.xml"  
    ```  
  
3.  BizTalk Server コンピューターで同じサイズのファイルが作成されたことを確認、 **C:\Demo**ディレクトリ。 これは、MySendPort 送信ポートで識別されたディレクトリです。  
  
## <a name="comments"></a>コメント  
 SendLargeMessage.exe 参照、 **LargeMessages** API で、さらに、BizTalk メッセージ キュー大きいメッセージ用拡張機能 (MQRTLarge.dll) API を参照します。 メッセージ キュー大きなメッセージ拡張機能 API では、ネイティブのメッセージをキュー用のアドオンがネイティブのメッセージ キューの 4 MB の制限を超えるメッセージの処理を実現できます。  
  
 このサンプルでは、 **MQSendLargeMessage** API と公開 API を .NET Framework を使用して、 **LargeMessages** API。  
  
## <a name="see-also"></a>参照  
 [BizTalk メッセージ キューの大きいメッセージ用拡張機能](../core/biztalk-message-queuing-large-message-extension.md)   
 [アダプタ サンプル – 使用法](../core/adapter-samples-usage.md)
---
title: "BizTalk Server を使用して SQL の特定のタスクを完了する通知メッセージを処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8538cb89-1cca-45ad-b6f4-041e117963ff
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efed30f3e65c4f58a060f67539672c95b3d6df59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk-server"></a>BizTalk Server を使用して SQL の特定のタスクを完了する通知メッセージの処理
使用することができます、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server データベース テーブルへの変更の通知を受信します。 ただし、アダプターのみ通知を送信することレコードの一部挿入、更新されると、またはされた特定のデータベース テーブルで削除します。 後処理これらのレコードには、クライアント アプリケーション自体で処理される必要があります。 このトピックでは、SQL Server データベースから受信した通知の種類に基づいてテーブル内のレコードを処理する方法のシナリオ ベースの説明を示します。  
  
## <a name="scenarios-for-performing-subsequent-actions-after-receiving-notification"></a>通知を受信した後の後続のアクションを実行するためのシナリオ  
 次に、いくつかのシナリオのアダプターのクライアントが特定の通知後タスクを実行する必要があります。  
  
-   **シナリオ 1**です。 アダプターのクライアントが SQL Server から受信する通知の種類に基づいて、特定のタスクを実行する必要があります、シナリオを検討してください。 たとえば、クライアント アプリケーションは、"B"のテーブルにレコードを挿入される場合、"A"テーブル内のレコードを更新する必要があります。 同様に、クライアント アプリケーションする必要がありますレコードを削除テーブル"A"から"B"のテーブルからレコードが削除された場合。  
  
     受信されると、通知メッセージはこのシナリオでアダプターのクライアントが、挿入操作または削除操作の通知がされたかどうかを決定する通知の種類を抽出する必要があります。 通知の種類を確認した後、アダプター クライアントは、挿入または関連するテーブルを更新する後続の操作を実行する必要があります。  
  
-   **シナリオ 2**です。 テーブルへの変更の通知メッセージを受信する受信場所がダウン シナリオを検討してください。 受信場所の停止中に、一部のレコードがテーブルに追加されます。 ただし、これらのレコードのアダプター クライアントは任意の通知を受け取るされません。 受信場所は、バックアップと、アダプターを特定のメッセージを送信することによってクライアントに通知し、クライアント アプリケーションは、受信場所がダウンしたときに、データベース テーブルに挿入されたすべてのレコードの注意する必要があります。  
  
     受信した通知メッセージはこのシナリオでアダプターのクライアントが、通知は、データベース テーブルへの変更や、受信場所を開始するためかどうかに関する情報を抽出する必要があります。 通知が受信場所を開始するためにある場合は、アダプターのクライアントは可能性がありますが挿入、更新、または削除された受信場所がダウンしたときにレコードを処理するためのロジックを実装する必要があります。  
  
> [!NOTE]
>  これらは、いくつかのシナリオ例で、通知機能を使用する方法の理解を深めるに記載されている、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 ただし、受信した通知の種類を抽出するために必要なタスクの基本的な設定は、すべてのシナリオと同様となります。 このトピックでは、通知メッセージからの通知の種類を抽出する方法について説明します。  
  
## <a name="how-this-topic-demonstrates-receiving-notification-messages-and-extracting-notification-type"></a>どのように、このトピックではメッセージを受信通知および通知の種類の抽出を示しています  
 このトピックでは、後続のタスクを実行する通知メッセージを処理する方法を示すおシナリオを考えます基本的なアダプター クライアントが、従業員テーブルに対する変更の通知メッセージを受信する BizTalk アプリケーションを使用します。 通知を受信した後、クライアントは、受信した通知の種類をフィルター処理し、後続のアクションを実行します。 非常に基本的なシナリオを示すためには、アダプターのクライアントが受信する通知の種類に基づいた別のフォルダーへの通知メッセージをコピーするをお知らせを検討します。 だから：  
  
-   通知メッセージを挿入または更新操作の場合は、アダプターのクライアントは、メッセージを C:\TestLocation\UpsertNotification フォルダーにコピーします。  
  
-   通知メッセージが他の操作の場合は、たとえばを削除、アダプターのクライアントがメッセージを C:\TestLocation\OtherNotificaiton フォルダーにコピーします。  
  
 これを実現する BizTalk アプリケーションの一部として、オーケストレーションは、次に含める必要があります。  
  
-   一方向の受信ポートを通知メッセージを受信します。  
  
-   受信した通知メッセージの種類に関する情報を抽出する xpath クエリを含む式図形です。  
  
-   オーケストレーションに判断ブロックを含めるの判断図形。 この判断ブロックでは、アプリケーションは、何を実行する後続の操作に基づいて受信した通知メッセージを決定します。  
  
-   2 つの一方向の送信を最後に、通知メッセージを受信するポート。  
  
## <a name="configuring-notifications-with-the-sql-adapter-binding-properties"></a>SQL アダプターのプロパティのバインドと通知の構成  
 次の表、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バインドのプロパティ構成の SQL Server から通知を受信するために使用します。 受信ポートを構成するときにこれらのバインディング プロパティを指定する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
> [!NOTE]
>  スキーマを生成するときに、これらのバインディング プロパティを指定することもできます、**通知**操作、必須ではない場合でもです。 これを行うと、ポートのバインド ファイル、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成され、メタデータの生成の一部では、バインドのプロパティを指定する値も含まれます。 このバインド ファイルを後でインポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロパティは既に設定されています。 バインドで wcf-custom または WCF SQL を作成する管理コンソールの受信ポート。 詳細については、バインド ファイルを使用するポートを作成する、次を参照してください。 [SQL アダプターを使用するポートのバインド ファイルを使用する物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)です。  
  
|プロパティのバインド|Description|  
|----------------------|-----------------|  
|**InboundOperationType**|受信操作を実行することを指定します。 通知メッセージを受信するには、これを設定**通知**です。|  
|**NotificationStatement**|SQL ステートメントを指定します (選択または EXEC\<ストアド プロシージャ >) のクエリ通知を登録するために使用します。 アダプターは、指定された SQL ステートメントの変更の結果セットの場合にのみ、SQL Server から通知メッセージを取得します。|  
|**NotifyOnListenerStart**|リスナーが開始されたときに、アダプターがアダプターのクライアントに通知を送信するかどうかを指定します。|  
  
 これらのプロパティの詳細については、次を参照してください。 [BizTalk Adapter for SQL Server アダプターのバインドのプロパティについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。 使用する方法の詳細については、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]さらに通知を受信する SQL Server から、読み取る。  
  
## <a name="how-to-receive-notification-messages-from-the-sql-server-database"></a>SQL Server データベースから通知メッセージを受信する方法  
 SQL Server データベースを使用して、操作を実行[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明する手順のタスクでは、 [SQL アダプターと BizTalk アプリケーションを開発する基盤](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)です。 これらのタスクは通知メッセージを受信アダプターを構成するのには。  
  
1.  BizTalk プロジェクトを作成しのスキーマを生成、**通知**操作を受信します。 必要に応じての値を指定することができます、 **InboundOperationType**と**NotificationStatement**プロパティをバインドします。  
  
2.  SQL Server データベースから通知を受信するための BizTalk プロジェクトでメッセージを作成します。  
  
3.  前のセクションで説明したように、オーケストレーションを作成します。  
  
4.  構築し、BizTalk プロジェクトを展開します。  
  
5.  BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。  
  
    > [!NOTE]
    >  通知メッセージを受信するように、受信操作の一方向の WCF カスタムのみを構成する必要があります。 または WCF SQL 受信ポート。 双方向の WCF カスタムまたは WCF SQL 受信ポートの受信操作はサポートされていません。  
  
6.  BizTalk アプリケーションを起動します。  
  
 このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 スキーマを生成する必要があります、**通知**操作を受信します。 参照してください[SQL アダプターを使用して Visual Studio での SQL Server 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)スキーマを生成する方法についての詳細。 スキーマを生成するときに、次のタスクを実行します。 デザイン時のバインドのプロパティを指定しない場合は、最初の手順をスキップします。  
  
1.  値を指定**InboundOperationType**と**NotificationStatement**スキーマの生成中にプロパティをバインドします。 このバインドのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。 バインドのプロパティを指定する方法については、次を参照してください。 [SQL アダプターのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)です。  
  
2.  コントラクトの種類を選択して**サービス (入力方向の操作)**です。  
  
3.  スキーマを生成、**通知**操作します。  
  
## <a name="defining-messages-and-message-types"></a>メッセージとメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに対して必要な「種類」がについて説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 スキーマが生成されるは、BizTalk プロジェクトのオーケストレーションの種類からのメッセージをリンクする必要があります。  
  
 このトピックでは、通知を受信する SQL Server データベースから 1 つのメッセージを作成する必要があります。  
  
 メッセージを作成し、それらのスキーマにリンクするには、次の手順を実行します。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  オーケストレーションを BizTalk プロジェクトに追加します。 ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックし、**追加**、クリックして**新しい項目の**します。 BizTalk オーケストレーションの名前を入力し、クリックして**追加**です。  
  
2.  まだ開いていない場合は、BizTalk プロジェクトのオーケストレーション ビュー ウィンドウを開きます。 をクリックして**ビュー**、 をポイント**その他のウィンドウ**、順にクリック**オーケストレーション ビュー**です。  
  
3.  **オーケストレーション ビュー**を右クリックして**メッセージ**、クリックして**新しいメッセージ**です。  
  
4.  新しく作成されたメッセージを右クリックし [**プロパティ] ウィンドウ**します。  
  
5.  **プロパティ**ウィンドウ**Message_1**を次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`NotifyReceive`.|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**を選択して*Process_Notification.Notification*ここで、 *Process_Notification* BizTalk プロジェクトの名前を指定します。 *通知*に対して生成されたスキーマは、**通知**操作します。|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションを設定します。  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の SQL Server データベースから通知メッセージを受信し、受信した通知の種類に基づいて、タスクを実行します。 このオーケストレーションでの指定した SELECT ステートメントに基づく通知メッセージを受信、 **NotificationStatement**プロパティをバインドします。 式図形内で指定された xpath クエリと、変数に通知の種類を抽出**NotificationType**です。 判断図形は、この変数に値を使用して、受信した通知の種類を決定し、後続の操作を実行する適切な"path"を受け取りします。 前述の前のセクションで、オーケストレーションは受信した通知メッセージの種類に基づいて、次の操作を実行します。  
  
-   通知メッセージを挿入または更新操作の場合は、アダプターのクライアントは、メッセージを C:\TestLocation\UpsertNotification フォルダーにコピーします。  
  
-   通知メッセージが他の操作の場合は、たとえばを削除、アダプターのクライアントがメッセージを C:\TestLocation\OtherNotificaiton フォルダーにコピーします。  
  
 そのため、オーケストレーションは、次が必要があります。  
  
-   一方向の受信ポートを通知メッセージを受信します。  
  
-   受信した通知の種類を抽出する xpath クエリを含む式図形です。  
  
-   オーケストレーションに判断ブロックを含めるの判断図形。 この判断ブロックでは、アプリケーションは、何を実行する後続の操作に基づいて受信した通知メッセージを決定します。  
  
-   2 つの一方向の送信を最後に、通知メッセージを受信するポート。  
  
-   図形が表示されます。  
  
 サンプル オーケストレーションには、次のようになります。  
  
 ![Post & #45 を実行するオーケストレーション以外の通知タスク](../../adapters-and-accelerators/adapter-sql/media/20f62716-603d-4293-84f7-8c8f6d82ccd0.gif "20f62716-603d-4293-84f7-8c8f6d82ccd0")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認してください。 図形 列に表示名は、単に記載されているオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveNotification|Receive|-設定**名前**に*ReceiveNotification*<br /><br /> -設定**アクティブ**に*は True。*|  
  
### <a name="adding-an-expression-shape"></a>式図形を追加します。  
 オーケストレーションの式図形をなどの目的は、受信した通知メッセージの種類を抽出する xpath クエリにです。 Xpath クエリを作成する前に、通知メッセージの形式について見てみましょう。 一般的な通知メッセージには、次のようになります。  
  
```  
<Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
  <Info>Insert</Info>   
  <Source>Data</Source>   
  <Type>Change</Type>   
</Notification>  
```  
  
 通知の種類に関する情報は内で使用できる表示のように、`<info>`親内のタグ`<Notification>`タグ。 一部として、この式図形の操作を行います。  
  
-   内の値を格納する変数を作成、`<Info>`タグ、およびその型 System.String に設定します。 変数の作成の詳細については、次を参照してください。[オーケストレーションで変数を使用して](../../core/using-variables-in-orchestrations.md)です。
  
     このトピックの名前を変数として**NotificationType**です。  
  
-   値を抽出する xpath クエリを作成、\<情報 > タグです。 Xpath クエリは、次のようになります。  
  
    ```  
    NotificationType = xpath(NotifyReceive,"string(/*[local-name()='Notification']/*[local-name()='Info']/text())");  
    ```  
  
     この xpath クエリで**NotifyReceive**通知メッセージの受信用に作成したメッセージです。 内の抜粋、`string`関数は、クエリが内の値を抽出する必要がありますを示す、`<Info>`内では、さらに、タグ、`<Notification>`タグ。 クエリによって抽出された値が最後に、割り当てられた、 **NotificaitonType**変数。  
  
### <a name="adding-a-decide-shape"></a>判断図形を追加します。  
 判断図形の追加の目的を実行する後続の操作が受信した通知メッセージの種類ベースを決定するオーケストレーションに判断ブロックを含めるです。 値に基づいて決定されます、 **NotificationType**変数。 このトピックでは、オーケストレーションは、受信した通知メッセージの種類に基づいて決定を行います。 そのため、ルール図形での条件はよう指定します。  
  
```  
NotificationType.Equals("Insert") | NotificationType.Equals("Update")  
```  
  
 この条件の値をする場合に提案**NotificaitonType**変数が挿入または更新プログラムをオーケストレーションが一連の 1 つのタスクを実行します。 場合の値**NotificationType**変数は何でも、オーケストレーションはその他の一連のタスクを実行します。  
  
 ように、前のセクションで、単純なアプローチを示すために、オーケストレーションはメッセージにコピー通知メッセージの種類に基づいた別のフォルダー。 規則内で、Else ブロックでは、別のポートにメッセージを送信する送信図形を追加する必要があります。 このトピックでは、名前とルール ブロックに送信図形**SendUpsertNotification**と Else ブロックに送信図形と**SendOtherNotification**です。  
  
### <a name="adding-ports"></a>ポートの追加  
 オーケストレーションに、次の論理ポートを追加する必要があります。  
  
-   一方向受信ポートを SQL Server から通知メッセージを受信します。  
  
-   特定のフォルダーに Insert および Update 操作用の通知メッセージを送信する一方向の送信ポート。  
  
-   特定のフォルダーに、他の操作の通知メッセージを送信する一方向の送信ポート。  
  
 論理ポートごとに、次のプロパティを指定することを確認してください。 ポート列に表示される名前は、オーケストレーションで表示されているポートの名前です。  
  
|ポート|[プロパティ]|  
|----------|----------------|  
|SQLNotifyPort|-設定**識別子**に*SQLNotifyPort*<br /><br /> -設定**型**に*SQLNotifyPortType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*受信*|  
|NotificationUpsertPort|-設定**識別子**に*NotificationUpsertPort*<br /><br /> -設定**型**に*NotificationUpsertPortType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*送信*|  
|OtherNotificationPort|-設定**識別子**に*OtherNotificationPort*<br /><br /> -設定**型**に*OtherNotificationPortType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*送信*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表は、プロパティとアクション図形のメッセージを指定して、メッセージ、ポートにリンクを設定する必要があります、値を指定します。 図形 列に表示名は、既に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveNotification|-設定**メッセージ**に*NotifyReceive*<br /><br /> -設定**操作**に*SQLNotifyPort.Notify.Request*|  
|SendUpsertNotification|-設定**メッセージ**に*NotifyReceive*<br /><br /> -設定**操作**に*NotificationUpsertPort.Upsert.Request*|  
|SendOtherNotification|-設定**メッセージ**に*選択*<br /><br /> -設定**操作**に*OtherNotificationPort.Other.Request*|  
  
 これらのプロパティを指定した後、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 今すぐ BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 以前に作成したオーケストレーションが下に表示、BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 チュートリアルについては、次を参照してください。[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)です。  
  
 アプリケーションの構成が含まれます。  
  
-   アプリケーションのホストを選択します。  
  
-   BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  
  
    -   物理 Wcf-custom を定義するか、WCF SQL 一方向の受信ポートです。 このポートは、SQL Server データベースからの通知をリッスンします。 ポートを作成する方法については、次を参照してください。 [SQL アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)です。 受信ポートのバインドのプロパティを指定することを確認してください。  
  
        > [!IMPORTANT]
        >  デザイン時のバインドのプロパティを指定した場合、この手順を実行する必要はありません。 このような場合は、WCF カスタムを作成または WCF SQL 受信ポート、必要なバインド プロパティを設定、によって作成されたバインド ファイルをインポートすることによって、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 詳細については、次を参照してください。 [SQL アダプターを使用するポートのバインド ファイルを使用する物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)です。  
  
        |プロパティのバインド|値|  
        |----------------------|-----------|  
        |**InboundOperationType**|これを設定して**通知**です。|  
        |**NotificationStatement**|これを設定します。<br /><br /> `SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0`<br /><br /> **注:**する必要があります具体的には、列名を指定、ステートメントで次の SELECT ステートメントで示すようにします。 また、スキーマ名と共に、テーブル名を必ず指定する必要があります。 たとえば、 `dbo.Employee`のようにします。|  
        |**NotifyOnListenerStart**|これを設定して**True**です。|  
  
         異なるバインディングのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。  
  
        > [!NOTE]
        >  使用して受信操作の実行中に、トランザクション分離レベルとトランザクションのタイムアウトを構成することをお勧め、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 サービスを追加することで、Wcf-custom または WCF SQL の構成中に動作の受信ポートを行うことができます。 サービスの動作を追加する方法については、次を参照してください。[トランザクション分離レベルの構成と SQL を使用したトランザクションのタイムアウト](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)です。  
  
    -   ハード ディスクと、対応する file ポートを BizTalk オーケストレーションが Insert および Update 操作用の SQL Server データベースから通知メッセージをドロップ場所に場所を定義します。 C:\TestLocation\UpsertNotification フォルダーへの通知メッセージを削除するには、このポートを構成します。  
  
    -   ハード ディスクと、対応する file ポートを BizTalk オーケストレーションがその他のすべての操作用の SQL Server データベースから通知メッセージをドロップ場所に場所を定義します。 C:\TestLocation\OtherNotification フォルダーへの通知メッセージを削除するには、このポートを構成します。  
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 SQL Server データベースから通知メッセージを受信して、Select および Update の後続の操作を実行するために、BizTalk アプリケーションを開始する必要があります。 BizTalk アプリケーションの起動方法の詳細については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)です。
  
 この段階で確認します。  
  
-   Wcf-custom または WCF SQL 一方向の受信ポートで、データベースが実行されている SQL Server から通知メッセージを受信します。  
  
-   SQL Server からメッセージを受信、2 つファイル送信ポートを実行しています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 BizTalk オーケストレーションを開始した後、次の一連のアクションが行われます。  
  
-   **NotifyOnListenerStart**に設定されているプロパティのバインド**True**、次のメッセージが表示されます。  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>  
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>ListenerStarted</Info>   
      <Source>SqlBinding</Source>   
      <Type>Startup</Type>   
    </Notification>  
    ```  
  
     なおの値、`<Info>`タグは、"ListnerStarted"です。 そのため、このメッセージは、C:\TestLocation\OtherNotification フォルダーに受信されます。  
  
-   Employee テーブルにレコードを挿入します。 次のような通知メッセージが表示されます。  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Insert</Info>   
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     なおの値、`<Info>`タグは、"Insert"です。 そのため、このメッセージは、C:\TestLocation\UpsertNotification フォルダーに受信されます。  
  
-   Employee テーブルのレコードを更新します。 次のような通知メッセージが表示されます。  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>  
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Update</Info>   
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     なおの値、`<Info>`タグは、「更新」です。 そのため、このメッセージは、C:\TestLocation\UpsertNotification フォルダーに受信されます。  
  
-   Employee テーブルからレコードを削除します。 次のような通知メッセージが表示されます。  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>  
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Delete</Info>   
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     なおの値、`<Info>`タグが"Delete"。 そのため、このメッセージは、C:\TestLocation\OtherNotification フォルダーに受信されます。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。 バインド ファイルを生成したできるように、送信ポートを作成し、同じオーケストレーション用のポートを受信する必要はありません、ファイルから構成設定をインポートすることができます。 バインド ファイルの詳細については、次を参照してください。[アダプターのバインドを再利用](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)です。
  
## <a name="performing-complex-operations-after-receiving-notification-messages"></a>通知メッセージを受信した後、複雑な操作を実行します。  
 わかりやすくするためより深く理解するは、このトピックで、オーケストレーションは、通知の種類に基づいて異なるフォルダーにメッセージをコピーします。 ただし、実際のシナリオより複雑な操作を実行する必要があります。 このトピックとする操作を実行するためにビルドに示されている同じような手順を実行できます。 たとえば、Employee テーブルに対して挿入操作の通知メッセージを取得する場合は、別のテーブルにレコードを挿入するオーケストレーションを変更することができます。 このような場合は、判断図形内で適切に変更することができます。  
  
 このようなシナリオの 1 つで詳しく説明しています[チュートリアル 2: 従業員の発注プロセスには、SQL アダプターを使用して](../../adapters-and-accelerators/adapter-sql/tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を使用して SQL クエリ通知を受信します。](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)
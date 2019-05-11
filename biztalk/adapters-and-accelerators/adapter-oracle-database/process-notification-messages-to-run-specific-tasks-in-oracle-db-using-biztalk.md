---
title: BizTalk Server を使用して Oracle データベースで特定のタスクを完了する通知メッセージを処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 376055a7-98a6-4055-b6cd-2f5971349a6a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e65c45ed3e4ee2914be89b2ee56d233ab2e58128
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376236"
---
# <a name="process-notification-messages-to-complete-specific-tasks-in-oracle-database-using-biztalk-server"></a>BizTalk Server を使用して Oracle データベースで特定のタスクを完了する通知メッセージの処理
使用することができます、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースのテーブルへの変更の通知を受信します。 ただし、アダプターのみ通知を送信するレコードの一部の電源が挿入されていること、更新、または特定のデータベース テーブルで削除されたことです。 これらのレコードに、後続の処理は、クライアント アプリケーション自体によって処理する必要があります。 このトピックでは、Oracle データベースから受信した通知の種類に基づいて、テーブル内のレコードを処理する方法のシナリオ ベースの説明を示します。  
  
## <a name="scenarios-for-performing-subsequent-actions-after-receiving-notification"></a>通知を受信した後、後続のアクションを実行するためのシナリオ  
 次に、いくつかのシナリオのアダプターのクライアントが特定の通知後タスクを実行する必要があります。  
  
-   **シナリオ 1。** アダプターのクライアントが Oracle データベースから受信した通知の種類に基づいて特定のタスクを実行する必要がありますシナリオを検討してください。 たとえば、"B"のテーブルにレコードを挿入する場合、クライアント アプリケーションは表内の"A"レコードを更新する必要があります。 同様に、クライアント アプリケーションする必要がありますレコード テーブルから削除"A"レコードが"B"のテーブルから削除された場合。  
  
     受信されると、通知メッセージからはこのシナリオでアダプターのクライアントが、挿入操作または削除操作の通知をしたかどうかを決定する通知の種類を抽出する必要があります。 通知の種類を確認すると後、アダプター クライアントは挿入または関連するテーブルを更新する後続のアクションを実行する必要があります。  
  
-   **シナリオ 2。** テーブルへの変更の通知メッセージを受信する受信場所がダウンするシナリオを検討してください。 受信場所の停止中に、一部のレコードがテーブルに追加されます。 ただし、これらのレコードのアダプターのクライアントは通知を送信されません。 受信場所は、バックアップが、アダプターを特定のメッセージを送信することによってクライアントに通知し、クライアント アプリケーションが受信場所がダウンしていたときに、データベース テーブルに挿入されたすべてのレコードを検索する必要があります。  
  
     受信されると、通知メッセージからはこのシナリオでアダプターのクライアントが通知はまたは受信場所を開始するためのデータベース テーブルに変更されたかどうかに関する情報を抽出する必要があります。 通知が受信場所を開始するためにある場合は、アダプター クライアントは、する可能性がありますが挿入、更新、または削除された受信場所がダウンしていたときにレコードを処理するロジックを実装する必要があります。  
  
> [!NOTE]
>  これらは、通知機能を使用する方法の理解を深めるに記載されているいくつかシナリオの例、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 ただし、受信した通知の種類の抽出に必要なタスクの基本的なセットは、すべてのシナリオのようになります。 このトピックでは、通知の種類を通知メッセージから抽出する方法について説明します。  
  
## <a name="how-this-topic-demonstrates-receiving-notification-messages"></a>このトピックで通知メッセージの受信について説明する方法  
 このトピックでは、後続のタスクを実行する通知メッセージを処理する方法を示すために、アダプターのクライアントが ACCOUNTACTIVITY テーブルへの変更の通知メッセージを受信する BizTalk アプリケーションを使用する基本的なシナリオ検討します。 通知が受信した後、クライアントが受信した通知の種類をフィルター処理し、後続のアクションを実行します。 非常に基本的なシナリオを示すためには、お知らせアダプター クライアントが通知メッセージを受信した通知の種類に基づいて異なるフォルダーにコピーされる検討してください。 そこで：  
  
- 通知メッセージを挿入または更新操作の場合は、アダプターのクライアントは、メッセージを C:\TestLocation\UpsertNotification フォルダーにコピーします。  
  
- 通知メッセージが、他の操作の場合は、削除など、アダプター クライアントがメッセージを C:\TestLocation\OtherNotificaiton フォルダーにコピーします。  
  
  これを実現する BizTalk アプリケーションの一部として、オーケストレーションは、次に含める必要があります。  
  
- 一方向の受信の通知メッセージを受信するポート。  
  
- 受信した通知メッセージの種類に関する情報を抽出する xpath クエリを含む式図形。  
  
- オーケストレーションに判断ブロックを含めるの判断図形。 この判断ブロックでは、アプリケーションは、受信した通知メッセージを実行する後続の操作のベースを決定します。  
  
- 最後に、通知メッセージを受信するポートは 2 つの一方向の送信します。  
  
## <a name="configuring-notifications-with-the-oracle-database-binding-properties"></a>バインドのプロパティが Oracle Database による通知の構成  
 次の表にまとめたものです、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインドのプロパティの構成、Oracle データベースから通知を受信するために使用します。 受信ポートを構成するときにこれらのバインドのプロパティを指定する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
> [!NOTE]
>  スキーマを生成するときに、これらのバインドのプロパティを指定することができます、**通知**は必須でない場合でも、操作します。 ポートのバインド ファイルをこのようにする場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]メタデータの生成の一部にもバインドのプロパティで指定する値が含まれているが生成されます。 後でこのバインド ファイルをインポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロパティは既に設定されています。 バインドで wcf-custom または Wcf-oracledb を作成する管理コンソールの受信ポート。 バインド ファイルを使用して、wcf-custom または Wcf-oracledb ポートを作成する方法の詳細については、次を参照してください。 [Oracle データベースへのポート バインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)します。  
  
|プロパティのバインド|説明|  
|----------------------|-----------------|  
|**InboundOperationType**|実行する受信操作を指定します。 通知メッセージを受信するこれを設定**通知**します。|  
|**NotificationPort**|Oracle データベースからのデータベース変更通知をリッスンする ODP.NET を開く必要があるポート番号を指定します。|  
|**NotificationStatement**|クエリ通知に登録するために使用する SELECT ステートメントを指定します。 アダプターは、指定した SELECT ステートメントの変更の結果セットの場合にのみ、通知メッセージを取得します。|  
|**NotifyOnListenerStart**|リスナーが開始されると、アダプターがアダプター クライアントに通知を送信するかどうかを指定します。|  
  
 これらのプロパティの詳細については、次を参照してください。[バインドのプロパティの操作](https://msdn.microsoft.com/library/dd788467.aspx)します。 使用する方法の詳細については、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースから通知を受信するさらに読み進める。  
  
## <a name="how-to-receive-notification-messages-from-oracle-database"></a>Oracle データベースから通知メッセージを受信する方法  
 使用して Oracle データベースでの操作を実行する[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[Oracle データベースと BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)します。 これらのタスクは通知メッセージを受信するアダプターを構成するには。  
  
1. BizTalk プロジェクトを作成しのスキーマを生成し、**通知**操作を受信します。 値を指定する、必要に応じて、 **InboundOperationType**、 **NotificationPort**、および**NotificationStatement**プロパティをバインドします。  
  
2. Oracle データベースから通知を受信するための BizTalk プロジェクトでは、メッセージを作成します。  
  
3. 前のセクションで説明したようにオーケストレーションを作成します。  
  
4. ビルドし、BizTalk プロジェクトを配置します。  
  
5. BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。  
  
   > [!NOTE]
   >  受信操作の場合、通知メッセージを受信するように Wcf-custom の一方向のみを構成する必要があります。 または Wcf-oracledb 受信ポート。 双方向受信ポートは受信操作のサポートされていません。  
  
6. BizTalk アプリケーションを起動します。  
  
   このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 スキーマを生成する必要があります、**通知**操作を受信します。 参照してください[Visual Studio での Oracle データベース操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)スキーマを生成する方法の詳細について。 スキーマを生成するときに、次のタスクを実行します。 デザイン時のバインドのプロパティを指定しない場合は、最初の手順をスキップします。  
  
1.  値を指定**InboundOperationType**、 **NotificationPort**、および**NotificationStatement**スキーマの生成中にプロパティをバインドします。 このバインドのプロパティの詳細については、次を参照してください。[バインドのプロパティの操作](https://msdn.microsoft.com/library/dd788467.aspx)します。 バインドのプロパティを指定する方法については、次を参照してください。 [for Oracle Database バインド プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)します。  
  
2.  コントラクトの種類を選択します。**サービス (受信操作)** します。  
  
3.  スキーマの生成、**通知**操作。  
  
## <a name="defining-messages-and-message-types"></a>メッセージおよびメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに必要な「型」について説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 スキーマが生成されるは、BizTalk プロジェクトのオーケストレーションからメッセージをリンクする必要があります。  
  
 このトピックでは、Oracle データベースから通知を受け取る 1 つのメッセージを作成する必要があります。  
  
 メッセージを作成し、スキーマにリンクするには、次の手順を実行します。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  オーケストレーションを BizTalk プロジェクトに追加します。 ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックして**追加**、 をクリックし、**新しい項目の**します。 BizTalk オーケストレーションの名前を入力し、クリックして**追加**します。  
  
2.  開いていない場合は、BizTalk プロジェクトのオーケストレーション ビュー ウィンドウを開きます。 をクリックして**ビュー**、 をポイント**その他の Windows**、順にクリックします**オーケストレーション**します。  
  
3.  **オーケストレーション**、右クリック**メッセージ**、順にクリックします**新しいメッセージ**します。  
  
4.  新しく作成されたメッセージを右クリックし、**プロパティ ウィンドウ**します。  
  
5.  **プロパティ**ウィンドウ **[message_1]** 次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`NotifyReceive`.|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、選び*Process_Notification.OracleDBBinding.Notification*ここで、 *Process_Notification*の名前を指定します、BizTalk プロジェクトです。 *OracleDBBinding*に対して生成されたスキーマには、**通知**操作。|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションのセットアップ  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Oracle データベースから通知メッセージを受信しから受信した通知の種類に基づいてタスクを実行するためです。 このオーケストレーションでの指定した SELECT ステートメントに基づいて、通知メッセージを受信、 **NotificationStatement**プロパティをバインドします。 式図形内で指定された xpath クエリと、変数に通知の種類を抽出**NotificationType**します。 判断図形は、この変数に値を使用して、受信した通知の種類を決定しては後続の操作を実行する適切な「パス」を受け取ります。 前述の前のセクションで、オーケストレーションは受信した通知メッセージの種類に基づいて、次の操作を実行します。  
  
- 通知メッセージを挿入または更新操作の場合は、アダプターのクライアントは、メッセージを C:\TestLocation\UpsertNotification フォルダーにコピーします。  
  
- 通知メッセージが、他の操作の場合は、削除など、アダプター クライアントがメッセージを C:\TestLocation\OtherNotificaiton フォルダーにコピーします。  
  
  そのため、オーケストレーションは、次に含める必要があります。  
  
- 一方向の受信の通知メッセージを受信するポート。  
  
- 受信した通知の種類を抽出する xpath クエリを含む式図形。  
  
- オーケストレーションに判断ブロックを含めるの判断図形。 この判断ブロックでは、アプリケーションは、受信した通知メッセージを実行する後続の操作のベースを決定します。  
  
- 最後に、通知メッセージを受信するポートは 2 つの一方向の送信します。  
  
- 図形が表示されます。  
  
  サンプル オーケストレーションでは、次の項目に似ています。  
  
  ![Post を実行するオーケストレーション&#45;通知タスク](../../adapters-and-accelerators/adapter-oracle-database/media/40c637ea-dbec-47a8-b53b-58d6820093b4.gif "40c637ea-dbec-47a8-b53b-58d6820093b4")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認します。 図形の列に示した名前は、単に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveNotification|Receive|-設定**名前**に*ReceiveNotification*<br /><br /> -設定**アクティブ**に*は True。*|  
  
### <a name="adding-an-expression-shape"></a>式図形を追加します。  
 オーケストレーションの式図形を含むの目的に受信した通知メッセージの種類を抽出する xpath クエリです。 Xpath クエリを作成する前に、通知メッセージの形式について見てみましょう。 一般的な通知メッセージには、次のようになります。  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification/">  
  <Details>  
    <NotificationDetails>  
      <ResourceName>SCOTT.ACCOUNTACTIVITY</ResourceName>   
      <Info>1</Info>   
      <QueryId>0</QueryId>   
    </NotificationDetails>  
  </Details>  
  <Info>Insert</Info>   
  <ResourceNames>  
    <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">SCOTT.ACCOUNTACTIVITY</string>   
  </ResourceNames>  
  <Source>Data</Source>   
  <Type>Change</Type>   
</Notification>  
```  
  
 通知の種類に関する情報は内で使用できるように、`<info>`親内のタグ`<Notification>`タグ。 一部として、この式図形の操作を行います。  
  
-   内の値を格納する変数を作成、`<Info>`タグ付けし、その型 System.String に設定します。 変数の作成方法の詳細については、次を参照してください。[オーケストレーションで変数を使用して](../../core/using-variables-in-orchestrations.md)します。  
  
     このトピックでは、名前を変数として**NotificationType**します。  
  
-   値を抽出する xpath クエリを作成、\<情報\>タグ。 Xpath クエリは、次のようになります。  
  
    ```  
    NotificationType = xpath(NotifyReceive,"string(/*[local-name()='Notification']/*[local-name()='Info']/text())");  
    ```  
  
     この xpath クエリで**NotifyReceive**通知メッセージの受信用に作成したメッセージです。 内の抜粋、`string`関数では、クエリ内の値を抽出する必要があることを示します、`<Info>`内では、さらに、タグ、`<Notification>`タグ。 クエリによって抽出された値が最後に、割り当てられた、 **NotificaitonType**変数。  
  
### <a name="adding-a-decide-shape"></a>判断図形を追加します。  
 判断図形を追加する目的は、受信した通知メッセージの種類を実行する後続の操作のベースを決定するオーケストレーションに判断ブロックを含めるです。 値に基づいて決定されます、 **NotificationType**変数。 このトピックでは、オーケストレーションは、受信した通知メッセージの種類に基づいて決定を行います。 そのため、ルール図形の条件はよう指定します。  
  
```  
NotificationType.Equals("Insert") | NotificationType.Equals("Update")  
```  
  
 この条件はいる場合の値を提案**NotificaitonType**変数が挿入または更新には、オーケストレーションが 1 つの一連のタスクを実行します。 場合の値**NotificationType**変数は、まず、オーケストレーションはその他の一連のタスクを実行します。  
  
 前述の前のセクションで、シンプルなアプローチを示すために、オーケストレーションはメッセージにコピー通知メッセージの種類に基づいて別のフォルダー。 ルール内で Else ブロックでは、別のポートにメッセージを送信する送信図形を追加する必要があります。 このトピックでは、名前としてルール ブロックに送信図形**SendUpsertNotification**として Else ブロックに送信図形と**SendOtherNotification**します。  
  
### <a name="adding-ports"></a>ポートの追加  
 オーケストレーションに、次の論理ポートを追加する必要がありますようになりました。  
  
- 一方向受信ポート、Oracle データベースから通知メッセージを受信します。  
  
- 特定のフォルダーに挿入または更新操作の通知メッセージを送信する一方向の送信ポート。  
  
- 特定のフォルダーに他の操作の通知メッセージを送信する一方向の送信ポート。  
  
  論理ポートごとに、次のプロパティを指定することを確認します。 ポート列に示した名前は、オーケストレーションで表示されているポートの名前です。  
  
|Port|[プロパティ]|  
|----------|----------------|  
|OracleNotifyPort|-設定**識別子**に*OracleNotifyPort*<br /><br /> -設定**型**に*OracleNotifyPortType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*受信*|  
|NotificationUpsertPort|-設定**識別子**に*NotificationUpsertPort*<br /><br /> -設定**型**に*NotificationUpsertPortType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*送信*|  
|OtherNotificationPort|-設定**識別子**に*OtherNotificationPort*<br /><br /> -設定**型**に*OtherNotificationPortType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*送信*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表では、プロパティとアクション図形のメッセージを指定して、メッセージ ポートにリンクを設定する必要があります、値を指定します。 図形の列に示した名前は、前に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveNotification|-設定**メッセージ**に*NotifyReceive*<br /><br /> -設定**操作**に*OracleNotifyPort.Notify.Request*|  
|SendUpsertNotification|-設定**メッセージ**に*NotifyReceive*<br /><br /> -設定**操作**に*NotificationUpsertPort.Upsert.Request*|  
|SendOtherNotification|-設定**メッセージ**に*を選択します*<br /><br /> -設定**操作**に*OtherNotificationPort.Other.Request*|  
  
 これらのプロパティを指定したら、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 ここで、BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 詳細については、次を参照してください。[を実行しているオーケストレーションのビルドと](../../core/building-and-running-orchestrations.md)します。  
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 先ほど作成したオーケストレーションが 下にある BizTalk プロジェクトを配置した後、**オーケストレーション**ペインで、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールにアプリケーションを構成します。 チュートリアルについては、次を参照してください。[チュートリアル。基本的な BizTalk アプリケーション展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)します。
  
 アプリケーションを構成する必要があります。  
  
- アプリケーションのホストを選択します。  
  
- 物理ポートにオーケストレーションで作成したポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 このオーケストレーションの次の操作を行う必要があります。  
  
  - Wcf-oracledb 一方向受信ポートまたは物理 Wcf-custom を定義します。 このポートは、Oracle データベースから通知をリッスンします。 受信ポートを作成する方法についてを参照してください[、Oracle データベース アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)します。 受信ポートのバインドのプロパティを指定することを確認します。  
  
    > [!IMPORTANT]
    >  デザイン時のバインドのプロパティが指定されている場合は、この手順を実行する必要はありません。 このような場合は、WCF カスタムを作成または Wcf-oracledb によって作成されたバインド ファイルをインポートすることによって、必要なバインドのプロパティを設定すると、ポートの受信、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 詳細については、「ポートのバインド ファイル物理ポート バインドを使用して、構成する」を参照してください。  
  
    |プロパティのバインド|値|  
    |----------------------|-----------|  
    |**InboundOperationType**|これを設定**通知**します。|  
    |**NotificationPort**|Oracle データベースからのデータベース変更通知をリッスンする ODP.NET を開く必要があるポート番号を指定します。 これは、Windows ファイアウォールの例外リストに追加する必要があります、同じポート番号に設定します。 Windows ファイアウォールの例外リストにポートを追加する方法については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959)します。<br /><br /> **重要:** これを既定値は-1 に設定した場合は通知メッセージを受信する Windows ファイアウォールを完全に無効にする必要があります。|  
    |**NotificationStatement**|これを設定します。<br /><br /> `SELECT TID,ACCOUNT,PROCESSED FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’`<br /><br /> **注:** スキーマ名とテーブル名を指定する必要があります。 たとえば、`SCOTT.ACCOUNTACTIVITY` のようにします。|  
    |**NotifyOnListenerStart**|これを設定**True**します。|  
  
     異なるバインディング プロパティの詳細については、次を参照してください。[バインドのプロパティの操作](https://msdn.microsoft.com/library/dd788467.aspx)します。  
  
    > [!NOTE]
    >  使用して受信操作の実行中に、トランザクション分離レベルとトランザクションのタイムアウトを構成することをお勧めします。、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 ように、サービスを追加することで、Wcf-custom または Wcf-oracledb を構成するときに動作の受信ポートを行うことができます。 サービスの動作を追加する方法については、次を参照してください。[トランザクション分離レベルの構成と Oracle データベースとトランザクション タイムアウト](../../adapters-and-accelerators/adapter-oracle-database/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-db.md)します。  
  
  - ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーション Insert および Update 操作用の Oracle データベースから通知メッセージをドロップできる場所での場所を定義します。 C:\TestLocation\UpsertNotification フォルダーへの通知メッセージを削除するには、このポートを構成します。  
  
  - ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーションの他のすべての操作用の Oracle データベースから通知メッセージをドロップできる場所での場所を定義します。 C:\TestLocation\OtherNotification フォルダーへの通知メッセージを削除するには、このポートを構成します。  
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 Oracle データベースから通知メッセージを受信するため、後続の Select および Update 操作を実行するために、BizTalk アプリケーションを開始する必要があります。 BizTalk アプリケーションを開始する手順については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)します。  
  
 この段階で、ことを確認します。  
  
-   Wcf-custom または Wcf-oracledb 一方向の受信ポートで、データベースが実行されている Oracle から通知メッセージを受信します。  
  
-   Oracle データベースからメッセージを受信、2 つファイル送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 BizTalk オーケストレーションを開始した後、次の一連のアクションが行われます。  
  
-   **NotifyOnListenerStart**に設定されているプロパティのバインド**True**、次のメッセージが表示されます。  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification/">  
      <Info>ListenerStarted</Info>   
      <Source>OracleDBBinding</Source>   
      <Type>Startup</Type>   
    </Notification>  
    ```  
  
     注意の値、`<Info>`タグは、"ListnerStarted"。 そのため、このメッセージは、C:\TestLocation\OtherNotification フォルダーで受信されます。  
  
-   ACCOUNTACTIVITY テーブルにレコードを挿入します。 次のような通知メッセージが表示されます。  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification/">  
      <Details>  
        <NotificationDetails>  
          <ResourceName>SCOTT.ACCOUNTACTIVITY</ResourceName>   
          <Info>1</Info>   
          <QueryId>0</QueryId>   
        </NotificationDetails>  
      </Details>  
      <Info>Insert</Info>   
      <ResourceNames>  
        <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">SCOTT.ACCOUNTACTIVITY</string>   
      </ResourceNames>  
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     注意の値、`<Info>`タグは、"Insert"。 そのため、このメッセージは、C:\TestLocation\UpsertNotification フォルダーで受信されます。  
  
-   ACCOUNTACTIVITY テーブル内のレコードを更新します。 次のような通知メッセージが表示されます。  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification/">  
      <Details>  
        <NotificationDetails>  
          <ResourceName>SCOTT.ACCOUNTACTIVITY</ResourceName>   
          <Info>32</Info>   
          <QueryId>0</QueryId>   
        </NotificationDetails>  
      </Details>  
      <Info>Update</Info>   
      <ResourceNames>  
        <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">SCOTT.ACCOUNTACTIVITY</string>   
      </ResourceNames>  
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     注意の値、`<Info>`タグは、「更新」します。 そのため、このメッセージは、C:\TestLocation\UpsertNotification フォルダーで受信されます。  
  
-   ACCOUNTACTIVITY テーブルからレコードを削除します。 次のような通知メッセージが表示されます。  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification/">  
      <Details>  
        <NotificationDetails>  
          <ResourceName>SCOTT.ACCOUNTACTIVITY</ResourceName>   
          <Info>16</Info>   
          <QueryId>0</QueryId>   
        </NotificationDetails>  
      </Details>  
      <Info>Delete</Info>   
      <ResourceNames>  
        <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">SCOTT.ACCOUNTACTIVITY</string>   
      </ResourceNames>  
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     注意の値、`<Info>`タグは「削除」です。 そのため、このメッセージは、C:\TestLocation\OtherNotification フォルダーで受信されます。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。 バインド ファイルを生成した、送信ポートを作成し、同じオーケストレーション用のポートを受信する必要はありませんように構成設定、ファイルからインポートできます。 バインド ファイルの詳細については、次を参照してください。 [Oracle データベース アダプターの再利用バインド](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)します。  
  
## <a name="performing-complex-operations-after-receiving-notification-messages"></a>通知メッセージを受信した後、複雑な操作を実行します。  
 単純化して理解を深めるは、このトピックの「オーケストレーションはメッセージを通知の種類に基づいて異なるフォルダーにコピーします。 ただし、実際のシナリオより複雑な操作を実行する必要があります。 このトピックとする操作を実行するためにビルドで指定された同じような手順を実行できます。 たとえば、ACCOUNTACTIVITY テーブルで挿入操作の通知メッセージが発生した場合、別のテーブルのレコードを挿入するオーケストレーションを変更することができます。 このような場合は、判断図形内で適切な変更を行うことができます。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を使用して Oracle データベースの変更通知を受け取る](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md)
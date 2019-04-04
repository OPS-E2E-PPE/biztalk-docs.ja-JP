---
title: Oracle E-business Suite で特定のタスクを完了する通知メッセージを処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4bddeb5a-3819-40cc-aae0-c49963f0beb1
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d671ee0b4ab351bce8109cdd20635d6f838da9ea
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995955"
---
# <a name="process-notification-messages-to-complete-specific-tasks-in-oracle-e-business-suite"></a>Oracle E-business Suite で特定のタスクを完了する通知メッセージの処理
使用することができます、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle データベースのテーブルへの変更の通知を受信します。 ただし、アダプターのみ通知を送信するレコードの一部の電源が挿入されていること、更新、または特定のデータベース テーブルで削除されたことです。 これらのレコードに、後続の処理は、クライアント アプリケーション自体によって処理する必要があります。 このトピックでは、Oracle データベースから受信した通知の種類に基づいて、テーブル内のレコードを処理する方法のシナリオ ベースの説明を示します。  
  
## <a name="scenarios-for-performing-subsequent-actions-after-receiving-notification"></a>通知を受信した後、後続のアクションを実行するためのシナリオ  
 次に、いくつかのシナリオのアダプターのクライアントが特定の通知後タスクを実行する必要があります。  
  
-   **シナリオ 1。** アダプターのクライアントが Oracle データベースから受信した通知の種類に基づいて特定のタスクを実行する必要がありますシナリオを検討してください。 たとえば、"B"のテーブルにレコードを挿入する場合、クライアント アプリケーションは表内の"A"レコードを更新する必要があります。 同様に、クライアント アプリケーションする必要がありますレコード テーブルから削除"A"レコードが"B"のテーブルから削除された場合。  
  
     受信されると、通知メッセージからはこのシナリオでアダプターのクライアントが、挿入操作または削除操作の通知をしたかどうかを決定する通知の種類を抽出する必要があります。 通知の種類を確認すると後、アダプター クライアントは挿入または関連するテーブルを更新する後続のアクションを実行する必要があります。  
  
-   **シナリオ 2。** テーブルへの変更の通知メッセージを受信する受信場所がダウンするシナリオを検討してください。 受信場所の停止中に、一部のレコードがテーブルに追加されます。 ただし、これらのレコードのアダプターのクライアントは通知を送信されません。 受信場所は、バックアップが、アダプターを特定のメッセージを送信することによってクライアントに通知し、クライアント アプリケーションが受信場所がダウンしていたときに、データベース テーブルに挿入されたすべてのレコードを検索する必要があります。  
  
     受信されると、通知メッセージからはこのシナリオでアダプターのクライアントが通知はまたは受信場所を開始するためのデータベース テーブルに変更されたかどうかに関する情報を抽出する必要があります。 通知が受信場所を開始するためにある場合は、アダプター クライアントは、する可能性がありますが挿入、更新、または削除された受信場所がダウンしていたときにレコードを処理するロジックを実装する必要があります。  
  
> [!NOTE]
>  これらは、通知機能を使用する方法の理解を深めるに記載されているいくつかシナリオの例、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 ただし、受信した通知の種類の抽出に必要なタスクの基本的なセットは、すべてのシナリオのようになります。 このトピックでは、通知の種類を通知メッセージから抽出する方法について説明します。  
  
## <a name="how-this-topic-demonstrates-receiving-notification-messages"></a>このトピックで通知メッセージの受信について説明する方法  
 このトピックでは、後続のタスクを実行する通知メッセージを処理する方法を示すために、アダプターのクライアントが ACCOUNTACTIVITY テーブルへの変更の通知メッセージを受信する BizTalk アプリケーションを使用する基本的なシナリオ検討します。 通知が受信した後、クライアントが受信した通知の種類をフィルター処理し、後続のアクションを実行します。 非常に基本的なシナリオを示すためには、お知らせアダプター クライアントが通知メッセージを受信した通知の種類に基づいて異なるフォルダーにコピーされる検討してください。 そこで：  
  
- 通知メッセージを挿入または更新操作の場合は、アダプターのクライアントは、メッセージを C:\TestLocation\UpsertNotification フォルダーにコピーします。  
  
- 通知メッセージが、他の操作の場合は、削除など、アダプター クライアントがメッセージを C:\TestLocation\OtherNotificaiton フォルダーにコピーします。  
  
  これを実現する BizTalk アプリケーションの一部として、オーケストレーションは、次に含める必要があります。  
  
- 一方向の受信の通知メッセージを受信するポート。  
  
- 受信した通知メッセージの種類に関する情報を抽出する xpath クエリを含む式図形。  
  
- オーケストレーションに判断ブロックを含めるの判断図形。 この判断ブロックでは、アプリケーションは、受信した通知メッセージを実行する後続の操作のベースを決定します。  
  
- 最後に、通知メッセージを受信するポートは 2 つの一方向の送信します。  
  
## <a name="configuring-notifications-with-the-oracle-e-business-adapter-binding-properties"></a>Oracle E-business アダプターのバインドのプロパティと通知の構成  
 次の表にまとめたものです、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite から通知を受け取る構成に使用するプロパティをバインドします。 受信ポートを構成するときに、これらのバインドのプロパティを指定する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
> [!NOTE]
>  スキーマを生成するときに、これらのバインドのプロパティを指定することができます、**通知**は必須でない場合でも、操作します。 ポートのバインド ファイルをこのようにする場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]メタデータの生成の一部にもバインドのプロパティで指定する値が含まれているが生成されます。 後でこのバインド ファイルをインポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロパティは既に設定されています。 バインドで wcf-custom または Wcf-oracleebs を作成する管理コンソールの受信ポート。 バインド ファイルを使用して、wcf-custom または Wcf-oracleebs ポートを作成する方法の詳細については、[Oracle E-business Suite へのポート バインド ファイルを、物理ポートを使用してバインディングを構成](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)を参照してください。  
  
|プロパティのバインド|説明|  
|----------------------|-----------------|  
|**InboundOperationType**|実行する受信操作を指定します。 通知メッセージを受信するこれを設定**通知**します。|  
|**NotificationPort**|Oracle データベースからのデータベース変更通知をリッスンする ODP.NET を開く必要があるポート番号を指定します。|  
|**NotificationStatement**|クエリ通知に登録するために使用する SELECT ステートメントを指定します。 アダプターは、指定した SELECT ステートメントの変更の結果セットの場合にのみ、通知メッセージを取得します。|  
|**NotifyOnListenerStart**|リスナーが開始されると、アダプターがアダプター クライアントに通知を送信するかどうかを指定します。|  
  
 これらのプロパティの詳細については、[[for Oracle E-business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)を参照してください。 使用する方法の詳細については、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite から通知を受信するさらに読み進める。  
  
## <a name="how-to-receive-notification-messages-from-oracle-e-business-suite"></a>Oracle E-business Suite から通知メッセージを受信する方法  
 Oracle E-business Suite を使用して、操作を実行する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[Oracle E-business Suite のアプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)します。 これらのタスクは通知メッセージを受信するアダプターを構成するには。  
  
1. BizTalk プロジェクトを作成しのスキーマを生成し、**通知**操作を受信します。 値を指定する、必要に応じて、 **InboundOperationType**、 **NotificationPort**、および**NotificationStatement**プロパティをバインドします。  
  
2. Oracle E-business Suite から通知を受信するための BizTalk プロジェクトでは、メッセージを作成します。  
  
3. 前のセクションで説明したようにオーケストレーションを作成します。  
  
4. ビルドし、BizTalk プロジェクトを配置します。  
  
5. BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。  
  
   > [!NOTE]
   >  受信操作の場合、通知メッセージを受信するように Wcf-custom の一方向のみを構成する必要があります。 または Wcf-oracleebs 受信ポート。 双方向受信ポートは受信操作のサポートされていません。  
  
6. BizTalk アプリケーションを起動します。  
  
   このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 スキーマを生成する必要があります、**通知**操作を受信します。 スキーマを生成する方法の詳細については、[Visual Studio での Oracle E-business Suite 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)を参照してください。 スキーマを生成するときに、次のタスクを実行します。 デザイン時のバインドのプロパティを指定しない場合は、最初の手順をスキップします。  
  
 スキーマを生成するときに、次のタスクを実行します。 デザイン時のバインドのプロパティを指定しない場合は、最初の手順をスキップします。  
  
1.  値を指定**InboundOperationType**、 **NotificationPort**、および**NotificationStatement**スキーマの生成中にプロパティをバインドします。 このバインドのプロパティの詳細については、[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)を参照してください。 バインドのプロパティを指定する方法については、[for Oracle E-business Suite のバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)を参照してください。  
  
2.  コントラクトの種類を選択します。**サービス (受信操作)** します。  
  
3.  スキーマの生成、**通知**操作。  
  
## <a name="defining-messages-and-message-types"></a>メッセージおよびメッセージの種類を定義します。  
 前のセクションで生成したスキーマには、オーケストレーション内のメッセージに必要な「型」について説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 スキーマが生成されるは、BizTalk プロジェクトのオーケストレーションからメッセージをリンクする必要があります。  
  
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
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、選び*Process_Notification.OracleEBSBinding.Notification*ここで、 *Process_Notification*の名前を指定します、BizTalk プロジェクトです。 *OracleEBSBinding*に対して生成されたスキーマには、**通知**操作。|  
  
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
  
  サンプル オーケストレーションには、次のようになります。  
  
  ![Post を実行するオーケストレーション&#45;通知タスク](../../adapters-and-accelerators/adapter-oracle-database/media/40c637ea-dbec-47a8-b53b-58d6820093b4.gif "40c637ea-dbec-47a8-b53b-58d6820093b4")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認します。 表示される名前、**図形**オーケストレーション ダイアグラムに表示される、列がメッセージの構築図形の名前を示します。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveNotification|Receive|-設定**名前**に*ReceiveNotification*<br /><br /> -設定**アクティブ**に*は True。*|  
  
### <a name="adding-an-expression-shape"></a>式図形を追加します。  
 オーケストレーションの式図形を含むの目的に受信した通知メッセージの種類を抽出する xpath クエリです。 Xpath クエリを作成する前に、通知メッセージの形式について見てみましょう。 一般的な通知メッセージには、次のようになります。  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<Notification xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/">  
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
  
-   内の値を格納する変数を作成、`<Info>`タグ付けし、その型 System.String に設定します。 変数の作成方法の詳細については、[オーケストレーションで変数を使用して](../../core/using-variables-in-orchestrations.md)を参照してください。  
  
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
  
  論理ポートごとに、次のプロパティを指定することを確認します。 表示される名前、**ポート**列は、ポートの名前では、このトピックで前述したオーケストレーション ダイアグラムに表示されます。  
  
|Port|[プロパティ]|  
|----------|----------------|  
|OracleNotifyPort|-設定**識別子**に*OracleNotifyPort*<br /><br /> -設定**型**に*OracleNotifyPortType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*受信*|  
|NotificationUpsertPort|-設定**識別子**に*NotificationUpsertPort*<br /><br /> -設定**型**に*NotificationUpsertPortType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*送信*|  
|OtherNotificationPort|-設定**識別子**に*OtherNotificationPort*<br /><br /> -設定**型**に*OtherNotificationPortType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*送信*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表では、プロパティとアクション図形のメッセージを指定して、メッセージ ポートにリンクを設定する必要があります、値を指定します。 表示される名前、**図形**列がこのトピックで前述したオーケストレーション ダイアグラムに表示される、メッセージの構築図形の名前を示します。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveNotification|-設定**メッセージ**に*NotifyReceive*<br /><br /> -設定**操作**に*OracleNotifyPort.Notify.Request*|  
|SendUpsertNotification|-設定**メッセージ**に*NotifyReceive*<br /><br /> -設定**操作**に*NotificationUpsertPort.Upsert.Request*|  
|SendOtherNotification|-設定**メッセージ**に*を選択します*<br /><br /> -設定**操作**に*OtherNotificationPort.Other.Request*|  
  
 これらのプロパティを指定したら、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 ここで、BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 詳細については、[を実行しているオーケストレーションのビルドと](../../core/building-and-running-orchestrations.md)を参照してください。
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 先ほど作成したオーケストレーションが 下にある BizTalk プロジェクトを配置した後、**オーケストレーション**ペインで、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールにアプリケーションを構成します。 チュートリアルについては、[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)を参照してください。  
  
 アプリケーションを構成する必要があります。  
  
- アプリケーションのホストを選択します。  
  
- 物理ポートにオーケストレーションで作成したポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 このオーケストレーションの次の操作を行う必要があります。  
  
  - Wcf-oracleebs 一方向受信ポートまたは物理 Wcf-custom を定義します。 このポートは、Oracle E-business Suite から送る通知をリッスンします。 受信ポートを作成する方法についてを参照してください[、Oracle E-business アダプターを物理ポート バインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)します。 受信ポートのバインドのプロパティを指定することを確認します。  
  
    > [!IMPORTANT]
    >  デザイン時のバインドのプロパティが指定されている場合は、この手順を実行する必要はありません。 このような場合は、WCF カスタムを作成または Wcf-oracleebs によって作成されたバインド ファイルをインポートすることによって、必要なバインドのプロパティを設定すると、ポートの受信、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 詳細については、[Oracle E-business Suite へのポートのバインド ファイルを物理ポートのバインドを使用して、を構成](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)を参照してください。  
  
    |プロパティのバインド|値|  
    |----------------------|-----------|  
    |**InboundOperationType**|これを設定**通知**します。|  
    |**NotificationPort**|Oracle データベースからのデータベース変更通知をリッスンする ODP.NET を開く必要があるポート番号を指定します。 これは、Windows ファイアウォールの例外リストに追加する必要があります、同じポート番号に設定します。 Windows ファイアウォールの例外リストにポートを追加する方法については、[ http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959)を参照してください。<br /><br /> **重要な**これを既定値は-1 に設定すると、通知メッセージを受信する Windows ファイアウォールを完全に無効にする必要があります。|  
    |**NotificationStatement**|これを設定します。<br /><br /> `SELECT TID,ACCOUNT,PROCESSED FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’`<br /><br /> **注**スキーマ名とテーブル名を指定する必要があります。 たとえば、 `SCOTT.ACCOUNTACTIVITY`のようにします。|  
    |**NotifyOnListenerStart**|これを設定**True**します。|  
  
     異なるバインディング プロパティの詳細については、[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)を参照してください。  
  
    > [!IMPORTANT]
    >  インターフェイス テーブルの通知を構成する場合は、必要なバインドのプロパティを指定することによってアプリケーション コンテキストを設定する必要があります。 アプリケーション コンテキストの設定の詳細については、[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)を参照してください。  
    > 
    > [!NOTE]
    >  使用して受信操作の実行中に、トランザクション分離レベルとトランザクションのタイムアウトを構成することをお勧めします。、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 WCF カスタムを構成するときに、サービスの動作を追加することで行うことができますか、Wcf-oracleebs 受信ポート。 サービスの動作を追加する方法については、[トランザクション分離レベルの構成と Oracle E-business Suite でのトランザクション タイムアウト](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md)を参照してください。  
  
  - ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーション Insert および Update 操作用の Oracle データベースから通知メッセージをドロップできる場所での場所を定義します。 C:\TestLocation\UpsertNotification フォルダーへの通知メッセージを削除するには、このポートを構成します。  
  
  - ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーションの他のすべての操作用の Oracle データベースから通知メッセージをドロップできる場所での場所を定義します。 C:\TestLocation\OtherNotification フォルダーへの通知メッセージを削除するには、このポートを構成します。  
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 Oracle データベースから通知メッセージを受信するため、後続の Select および Update 操作を実行するために、BizTalk アプリケーションを開始する必要があります。 BizTalk アプリケーションを開始する手順については、[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)を参照してください。  
  
 この段階で、ことを確認します。  
  
-   Wcf-custom または Wcf-oracleebs 一方向の受信ポートで、データベースが実行されている Oracle から通知メッセージを受信します。  
  
-   Oracle データベースからメッセージを受信、2 つファイル送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 BizTalk オーケストレーションを開始した後、次の一連のアクションが行われます。  
  
-   **NotifyOnListenerStart**に設定されているプロパティのバインド**True**、次のメッセージが表示されます。  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/">  
      <Info>ListenerStarted</Info>   
      <Source>OracleEBSBinding</Source>   
      <Type>Startup</Type>   
    </Notification>  
    ```  
  
     注意の値、`<Info>`タグは、"ListnerStarted"。 そのため、このメッセージは、C:\TestLocation\OtherNotification フォルダーで受信されます。  
  
-   ACCOUNTACTIVITY テーブルにレコードを挿入します。 次のような通知メッセージが表示されます。  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/">  
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
    <Notification xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/">  
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
    <Notification xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/">  
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
 展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。 バインド ファイルを生成した、送信ポートを作成し、同じオーケストレーション用のポートを受信する必要はありませんように構成設定、ファイルからインポートできます。 バインド ファイルの詳細については、[Oracle E-business suite アダプターのバインドを再利用](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)を参照してください。  
  
## <a name="performing-complex-operations-after-receiving-notification-messages"></a>通知メッセージを受信した後、複雑な操作を実行します。  
 単純化して理解を深めるは、このトピックの「オーケストレーションはメッセージを通知の種類に基づいて異なるフォルダーにコピーします。 ただし、実際のシナリオより複雑な操作を実行する必要があります。 このトピックとする操作を実行するためにビルドで指定された同じような手順を実行できます。 たとえば、ACCOUNTACTIVITY テーブルで挿入操作の通知メッセージが発生した場合、別のテーブルのレコードを挿入するオーケストレーションを変更することができます。 このような場合は、判断図形内で適切な変更を行うことができます。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を使用して Oracle E-business Suite データベース変更通知を受信します。](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-using-biztalk-server.md)
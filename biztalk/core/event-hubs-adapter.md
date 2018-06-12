---
title: Event Hubs アダプターを使用して |Microsoft ドキュメント
description: BizTalk Server で Azure Event Hubs アダプターを使用してメッセージの送受信を行う
ms.custom: ''
ms.date: 11/16/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: MandiOhlinger
ms.author: plarsen
manager: anneta
ms.openlocfilehash: cb9bbe26f07d87d7cccc084b6842b6d0974fdbb3
ms.sourcegitcommit: 3371ffd8ceca02e2b3715d53a1e0c0a59045912e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2018
ms.locfileid: "34848922"
---
# <a name="event-hub-adapter-in-biztalk"></a>BizTalk でイベント ハブのアダプター

## <a name="overview"></a>概要
**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]Feature Pack 2**、BizTalk Server と Azure Event Hubs 間でメッセージを送受信できます。 

Azure Event Hubs は現在ストリーミング プラットフォーム、拡張性の高いデータは、および受信、および数百万の 1 秒あたりのイベントを処理できます。 [Event Hubs は何ですか。](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs)詳細を示します。

## <a name="prerequisites"></a>前提条件

* 作成、 [Azure イベント ハブの名前空間とイベント ハブ](https://docs.microsoft.com/azure/event-hubs/event-hubs-create)
* 作成、[コンテナーと Azure blob ストレージ アカウント](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account)
* インストール[Feature Pack 2](https://aka.ms/bts2016fp2) BizTalk Server で

イベント ハブが作成されましたが、およびイベントを送受信する必要がある、接続文字列があります。

## <a name="send-messages-to-event-hubs"></a>Event Hub にメッセージを送信します。

1.  BizTalk Server 管理コンソールを右クリックして**送信ポート****新規**を選択し、**静的な一方向送信ポート**です。

    [送信ポートを作成](../core/how-to-create-a-send-port2.md)のガイダンスを紹介します。

2. 入力、**名前**です。 **トランスポート**、設定、**型**に**EventHub**を選択して**構成**です。 

3. 構成、 **Azure アカウント**プロパティ。 

    |プロパティ|目的|  
    |---|---|  
    | **サインイン** | Azure アカウントにサインインします。 |
    | **サブスクリプション** | EventHubs 名前空間を持つサブスクリプションを選択します。 |
    | **リソース グループ** | EventHubs 名前空間を持つリソース グループを選択します。 |

4. 構成、**エンドポイント**プロパティ。 

    |プロパティ|目的|  
    |---|---|  
    | **Namespace** | Sb のようなものである、イベント ハブ名前空間を選択します//*youreventhubnamespace*.servicebus.windows.net/。 |
    | **Name** | (これは、イベント ハブ名前空間内で作成した)、イベント ハブの名前を選択します。 |
    | **既定のパーティション キー** | 任意。 [Event Hub プログラミング ガイド](https://docs.microsoft.com/azure/event-hubs/event-hubs-programming-guide)このキーの詳細を提供します。 |
    | **[認証]** | **Namespace Access Signature** 、既定値は、イベント ハブ名前空間を作成するときに作成される RootManageSharedAccessKey が自動的に使用します。<br/><br/>**エンティティ Access Signature** SAS ポリシーが、イベント ハブのレベルで (、イベント ハブ名前空間レベルではなく) を作成することができます。 <br/><br/>[Event Hubs の機能概要](https://docs.microsoft.com/azure/event-hubs/event-hubs-features)の詳細について説明します。 |

    完了したらのプロパティが、次のようになります。 

    ![エンドポイントのプロパティ](../core/media/event-hub-endpoint-properties.png)


5. 任意。 構成、**メッセージ**プロパティです。 **ユーザー定義メッセージのプロパティの Namespace**値は、Event Hubs メッセージ プロパティにマップされる BizTalk メッセージのスキーマを表します。

6. 選択**Ok**して変更を保存します。 


### <a name="test-your-send-port"></a>送信ポートをテストします。

単純なを使用するファイルの受信ポートと、Azure Event Hub にメッセージを送信する場所です。 

1. ファイル アダプターを使用して受信ポートを作成します。 内で、受信場所は、設定、**受信フォルダー**に **C:\Temp\In\** に、ファイル マスクを設定および **\*.xml**です。
2. Event Hub に送信ポートのプロパティを設定、**フィルター**に`BTS.ReceivePortName == FileReceivePort`です。
3. テキスト エディターに貼り付け、ファイルに保存**EventHubMessage.xml**です。 これは、サンプル メッセージです。 

    ```xml
    <Data>
      <DataID>DataID_0</DataID>
      <DataDetails>DataDetails_0</DataDetails>
    </Data>
    ```

4. 開始ファイルは、場所と、イベント ハブの送信ポートを受信します。
5. コピー **EventHubMessage.xml**受信フォルダにサンプル メッセージ (C:\Temp\In\)です。 送信ポートは、XML ファイルを event hub に送信します。

## <a name="receive-messages-from-event-hubs"></a>Event Hub からメッセージを受信します。

1. BizTalk Server 管理コンソールを右クリックし**受信ポート****新規**を選択し、**一方向受信ポート**です。 

    [受信ポートを作成](../core/how-to-create-a-receive-port.md)のガイダンスを紹介します。

2. 名前を入力し、選択**受信場所**です。 

3. 選択**新規**、および**名前**受信場所。 **トランスポート** **EventHub**から、**型**クリックしてドロップダウン リスト、**構成**です。 

4. 構成、 **Azure アカウント**プロパティ。 

    |プロパティ|目的|  
    |---|---|  
    | **サインイン** | Azure アカウントにサインインします。 |
    | **サブスクリプション** | EventHubs 名前空間を持つサブスクリプションを選択します。 |
    | **リソース グループ** | EventHubs 名前空間を持つリソース グループを選択します。 |

4. 構成、**エンドポイント**プロパティ。 

    |プロパティ|目的|  
    |---|---|  
    | **Namespace** | Sb のようなものである、イベント ハブ名前空間を選択します//*youreventhubnamespace*.servicebus.windows.net/。 |
    | **Name** | (これは、イベント ハブ名前空間内で作成した)、イベント ハブの名前を選択します。 |
    | **コンシューマー グループ** | Event Hub 内のコンシューマー グループを選択します。 既定のグループが自動的に作成されます。 <br/><br/>[Event Hubs の機能概要](https://docs.microsoft.com/azure/event-hubs/event-hubs-features)詳細を示します。 |
    | **[認証]** | **Namespace Access Signature** 、既定値は、イベント ハブ名前空間を作成するときに作成される RootManageSharedAccessKey が自動的に使用します。<br/><br/>**エンティティ Access Signature** SAS ポリシーが、イベント ハブのレベルで (、イベント ハブ名前空間レベルではなく) を作成することができます。 <br/><br/>[Event Hubs の機能概要](https://docs.microsoft.com/azure/event-hubs/event-hubs-features)の詳細について説明します。 |

    完了したらのプロパティが、次のようになります。 

    ![エンドポイントのプロパティ](../core/media/event-hub-endpoint-receive-properties.png)

5. 構成、**チェックポイント**プロパティです。 このアダプターは、確実に、チェックポイントを使用してイベントを読み取るし、再起動からの再開を Azure blob ストレージ アカウントを使用します。 

    **記憶域の認証**   
    認証方法を選択します。 通常、共有アクセス署名を使用することをお勧めします。 次のリンクでは、これは、シナリオに適したの判断に役立つ優れたリソースです。<br/><br/>[Azure ストレージ アカウントの概要](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account)<br/>[共有アクセス署名 (SAS) を使用します。](https://docs.microsoft.com/azure/storage/common/storage-dotnet-shared-access-signature-part-1)

    完了したらのプロパティが、次のようになります。 

    ![チェックポイントのプロパティ](../core/media/event-hub-receive-checkpoint.png)

6. 構成、**メッセージ**プロパティ。 

    |プロパティ|目的|  
    |---|---|  
    | **ユーザーの Namespace メッセージのプロパティを定義します。** | http://schemas.microsoft.com/BizTalk/EventHubAdapter/EventData/User 既定のスキーマが、別のスキーマを入力することができます。 この値は、Event Hubs メッセージ プロパティにマップされる BizTalk メッセージのスキーマを表します。 |
    | **ユーザー定義プロパティを昇格させる** | 任意。 たい場合は、これらのプロパティを昇格させることができます。 <br/><br/>**注**<br/>昇格させる必要があるプロパティが展開されている porperty スキーマを持っている必要があります*する前に*イベントを受信します。|

7. 選択**Ok**して変更を保存します。 

### <a name="test-your-receive-settings"></a>テストの設定を受け取る

単純な File 送信ポートを使用するには、Azure Event Hub からメッセージを受信します。 

1. ファイル アダプターを使用して送信ポートを作成します。 送信ポートのプロパティ内で、設定、**コピー先フォルダー**に **C:\Temp\Out\**、設定と、および**ファイル名**に **%MessageID%.xml**.
2. 送信ポートのプロパティは、ファイルで、設定、**フィルター**に`BTS.ReceivePortName == EHReceivePort`です。
3. 開始イベント ハブは、場所とファイル送信ポートを受信します。
4. コピー先フォルダー (c:\temp\out) にメッセージを探します。

## <a name="do-more"></a>複数の操作を行います
Event Hubs は、多数の Azure Data Lake、HD Insight など他の Azure サービスへの「フロント ドア」と見なされます。 多数のメッセージを処理し、高速に処理することは想定がします。 Event Hubs とその機能について詳細を参照してください。 

[Event Hubs の機能の概要](https://docs.microsoft.com/azure/event-hubs/event-hubs-features)  
[Event Hubs は何ですか。](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs)
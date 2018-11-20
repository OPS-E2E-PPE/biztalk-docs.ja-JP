---
title: Event Hubs アダプターを使用して、|Microsoft Docs
description: BizTalk Server で Azure Event Hubs アダプターを使用してメッセージを送受信します。
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
ms.openlocfilehash: a1e30b1ab1aacc1c5134d1dd5b44744bd670b308
ms.sourcegitcommit: c3070a7a3f332857357f056dc632829b43869c17
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2018
ms.locfileid: "51630335"
---
# <a name="event-hub-adapter-in-biztalk"></a>BizTalk でイベント ハブのアダプター

## <a name="overview"></a>概要
**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]Feature Pack 2**、BizTalk Server と Azure Event Hubs 間のメッセージを送受信できます。 

Azure Event Hubs は現在は拡張性の高いデータ ストリーミング プラットフォーム、および受信、および数百万の 1 秒あたりのイベントを処理できます。 [Event Hubs とは何ですか。](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs)について詳しく説明します。

## <a name="prerequisites"></a>前提条件

* 作成、 [Azure event hubs 名前空間とイベント ハブ](https://docs.microsoft.com/azure/event-hubs/event-hubs-create)
* 作成、[コンテナーで Azure blob storage アカウント](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account)
* インストール[Feature Pack 2](https://aka.ms/bts2016fp2) BizTalk Server で

イベント ハブが作成し、イベントの送受信に必要な接続文字列があります。

## <a name="send-messages-to-event-hubs"></a>Event Hubs にメッセージを送信します。

1.  右クリックし、BizTalk Server 管理コンソールで**送信ポート**を選択します**新規**、選択と**静的な一方向送信ポート**します。

    [送信ポートを作成](../core/how-to-create-a-send-port2.md)いくつかのガイダンスを提供します。

2. 入力、**名前**します。 **トランスポート**、設定、**型**に**EventHub**を選択し、**構成**します。 

3. 構成、 **Azure アカウント**プロパティ。 

    |プロパティ|目的|  
    |---|---|  
    | **サインイン** | Azure アカウントにサインインします。 |
    | **サブスクリプション** | Event Hubs 名前空間を持つサブスクリプションを選択します |
    | **リソース グループ** | Event Hubs 名前空間を持つリソース グループを選択します |

4. 構成、**エンドポイント**プロパティ。 

    |プロパティ|目的|  
    |---|---|  
    | **Namespace** | Sb ようなものである、Event Hubs 名前空間を選択://*youreventhubnamespace*.servicebus.windows.net/ |
    | **名前** | (これは、Event Hubs 名前空間内で作成された)、イベント ハブの名前を選択します。 |
    | **既定のパーティション キー** | 任意。 [Event Hubs のプログラミング ガイド](https://docs.microsoft.com/azure/event-hubs/event-hubs-programming-guide)このキーの詳細を提供します。 |
    | **[認証]** | **Namespace Access Signature**既定であり、Event Hubs 名前空間を作成するときに作成される RootManageSharedAccessKey は自動的に使用します。<br/><br/>**エンティティ アクセス シグネチャ**SAS ポリシーがイベント ハブのレベル (いない、Event Hubs 名前空間レベル) を作成することができます。 <br/><br/>[Event Hubs の機能概要](https://docs.microsoft.com/azure/event-hubs/event-hubs-features)の詳細について説明します。 |

    完了したらのプロパティは、次のようになります。 

    ![エンドポイントのプロパティ](../core/media/event-hub-endpoint-properties.png)


5. 任意。 構成、**メッセージ**プロパティ。 **ユーザー定義メッセージのプロパティの Namespace**値は、Event Hubs のメッセージ プロパティにマップする BizTalk メッセージのスキーマを表します。

6. 選択**Ok**変更を保存します。 


### <a name="test-your-send-port"></a>送信ポートをテストします。

単純なを使用するファイルの受信ポートと、Azure Event Hub にメッセージを送信する場所。 

1. ファイル アダプターを使用して受信ポートを作成します。 内で、受信場所、設定、**受信フォルダー**に**C:\Temp\In\\**、ファイル マスクを設定 **\*.xml**します。
2. イベント ハブに送信ポートのプロパティは、設定、**フィルター**に`BTS.ReceivePortName == FileReceivePort`します。
3. テキスト エディターに貼り付け、ファイルに保存します**EventHubMessage.xml**します。 これは、サンプル メッセージです。 

    ```xml
    <Data>
      <DataID>DataID_0</DataID>
      <DataDetails>DataDetails_0</DataDetails>
    </Data>
    ```

4. 開始ファイルは、場所とイベント ハブの送信ポートを受信します。
5. コピー **EventHubMessage.xml**受信フォルダーにサンプル メッセージ (C:\Temp\In\)します。 送信ポートは、XML ファイルをイベント ハブに送信します。

## <a name="receive-messages-from-event-hubs"></a>Event Hubs からメッセージを受信します。

1. 右クリックし、BizTalk Server 管理コンソールで**受信ポート**を選択します**新規**、選択と**一方向受信ポート**します。 

    [受信ポートを作成](../core/how-to-create-a-receive-port.md)いくつかのガイダンスを提供します。

2. 名前を入力し、選択**受信場所**します。 

3. 選択**新規**、および**名前**受信場所。 **トランスポート**を選択します**EventHub**から、**型**クリックしてドロップダウン リスト、**構成**します。 

4. 構成、 **Azure アカウント**プロパティ。 

    |プロパティ|目的|  
    |---|---|  
    | **サインイン** | Azure アカウントにサインインします。 |
    | **サブスクリプション** | Event Hubs 名前空間を持つサブスクリプションを選択します |
    | **リソース グループ** | Event Hubs 名前空間を持つリソース グループを選択します |

4. 構成、**エンドポイント**プロパティ。 

    |プロパティ|目的|  
    |---|---|  
    | **Namespace** | Sb ようなものである、Event Hubs 名前空間を選択://*youreventhubnamespace*.servicebus.windows.net/ |
    | **名前** | (これは、Event Hubs 名前空間内で作成された)、イベント ハブの名前を選択します。 |
    | **コンシューマー グループ** | イベント ハブ内でコンシューマー グループを選択します。 既定のグループが自動的に作成されます。 <br/><br/>[Event Hubs の機能概要](https://docs.microsoft.com/azure/event-hubs/event-hubs-features)について詳しく説明します。 |
    | **[認証]** | **Namespace Access Signature**既定であり、Event Hubs 名前空間を作成するときに作成される RootManageSharedAccessKey は自動的に使用します。<br/><br/>**エンティティ アクセス シグネチャ**SAS ポリシーがイベント ハブのレベル (いない、Event Hubs 名前空間レベル) を作成することができます。 <br/><br/>[Event Hubs の機能概要](https://docs.microsoft.com/azure/event-hubs/event-hubs-features)の詳細について説明します。 |

    完了したらのプロパティは、次のようになります。 

    ![エンドポイントのプロパティ](../core/media/event-hub-endpoint-receive-properties.png)

5. 構成、**チェックポイント**プロパティ。 このアダプターは、確実に、チェックポイントを使用してイベントを読み取るし、再起動から再開する、Azure blob ストレージ アカウントを使用します。 

    **ストレージの認証**   
    認証方法を選択します。 通常、Shared Access Signature を使用することをお勧めします。 これは、シナリオに適切な判断に役立つ優れたリソースを次のリンクには。<br/><br/>[Azure ストレージ アカウントについて](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account)<br/>[Shared access signature (SAS) を使用します。](https://docs.microsoft.com/azure/storage/common/storage-dotnet-shared-access-signature-part-1)

    完了したらのプロパティは、次のようになります。 

    ![チェックポイントのプロパティ](../core/media/event-hub-receive-checkpoint.png)

6. 構成、**メッセージ**プロパティ。 

    |プロパティ|目的|  
    |---|---|  
    | **Namespace のユーザー定義メッセージのプロパティ** | `http://schemas.microsoft.com/BizTalk/EventHubAdapter/EventData/User` 既定のスキーマが別のスキーマを入力することができます。 この値は、Event Hubs のメッセージ プロパティにマップする BizTalk メッセージのスキーマを表します。 |
    | **ユーザー定義プロパティを昇格させる** | 任意。 使用する場合は、これらのプロパティを昇格できます。 <br/><br/>**注**<br/>プロパティを昇格させる必要があるが展開 porperty スキーマを持っている必要があります*する前に*イベントを受信します。|

7. 選択**Ok**変更を保存します。 

### <a name="test-your-receive-settings"></a>テストの設定を受け取る

単純な File 送信ポートを使用すると、Azure イベント ハブからメッセージを受信します。 

1. ファイル アダプターを使用して送信ポートを作成します。 送信ポートのプロパティ内で次のように設定します、**先フォルダー**に**C:\Temp\Out\\**、設定、および**ファイル名**に **%MessageID%.xml。**.
2. ファイルの送信ポートのプロパティは、設定、**フィルター**に`BTS.ReceivePortName == EHReceivePort`します。
3. 開始イベント ハブでは、場所とファイルの送信ポートを受信します。
4. 保存先フォルダー (c:\temp\out) にメッセージを探します。

## <a name="do-more"></a>さらに活用します。
Event Hubs は、Azure Data Lake、HD Insight などの他の Azure サービスの多くに「フロント ドア」と見なされます。 大量のメッセージを処理し、高速に処理する設計います。 Event Hubs とその機能についての詳細。 

[Event Hubs の機能の概要](https://docs.microsoft.com/azure/event-hubs/event-hubs-features)  
[Event Hubs とは何ですか。](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs)

---
title: Service Bus メッセージング アダプター |Microsoft ドキュメント
description: BizTalk Server で Azure Sb-messaging アダプターを使用してメッセージの送受信を行う
ms.custom: ''
ms.date: 11/21/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c06c4934-45b2-4f6f-9d19-3ebd937c32ae
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1775606a911d8ce23fd2999ad367053c4f8f72de
ms.sourcegitcommit: f65e8ed2b8c18cded26b9d60868fb6a56bcc1205
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
ms.locfileid: "25497875"
---
# <a name="sb-messaging-adapter"></a>SB-Messaging アダプター
Service Bus (**Sb-messaging**) を受信し、キュー、トピック、およびリレーなどの Service Bus エンティティから送信アダプターを使用します。 使用することができます、 **Sb-messaging**アダプター、内部設置型の接続を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を Azure にします。

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]Feature Pack 2**、Service Bus Premium がサポートされています。 このアダプターを使用して送信ポートを構成するときに、パーティション分割されたキューおよびトピックにメッセージを送信することができます。 

## <a name="authenticating-with-service-bus"></a>Service Bus を使用した認証
Service Bus の認証に 2 つの方法を示します。 

- アクセス制御サービス (ACS) 
- Shared Access Signature (SAS)

Service Bus での認証に Shared Access Signature (SAS) を使用することをお勧めします。 共有アクセス キー値として記載されて、 [Azure ポータル](https://portal.azure.com)です。

Service Bus 名前空間を作成するときに、アクセス制御 (ACS) 名前空間は自動的に作成されません。 アクセス制御を使用して、この名前空間の発行者名および発行者キーの値が必要です。 これらの値は、Windows PowerShell を使用して、新しい ACS 名前空間を作成するときに使用できます。 これらの値は、Azure ポータルでは表示されません。

使用して ACS 認証の発行者名および発行者キーの値を取得、全体的な手順は次のとおりです。

1. インストール、 [Azure Powershell コマンドレット](https://azure.microsoft.com/documentation/articles/powershell-install-configure/)です。
2. Azure アカウントを追加します。`Add-AzureAccount`
3. サブスクリプション名が返されます。`get-azuresubscription`
4. お客様のサブスクリプションを選択します。`select-azuresubscription <name of your subscription>` 
5. 新しい名前空間を作成します。`new-azuresbnamespace <name for the service bus> "Location" -CreateACSNamespace $true -NamespaceType Messaging`

    例:`new-azuresbnamespace biztalksbnamespace "South Central US" -CreateACSNamespace $true -NamespaceType Messaging`
      
5. 新しい ACS 名前空間が作成されると (これは、数分かかる場合が)、IssuerName と IssuerKey の値が、接続文字列に表示されます。 

    ```
    Name                  : biztalksbnamespace
    Region                : South Central US
    DefaultKey            : abcdefghijklmnopqrstuvwxyz
    Status                : Active
    CreatedAt             : 10/18/2016 9:36:30 PM
    AcsManagementEndpoint : https://biztalksbnamespace-sb.accesscontrol.windows.net/
    ServiceBusEndpoint    : https://biztalksbnamespace.servicebus.windows.net/
    ConnectionString      : Endpoint=sb://biztalksbnamespace.servicebus.windows.net/;SharedSecretIssuer=owner;SharedSecretValue=abcdefghijklmnopqrstuvwxyz
    NamespaceType         : Messaging
    ```

参照してください[New-azuresbnamespace](https://docs.microsoft.com/powershell/module/Azure/New-AzureSBNamespace)のガイダンスについてはします。

## <a name="receive-messages-from-service-bus"></a>Service Bus からメッセージを受信します。
  
1. BizTalk Server 管理コンソールで、展開**BizTalk グループ**、展開**アプリケーション**、し、アプリケーションを展開します。 

2. 右クリック**受信ポート****新規**を選択し、**一方向受信ポート**です。 

3. クリックし、名前を付けます**受信場所**です。 

4. 選択**新規**、付けます、**名前**です。 **トランスポート**セクションで、 **Sb-messaging**から、**型**クリックしてドロップダウン リスト、**構成**です。  
  
5. 構成、**全般**プロパティ。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**キューまたはサブスクリプションの URL**|Service Bus キューを展開する URL を指定します。 通常、URL は次のような形式になっています。<br /><br /> `sb://<namespace>.servicebus.windows.net/<queue_name>`|  
    |**オープン タイムアウト**|チャネルを開く操作が完了するまでの時間を示す期間値を指定します。<br /><br /> **既定値:** 1 分|  
    |**クローズ タイムアウト**|チャネルを閉じる操作が完了するまでの時間を示す期間値を指定します。<br /><br /> **既定値:** 1 分|  
    |**受信タイムアウト**|受信操作が完了するまでの時間を示す期間値を指定します。<br /><br /> **既定値:** 10 分|  
    |**プリフェッチ数**|Service Bus キューまたはトピックから同時に受信するメッセージの数を指定します。 プリフェッチにより、キューまたはサブスクリプション クライアントは、受信操作を実行するときにサービスから追加のメッセージを読み込むことができます。 クライアントはこれらのメッセージをローカル キャッシュに格納します。 キャッシュのサイズは、ここで指定する [プリフェッチ数] プロパティの値によって決まります。<br /><br /> 詳細については、セクションを参照してください「プリフェッチ」 [https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements/](https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements/)<br /><br /> **既定値:** -1|  
    |**セッションを使用します。**|Service Bus セッションを使用してキューまたはサブスクリプションからメッセージを受信する場合は、このチェック ボックスをオンにします。|  
  
6.  構成、**認証**プロパティ。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**アクセス制御サービス**|認証に ACS を使用するにはこれを選択して次の値を指定します:<br /><br /> Service Bus アクセス制御サービス STS URI を入力します。 通常、URI は次のような形式になっています。<br /><br /> `https://<namespace>-sb.accesscontrol.windows.net/`<br /><br /> Service Bus 名前空間の発行者名を入力します。<br /><br /> Service Bus 名前空間の発行者キーを入力します。|  
    |**Shared Access Signature** (で始まる新しい[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)])|認証に Shared Access Signature (SAS) を使用する場合はこれを選択し、SAS キーの名前とキーの値を指定します。|  
  
7.  **プロパティ**] タブの [、**ブローカー メッセージのプロパティの Namespace**、アダプターのメッセージ コンテキスト プロパティとしてブローカー メッセージのプロパティを作成に使用する名前空間を入力しますによって受信されたメッセージ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 仲介型メッセージのプロパティを昇格する場合は、選択、**仲介型メッセージ プロパティの昇格**チェック ボックスをオンします。  
  
8.  **[OK]** を選択します。  
  
9. 選択、**受信ハンドラー**、および**受信パイプライン**です。 **[OK]** を選択して変更を保存します。 [受信場所を作成](../core/how-to-create-a-receive-location.md)のガイダンスを紹介します。  
  
## <a name="send-messages-to-service-bus"></a>Service Bus にメッセージを送信します。
  
1.  BizTalk Server 管理コンソールを右クリックして**送信ポート****新規**を選択し、**静的な一方向送信ポート**です。

    [送信ポートを作成](../core/how-to-create-a-send-port2.md)のガイダンスを紹介します。

2. 入力、**名前**です。 **トランスポート**、設定、**型**に**Sb-messaging**を選択して**構成**です。 
  
3.  構成、**全般**プロパティ。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**送信先 URL**|Service Bus キューが配置されている URL を入力します。 通常、URL は次のような形式になっています。<br /><br /> `sb://<namespace>.servicebus.windows.net/<queue_name>`|  
    |**バッチのフラッシュ間隔**|キューまたはトピックに送られたメッセージ バッチがフラッシュされる間隔を示す期間値を指定します。 既定値は、20 ミリ秒です。<br /><br /> Service Bus キューおよびトピックに関するバッチ処理の詳細については、次を参照してください。、**クライアント側のバッチ処理**セクションで[https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements](https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements)です。|  
    |**オープン タイムアウト**|チャネルを開く操作が完了するまでの時間を示す期間値を指定します。<br /><br /> **既定値:** 1 分|  
    |**送信タイムアウト**|送信操作が完了するまでの時間を示す期間値を指定します。<br /><br /> **既定値:** 1 分|  
    |**クローズ タイムアウト**|チャネルを閉じる操作が完了するまでの時間を示す期間値を指定します。<br /><br /> **既定値:** 1 分|  
  
4.  構成、**認証**プロパティ。 
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**アクセス制御サービス**|認証に ACS を使用するにはこれを選択して次の値を指定します:<br /><br /> Service Bus アクセス制御サービス STS URI を入力します。 通常、URI は次のような形式になっています。<br /><br /> `https://<namespace>-sb.accesscontrol.windows.net/`<br /><br /> Service Bus 名前空間の発行者名を入力します。<br /><br /> Service Bus 名前空間の発行者キーを入力します。|  
    |**Shared Access Signature** (で始まる新しい[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)])|認証に Shared Access Signature (SAS) を使用する場合はこれを選択し、SAS キーの名前とキーの値を指定します。|  
  
5.  **プロパティ** タブで、入力、 **Namespace のユーザーには、ブローカー メッセージのプロパティが定義されている**への送信メッセージを記述する BizTalk メッセージ コンテキスト プロパティを格納しています。Service Bus。 名前空間のすべてのプロパティは、ユーザー定義ブローカー メッセージのプロパティとしてメッセージに書き込まれます。 アダプターは、プロパティをブローカー メッセージのプロパティとして書き込むときに、この名前空間を無視します。 この名前空間は、書き込むプロパティを確認するためにのみ使用されます。  
  
     BrokeredMessage プロパティの値を入力することもできます。 これらのプロパティが説明されている[BrokeredMessage プロパティ](https://docs.microsoft.com/dotnet/api/microsoft.servicebus.messaging.brokeredmessage)など、**パーティション キー**です。
  
6.  **[OK]** を選択して変更を保存します。  
  
## <a name="see-also"></a>参照
[アダプターを使用します。](../core/using-adapters.md)
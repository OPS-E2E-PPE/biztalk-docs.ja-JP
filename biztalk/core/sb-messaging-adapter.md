---
title: Service Bus メッセージング アダプター |Microsoft Docs
description: BizTalk Server で Azure SB Messaging アダプターを使用してメッセージの送受信
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
ms.openlocfilehash: d050a2f2b4435daa0ea2bff8b7f2a2f19456d624
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65309419"
---
# <a name="sb-messaging-adapter"></a>SB-Messaging アダプター
Service Bus (**Sb-messaging**) を受信し、キュー、トピック、およびリレーなど、Service Bus エンティティから送信アダプターが使用されます。 使用することができます、 **Sb-messaging**アダプターで、オンプレミスの接続を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を Azure にします。

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]Feature Pack 2**、Service Bus Premium はサポートされています。 このアダプターを使用して送信ポートを構成する場合は、パーティション分割されたキューおよびトピックにメッセージを送信できます。 

## <a name="authenticating-with-service-bus"></a>Service Bus を使用した認証
Service Bus は、認証に 2 つのメソッドを提供します。 

- Access Control Service (ACS) 
- Shared Access Signature (SAS)

Service Bus での認証に Shared Access Signature (SAS) を使用することをお勧めします。 共有アクセス キーの値が記載されて、 [Azure portal](https://portal.azure.com)します。

Service Bus 名前空間を作成するときに、Access Control (ACS) 名前空間は自動的に作成されません。 アクセス制御を使用するには、この名前空間の発行者名および発行者キーの値が必要です。 これらの値は、Windows PowerShell を使用して、新しい ACS 名前空間を作成するときに使用できます。 これらの値は、Azure portal では表示されません。

で ACS を使用して認証をして、発行者名および発行者キーの値を取得するには、全体的な手順は次のとおりです。

1. インストール、 [Azure Powershell コマンドレット](https://azure.microsoft.com/documentation/articles/powershell-install-configure/)します。
2. Azure アカウントを追加します。 `Add-AzureAccount`
3. サブスクリプション名が返されます。 `get-azuresubscription`
4. サブスクリプションを選択します。 `select-azuresubscription <name of your subscription>` 
5. 新しい名前空間を作成します。 `new-azuresbnamespace <name for the service bus> "Location" -CreateACSNamespace $true -NamespaceType Messaging`

    例:    `new-azuresbnamespace biztalksbnamespace "South Central US" -CreateACSNamespace $true -NamespaceType Messaging`

5. 新しい ACS 名前空間には、(これは、数分かかる場合) が作成されると、IssuerName と IssuerKey の値は、接続文字列に表示されます。 

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

1. BizTalk Server 管理コンソールで  **BizTalk グループ**、展開**アプリケーション**、アプリケーションを展開します。 

2. 右クリック**受信ポート**を選択します**新規**、選び**一方向受信ポート**します。 

3. 場合、名前を付けるし、選択**受信場所**します。 

4. 選択**新規**、試して、**名前**。 **トランスポート**セクションで、 **Sb-messaging**から、**型**クリックしてドロップダウン リスト、**構成**します。  

5. 構成、**全般**プロパティ。  


   |           プロパティ            |                                                                                                                                                                                                                                                                                                                                              目的                                                                                                                                                                                                                                                                                                                                               |
   |-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **キューまたはサブスクリプション URL** |                                                                                                                                                                                                                                                               Service Bus キューを展開する URL を指定します。 通常、URL は次のような形式になっています。<br /><br /> `sb://<namespace>.servicebus.windows.net/<queue_name>`                                                                                                                                                                                                                                                               |
   |       **オープン タイムアウト**        |                                                                                                                                                                                                                                                                                 チャネルを開く操作が完了するまでの時間を示す期間値を指定します。<br /><br /> **既定値:** 1 分                                                                                                                                                                                                                                                                                 |
   |       **クローズ タイムアウト**       |                                                                                                                                                                                                                                                                                チャネルを閉じる操作が完了するまでの時間を示す期間値を指定します。<br /><br /> **既定値:** 1 分                                                                                                                                                                                                                                                                                 |
   |      **受信タイムアウト**      |                                                                                                                                                                                                                                                                                  受信操作が完了するまでの時間を示す期間値を指定します。<br /><br /> **既定値:** 10 分                                                                                                                                                                                                                                                                                   |
   |      **プリフェッチ数**       | Service Bus キューまたはトピックから同時に受信するメッセージの数を指定します。 プリフェッチにより、キューまたはサブスクリプション クライアントは、受信操作を実行するときにサービスから追加のメッセージを読み込むことができます。 クライアントはこれらのメッセージをローカル キャッシュに格納します。 キャッシュのサイズは、ここで指定する [プリフェッチ数] プロパティの値によって決まります。<br /><br /> 詳細については、セクションを参照してくださいでは、「プリフェッチ」 [https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements/](https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements/)<br /><br /> **既定値:** -1 |
   |        **セッションを使用します。**        |                                                                                                                                                                                                                                                                                                Service Bus セッションを使用してキューまたはサブスクリプションからメッセージを受信する場合は、このチェック ボックスをオンにします。                                                                                                                                                                                                                                                                                                 |


6. 構成、**認証**プロパティ。  


   |                                               プロパティ                                                |                                                                                                                                                                                             目的                                                                                                                                                                                             |
   |-------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                                      **Access Control Service**                                       | 認証に ACS を使用するにはこれを選択して次の値を指定します:<br /><br /> -Service Bus アクセス制御サービス STS URI を入力します。 通常、URI は次のような形式になっています。<br /><br /> `https://<namespace>-sb.accesscontrol.windows.net/`<br /><br /> -Service Bus 名前空間の発行者名を入力します。<br /><br /> -Service Bus 名前空間の発行者キーを入力します。 |
   | **Shared Access Signature** (以降では新しい[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]) |                                                                                                                                          認証に Shared Access Signature (SAS) を使用する場合はこれを選択し、SAS キーの名前とキーの値を指定します。                                                                                                                                          |


7. **プロパティ** タブで、**ブローカー メッセージのプロパティの Namespace**、アダプターのメッセージ コンテキスト プロパティとしてブローカー メッセージのプロパティを作成に使用する名前空間を入力してください、受信したメッセージ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 仲介型メッセージのプロパティを昇格する場合は、選択、**仲介型メッセージ プロパティの昇格**チェック ボックスをオンします。  

8. **[OK]** を選択します。  

9. 選択、**受信ハンドラー**、および**受信パイプライン**します。 **[OK]** を選択して変更を保存します。 [受信場所を作成](../core/how-to-create-a-receive-location.md)いくつかのガイダンスを提供します。  

## <a name="send-messages-to-service-bus"></a>Service Bus にメッセージを送信します。

1. 右クリックし、BizTalk Server 管理コンソールで**送信ポート**を選択します**新規**、選択と**静的な一方向送信ポート**します。

   [送信ポートを作成](../core/how-to-create-a-send-port2.md)いくつかのガイダンスを提供します。

2. 入力、**名前**します。 **トランスポート**、設定、**型**に**Sb-messaging**を選択し、**構成**します。 

3. 構成、**全般**プロパティ。  


   |         プロパティ         |                                                                                                                                                                                                                                             目的                                                                                                                                                                                                                                              |
   |--------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |   **送信先 URL**    |                                                                                                                                                               Service Bus キューを配置する場所の URL を入力します。 通常、URL は次のような形式になっています。<br /><br /> `sb://<namespace>.servicebus.windows.net/<queue_name>`                                                                                                                                                               |
   | **バッチのフラッシュ間隔** | キューまたはトピックに送られたメッセージ バッチがフラッシュされる間隔を示す期間値を指定します。 既定値は、20 ミリ秒です。<br /><br /> Service Bus キューおよびトピックに関するバッチ処理の詳細については、次を参照してください。、**クライアント側のバッチ処理**セクションで[ https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements](https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements)します。 |
   |     **オープン タイムアウト**     |                                                                                                                                                                                チャネルを開く操作が完了するまでの時間を示す期間値を指定します。<br /><br /> **既定値:** 1 分                                                                                                                                                                                |
   |     **送信タイムアウト**     |                                                                                                                                                                                    送信操作が完了するまでの時間を示す期間値を指定します。<br /><br /> **既定値:** 1 分                                                                                                                                                                                    |
   |    **クローズ タイムアウト**     |                                                                                                                                                                               チャネルを閉じる操作が完了するまでの時間を示す期間値を指定します。<br /><br /> **既定値:** 1 分                                                                                                                                                                                |


4. 構成、**認証**プロパティ。 


   |                                               プロパティ                                                |                                                                                                                                                                                             目的                                                                                                                                                                                             |
   |-------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                                      **Access Control Service**                                       | 認証に ACS を使用するにはこれを選択して次の値を指定します:<br /><br /> -Service Bus アクセス制御サービス STS URI を入力します。 通常、URI は次のような形式になっています。<br /><br /> `https://<namespace>-sb.accesscontrol.windows.net/`<br /><br /> -Service Bus 名前空間の発行者名を入力します。<br /><br /> -Service Bus 名前空間の発行者キーを入力します。 |
   | **Shared Access Signature** (以降では新しい[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]) |                                                                                                                                          認証に Shared Access Signature (SAS) を使用する場合はこれを選択し、SAS キーの名前とキーの値を指定します。                                                                                                                                          |


5. **プロパティ** タブで、入力、 **Namespace のユーザーには、ブローカー メッセージのプロパティが定義されている**への送信メッセージを記述する BizTalk メッセージ コンテキストのプロパティを格納しています。Service Bus。 名前空間のすべてのプロパティは、ユーザー定義ブローカー メッセージのプロパティとしてメッセージに書き込まれます。 アダプターは、プロパティをブローカー メッセージのプロパティとして書き込むときに、この名前空間を無視します。 この名前空間は、書き込むプロパティを確認するためにのみ使用されます。  

    BrokeredMessage プロパティの値を入力することもできます。 これらのプロパティの説明にある[BrokeredMessage プロパティ](https://docs.microsoft.com/dotnet/api/microsoft.servicebus.messaging.brokeredmessage)など、**パーティション キー**します。

6. **[OK]** を選択して変更を保存します。  

## <a name="see-also"></a>参照
[アダプターを使用します。](../core/using-adapters.md)
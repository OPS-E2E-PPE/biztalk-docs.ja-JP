---
title: "Sb-messaging アダプター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c06c4934-45b2-4f6f-9d19-3ebd937c32ae
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fb2eb8f532d72708dfca199f0eef794afdf77df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sb-messaging-adapter"></a>SB-Messaging アダプター
Service Bus (**Sb-messaging**) を受信し、キュー、トピック、およびリレーなどの Service Bus エンティティから送信アダプターを使用します。 使用することができます、 **Sb-messaging**アダプター間の接続を確立する[!INCLUDE[winazure](../includes/winazure-md.md)]と内部設置型[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]これにより、一般的なハイブリッド アプリケーションを作成するユーザーを有効にするとします。 このセクションのトピックでは、手順を構成する方法について説明、 **Sb-messaging**受信場所および送信ポートを受信し、Service Bus エンティティからメッセージを送信します。  

## <a name="before-you-get-started"></a>始める前に
Service Bus の認証に 2 つのメソッドを提供します。 アクセス制御サービス (ACS) と Shared Access Signature (SAS)。 Service Bus の認証に Shared Access Signature (SAS) を使用するにはお勧めします。 共有アクセス キー値として記載されて、 [Azure ポータル](https://portal.azure.com)です。

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
[新しい AzureSBNamespace](https://msdn.microsoft.com/library/dn495165.aspx)

## <a name="receive-messages-from-service-bus"></a>Service Bus からメッセージを受信します。
  
このセクションで構成する方法に関する情報を提供する、 **Sb-messaging**受信場所を使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
> [!NOTE]
>  次の手順を完了する前にする必要がありますが既に追加して、一方向受信ポート。 参照してください[受信ポートを作成する方法](../core/how-to-create-a-receive-port.md)です。  

 
1.  BizTalk Server 管理コンソールで、 [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**アプリケーションを展開し、受信場所を作成する です。  
  
2.  左側のウィンドウで、[ **受信ポート** ] ノードをクリックし、右側のウィンドウで、新しい受信場所に関連付ける受信ポートを右クリックし、[ **プロパティ**] をクリックします。  
  
3.  [ **受信ポートのプロパティ** ] ダイアログ ボックスの左側のウィンドウで [ **受信場所**] を選択し、右側のウィンドウで [ **新規作成** ] をクリックして、新しい受信場所を作成します。  
  
4.  **受信場所のプロパティ** ダイアログ ボックスで、**トランスポート**セクションで、 **Sb-messaging**から、**型**ドロップダウン リスト、をクリックして**構成**受信場所のトランスポートのプロパティを構成します。  
  
5.  **Sb-messaging トランスポートのプロパティ** ダイアログ ボックスで、**全般** タブで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**キューまたはサブスクリプションの URL**|Service Bus キューを展開する URL を指定します。 通常、URL は次のような形式になっています。<br /><br /> `sb://<namespace>.servicebus.windows.net/<queue_name>`|  
    |**オープン タイムアウト**|チャネルを開く操作が完了するまでの時間を示す期間値を指定します。<br /><br /> **既定値:** 1 分|  
    |**クローズ タイムアウト**|チャネルを閉じる操作が完了するまでの時間を示す期間値を指定します。<br /><br /> **既定値:** 1 分|  
    |**受信タイムアウト**|受信操作が完了するまでの時間を示す期間値を指定します。<br /><br /> **既定値:** 10 分|  
    |**プリフェッチ数**|Service Bus キューまたはトピックから同時に受信するメッセージの数を指定します。 プリフェッチにより、キューまたはサブスクリプション クライアントは、受信操作を実行するときにサービスから追加のメッセージを読み込むことができます。 クライアントはこれらのメッセージをローカル キャッシュに格納します。 キャッシュのサイズは、ここで指定する [プリフェッチ数] プロパティの値によって決まります。<br /><br /> 詳細については、セクションを参照してください「プリフェッチ」 [https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements/](https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements/)<br /><br /> **既定値:** -1|  
    |**セッションを使用します。**|Service Bus セッションを使用してキューまたはサブスクリプションからメッセージを受信する場合は、このチェック ボックスをオンにします。|  
  
6.  **認証** タブで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**アクセス制御サービス**|認証に ACS を使用するにはこれを選択して次の値を指定します:<br /><br /> Service Bus アクセス制御サービス STS URI を入力します。 通常、URI は次のような形式になっています。<br /><br /> `https://<namespace>-sb.accesscontrol.windows.net/`<br /><br /> Service Bus 名前空間の発行者名を入力します。<br /><br /> Service Bus 名前空間の発行者キーを入力します。|  
    |**Shared Access Signature** (で始まる新しい[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)])|認証に Shared Access Signature (SAS) を使用する場合はこれを選択し、SAS キーの名前とキーの値を指定します。|  
  
7.  **プロパティ** タブで、**ブローカー メッセージのプロパティの Namespace**フィールドに、アダプターのメッセージ コンテキスト プロパティとしてブローカー メッセージのプロパティを作成に使用する名前空間を指定受信したメッセージ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 さらに、仲介型メッセージのプロパティを昇格する場合は、選択、**仲介型メッセージ プロパティの昇格**チェック ボックスをオンします。  
  
8.  **[OK]**をクリックします。  
  
9. [ **受信場所のプロパティ** ] ダイアログ ボックスで、受信場所を構成するための適切な値を入力し、[ **OK** ] をクリックして設定を保存します。 については、**受信場所のプロパティ**ダイアログ ボックスを参照してください[受信場所を作成する方法](../core/how-to-create-a-receive-location.md)です。  
  
## <a name="send-messages-to-service-bus"></a>Service Bus にメッセージを送信します。
このセクションで構成する方法に関する情報を提供する、 **Sb-messaging**送信ポートを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
1.  BizTalk Server 管理コンソールで、新しい送信ポートを作成または変更する既存の送信ポートをダブルクリックします。 詳細については、次を参照してください。[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)です。 すべての送信ポートのオプションを構成し、指定**Sb-messaging**の**型**オプション、**トランスポート**のセクションで、**全般**タブ  
  
2.  **全般**] タブの [、**トランスポート**セクションで、をクリックして、**構成**ボタンをクリックします。  
  
3.  **Sb-messaging トランスポートのプロパティ** ダイアログ ボックスで、**全般** タブで、次の指定します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**送信先 URL**|Service Bus キューが配置されている URL を入力します。 通常、URL は次のような形式になっています。<br /><br /> `sb://<namespace>.servicebus.windows.net/<queue_name>`|  
    |**バッチのフラッシュ間隔**|キューまたはトピックに送られたメッセージ バッチがフラッシュされる間隔を示す期間値を指定します。 既定値は、20 ミリ秒です。<br /><br /> Service Bus キューおよびトピックに関するバッチ処理の詳細については、次を参照してください。、**クライアント側のバッチ処理**セクションで[https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements](https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements)です。|  
    |**オープン タイムアウト**|チャネルを開く操作が完了するまでの時間を示す期間値を指定します。<br /><br /> **既定値:** 1 分|  
    |**送信タイムアウト**|送信操作が完了するまでの時間を示す期間値を指定します。<br /><br /> **既定値:** 1 分|  
    |**クローズ タイムアウト**|チャネルを閉じる操作が完了するまでの時間を示す期間値を指定します。<br /><br /> **既定値:** 1 分|  
  
4.  **認証** タブで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**アクセス制御サービス**|認証に ACS を使用するにはこれを選択して次の値を指定します:<br /><br /> Service Bus アクセス制御サービス STS URI を入力します。 通常、URI は次のような形式になっています。<br /><br /> `https://<namespace>-sb.accesscontrol.windows.net/`<br /><br /> Service Bus 名前空間の発行者名を入力します。<br /><br /> Service Bus 名前空間の発行者キーを入力します。|  
    |**Shared Access Signature** (で始まる新しい[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)])|認証に Shared Access Signature (SAS) を使用する場合はこれを選択し、SAS キーの名前とキーの値を指定します。|  
  
5.  **プロパティ**] タブの [、 **Namespace のユーザーには、ブローカー メッセージのプロパティが定義されている**フィールドに、として記述する BizTalk メッセージ コンテキスト プロパティを含む名前空間の指定ユーザー定義ブローカー メッセージのプロパティ、Service Bus キューに送る送信メッセージにします。 この名前空間に属しているすべてのプロパティは、ユーザー定義ブローカー メッセージのプロパティとしてメッセージに書き込まれます。 アダプターは、プロパティをブローカー メッセージのプロパティとして書き込むときに、この名前空間を無視します。 この名前空間は、書き込むプロパティを確認するためにのみ使用されます。  
  
     BrokeredMessage プロパティの値を指定することもできます。 プロパティの詳細については、次を参照してください。 [BrokeredMessage プロパティ](https://msdn.microsoft.com/library/azure/microsoft.servicebus.messaging.brokeredmessage_properties.aspx)です。  
  
6.  をクリックして**[ok]**と**OK**もう一度設定を保存します。  
  
## <a name="see-also"></a>参照
[アダプターを使用します。](../core/using-adapters.md)
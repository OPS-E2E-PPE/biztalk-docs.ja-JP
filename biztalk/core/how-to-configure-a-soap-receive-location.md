---
title: SOAP 受信場所を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [SOAP adapters], virtual directories
- SOAP adapters, code samples
- configuring [SOAP adapters], receive locations
- virtual directories, SOAP adapters
- SOAP adapters, receive locations
- code samples, SOAP adapters
- configuring [SOAP adapters], code samples
- SOAP adapters, virtual directories
- receive locations, SOAP adapters
ms.assetid: 7e348409-9181-47e4-b3c0-c73eb2acffa3
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4de95a4d414cddde0812f590c84c237866772741
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999267"
---
# <a name="how-to-configure-a-soap-receive-location"></a>SOAP の受信場所を構成する方法
SOAP の受信場所は、プログラムから、または [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して構成できます。  

 **SOAP 受信場所構成するプログラムを使用する方法**  

 オブジェクト モデルでは、作成および構成することができます、BizTalk エクスプ ローラーは受信場所をプログラムでします。 BizTalk エクスプローラ オブジェクト モデルを公開、**という**受信場所の構成インターフェイスを持つ、 **TransportTypeData**読み取り/書き込みプロパティ。 このプロパティでは、名前と値の組の XML 文字列の形式で SOAP の受信場所の構成プロパティ バッグを指定できます。 BizTalk エクスプ ローラー オブジェクト モデルでこのプロパティを設定するに設定する必要があります、 **InboundTransportLocation**のプロパティ、**という**インターフェイス。  

 **TransportTypeData**のプロパティ、**という**インターフェイスを設定する必要はありません。 このプロパティを設定しない場合、SOAP アダプターでは、次の表に記載されている SOAP 受信場所の構成の既定値が使用されます。  

 次の表に、BizTalk エクスプローラーのオブジェクト モデルで SOAP 受信場所用に設定できる構成プロパティを示します。  

|プロパティ名|型|説明|  
|-------------------|----------|-----------------|  
|**URI**|String|展開サーバーの Web サービスを含んでいる仮想ディレクトリです。|  
|**AddressableURI**|String|呼び出し可能な URL 全体を含むパブリック アドレス フィールドです。<br /><br /> 既定値: 空白|  
|**UseSSO**|ブール値|SOAP アダプターが、この受信場所で受信するメッセージにシングル サインオン チケットを発行するかどうかを指定します。<br /><br /> 既定値: False|  

 これらのプロパティを設定するには、以下の形式を使用します。  

```  
receiveLocation.TransportTypeData = "<CustomProps><UseSSO vt=\"11\">-1</UseSSO></CustomProps>";  
```  

 **URI**と**AddressableURI**を使用してプロパティを設定、**アドレス**と**PublicAddress**受信場所のプロパティオブジェクト。  

 次のコードは、SOAP 受信場所の作成方法を示しています。  

```  
// Use BizTalk Explorer object model to create new SOAP receive location.  
string server = System.Environment.MachineName;  
string database = "BizTalkMgmtDb";  
string connectionString = string.Format("Server={0};Database={1};Integrated Security=true", server, database);  
//requires project reference to \Program Files\Microsoft BizTalk Server 2009\Developer Tools\Microsoft.BizTalk.ExplorerOM.dll  
BtsCatalogExplorer explorer = new Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer();  
explorer.ConnectionString = connectionString;  

// Add a new Request-Response port  
ReceivePort receivePort = explorer.AddNewReceivePort(true);  
receivePort.Name = "SampleReceivePort";  
receivePort.SendPipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruTransmit"];  

// Add primary SOAP receive location  
ReceiveLocation receiveLocation = receivePort.AddNewReceiveLocation();  
receiveLocation.Name = "SampleReceiveLocation";  
receiveLocation.Address = "/PurchaseOrder/POOrchestration.asmx";  
receiveLocation.TransportType = explorer.ProtocolTypes["SOAP"];  
receiveLocation.TransportTypeData = "<CustomProps><UseSSO vt=\"11\">-1</UseSSO></CustomProps>";  
receiveLocation.ReceivePipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruReceive"];  
foreach (ReceiveHandler receiveHandler in explorer.ReceiveHandlers)  
{  
if (receiveHandler.TransportType.Name == receiveLocation.TransportType.Name)  
{  
receiveLocation.ReceiveHandler = receiveHandler;   
}  
}  

// Save  
explorer.SaveChanges();   
```  

 **SOAP 受信場所を BizTalk Server 管理コンソールを構成する方法**  

 SOAP の受信場所のアダプター変数は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで設定できます。 受信場所のプロパティが設定されていない場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで設定された既定の受信ハンドラーの値が使用されます。  

> [!NOTE]
>  次の手順を実行する前に、受信ポートを追加しておく必要があります。 詳細については、次を参照してください。[受信ポートを作成する方法](../core/how-to-create-a-receive-port.md)します。  

### <a name="to-configure-variables-for-a-soap-receive-location"></a>SOAP の受信場所の変数を構成するには  

1. BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**の順に展開し、受信場所を作成するアプリケーション。  

2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、左側のウィンドウで、**受信ポート**ノード。 次に右ウィンドウで、既存の受信場所に関連付けられているか、新しい受信場所に関連付ける受信ポートを右クリックし、**[プロパティ]** をクリックします。  

3. **受信ポートのプロパティ**ダイアログ ボックスで、左側のウィンドウで、**受信場所**、右側のウィンドウは、既存の受信場所] をクリックしてまたはダブルクリックし [**新規**、新しい受信場所を作成します。  

4. **受信場所のプロパティ** ダイアログ ボックスで、**トランスポート**の横**型**を選択します**SOAP**ドロップダウン リストからクリックして**構成**します。  

5. **SOAP トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  


   |                     プロパティ                      |                                                                                                                                                                                                                                                                                                              目的                                                                                                                                                                                                                                                                                                               |
   |---------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **仮想ディレクトリと Web サービス .asmx ファイル** |                                                                                                                 Microsoft BizTalk Web サービス公開ウィザードで作成された .asmx ファイルを示します。<br /><br /> このメッセージの形式は次のようになります。 <br /><br /> /PurchaseOrder/POOrchestration.asmx<br /><br /> .Asmx ファイルの完全な場所はhttp://localhost/PurchaseOrder/POOrchestration.asmxします。 **注:** の URI を送信ポートまたは受信場所が 256 文字を超えることはできません。                                                                                                                 |
   |                **パブリック アドレス**                 | この受信場所の完全修飾 URI を指定します。 このプロパティの値は、サーバー名と仮想ディレクトリの組み合わせです。 指定した URI は、取引先が [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にメッセージを送信するときに接続するパブリック Web サイトの URL を示す必要があります。<br /><br /> この情報は省略可能であり、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では使用されません。 このパラメーターを使用すると、管理者は、受信場所が関連付けられているパブリック URL を記述できます。 |
   |              **シングル サインオンの使用**               |                                                                                                                                                                                                 SOAP アダプターがエンタープライズ シングル サインオンを使用することを示します。 **注:** BizTalk Web サービス公開ウィザードでは、SharePoint Portal Server シングル サインオンを使用できます。 は、このプロパティは、エンタープライズ シングル サインオンのみ有効です。                                                                                                                                                                                                 |


6. **[OK]** をクリックします。  

7. **受信場所のプロパティ** ダイアログ ボックスで、クリックして、受信場所の構成を完了するには、適切な値を入力して**OK**設定を保存します。 については、**受信場所のプロパティ**ダイアログ ボックスを参照してください[受信場所を作成する方法](../core/how-to-create-a-receive-location.md)します。  

   SOAP の受信場所で使用されるセキュリティ設定は IIS で設定します。 既定では、SOAP の受信場所は、匿名認証を使用するように設定されていません。  

   SOAP クライアントが Web サービスを呼び出すと、SOAP アダプターでは、匿名認証、基本認証、ダイジェスト認証、または Windows 統合認証を使用して SOAP クライアントを認証します。 ユーザーが確認されると、受信ハンドラーにユーザー コンテキストが渡されます。  

> [!NOTE]
>  同一プロセスを共有する SOAP と HTTP を使用する IIS 構成は無効です。 プロセスごとに 1 つの分離受信場所のみを指定できます。  

### <a name="to-update-a-virtual-directory-to-use-aspnet-40"></a>ASP.NET 4.0 を使用する仮想ディレクトリを更新するには  

1.  インターネット インフォメーション サービス (IIS) マネージャーを起動します。 クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリック**インターネット インフォメーション サービス (IIS) マネージャー**します。  

2.  リモートの IIS サーバーに接続する場合は、右クリックして、**インターネット インフォメーション サービス**ノードをクリック**Connect**します。  

3.  リモートの IIS サーバーのコンピューター名を入力し、必要な場合は資格情報を入力します。  

4.  設定を更新する Web サイトまたは仮想ディレクトリをホストしているサーバー名を展開します。  

5.  展開**サイト**します。  

6.  展開**Default Web Site**します。  

7.  規定の Web サイトを展開し、Web サイトの下にある仮想ディレクトリを表示します。  

8.  クリックして、ASP.NET 4.0 を使用して更新する仮想ディレクトリを右クリックして**アプリケーションの管理**、 をクリックし、**詳細設定**します。 **アプリケーション プール**フィールドが選択されている仮想ディレクトリの設定、アプリケーション プールが表示されます。 **[OK]** をクリックします。  

9. [インターネット インフォメーション サービス (IIS) マネージャー] ウィンドウで、次のようにクリックします。**アプリケーション プール**します。 詳細ペインに、サーバーのアプリケーション プールの一覧が表示されます。  

10. 手順 8. でアプリケーション プールのセットを右クリックし、をクリックし、**基本設定**します。  

11. **アプリケーション プールの編集** ダイアログ ボックスで、次の変更します。  

    -   **.NET framework のバージョン**に**4.0**  

    -   **マネージ パイプライン モード**に**クラシック**  

12. クリックして**OK**変更を適用します。  

## <a name="see-also"></a>参照  
 [Web サービスの利用](../core/consuming-web-services.md)
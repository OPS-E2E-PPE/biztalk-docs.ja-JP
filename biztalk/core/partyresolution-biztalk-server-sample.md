---
title: PartyResolution (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, parties
- orchestrations, examples
- parties, examples
- parties, orchestrations
- examples, routing
- orchestrations, parties
- examples, orchestrations
- examples, messages
- routing, messages
- messages, routing
ms.assetid: 220e6bc5-6f04-4f37-b0d0-f11c2cc14422
caps.latest.revision: 33
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35334b61199d758a5eafe8623ea576a047799925
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984435"
---
# <a name="partyresolution-biztalk-server-sample"></a>PartyResolution (BizTalk Server サンプル)
PartyResolution サンプルは、パーティの解決で BizTalk オーケストレーションを使用して、2 つのうちいずれかの受信側にメッセージをルーティングする方法を示すものです。  

## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、次に示す複数のオーケストレーションがそれぞれのロールを実行します。  

-   購入側のオーケストレーション : 注文書 (PO) メッセージの処理を開始するときに使用されます。  

-   供給業者側のオーケストレーション : 受信パーティおよび送信パーティの両方の解決を実行します。  

-   ShipmentAgency1 および ShipmentAgency2 オーケストレーション : PO の出荷先に基づいて供給業者側のオーケストレーションに応答します。  

## <a name="how-this-sample-is-designed-and-why"></a>このサンプルのデザイン方法とその理由  
 パーティの解決とは、メッセージの送信元 (パーティ) を特定するプロセスのことです。 たとえば、既存のパーティのみがメッセージを送信できるようにする場合などに使用します。 また、送信パーティの解決とは、メッセージの送信先のパーティを特定するプロセスのことです。  

 このサンプルでは、パーティの解決方法の他に、ロールの実装方法と使用方法も示しています。 たとえば、製品の出荷を処理するには、出荷業者に製品の出荷を指示するドキュメントを送信するための送信ポートを作成します。 出荷業者が複数ある場合は、出荷業者の URL だけが異なる複数の送信ポートを作成するのではなく、オーケストレーション内に出荷業者のロールを作成でき、 製品出荷品の出荷業者のロールに関連するメッセージを送信できます。 次にパーティを作成し、送信ポートを各パーティとパーティの証明書に関連付けます。 最後に、各パーティを出荷業者のロールに参加させて有効にします。 オーケストレーションではさらに、メッセージの送信先となる出荷業者を動的に指定できます。  

 このサンプルでは、関連付けを使用して受信メッセージを正しいオーケストレーション インスタンスと組み合わせる方法も示します。  

- 購入者、供給業者、および出荷業者のビジネス プロセス フローは次のとおりです。  

- 購入者のビジネス プロセス フロー  

  1.  .xml ファイルの PO メッセージを社内の部署から受信します。  

  2.  PO メッセージを供給業者に送信します。  

- 供給業者のビジネス プロセス フロー  

  1.  パーティを解決し (受信パーティの解決)、署名証明書に基づいて送信元のパーティを更新します。  

  2.  購入者からアクティベーション メッセージ (PO) を受信します。  

  3.  PO の確認メッセージを購入者に送信します。  

  4.  配送する国/地域を確認します。  

  5.  送信パーティを解決し、使用する出荷業者を決定します。 国/地域が米国の場合、出荷業者は ShipmentAgency2 です。 国/地域がカナダの場合、出荷業者は ShipmentAgency1 です。  

  6.  出荷指令の要求メッセージを対象の出荷業者に送信します。  

  7.  対象の出荷業者から出荷指令の確認メッセージを受信します。  

  8.  出荷通知メッセージを対象の出荷業者に送信します。  

  9. 対象の出荷業者から出荷通知の確認メッセージを受信します。  

  10. 最終の PO 配信確認メッセージを購入者に送信します。  

- 出荷業者のビジネス プロセス フロー (ShipmentAgency1 および ShipmentAgency2 両方の出荷業者に共通)  

  1.  供給業者から出荷指令の要求メッセージを受信します。  

  2.  出荷指令の要求メッセージに対する確認メッセージを生成して送信します。  

  3.  供給業者から出荷通知メッセージを受信します。  

  4.  出荷通知メッセージに対する確認メッセージを生成して送信します。  

  このサンプルの処理は次のとおりです。  

- BuyerProcess.odx オーケストレーションで、メッセージを受信した後、カスタム パイプライン MimePartyResSendPipeline を使用してメッセージをエンコードし供給業者に送信します。 この処理を行うには、パイプライン デザイナーで、カスタムの送信パイプラインをビルドし展開します。 メッセージは供給業者への送信前に購入者の秘密キーでデジタル署名されます。この秘密キーは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールの [BizTalk グループのプロパティ] で指定します。  

- SupplierProcess.odx オーケストレーションで、MIME/SMIME デコーダー コンポーネントを含むカスタム パイプライン MimePartyResReceivePipeline を使用してメッセージをデコードし、受信パーティを解決します。このとき、購入者の公開キーを使用して購入者の ID を解決します。 この処理を行うには、カスタム受信パイプラインをビルドし展開します。  

- 供給業者側のオーケストレーションで、POCorrelationSets を開始します。POCorrelationSets は昇格されたプロパティ PONo に基づくよう定義されています。 PONo は、後の段階で、このオーケストレーション インスタンスに対する受信メッセージと送信メッセージを照合する際に使用されます。この照合が必要な理由は、オーケストレーション全体で複数の送信アクションと受信アクションが行われるためです。  

- 供給業者側のオーケストレーションで、受信パーティおよび送信パーティの解決を行うためのロール リンクを実装します。 供給業者のオーケストレーションでは、次の 2 種類のロール リンクを使用します。  

  -   Buyer_Supplier ロール リンク  

  -   Supplier_Shipment ロール リンク  

- Buyer_supplier**ロール リンク**図形、供給業者は、プロバイダーの役割と業者が購入者から最初のメッセージを受信するために、コンシューマー ロールで、購入者は。 供給業者側のオーケストレーションで購入者のロールに確認メッセージを送信するときには、購入者に関連付けられている送信ポートを使用します。これによって、購入者にメッセージが送信されます。 送信ポートを検索するには、右クリック**BuyerAgency**で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールとクリック**プロパティ**します。 送信ポートが下に表示される**送信ポート**します。  

- オーケストレーションで、次のコードを使用してパートナー情報を返し、CheckPartyName という名前の外部アセンブリを呼び出して、XML ファイルをフォルダーに書き込みます。  

  ```  
  Buyer_Supplier(Microsoft.XLANGs.BaseTypes.SourceParty)  
  ```  

- Supplier_shipment**ロール リンク**図形、出荷業者のロールには、業者から、送信先パーティに応じて適切な出荷業者にメッセージを送信に使用される 2 つの操作の送信ポートが含まれています。 また、供給業者のロールには受信ポートと 2 つの操作が含まれます。これらの操作は、出荷業者から応答を受信するために使用されます。 これらのメッセージの送信および受信時には PONo に基づく関連付けが使用されます。  

  > [!NOTE]
  >  供給業者側のオーケストレーションをバインドするとき、バインドする必要があるのは、1 つの送信ポートと 2 つの受信ポートだけです。 送信先パーティに対する送信ポートは、既にパーティにバインドされています。 2 つの受信操作を含むオーケストレーションの受信ポートのいずれかのさらに、3 つが表示された場合でもその**受信**図形、2 つのバインドする必要があります。  

- 供給業者側のオーケストレーションでは、次のコードの 1 行目で QueryShipmentCatalogComponent という名前の外部アセンブリを呼び出し、出荷業者を取得します。 2 行目では、出荷業者のロールの送信先パーティを設定します。  

  ```  
  strShipmentName= objQueryShipmentCatalog.GetShipmentDetails(POMessage.MessagePart_1.POHeader.Address.Country);  
  Supplier_Shipment(Microsoft.XLANGs.BaseTypes.DestinationParty) = new Microsoft.XLANGs.BaseTypes.Party(strShipmentName,"OrganizationName");  
  ```  

- Shipper1Process.odx および Shipper2Process.odx は、SupplierProcess.odx から出荷指令と出荷通知を受信し、SupplierProcess.odx に応答を返すようビルドされています。 両方の出荷業者側のオーケストレーションで、昇格させたプロパティ PONo に基づく種類の関連付けが使用されます。  

## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 *\<パスのサンプル\>* \Orchestrations\PartyResolution\  

 次の表は、このサンプルのファイルとその目的を示しています。  


|                                                                                                                                 ファイル                                                                                                                                 |                                                                                                                                                              説明                                                                                                                                                              |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                      BuyerBinding.xml、ShippingAgency1Binding.xml、ShippingAgency2Binding.xml、SupplierBinding.xml                                                                                      |                                                                                                                                            ポートのバインドなど、自動化されたセットアップに使用されます。                                                                                                                                             |
|                                                                                                                               Cleanup.bat                                                                                                                               |                                                                   アセンブリの展開を解除し、グローバル アセンブリ キャッシュからアセンブリを削除するために使用されます。 送信ポートと受信ポートが削除されます。 必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。                                                                    |
|                                                                                                                           PartyResolution.sln                                                                                                                           |                                                                                                                              各種サブフォルダー内にあるすべてのプロジェクトが格納されているソリューション ファイルです。                                                                                                                               |
|                                                                                                                            PurchaseOrder.xml                                                                                                                            |                                                                                                                                                           サンプルの入力 PO です。                                                                                                                                                            |
|                                                                                                                                Setup.bat                                                                                                                                |                                                                                                                                         このサンプルの各部分をビルドおよび初期化するために使用されます。                                                                                                                                         |
|                                                                                                    \Buyer フォルダーには、次のファイルが含まれます。<br /><br /> Buyer.btproj、BuyerProcess.odx                                                                                                     |                                                                                                                             このサンプルの購入者を実装するために使用される、BizTalk プロジェクトおよびオーケストレーションです。                                                                                                                             |
|                                                                                                             \Catalog フォルダーには、次のファイルが含まれます。<br /><br /> Catalog.xml                                                                                                             |                                                                                                                         PO で指定された出荷先に基づいて出荷業者を決定するために使用されます。                                                                                                                          |
|                                                                                      \CheckPartyName フォルダーには、次のファイルが含まれます。<br /><br /> AssemblyInfo.cs、CheckPartyName.csproj、Class1.cs                                                                                       |                                                                                                  CheckPartyName アプリケーション用の Microsoft Visual C# プロジェクトおよびソース ファイルです。送信元パーティのプロパティにアクセスするために使用されます。                                                                                                   |
|                                                                \FilePolling フォルダーには、次のファイルが含まれます。<br /><br /> App.ico、AssemblyInfo.cs、FilePolling.cs、FilePolling.csproj、FilePolling.resx、FilePolling.sln                                                                 |                                                                 FilePolling アプリケーション用の Visual C# ソリューション、プロジェクト、ソース、および関連ファイルです。<br /><br /> このアプリケーションを使用すると、この自動化されたシナリオの進行状況に関する情報を入手できます。                                                                  |
|                                                                            \Pipeline\projectschema フォルダーには、次のファイルが含まれます。<br /><br /> MimePartyResReceivePipeline.btp、MimePartyResSendPipeline.btp                                                                             |                                                                                             このサンプルの各ロールで使用される [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] パイプライン ファイルです。                                                                                             |
|                                                                \QueryShipmentCatalogComponent フォルダーには、次のファイルが含まれます。<br /><br /> AssemblyInfo.cs、QueryShipmentCatalog.cs、QueryShipmentCatalogComponent.csproj                                                                 | QueryShipmentCatalog コンポーネント用の Visual C# プロジェクトおよびソース ファイルです。ファイル Catalog.xml で定義されている出荷カタログにアクセスするために使用されます。<br /><br /> QueryShipmentCatalog コンポーネントは、供給業者が使用する出荷業者を決定します。 地理的に最も近い出荷業者を決定するため、Catalog.xml のデータが使用されます。 |
| \Schemas フォルダーには、次のファイルが含まれます。<br /><br /> PODeliveryReceipt.xsd、POPropertySchema.xsd、PurchaseOrder.xsd、PurchaseOrderAcknowledgement.xsd、Schemas.btproj、ShipmentAdvice.xsd、ShipmentAdviceAcknowledgement.xsd、ShipmentOrderAcknowledgement.xsd、ShipmentOrderRequest.xsd |                                                                                                                                           このサンプルの各ロールで使用されるスキーマです。                                                                                                                                           |
|                                                                  \ShipmentAgency1 フォルダーには、次のファイルが含まれます。<br /><br /> ShipmentAdviceAck.btm、ShipmentAgency1.btproj、ShipmentOrderAck.btm、Shipper1Process.odx                                                                   |                                                                                                                      このサンプルの ShipmentAgency1 を実装するために使用される、BizTalk プロジェクト、オーケストレーション、およびマップです。                                                                                                                       |
|                                                                  \ShipmentAgency2 フォルダーには、次のファイルが含まれます。<br /><br /> ShipmentAdviceAck.btm、ShipmentAgency2.btproj、ShipmentOrderAck.btm、Shipper2Process.odx                                                                   |                                                                                                                      このサンプルの ShipmentAgency2 を実装するために使用される、BizTalk プロジェクト、オーケストレーション、およびマップです。                                                                                                                       |
|                                     \Supplier フォルダーには、次のファイルが含まれます。<br /><br /> PO_POAck.btm、PO_ShipmentOrderRequest.btm、ShipmentAdviceAck_PODeliveryReceipt.btm、ShipmentOrder_ShipmentAdvice.btm、Supplier.btproj、SupplierProcess.odx                                     |                                                                                                                        このサンプルの供給業者を実装するために使用される、BizTalk プロジェクト、オーケストレーション、およびマップです。                                                                                                                        |

## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  

> [!NOTE]
>  このサンプルをビルドおよび初期化する前に、既定の BizTalk インプロセス ホストが、信頼されている認証として構成されていることを確認する必要があります。 詳細については、[BizTalk Server ランタイムのセキュリティに関する推奨事項](../core/biztalk-server-runtime-security-recommendations.md)を参照してください。  

 MIME パイプライン コンポーネントは 64 ビット ホスト インスタンスではサポートされていません。 ファイル アダプターの送信および受信ハンドラーと関連付けられているホストを、32 ビット専用ホストとして構成する必要があります。 この参照の詳細については[ホスト プロパティを変更する方法](../core/how-to-modify-host-properties.md)します。 既にしている場合、システムで構成されている 32 ビット専用ホストを参照してください、それを使用する[ファイル アダプタ構成](../core/configure-the-file-adapter.md)ファイル アダプターの関連付けられているホストを構成する手順については、送信および受信ハンドラー。  

 このセクションで説明されている証明書を、メッセージに署名する既定の BizTalk インプロセス ホスト インスタンス用に構成されているログオン アカウントの個人用ストアに追加する必要があります。  

 既定では、以下で説明する setup.bat ファイルによって、パーティの解決サンプルが既定の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションにインストールされます。 setup.bat ファイルを開き、ステートメント `@ECHO Deploy Assemblies...` の後に続くセクションを以下に置き換えることで、サンプルを新しい [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションに展開できます。  

```  
@ECHO Deploy Assemblies...  

btstask AddApp -ApplicationName:PartyResolutionSample -Description:"Party Resolution Orchestration sample from the SDK"  
btstask AddResource -ApplicationName:PartyResolutionSample -Type:System.BizTalk:BizTalkAssembly  -Source:Schemas\bin\Release\Schemas.dll -Options:GacOnAdd  
btstask AddResource -ApplicationName:PartyResolutionSample -Type:System.BizTalk:BizTalkAssembly  -Source:Pipeline\projectschema\bin\Release\ProjectSchema.dll -Options:GacOnAdd   
btstask AddResource -ApplicationName:PartyResolutionSample -Type:System.BizTalk:BizTalkAssembly  -Source:Buyer\bin\Release\Buyer.dll -Options:GacOnAdd  
btstask ImportBindings -ApplicationName:PartyResolutionSample -Source:%BuyerBindingFileName%  
btstask AddResource -ApplicationName:PartyResolutionSample -Type:System.BizTalk:BizTalkAssembly  -Source:ShipmentAgency1\bin\Release\ShipmentAgency1.dll -Options:GacOnAdd  
btstask ImportBindings -ApplicationName:PartyResolutionSample -Source:%ShipmentAgency1BindingFileName%  
btstask AddResource -ApplicationName:PartyResolutionSample -Type:System.BizTalk:BizTalkAssembly  -Source:ShipmentAgency2\bin\Release\ShipmentAgency2.dll -Options:GacOnAdd  
btstask ImportBindings -ApplicationName:PartyResolutionSample -Source:%ShipmentAgency2BindingFileName%  
btstask AddResource -ApplicationName:PartyResolutionSample -Type:System.BizTalk:BizTalkAssembly  -Source:Supplier\bin\Release\Supplier.dll -Options:GacOnAdd  
btstask ImportBindings -ApplicationName:PartyResolutionSample -Source:%SupplierBindingFileName%  
```  

#### <a name="to-build-and-initialize-the-partyresolution-sample"></a>PartyResolution サンプルをビルドおよび初期化するには  

1. コマンド ウィンドウで、次のフォルダーに移動します。  

    \<*パスのサンプル*> \Orchestrations\PartyResolution  

2. ファイルは、次の操作を実行します。 Setup.bat を実行します。  

   - このサンプル用に [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトをコンパイルし、生成されたアセンブリを展開します。  

   - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の送信ポートおよび受信ポートを作成し、バインドします。  

      セットアップ プロセス中、次のような警告が表示される場合があります。 これらの警告は、無視してもかまいません。  

     ```  
     "C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\PartyResolution.sln" (Buildtarget) (1) ->  
     "C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\Supplier.btproj" (default target) (5) ->  
     "C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\Supplier.btproj" (default target) (5:2) ->  
     (CompileODX target) ->  
       C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\SupplierProcess.odx(831,13): warning X4014: convoy processing will not occur -- check your protocol if you were expecting it [C:\ProgramFiles\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\Supplier.btproj]  
       C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\SupplierProcess.odx(841,13): warning X4014: convoy processing will not occur -- check your protocol if you were expecting it [C:\ProgramFiles\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\Supplier.btproj]  

     ```  

3. 開始**Visual Studio コマンド プロンプト**します。  

4. 次のコマンドを入力して、アセンブリをグローバル アセンブリ キャッシュにインストールします。  

   - gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Schemas\bin\Release\schemas.dll  

   - gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Pipeline\projectschema\bin\Release\ProjectSchema.dll  

   - gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Buyer\bin\Release\Buyer.dll  

   - gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\ShipmentAgency1\bin\Release\ShipmentAgency1.dll  

   - gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\ShipmentAgency2\bin\Release\ShipmentAgency2.dll  

   - gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Supplier\bin\Release\Supplier.dll  

5. 証明機関 (CA) から、安全な電子メールの証明書を入手します。 CA は、第三者機関である場合と組織内の機関である場合があります。 証明書を取得した後は、公開キーと秘密キーをエクスポートします。  

6. 秘密キーをホスト インスタンス ログオン アカウントの個人用ストアにインポートしたり、公開キーをローカル コンピューターの "他の人" ストアにインポートするには、次の操作を行います。  

   1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールでは、BizTalk グループを展開し、展開**プラットフォームの設定**します。  

   2. をクリックして**ホスト インスタンス**と既定のインプロセス ホスト インスタンスに対して表示されるログオン アカウントを検索します。 既定のインストールでは、既定のインプロセス ホストの名前は BizTalkServerApplication です。  

   3. **[スタート]** ボタンをクリックし、 **[ファイル名を指定して実行]** をクリックします。 **実行**ボックスに「 **mmc.exe**、順にクリックします**OK**します。 ホスト インスタンス ログオン アカウントの正しいパスワードを入力し、そのアカウントで Microsoft 管理コンソール (MMC) を開きます。  

   4. **[ファイル]** メニューの **[スナップインの追加と削除]** をクリックします。  

   5. **スナップインを追加または**ダイアログ ボックスで、**証明書**、 をクリックし、**追加**します。  

   6. **証明書スナップイン**ダイアログ ボックスで、 **[ユーザー アカウント**、] をクリックし、**完了**。  

   7. **スナップインを追加または**ダイアログ ボックスで、**証明書**、 をクリックし、**追加**します。  

   8. **証明書スナップイン**ダイアログ ボックスで、**コンピューター アカウント**、順にクリックします**次**します。  

   9. **コンピューターの選択**ダイアログ ボックスで、**ローカル コンピューター**、 をクリックし、**完了**。  

   10. **スナップインを追加または**ダイアログ ボックスで、をクリックして**OK**。  

   11. 展開、**証明書 - 現在のユーザー**ノードを展開し、**個人**します。 右クリック**証明書**、 をクリックして**すべてのタスク**、 をクリックし、**インポート**します。  

   12. ウィザードで秘密キーをインポートし、パスワードを指定します。  

   13. 展開、**証明書 (ローカル コンピューター)** ノードを展開し、**その他のユーザー**します。 右クリック**証明書**、 をクリックして**すべてのタスク**、 をクリックし、**インポート**します。  

   14. 公開キーをインポートします。  

7. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックし、 **BizTalk グループ**ノードをクリック**プロパティ**します。 **BizTalk グループ - グループのプロパティ**ダイアログ ボックスで、**証明書**します。  

8. **証明書**ダイアログ ボックスで、をクリックして**参照**インポートした秘密キーを選択します。 ここで指定した証明書は、送信メッセージの署名に使用されます。 **[OK]** をクリックします。  

9. このサンプルの BuyerAgency パーティを更新するには、次の操作を行います。  

   1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、**パーティ**します。  

   2. 右クリックして**BuyerAgency**  をクリックし、**プロパティ**します。 **BuyerAgency - パーティのプロパティ**ダイアログ ボックスで、**全般**します。  

   3. 下、**エイリアス**セクションに設定する修飾子と名前で新しいエイリアスを追加、ダイアログの**WindowsUser**します。 値の形式でユーザー名を設定\<ドメイン \ ユーザー名 > (somedomain \someuser など)。  

   4. 選択**証明書** をクリックし、**参照**インポートした公開キーを選択します。 ここで指定した証明書は、受信メッセージの送信者 ID の検証に使用されます。 **[OK]** をクリックします。  

10. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、**プラットフォームの設定**、し、**ホスト**します。  

11. 右クリック**BizTalkServerApplication**  をクリックし、**プロパティ**します。 **BizTalkServerApplication - ホストのプロパティ**ダイアログ ボックスで、**証明書**します。  

12. クリックして**参照**インポートした秘密キーを選択します。 ここで指定した証明書は、受信メッセージの解読に使用されます。 **[OK]** をクリックします。  

13. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、**プラットフォームの設定**、し、**ホスト インスタンス**します。  

14. 右クリックして**BizTalkServerApplication**順にクリックします**再起動**します。  

## <a name="running-this-sample"></a>このサンプルの実行  

#### <a name="to-run-the-partyresolution-sample"></a>PartyResolution サンプルを実行するには  

1.  次のフォルダーから FilePolling.exe を実行します。  

     *\<サンプル パス >* \Orchestrations\PartyResolution\FilePolling\bin\Debug  

2.  クリックして**ポーリングを開始**します。  

3.  用意されている PO インスタンス ファイル PurchaseOrder.xml を、次のフォルダーにコピーします。  

     *\<サンプル パス >* \Orchestrations\PartyResolution\FileDrop\PurchaseOrder  

4.  次の各時点でサンプルの進行状況を知らせるメッセージがメッセージ ボックスの形式で表示されるので、それを確認します。  

    1.  供給業者が購入者から PO を受信したとき。  

    2.  出荷業者 1 または 2 から出荷指令の要求を受信したとき。  

    3.  出荷業者 1 または 2 から出荷通知を受信したとき。  

    4.  供給業者が購入者に PO の配信確認を送信したとき。  

5.  クリックして**終了**ファイル ポーリング プログラムを終了します。  

> [!NOTE]
>  PurchaseOrder.xml 内の "Country" タグを "US" に編集し、手順 2. と 3. を繰り返します。 出荷指令が ShipmentAgency2 に送信されることを確認します。  

## <a name="uninstalling-this-sample"></a>このサンプルのアンインストール  

#### <a name="to-uninstall-the-partyresolution-sample"></a>PartyResolution サンプルをアンインストールするには  

1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトでディレクトリ変更コマンド (**cd**) に\<*サンプル パス*> \Orchestrations\ PartyResolution\\します。  

2. Cleanup.bat を実行します。  

## <a name="see-also"></a>参照  
 [パーティの解決パイプライン コンポーネント](../core/party-resolution-pipeline-component.md)   
 [MIME-SMIME エンコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)   
 [MIME-SMIME デコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)   
 [オーケストレーション (BizTalk Server サンプル フォルダー)](../core/orchestrations-biztalk-server-samples-folder.md)
---
title: アダプターの登録ファイル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6750f0ed-4411-4a63-a7fe-f66132cd1e22
caps.latest.revision: 35
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9798d56c4f3896e652a288d20b4e39e6a2537d3c
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752962"
---
# <a name="adapter-registration-file"></a>アダプターの登録ファイル
カスタム アダプター コードを正常にビルドしたら、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に登録する必要があります。 これを行うには、レジストリを適切なアダプターの設定で更新します。 レジストリ ファイルは手動で記述できますが、正確かつ複雑な情報を入力する必要があるため、手動での記述はエラーを招く原因となります。 推奨される方法は、アダプターのレジストリ ウィザードを実行することです。 アダプターのレジストリ ウィザードには、最初からレジストリ ファイルを作成するのとまったく同じオプションが用意されており、ファイルでエラーが発生する可能性を減らすことができます。 アダプター レジストリ ウィザードの詳細については、次を参照してください。[アダプター レジストリ ウィザード](../core/adapter-registry-wizard.md)します。  
  
 StaticAdapterManagement.reg ファイルと DynamicAdapterManagement.reg ファイル*\<ドライブ\>*: \Program Files\Microsoft BizTalk Server\SDK\Samples\AdaptersDevelopment\File アダプター。 これらのファイルのいずれかを実行すると (それをダブルクリックまたは右クリックして選択できます**マージ**)、レジストリのサンプル ファイル アダプターを登録し、アセンブリをグローバル アセンブリ キャッシュにインストールします。 カスタム アダプターを登録するための最適な方法としては、アダプターのレジストリ ウィザードを使用して新しいレジストリ ファイルを作成することをお勧めします。 カスタムの静的アダプターがサンプル アダプターに似ている場合は、作成する代わりに既存のレジストリ ファイルを変更し、StaticAdapterManagement.reg ファイルの次のプロパティを開いて変更します。  
  
-   **制約**  
  
-   **InboundTypeName**  
  
-   **InboundAssemblyPath**  
  
-   **OutboundTypeName**  
  
-   **OutboundAssemblyPath**  
  
-   **AdapterMgmtTypeName**  
  
-   **AdapterMgmtAssemblyPath**  
  
-   **PropertyNameSpace**  
  
> [!NOTE]
>  **OutboundAssemblyPath**と**AdapterMgmtAssemblyPath**をお勧めのローカル パスは、プロパティの値に含めないこと、構成が分割される場合にインストールされているさまざまなので、サーバーの場所。 厳密な名前を使用し、グローバル アセンブリ キャッシュにインストールすることが推奨されます。  
  
 受信元アダプター、送信元アダプター、およびアダプター管理を実装する .NET 型を指定するには、次の 2 つの方法があります。  
  
1. フォルダーに、アダプターをインストールし、指定 * TypeName と\*AssemblyPath 場所\*TypeName は型です。クラスの FullName と\*AssemblyPath はアセンブリのパスとファイル名。  
  
2. グローバル アセンブリ キャッシュにアダプターをインストールし、だけを指定 * TypeName を\*TypeName は型です。クラスの AssemblyQualifiedName します。 これが推奨されるオプションです。  
  
   すべてのアダプターには、GUID が指定されている次のレジストリ キーが必要です。  
  
- **カテゴリを実装\\{7F46FC3E-3C2C-405B-A47F-8D17942BA8F9}**  
  
- **"InboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A281}"**  
  
- **"OutboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A283}"**  
  
- **"ReceiveLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A280}"**  
  
- **"TransmitLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A282}"**  
  
  アダプター フレームワークに基づいたアダプターは、送信ハンドラー、受信ハンドラー、および場所のプロパティ ページでこれらの固有の GUID を使用する必要があります。 アダプターが送信専用のアダプターの場合にだけ必要があることに注意してください、 **OutboundProtocol_PageProv**と**TransmitLocation_PageProv**Guid。 単に受信専用のアダプターを必要と同様に、 **InboundProtocol_PageProv**と**ReceiveLocation_PageProv** Guid。  
  
  次のコードは、StaticAdapterManagement.reg ファイルのものですが、DynamicAdapterManagement.reg ファイルのコードもこれとほぼ同じです。 各レジストリ プロパティの詳細については、次を参照してください。[アダプターの登録](../core/registering-an-adapter.md)します。 レジストリ ファイルを変更した場合は、ファイルを保存してから実行します。  
  
```  
Windows Registry Editor Version 5.00  
[HKEY_CLASSES_ROOT\CLSID\{62018D08-281A-415b-A6D3-6172E3762867}]  
@="Static DotNetFile Adapter"  
"AppID"="{12A6EBAA-CF68-4B58-B36E-A5A19B22C04E}"  
  
[HKEY_CLASSES_ROOT\CLSID\{62018D08-281A-415b-A6D3-6172E3762867}\BizTalk]  
@="BizTalk"  
"TransportType"="Static DotNetFile"  
"Constraints"=dword:00003C0b  
  
"InboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A281}"  
"OutboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A283}"  
"ReceiveLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A280}"  
"TransmitLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A282}"  
  
"InboundEngineCLSID"="{3D4B599E-2202-4bbb-9FC6-7ACA3906E5DE}"  
"InboundTypeName"="Microsoft.BizTalk.SDKSamples.Adapters.DotNetFileReceiver""InboundAssemblyPath"="C:\\Program Files\\Microsoft BizTalk Server <version>\\SDK\\Samples\\AdaptersDevelopment\\File Adapter\\Runtime\\bin\\Debug\\Microsoft.BizTalk.SDKSamples.Adapters.DotNetFile.Runtime.dll"  
"OutboundEngineCLSID"="{024DB758-AAF9-415e-A121-4AC245DD49EC}"  
"OutboundTypeName"="Microsoft.BizTalk.SDKSamples.Adapters.DotNetFileTransmitter""OutboundAssemblyPath"="C:\\Program Files\\Microsoft BizTalk Server <version>\SDK\\Samples\\AdaptersDevelopment\\File Adapter\\Runtime\\bin\\Debug\\Microsoft.BizTalk.SDKSamples.Adapters.DotNetFile.Runtime.dll""AdapterMgmtTypeName"="Microsoft.BizTalk.SDKSamples.Adapters.Designtime.StaticAdapterManagement""AdapterMgmtAssemblyPath"="C:\\Program Files\\Microsoft BizTalk Server <version>\SDK\\Samples\\AdaptersDevelopment\\File Adapter\\Design Time\\Adapter Management\\bin\\Debug\\Microsoft.BizTalk.SDKSamples.Adapters.DotNetFile.Designtime.dll""PropertyNameSpace"="http://schemas.microsoft.com/BizTalk/2003/SDK_Samples/Messaging/Transports/dotnetfile-properties"  
"AliasesXML"="<AdapterAliasList><AdapterAlias>DotNetFILE://</AdapterAlias></AdapterAliasList>"  
"ReceiveHandlerPropertiesXML"="<CustomProps><AdapterConfig vt=\"8\"/></CustomProps>"  
"SendHandlerPropertiesXML"="<CustomProps><AdapterConfig vt=\"8\"/></CustomProps>"  
"ReceiveLocationPropertiesXML"="<CustomProps><AdapterConfig vt=\"8\"/></CustomProps>"  
"SendLocationPropertiesXML"="<CustomProps><AdapterConfig vt=\"8\"/></CustomProps>"  
[HKEY_CLASSES_ROOT\CLSID\{62018D08-281A-415b-A6D3-6172E3762867}\Implemented Categories]  
[HKEY_CLASSES_ROOT\CLSID\{62018D08-281A-415b-A6D3-6172E3762867}\Implemented Categories\{7F46FC3E-3C2C-405B-A47F-8D17942BA8F9}]  
```  
  
### <a name="to-register-the-static-sample-adapter"></a>サンプルの静的アダプターを登録するには  
  
1. 次の手順を使用して、SDK のファイル アダプター サンプルを実行します。 詳細については、次を参照してください。[ファイル アダプター (BizTalk Server サンプル)](../core/file-adapter-biztalk-server-sample.md)します。  
  
2. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**アクセサリ**、順にクリックします**Windows エクスプ ローラー**します。  
  
3. BizTalk Server のインストール ドライブに移動しに移動し、 **<** `drive` **>: \Program Files\Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **\SDK\Samples\AdaptersUsage\File アダプター**します。  
  
4. サンプル アダプターをレジストリに追加するには、ダブルクリック**StaticAdapterManagement.reg**します。(動的ファイル アダプターを実行、レジストリに追加する場合**DynamicAdapterManagement.reg**代わりに、それ以外の場合、適切なファイルすべての場所で使用します)。  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をコンピューターの C ドライブにインストールしなかった場合は、StaticAdapterManagement.reg ファイルを変更して適切なインストール パスを指定する必要があります。 C: のファイルを検索し、正しいインストール ドライブに置き換えます。  
  
5. **レジストリ エディター**ダイアログ ボックスで、をクリックして**はい**サンプル アダプターをレジストリに追加し、クリックする **[ok]** 情報がしたことを確認する、ダイアログ ボックスを閉じますレジストリに追加します。  
  
6. Windows エクスプ ローラーを閉じる、**ファイル** メニューのをクリックして**閉じます**します。  
  
    これで、サンプルの静的アダプターが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に登録されました。
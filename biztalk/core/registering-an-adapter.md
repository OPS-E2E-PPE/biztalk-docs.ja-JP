---
title: "アダプターの登録 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bc85b96e-7b7b-4131-88ec-87b419a61bc2
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2cc195a55b38a232880ed04108d5a533afd1a311
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="registering-an-adapter"></a>アダプターの登録
カスタム アダプターを開発している場合が変更され、ソフトウェア開発キット (SDK) にサンプル ファイル アダプターに含まれているレジストリ ファイルの 1 つを実行して BizTalk Server に登録することができます。 また、アダプター レジストリ ウィザードを使用してレジストリ ファイルを作成することもできます。 このウィザードは、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Utilities\AdapterRegistryWizard フォルダーにあります。  
  
> [!IMPORTANT]
>  -   32 ビット マシンでは、アダプターの登録ウィザードで生成されたレジストリ (.reg) ファイルをコマンド プロンプトから実行する必要があります。  
> -   64 ビット マシンでは、アダプターの登録ウィザードで生成されたレジストリ (.reg) ファイルを 32 ビットと 64 ビットの両方のコマンド プロンプトから実行する必要があります。  
  
 レジストリ エントリを作成した後、アダプターを BizTalk Server 管理コンソールに追加するか、WMI (Windows Management Instrumentation) のメソッドを使用することでプログラム的に追加することができます。 このトピックでは、各レジストリ エントリについて説明してから、既存のレジストリ ファイルをカスタム アダプター用に変更する場所と方法を示します。  
  
 アダプター レジストリ ウィザードの使用方法の詳細については、次を参照してください。[アダプター レジストリ ウィザード](../core/adapter-registry-wizard.md)です。 SDK に含まれているサンプル レジストリ ファイルを変更する方法については、次を参照してください。[アダプターの登録ファイル](../core/adapter-registration-file.md)です。  
  
## <a name="registry-keys"></a>レジストリ キー  
 アダプターを展開するには、次に示すレジストリ エントリを作成する必要があります。  
  
 **レジストリ キーの場所**  
  
```  
[HKEY_CLASSES_ROOT\CLSID\{%uuid of custom transport%}\BizTalk]  
@="BizTalk"  
  
```  
  
 **型名**  
  
 アダプターの種類名は、BizTalk Server コンピューターのアダプターの種類を識別します。 このキーはすべてのアダプターに必要です。  
  
```  
"TransportType"="MyTransportAdapter"  
  
```  
  
 **制約**  
  
 アダプターの制約は、アダプターの機能を定義します。  
  
 このキーはすべてのアダプターに必須です。 作成するアダプターの種類に応じて、制約のビットマスク値を変更できます。  
  
```  
"Constraints"=dword:00003C0b  
```  
  
 アダプターの機能を表す値は、次の表に示す値の組み合わせとなります。  
  
|値|16 進値|フラグ|Description|  
|-----------|---------------|----------|-----------------|  
|1|0x0001|eProtocolSupportsReceive|アダプターが受信操作をサポートします。|  
|2|0x0002|eProtocolSupportsTransmit|アダプターが送信操作をサポートします。|  
|8|0x0008|eProtocolReceiveIsCreatable|アダプターの受信ハンドラーがインプロセスでホストされます。|  
|128|0x0080|eProtocolSupportsRequestResponse|アダプターが要求 - 応答操作をサポートします。|  
|256|0x0100|eProtocolSupportsSolicitResponse|アダプターが送信請求 - 応答操作をサポートします。|  
|1024|0x4000|eOutboundProtocolRequiresContextInitialization|アダプターが送信ハンドラー構成にアダプター フレームワーク ユーザー インターフェイスを使用することを示します。|  
|2048|0x0800|eInboundProtocolRequiresContextInitialization|アダプターが受信ハンドラー構成にアダプター フレームワーク ユーザー インターフェイスを使用することを示します。|  
|4096|0x1000|eReceiveLocationRequiresContextInitialization|アダプター フレームワーク ユーザー インターフェイスをアダプタの使用が受信場所の構成であることを示します。|  
|8192|0x2000|eTransmitLocationRequiresContextInitialization|アダプターが送信ポートの構成、アダプター フレームワーク ユーザー インターフェイスを使用することを示します。|  
|16384|0x4000|eSupportsOrderedDelivery|アダプターがメッセージの順次配送をサポートすることを示します。|  
|32768|0x8000|eInitTransmitterOnServiceStart|最初のメッセージの送信時ではなく、サービスの開始時に、送信アダプターが起動します。|  
|65536|0x10000|eSupport32BitOnly|アダプターが 32 ビット ホストでのみ実行をサポートすることを示します。|  
  
### <a name="namespace"></a>名前空間  
 アダプターごとに、プロパティの名前空間を定義する必要があります。 BizTalk Server によって、アダプター固有のプロパティが、この名前空間のメッセージ コンテキストに格納されます。 このプロパティはすべてのアダプターに必須です。  
  
```  
"PropertyNameSpace"="namespace"  
```  
  
### <a name="aliases"></a>エイリアス  
 アダプターごとに、アダプターの種類を BizTalk Server 内で一意に識別する一連のプレフィックスを指定できます。 これにより、動的送信ポート経由でのメッセージ送信時に、トランスポートの種類を正しく解決できます。 アダプターのプレフィックスの一覧は、登録時に指定する必要があります。  
  
```  
"AliasesXML"="<AdapterAliasList><AdapterAlias>sample://</AdapterAlias></AdapterAliasList>"  
```  
  
### <a name="configuration-property-pages"></a>構成プロパティ ページ  
 アダプターには、受信場所と送信ポートを構成するための構成プロパティ ページが必要です。 それぞれのクラス ID を指定して、アダプターごとにプロパティ ページを登録します。  
  
```  
"InboundProtocol_PageProv"="{%CLSID for inbound protocol prop page%}"  
"OutboundProtocol_PageProv"="{%CLSID for outbound protocol prop page%}"  
"ReceiveLocation_PageProv"="{%CLSID for receive location prop page%}"  
"TransmitLocation_PageProv"="{%CLSID for transmit location prop page%}"  
```  
  
 アダプターで、アダプター フレームワークのユーザー インターフェイスを使用してプロパティ ページを生成する場合、レジストリ キーに次の値を指定する必要があります。  
  
```  
"InboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A281}"  
"OutboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A283}"  
"ReceiveLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A280}"  
"TransmitLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A282}"  
```  
  
 いずれかのエンドポイントが不要である場合 (アダプターが送信専用または受信専用の場合)、使用されないレジストリ キーはレジストリから削除できます。  
  
### <a name="runtime-component-registration"></a>ランタイム コンポーネントの登録  
 アダプターのランタイム コンポーネントを登録するには、受信ランタイム コンポーネントと送信ランタイム コンポーネントのクラス ID (COM および .NET の場合)、種類名、およびアセンブリ パス (.NET の場合) を指定します。  
  
> [!NOTE]
>  すべての**OutboundEngineCLSID**と**InboundEngineCLSID**キーは一意である必要があります。 データベースでは、単一行の**OutboundEngineCLSID**と**InboundEngineCLSID**と同じである可能性があります。  
  
```  
"OutboundEngineCLSID"="{%CLSID of outbound transport%}"  
"InboundEngineCLSID"="{%CLSID of inbound transport%}"  
"InboundTypeName"="BizTalk.Samples.Adapters.MyReceiver"  
"OutboundTypeName"="BizTalk.Samples.Adapters.MyTransmitter"  
"InboundAssemblyPath"="C:\Program Files\MyTransport.dll"  
"OutboundAssemblyPath"="C:\Program Files\MyTransport.dll"  
```  
  
> [!NOTE]
>  アダプターのアセンブリをグローバル アセンブリ キャッシュ内にインストールすると、レジストリ ファイルで参照できます。  
  
### <a name="registration-of-adapter-properties-for-sso-configuration-store"></a>SSO 構成ストアのアダプター プロパティの登録  
 アダプターのプロパティをデザイン時および実行時に保存したり取得したりできるようにするには、BizTalk Server SSO データベースにこれらのプロパティを登録する必要があります。  
  
```  
ReceiveHandlerPropertiesXML  
ReceiveLocationPropertiesXML  
SendHandlerPropertiesXML  
SendLocationPropertiesXML  
```  
  
 これらの値には、アダプターに対応するエンティティで使用可能なプロパティの定義 (スキーマ) が含まれ、これらを構成ストアに格納できます。 これらの定義は、XML 文字列として保存されます。この XML 文字列は、プロパティの種類を含むが値は含まないプロパティ バッグによってシリアル化解除されます。 プロパティ要素の値が空でない場合、プロパティはマスクされています  ("マスクされている" とは、書き込み専用であり、管理モードでの呼び出し時にセキュリティ保護されたストア API によって返されないことを意味します。セキュリティ保護されたストア API は、このようなプロパティに対して VT_NULL を返します)。  
  
### <a name="example"></a>例  
 HTTP アダプターが定義することで、HTTP 送信ポートのプロパティを登録、 **SendLocationPropertiesXML**次の値を持つレジストリ キー。  
  
```  
<CustomProps><Username vt="8"/><Password vt="8">Encrypted</Password><Certificate vt="8"/><RequestTimeout vt="3"/><MaxRedirects vt="3"/><ContentType vt="8"/><UseProxy vt="11"/><ProxyName vt="8"/><ProxyPort vt="3"/><ProxyUsername vt="8"/><ProxyPassword vt="8">Encrypted</ProxyPassword><UseHandlerSetting vt="11"/><AuthenticationScheme vt="8"/><UseSSO vt="11"/><AffiliateApplicationName vt="8"/></CustomProps>  
```  
  
### <a name="registration-of-the-component-as-a-transport-provider"></a>トランスポート プロバイダーとしてのコンポーネントの登録  
 アダプターは、レジストリの Implemented Categories 属性の下に、トランスポート プロバイダーとして登録される必要があります。 この属性は、アダプターのコンシューマーに対する特性を示します。  
  
```  
[HKEY_CLASSES_ROOT\CLSID\{%uuid of custom transport%}\Implemented Categories]  
[HKEY_CLASSES_ROOT\CLSID\{%uuid of custom transport%}\Implemented Categories\{7F46FC3E-3C2C-405B-A47F-8D17942BA8F9}]  
```  
  
## <a name="see-also"></a>参照  
 [アダプターのデザインに関する問題](../core/adapter-design-issues.md)
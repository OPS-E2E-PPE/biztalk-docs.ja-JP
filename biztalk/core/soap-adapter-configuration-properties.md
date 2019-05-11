---
title: SOAP アダプター構成プロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP adapters, send ports
- SOAP adapters, code samples
- SOAP adapters, properties
- receive locations, adapters
- SOAP adapters, receive locations
- send ports, adapters
ms.assetid: 0d033371-ee31-4e43-a7d3-e0975791d981
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe4ef2a17df290c78c821d85995d450e8af90ca9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65314033"
---
# <a name="soap-adapter-configuration-properties"></a>SOAP アダプター構成プロパティ
次の表 SOAP アダプターの設定できる構成プロパティには、場所が表示されます。  
  
|プロパティ名|型|説明|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|UseSSO|VT_BOOL|シングル サインオンを使用するかどうかを指定します。|-有効な値は次のとおりです。<br />-   -1 (true)<br />-0 (false)|既定値は 0 (false です)。|  
  
 次のコードでは、プロパティの設定に使用する XML 文字列の形式を示します。  
  
```  
<CustomProps>  
<UseSSO vt="11">0</UseSSO>  
</CustomProps>  
```  
  
 SOAP アダプターの設定できる構成プロパティ送信ポートに次の表に示します。  
  
|プロパティ名|型|説明|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|ProxyPort|VT_I4|この送信ポートのプロキシ サーバー ポートを指定します。|なし|このプロパティでは、UseProxy プロパティが-1 (true) に設定しない限り、値は必要ありません。<br /><br /> 既定値は 80 です。|  
|AuthenticationScheme|VT_BSTR|接続先のサーバーで使用する認証の種類を指定します。|有効な値は、<br /><br /> 匿名<br />-基本<br />-ダイジェスト<br />-NTLM|既定値には Anonymous です。|  
|Username|VT_BSTR|移行先サーバーでの認証に使用するユーザー名を指定します。|最小長:0<br /><br /> 最大長:256|このプロパティでは基本認証またはダイジェストを AuthenticationScheme プロパティが設定され、UseSSO プロパティが 0 (false) に設定しない限り、値は必要ありません。|  
|UseProxy|VT_BOOL|SOAP 送信ハンドラーがプロキシ サーバーを使用するかどうかを指定します。|有効な値は、<br /><br /> -   -1 (true)<br />-0 (false)|既定値は 0 (false です)。|  
|UseSoap12|VT_BOOL|SOAP 1.2 プロトコルをサポートするプロキシ コードを生成する場合に指定します。|このオプションが選択されていない場合、SOAP 1.1 準拠のプロキシ コードが生成されます。<br /><br /> 有効な値は、<br /><br /> -   -1 (true)<br />-0 (false)|既定値は 0 (false です)。|  
|UsingOrchestration|VT_BOOL|この送信ポートのアドレスに関連付けられている Web サービス プロキシを使用するかどうかを指定します。|有効な値は、<br /><br /> -   -1 (true)<br />-0 (false)|既定値は-1 (true です)。|  
|UseSSO|VT_BOOL|エンタープライズ シングル サインオンが使用されることを指定します。|有効な値は、<br /><br /> -   -1 (true)<br />-0 (false)|既定値は 0 (false です)。|  
|ProxyAddress|VT_BSTR|プロキシ サーバーの名前を指定します。|このプロパティは、UseProxy プロパティが-1 (true) に設定されている場合のみ有効です。|なし|  
|パスワード|VT_NULL|移行先サーバーでの認証に使用するパスワードを指定します。|この値は常に、バインド ファイルをエクスポートする場合は null に設定します。 このフィールドは、ターゲットの BizTalk Server の構成にバインド ファイルをインポートする前に、パスワードを使用して手動設定する必要があります。|このプロパティでは基本認証またはダイジェストを AuthenticationScheme プロパティが設定され、UseSSO プロパティが 0 (false) に設定しない限り、値は必要ありません。|  
|AssemblyPath|VT_BSTR|Web サービス プロキシを含んでいるアセンブリへのパスを指定します。|なし|なし|  
|TypeName|VT_BSTR|呼び出す Web メソッドを含むクラスの名前を指定します。|なし|なし|  
|MethodName|VT_BSTR|呼び出すクラスのメソッドを指定します。|なし|なし|  
|UseHandlerSetting|VT_BOOL|使用するかどうかと、SOAP 送信ハンドラーの既定のプロキシ構成を指定します。|有効な値は、<br /><br /> -   -1 (true)<br />-0 (false)|既定値は-1 (true です)。|  
|ClientCertificate|VT_BSTR|接続の確立に使用するクライアント証明書の拇印を指定します。|最小長:0<br /><br /> 最大長:59|なし|  
|ProxyPassword|VT_NULL|プロキシ サーバーでの認証に使用するパスワードを指定します。|この値は常に、バインド ファイルをエクスポートする場合は null に設定します。 このフィールドは、ターゲットの BizTalk Server の構成にバインド ファイルをインポートする前に、パスワードを使用して手動設定する必要があります。|UseProxy が 0 (false) に設定されている場合、このプロパティは、値を必要ありません。|  
|ProxyUsername|VT_BSTR|プロキシ サーバーで認証に使用するユーザー名を指定します。|なし|このプロパティでは、UseProxy プロパティが-1 (true) に設定しない限り、値は必要ありません。|  
  
 次のコードでは、プロパティの設定に使用する XML 文字列の形式を示します。  
  
```  
<CustomProps>  
<ProxyPort vt="3">80</ProxyPort>  
<AuthenticationScheme vt="8">Basic</AuthenticationScheme>  
<Username vt="8">domain\testuser</Username>  
<UseProxy vt="11">-1</UseProxy>  
<UseSoap12 vt="11">-1</UseSoap12>  
<UsingOrchestration vt="11">-1</UsingOrchestration>  
<UseSSO vt="11">0</UseSSO>  
<ProxyAddress vt="8">proxy</ProxyAddress>  
<Password vt="1" />  
<ProxyPort vt="3">80</ProxyPort>  
<AssemblyPath vt="8">C:\Websvc.dll</AssemblyPath>  
<TypeName vt="8">Websvc.svc</TypeName>  
<MethodName vt="8">WebMethod</MethodName>  
<UseHandlerSetting vt="11">0</UseHandlerSetting></  
<ClientCertificate vt="8">23779A5EEA9693A37409021EFCDAB713A3680C34</ClientCertificate>  
<ProxyPassword vt="1" />  
<ProxyUsername vt="8">proxyuser</ProxyUsername>  
</CustomProps>  
```
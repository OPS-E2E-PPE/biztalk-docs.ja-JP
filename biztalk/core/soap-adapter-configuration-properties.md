---
title: SOAP アダプター構成プロパティ |Microsoft ドキュメント
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
ms.openlocfilehash: f52fde9d80717d192d3a5b90548ccc01e87d2044
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279818"
---
# <a name="soap-adapter-configuration-properties"></a>SOAP アダプター構成プロパティ
次の表に、SOAP アダプターの受信場所に設定できる構成プロパティを示します。  
  
|プロパティ名|型|Description|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|UseSSO|VT_BOOL|シングル サインオンを使用するかどうかを指定します。|-有効な値は次のとおりです。<br />-1 (true)<br />-0 (false)|既定値は 0 (false) です。|  
  
 次のコード例は、プロパティの設定に使用する XML 文字列の形式を示しています。  
  
```  
<CustomProps>  
<UseSSO vt="11">0</UseSSO>  
</CustomProps>  
```  
  
 次の表に、SOAP アダプターの送信ポートに設定できる構成プロパティを示します。  
  
|プロパティ名|型|Description|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|ProxyPort|VT_I4|この送信ポートのプロキシ サーバー ポートを指定します。|なし|UseProxy プロパティが -1 (true) 以外の値に設定されている場合、このプロパティの値は必要ありません。<br /><br /> 既定値は 80 です。|  
|AuthenticationScheme|VT_BSTR|接続先のサーバーで使用する認証の種類を指定します。|有効な値は、<br /><br /> 匿名<br />-基本<br />ダイジェスト<br />-NTLM|既定値は "Anonymous" です。|  
|[ユーザー名]|VT_BSTR|接続先のサーバーで認証に使用するユーザー名を指定します。|最小長: 0<br /><br /> 最大長: 256|AuthenticationScheme プロパティが [基本] または [ダイジェスト] 以外の値に設定されており、UseSSO プロパティが 0 (false) 以外の値に設定されている場合、このプロパティの値は必要ありません。|  
|UseProxy|VT_BOOL|SOAP 送信ハンドラーがプロキシ サーバーを使用するかどうかを指定します。|有効な値は、<br /><br /> -1 (true)<br />-0 (false)|既定値は 0 (false) です。|  
|UseSoap12|VT_BOOL|SOAP 1.2 プロトコルをサポートするプロキシ コードを生成する場合に指定します。|このオプションを指定しなかった場合は、SOAP 1.1 準拠のプロキシ コードが生成されます。<br /><br /> 有効な値は、<br /><br /> -1 (true)<br />-0 (false)|既定値は 0 (false) です。|  
|UsingOrchestration|VT_BOOL|この送信ポートのアドレスに関連付けられている Web サービス プロキシを使用するかどうかを指定します。|有効な値は、<br /><br /> -1 (true)<br />-0 (false)|既定値は -1 (true) です。|  
|UseSSO|VT_BOOL|エンタープライズ シングル サインオンを使用するように指定します。|有効な値は、<br /><br /> -1 (true)<br />-0 (false)|既定値は 0 (false) です。|  
|ProxyAddress|VT_BSTR|プロキシ サーバーの名前を指定します。|このプロパティは、UseProxy プロパティが -1 (true) に設定されている場合にのみ有効です。|なし|  
|Password|VT_NULL|接続先サーバーでの認証に使用するパスワードを指定します。|バインド ファイルをエクスポートする場合は、この値を必ず Null に設定します。 ターゲットの BizTalk Server 構成にバインド ファイルをインポートする前に、このフィールドにパスワードを手動で設定する必要があります。|AuthenticationScheme プロパティが [基本] または [ダイジェスト] 以外の値に設定されており、UseSSO プロパティが 0 (false) 以外の値に設定されている場合、このプロパティの値は必要ありません。|  
|AssemblyPath|VT_BSTR|Web サービスのプロキシを含んでいるアセンブリへのパスを指定します。|なし|なし|  
|TypeName|VT_BSTR|呼び出す Web メソッドを含むクラスの名前を指定します。|なし|なし|  
|MethodName|VT_BSTR|呼び出すクラスのメソッドを指定します。|なし|なし|  
|UseHandlerSetting|VT_BOOL|SOAP 送信ハンドラーの既定のプロキシ構成を使用するかどうかを指定します。|有効な値は、<br /><br /> -1 (true)<br />-0 (false)|既定値は -1 (true) です。|  
|ClientCertificate|VT_BSTR|接続の確立に使用するクライアント証明書の拇印を指定します。|最小長: 0<br /><br /> 最大長: 59|なし|  
|ProxyPassword|VT_NULL|プロキシ サーバーで認証に使用するパスワードを指定します。|バインド ファイルをエクスポートする場合は、この値を必ず Null に設定します。 ターゲットの BizTalk Server 構成にバインド ファイルをインポートする前に、このフィールドにパスワードを手動で設定する必要があります。|UseProxy プロパティが 0 (false) に設定されている場合、このプロパティの値は必要ありません。|  
|ProxyUsername|VT_BSTR|プロキシ サーバーで認証に使用するユーザー名を指定します。|なし|UseProxy プロパティが -1 (true) 以外の値に設定されている場合、このプロパティの値は必要ありません。|  
  
 次のコード例は、プロパティの設定に使用する XML 文字列の形式を示しています。  
  
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
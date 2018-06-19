---
title: オーケストレーションのリモート デバッグの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Microsoft.XLANGs.BizTalk.Client.dll.config, code sample
- BTSNTSvc.exe.config, code sample
- orchestrations, debugging
- building, debugging
- building, code sample
ms.assetid: 722efaec-d160-48dc-b94b-0733c9904d98
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4184b82efccd0ab2dcc2b871b6389b28148754c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233410"
---
# <a name="configuring-remote-debugging-for-orchestrations"></a>オーケストレーションのリモート デバッグの構成
クライアントとサーバーの間のリモート デバッグは詳細に構成することができます。 クライアントの構成は、Microsoft.XLANGs.BizTalk.Client.dll.config で指定されます。サーバーの構成は、BTSNTSvc.exe.config で指定されます。それぞれの既定の構成の一覧を次に示します。  
  
## <a name="client-microsoftxlangsbiztalkclientdllconfig"></a>クライアント (Microsoft.XLANGs.BizTalk.Client.dll.config)  
  
```  
<configuration>  
     <system.runtime.remoting>  
  
 <channelSinkProviders>  
       <clientProviders>  
         <provider id="sspi" type="Microsoft.BizTalk.XLANGs.Client.SecurityClientChannelSinkProvider,Microsoft.XLANGs.BizTalk.Client" securityPackage="negotiate" authenticationLevel="packetPrivacy"/>  
       </clientProviders>  
</channelSinkProviders>  
  
<application>  
<channels>  
    <channel ref="tcp" port="0" name="">  
       <clientProviders>  
             <formatter ref="binary"/>  
             <provider ref="sspi" />  
        </clientProviders>  
       <serverProviders>  
             <formatter ref="binary" typeFilterLevel="Full"/>  
       </serverProviders>  
    </channel>  
</channels>  
</application>  
  </system.runtime.remoting>  
</configuration>  
```  
  
## <a name="serverbtsntsvcexeconfig"></a>サーバー (BTSNTSvc.exe.config)  
  
```  
<?xml version="1.0" ?>  
<configuration>  
    <runtime>  
        <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
            <probing privatePath="BizTalk Assemblies;Developer Tools;Tracking;Tracking\interop" />  
        </assemblyBinding>  
    </runtime>  
  
    <system.runtime.remoting>  
  
        <channelSinkProviders>  
            <serverProviders>  
                <provider id="sspi" type="Microsoft.BizTalk.XLANGs.BTXEngine.SecurityServerChannelSinkProvider,Microsoft.XLANGs.BizTalk.Engine" securityPackage="ntlm" authenticationLevel="packetPrivacy" />  
            </serverProviders>  
        </channelSinkProviders>  
  
        <application>  
            <channels>  
                <channel ref="tcp" port="0" name="">  
                <serverProviders>  
                    <provider ref="sspi" />  
                        <formatter ref="binary" typeFilterLevel="Full"/>  
                    </serverProviders>  
                </channel>  
            </channels>  
        </application>  
    </system.runtime.remoting>  
  
</configuration>  
```  
  
## <a name="configurable-parameters"></a>構成可能なパラメーター  
 既定値でも最大限のセキュリティ構成が保証されますが、 ユーザーがこれらの既定値を変更することが可能です。これらのファイルはプログラム ファイル フォルダーにあるため、ACL で制御されます。  
  
 要素\<プロバイダー/> は省略可能とカスタム シンクを使用して相互に認証が、チャネルは指定されていない場合とします。 しかし、このオプションを無効にすると、チャネルが開放されるため危険です。 セキュリティ上の攻撃の心配がいらない場合、パフォーマンスを高めるにはこのオプションを無効にします。  
  
 チャネル要素には、プロパティ rejectRemoteRequests = true を指定することができます。このオプションを指定すると、ローカルな呼び出しだけが可能となり、リモート要求が拒否されます。  
  
 内の securityPackage 属性、 \<serverProviders/> 要素には、次の値を持つことができます。  
  
-   negotiate  
  
-   ntlm  
  
-   Kerberos  
  
 AuthenticationLevel 属性、 \<serverProviders/> 要素には、次の値を持つことができます。  
  
-   packetPrivacy - メッセージの暗号化と復号化が行われます。  
  
-   packetIntegrity – メッセージの署名と検証が行われます。  
  
-   call - メッセージはそのまま送信されます。  
  
 Ref 属性、\<チャネル/> 要素は tcp または http に変更することができます。 属性の名前とポート、\<チャネル/> 要素は明示的な値にも変更できます。  
  
 詳細については、『.NET Framework 開発者ガイド』の「チャネルとフォーマッタの構成プロパティ」を参照してください。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションのデバッグ](../core/debugging-orchestrations.md)
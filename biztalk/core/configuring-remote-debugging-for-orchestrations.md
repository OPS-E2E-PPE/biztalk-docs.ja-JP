---
title: オーケストレーションのリモート デバッグの構成 |Microsoft Docs
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
ms.openlocfilehash: 96fa7775bc6e67e0c56e2b93e9ca334ac361794c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390910"
---
# <a name="configuring-remote-debugging-for-orchestrations"></a>オーケストレーションのリモート デバッグの構成
クライアントとサーバー間のリモート デバッグを完全に構成することができます。 クライアントの構成は、Microsoft.XLANGs.BizTalk.Client.dll.config で指定されます。サーバーの構成は、BTSNTSvc.exe.config で指定されます。それぞれの既定の構成の一覧を次に示します。  
  
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
  
## <a name="serverbtsntsvcexeconfig"></a>Server(BTSNTSvc.exe.config)  
  
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
 既定値により、最大限のセキュリティ構成。 ただしこれらの既定値を変更するユーザーに任されており、プログラム ファイル フォルダーであるために、これらのファイルは acl を設定します。  
  
 要素\<プロバイダー/> は省略可能とカスタム シンクを使用して相互に認証が、チャネルは指定されていない場合があるとします。 ただし、これは、チャネルが開放されるとオフにする危険なオプションです。 これは、パフォーマンスを向上させるときにセキュリティ攻撃に問題がないを実行できます。  
  
 Channel 要素は、プロパティ rejectRemoteRequests を持つことができます = true をローカルな呼び出しだけを有効にしてリモート要求が拒否されます。  
  
 内の securityPackage 属性、 \<serverProviders/> 要素には次の値を持つことができます。  
  
- ネゴシエート  
  
- Ntlm  
  
- Kerberos  
  
  AuthenticationLevel 属性は、 \<serverProviders/> 要素には次の値を持つことができます。  
  
- packetPrivacy - メッセージれます暗号化/復号化  
  
- packetIntegrity – メッセージが署名と検証が  
  
- 呼び出しのまま、メッセージが送信されます。  
  
  Ref 属性は、\<チャネル/> 要素は tcp または http に変更することができます。 属性の名前とポート、\<チャネル/> 要素は明示的な値にも変更できます。  
  
  詳細については、.NET Framework 開発者ガイド (チャネルとフォーマッタの構成プロパティ) を参照してください。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションのデバッグ](../core/debugging-orchestrations.md)
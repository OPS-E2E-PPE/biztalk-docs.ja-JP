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
ms.openlocfilehash: 6f5d28c13cb9da4454efcad1a43a4048c8881ea8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967291"
---
# <a name="configuring-remote-debugging-for-orchestrations"></a><span data-ttu-id="a901d-102">オーケストレーションのリモート デバッグの構成</span><span class="sxs-lookup"><span data-stu-id="a901d-102">Configuring Remote Debugging for Orchestrations</span></span>
<span data-ttu-id="a901d-103">クライアントとサーバーの間のリモート デバッグは詳細に構成することができます。</span><span class="sxs-lookup"><span data-stu-id="a901d-103">You can completely configure remote debugging between client and server.</span></span> <span data-ttu-id="a901d-104">クライアントの構成は、Microsoft.XLANGs.BizTalk.Client.dll.config で指定されます。サーバーの構成は、BTSNTSvc.exe.config で指定されます。それぞれの既定の構成の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a901d-104">The client configuration is specified in Microsoft.XLANGs.BizTalk.Client.dll.config. The server configuration is specified in BTSNTSvc.exe.config. The following is a listing of the default configuration for each.</span></span>  
  
## <a name="client-microsoftxlangsbiztalkclientdllconfig"></a><span data-ttu-id="a901d-105">クライアント (Microsoft.XLANGs.BizTalk.Client.dll.config)</span><span class="sxs-lookup"><span data-stu-id="a901d-105">Client (Microsoft.XLANGs.BizTalk.Client.dll.config)</span></span>  
  
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
  
## <a name="serverbtsntsvcexeconfig"></a><span data-ttu-id="a901d-106">サーバー (BTSNTSvc.exe.config)</span><span class="sxs-lookup"><span data-stu-id="a901d-106">Server(BTSNTSvc.exe.config)</span></span>  
  
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
  
## <a name="configurable-parameters"></a><span data-ttu-id="a901d-107">構成可能なパラメーター</span><span class="sxs-lookup"><span data-stu-id="a901d-107">Configurable Parameters</span></span>  
 <span data-ttu-id="a901d-108">既定値でも最大限のセキュリティ構成が保証されますが、</span><span class="sxs-lookup"><span data-stu-id="a901d-108">The default ensures maximum security configuration.</span></span> <span data-ttu-id="a901d-109">ユーザーがこれらの既定値を変更することが可能です。これらのファイルはプログラム ファイル フォルダーにあるため、ACL で制御されます。</span><span class="sxs-lookup"><span data-stu-id="a901d-109">However it is left to the user to change these defaults and these files are ACL'ed since they are in the program files folder.</span></span>  
  
 <span data-ttu-id="a901d-110">要素\<プロバイダー/> は省略可能とカスタム シンクを使用して相互に認証が、チャネルは指定されていない場合があるとします。</span><span class="sxs-lookup"><span data-stu-id="a901d-110">The element \<provider/> is optional and if not provided will cause the channels not to be mutually authenticated using the custom sinks.</span></span> <span data-ttu-id="a901d-111">しかし、このオプションを無効にすると、チャネルが開放されるため危険です。</span><span class="sxs-lookup"><span data-stu-id="a901d-111">However this is a dangerous option to turn off as it will open up the channels.</span></span> <span data-ttu-id="a901d-112">セキュリティ上の攻撃の心配がいらない場合、パフォーマンスを高めるにはこのオプションを無効にします。</span><span class="sxs-lookup"><span data-stu-id="a901d-112">This can be done for better performance and when security attacks are not a concern.</span></span>  
  
 <span data-ttu-id="a901d-113">チャネル要素には、プロパティ rejectRemoteRequests = true を指定することができます。このオプションを指定すると、ローカルな呼び出しだけが可能となり、リモート要求が拒否されます。</span><span class="sxs-lookup"><span data-stu-id="a901d-113">The channel element can have property rejectRemoteRequests = true which will enable only local calls and reject remote requests.</span></span>  
  
 <span data-ttu-id="a901d-114">内の securityPackage 属性、 \<serverProviders/> 要素には次の値を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="a901d-114">The securityPackage attribute in the \<serverProviders/> element can have any of the following values:</span></span>  
  
- <span data-ttu-id="a901d-115">negotiate</span><span class="sxs-lookup"><span data-stu-id="a901d-115">negotiate</span></span>  
  
- <span data-ttu-id="a901d-116">ntlm</span><span class="sxs-lookup"><span data-stu-id="a901d-116">ntlm</span></span>  
  
- <span data-ttu-id="a901d-117">Kerberos</span><span class="sxs-lookup"><span data-stu-id="a901d-117">Kerberos</span></span>  
  
  <span data-ttu-id="a901d-118">AuthenticationLevel 属性は、 \<serverProviders/> 要素には次の値を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="a901d-118">The authenticationLevel attribute in the \<serverProviders/> element can have any of the following values:</span></span>  
  
- <span data-ttu-id="a901d-119">packetPrivacy - メッセージの暗号化と復号化が行われます。</span><span class="sxs-lookup"><span data-stu-id="a901d-119">packetPrivacy  - the messages will be encrypted/decrypted</span></span>  
  
- <span data-ttu-id="a901d-120">packetIntegrity – メッセージの署名と検証が行われます。</span><span class="sxs-lookup"><span data-stu-id="a901d-120">packetIntegrity – the messages will be signed/verified</span></span>  
  
- <span data-ttu-id="a901d-121">call - メッセージはそのまま送信されます。</span><span class="sxs-lookup"><span data-stu-id="a901d-121">call  - the messages will be sent as is</span></span>  
  
  <span data-ttu-id="a901d-122">Ref 属性は、\<チャネル/> 要素は tcp または http に変更することができます。</span><span class="sxs-lookup"><span data-stu-id="a901d-122">The ref attribute in the \<channel/> element can be changed to tcp or http.</span></span> <span data-ttu-id="a901d-123">属性の名前とポート、\<チャネル/> 要素は明示的な値にも変更できます。</span><span class="sxs-lookup"><span data-stu-id="a901d-123">The port and name attribute in the \<channel/> element can be changed as well to explicit values.</span></span>  
  
  <span data-ttu-id="a901d-124">詳細については、『.NET Framework 開発者ガイド』の「チャネルとフォーマッタの構成プロパティ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a901d-124">For more information, see .NET Framework Developer's Guide (Channel and formatter configuration properties).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a901d-125">参照</span><span class="sxs-lookup"><span data-stu-id="a901d-125">See Also</span></span>  
 [<span data-ttu-id="a901d-126">オーケストレーションのデバッグ</span><span class="sxs-lookup"><span data-stu-id="a901d-126">Debugging Orchestrations</span></span>](../core/debugging-orchestrations.md)
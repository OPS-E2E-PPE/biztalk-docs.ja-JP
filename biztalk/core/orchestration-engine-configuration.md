---
title: オーケストレーション エンジンの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestration engine, examples
- orchestration engine, code sample
- orchestration engine, dehydration
- orchestration engine, configuring
ms.assetid: d4f253c3-317d-4b52-bf54-81d50f03eeb3
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f45fbc1d4114fc6c20011a7b03670b0e874345f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262743"
---
# <a name="orchestration-engine-configuration"></a><span data-ttu-id="71b53-102">オーケストレーション エンジンの構成</span><span class="sxs-lookup"><span data-stu-id="71b53-102">Orchestration Engine Configuration</span></span>
<span data-ttu-id="71b53-103">オーケストレーション エンジンでは、BTSNTSvc.exe.config という XML ファイルを使用して特定の動作を決定します。</span><span class="sxs-lookup"><span data-stu-id="71b53-103">The orchestration engine uses an XML file called BTSNTSvc.exe.config to determine certain behaviors.</span></span> <span data-ttu-id="71b53-104">たとえば、退避プロパティとその既定値は BTSNTSvc.exe.config ファイルに XML として構成し、は読み取り専用とすべてのホスト インスタンスがオーケストレーションの開始を含みます。</span><span class="sxs-lookup"><span data-stu-id="71b53-104">For example, dehydration properties and their default values are configured as XML in the BTSNTSvc.exe.config file and are read when all host instances containing an orchestration start.</span></span> <span data-ttu-id="71b53-105">詳細については、次を参照してください。[オーケストレーションの退避と復元](../core/orchestration-dehydration-and-rehydration.md)します。</span><span class="sxs-lookup"><span data-stu-id="71b53-105">For more information, see [Orchestration Dehydration and Rehydration](../core/orchestration-dehydration-and-rehydration.md).</span></span>  
  
 <span data-ttu-id="71b53-106">サービスは、起動時に 1 回、この構成情報を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="71b53-106">A service reads this configuration information once, when it is started.</span></span> <span data-ttu-id="71b53-107">サービスが停止および再起動しない限りに変更内容が取得されません。</span><span class="sxs-lookup"><span data-stu-id="71b53-107">Any changes to it will not be picked up unless the service is stopped and restarted.</span></span>  
  
 <span data-ttu-id="71b53-108">別のノードと使用可能な値は、以下の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71b53-108">See the examples below for different nodes and possible values.</span></span>  
  
## <a name="example-all-validations-on"></a><span data-ttu-id="71b53-109">例: 上のすべての検証</span><span class="sxs-lookup"><span data-stu-id="71b53-109">Example: all validations on</span></span>  
  
```  
<?xml version="1.0" ?>  
<configuration>  
       <configSections>  
              <section   
                     name="xlangs"  
                     type="Microsoft.XLANGs.BizTalk.CrossProcess.XmlSerializationConfigurationSectionHandler, Microsoft.XLANGs.BizTalk.CrossProcess" />  
       </configSections>  
       <runtime>  
              <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
                     <probing privatePath="BizTalk Assemblies;Developer Tools;Tracking" />  
              </assemblyBinding>  
       </runtime>  
  
       <xlangs>  
              <Configuration>  
                     <Debugging   
                            ValidateAssemblies="true"  
                            ValidateSchemas="true"  
                            ValidateCorrelations="true"  
                            ExtendedLogging="true"  
                     />  
              </Configuration>  
       </xlangs>  
</configuration>  
```  
  
## <a name="example-assembly-validation-only"></a><span data-ttu-id="71b53-110">例: アセンブリの検証のみ</span><span class="sxs-lookup"><span data-stu-id="71b53-110">Example: assembly validation only</span></span>  
  
```  
<?xml version="1.0" ?>  
<configuration>  
       <configSections>  
              <section   
                     name="xlangs"  
                     type="Microsoft.XLANGs.BizTalk.CrossProcess.XmlSerializationConfigurationSectionHandler, Microsoft.XLANGs.BizTalk.CrossProcess"  
              />  
       </configSections>  
       <runtime>  
              <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
                     <probing privatePath="BizTalk Assemblies;Developer Tools;Tracking" />  
              </assemblyBinding>  
       </runtime>  
  
       <xlangs>  
              <Configuration>  
                     <Debugging   
                            ValidateAssemblies="true"  
                            ExtendedLogging="false"  
                     />  
              </Configuration>  
       </xlangs>  
</configuration>  
```  
  
## <a name="example-remote-debugging-enabled"></a><span data-ttu-id="71b53-111">例: 有効になっているリモート デバッグ</span><span class="sxs-lookup"><span data-stu-id="71b53-111">Example: remote debugging enabled</span></span>  
  
```  
<?xml version="1.0" ?>  
<configuration>  
       <runtime>  
              <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
                     <probing privatePath="BizTalk Assemblies;Developer Tools;Tracking" />  
              </assemblyBinding>  
       </runtime>  
  
       <system.runtime.remoting>  
              <customErrors mode="on"/>  
              <channelSinkProviders>  
                     <serverProviders>  
                            <provider id="sspi"  
                                    type="Microsoft.BizTalk.XLANGs.BTXEngine.SecurityServerChannelSinkProvider,Microsoft.XLANGs.BizTalk.Engine" securityPackage="negotiate" authenticationLevel="packetPrivacy" />  
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
  
## <a name="example-appdomain-configuration"></a><span data-ttu-id="71b53-112">例:AppDomain の構成</span><span class="sxs-lookup"><span data-stu-id="71b53-112">Example: AppDomain configuration</span></span>  
 <span data-ttu-id="71b53-113">割り当ての規則を使用して名前付きドメインに割り当てられているアセンブリ (以下を参照)。</span><span class="sxs-lookup"><span data-stu-id="71b53-113">Assemblies are assigned to named domains using assignment rules (see more below).</span></span> <span data-ttu-id="71b53-114">いくつかのアセンブリのルールが指定されていない場合、アセンブリはアド ホック ドメインに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="71b53-114">If no rule is specified for some assembly, the assembly will be assigned to an ad hoc domain.</span></span> <span data-ttu-id="71b53-115">このような割り当てられたアセンブリ アド ホック ドメインあたりの数については、AssembliesPerDomain の値によって決まります。</span><span class="sxs-lookup"><span data-stu-id="71b53-115">The number of such assigned assemblies per ad hoc domain is determined by the value of AssembliesPerDomain.</span></span>  
  
```  
<?xml version="1.0" ?>  
<configuration>  
    <configSections>  
        <section name="xlangs" type="Microsoft.XLANGs.BizTalk.CrossProcess.XmlSerializationConfigurationSectionHandler, Microsoft.XLANGs.BizTalk.CrossProcess" />  
    </configSections>  
    <runtime>  
        <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
            <probing privatePath="BizTalk Assemblies;Developer Tools;Tracking" />  
        </assemblyBinding>  
    </runtime>  
    <xlangs>  
        <Configuration>  
            <!--   
                <!--   
AppDomain configuration.  
                Assemblies are assigned to named domains using assignment rules (see more below). If no rule is specified for some assembly, the assembly will be assigned to an ad hoc domain. The number of such assigned assemblies per ad hoc domain is determined by the value of AssembliesPerDomain.  
            -->-->   
            <AppDomains AssembliesPerDomain="10">  
                <!--   
                    <!--   
In this section the user may specify defualt configuration for any app domain created that does not have a named configuration associated with it (see AppDomainSpecs below)  
                    SecondsEmptyBeforeShutdown is the number of seconds that an app domain is empty (that is, it does not contain any orchestrations) before being unloaded. Specify -1 to signal that an app domain should never unload, even when empty.  
                    Similarly, SecondsIdleBeforeShutdown is the number of seconds that an app domain is idle (that is, it contains only dehydratable orchestrations) before being unloaded. Specify -1 to signal that an app domain should never unload when idle but not empty. When an idle but non-empty domain is shut down, all of the contained instances are dehydrated first.  
                -->  
                -->   
<DefaultSpec SecondsIdleBeforeShutdown="1200" SecondsEmptyBeforeShutdown="1800">  
                    <!--   
                        <!--   
BaseSetup is a serialized System.AppDomainSetup object. This is passed as-is to  
                        AppDomain.CreateAppDomain() and can be used to influence assembly search path etc.  
                    -->  
                    -->   
<BaseSetup>  
                        <ApplicationBase>c:\myAppBase</ApplicationBase>_0</ApplicationBase>   
                        <ConfigurationFile>c:\myAppBase\myConfig.config</ConfigurationFile>_0</ConfigurationFile>   
                    <DynamicBase>DynamicBase_0</DynamicBase>   
<DisallowPublisherPolicy>true</DisallowPublisherPolicy>   
<ApplicationName>ApplicationName_0</ApplicationName>   
<PrivateBinPath>PrivateBinPath_0</PrivateBinPath>   
<PrivateBinPathProbe>PrivateBinPathProbe_0</PrivateBinPathProbe>   
<ShadowCopyDirectories>ShadowCopyDirectories_0</ShadowCopyDirectories>   
<ShadowCopyFiles>ShadowCopyFiles_0</ShadowCopyFiles>   
<CachePath>CachePath_0</CachePath>   
<LicenseFile>LicenseFile_0</LicenseFile>   
<LoaderOptimization>NotSpecified</LoaderOptimization>   
</BaseSetup>  
                </DefaultSpec>  
                <!--   
                    - <!--   
In this section the user may specify named configurations for specific app domains, identified by their "friendly name". The format of any app-domain spec is identical to that of the default app-domain spec.  
                -->-->   
                <AppDomainSpecs>  
                    <AppDomainSpec Name="MyDomain1" SecondsIdleBeforeShutdown="-1" SecondsEmptyBeforeShutdown="12000">  
                        <BaseSetup>  
                            <PrivateBinPath>c:\PathForAppDomain1</PrivateBinPath>  
                        <PrivateBinPath>PrivateBinPath_0</PrivateBinPath>   
<PrivateBinPathProbe>PrivateBinPathProbe_0</PrivateBinPathProbe>   
</BaseSetup>  
                    </AppDomainSpec>  
                    <AppDomainSpec Name="MyFrequentlyUnloadingDomainMyTrashyDomain" SecondsIdleBeforeShutdown="60" SecondsEmptyBeforeShutdown="60" />   
                </AppDomainSpecs>  
                <!--   
                    <!--   
The PatternAssignmentRules and ExactAssignmentRules control assignment of assemblies to app domains.  
                    When a message arrives, the name of its corresponding orchestration's assembly is determined. Then, the assembly is assigned an app domain name. The rules guide this assignment. Exact rules are consulted first, in their order of definition, and then the pattern rules. The first match is used.  
                    If no match is found, the assembly will be assigned to an ad-hoc domain. The configuration and number of assemblies per ad-hoc domain is controlled by the AssembliesPerDomain attribute and the DefaultSpec section.  
                -->  
               -->   
- <ExactAssignmentRules>  
                    <!--   
                        <!--   
An exact assembly rule specifies a strong assembly name and an app domain name. If the strong assembly name equals the rule's assembly name, it is assigned to the corresponding app domain.  
                    -->-->   
                    <ExactAssignmentRule AssemblyName="BTSAssembly1, Version=1.0.0.0, Culture=neutral, PublicKeyToken=9c7731c5584592ad"  
                       AssemblyName_0" AppDomainName="MyDomain1" />AppDomainName_1" />   
                    <ExactAssignmentRule AssemblyName="BTSAssembly2, Version=1.0.0.0, Culture=neutral, PublicKeyToken=9c7731c5584592ad"AssemblyName_0" AppDomainName="AppDomainName_1" />   
                        AppDomainName="MyFrequentlyUnloadingDomain " />  
                <ExactAssignmentRule AssemblyName="AssemblyName_0" AppDomainName="AppDomainName_1" />   
</ExactAssignmentRules>  
                <PatternAssignmentRules>  
                    <!--   
                        <!--   
A pattern assignment rule specifies a regular expression and an app domain name. If the strong assembly name matches the expression, it is assigned to the corresponding app domain. This allows version independent assignment, assignment by public key token, or assignment by the custom assembly key.  
                    -->-->   
                    <!--  
                        assign all assemblies with name BTSAssembly3, regardless of version and public key,  
                        to the MyDomain1 app domain   
                    -->  
                    <PatternAssignmentRule AssemblyNamePattern=" BTSAssembly3, Version=\d.\d.\d.\d, Culture=neutral, PublicKeyToken=.{16}"AssemblyNamePattern_0" AppDomainName=" MyDomain1" />  
                <PatternAssignmentRule AssemblyNamePattern="AssemblyNamePattern_0" AppDomainName="AppDomainName_1" />   
<PatternAssignmentRule AssemblyNamePattern="AssemblyNamePattern_0" AppDomainName="AppDomainName_1" />   
</PatternAssignmentRules>  
            </AppDomains>  
        </Configuration>  
    </xlangs>  
</configuration>  
```  
  
## <a name="modifying-other-sections-of-the-btsntsvcexeconfig-file"></a><span data-ttu-id="71b53-116">BTSNTSvc.exe.config ファイルの他のセクションを変更します。</span><span class="sxs-lookup"><span data-stu-id="71b53-116">Modifying other sections of the BTSNTSvc.exe.config file</span></span>  
 <span data-ttu-id="71b53-117">BTSNTSvc.exe.config における退避値を変更する方法の詳細については、次を参照してください。[既定の退避プロパティ](../core/dehydration-default-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="71b53-117">For information about modifying the dehydration values in BTSNTSvc.exe.config, see [Dehydration Default Properties](../core/dehydration-default-properties.md).</span></span>  
  
 <span data-ttu-id="71b53-118">BTSNTSvc.exe 構成ファイルには、.NET Framework 全般リファレンスに記載されているその他のいくつかのセクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="71b53-118">The BTSNTSvc.exe configuration file contains several other sections documented in the .NET Framework General Reference.</span></span> <span data-ttu-id="71b53-119">これらのセクションの変更の詳細については、次を参照してください。、**構成ファイル スキーマ**で .NET Framework 全般リファレンスの[ http://go.microsoft.com/FWLink/?LinkID=52964](http://go.microsoft.com/FWLink/?LinkID=52964)します。</span><span class="sxs-lookup"><span data-stu-id="71b53-119">For more information about the modification of these sections see the **Configuration File Schema** of the .NET Framework General Reference at [http://go.microsoft.com/FWLink/?LinkID=52964](http://go.microsoft.com/FWLink/?LinkID=52964).</span></span>  
  
 <span data-ttu-id="71b53-120">BizTalk 固有の構成情報に加え、BTSNTSvc.exe.config ファイルも、オーケストレーション、アダプターまたはパイプラインのコンテキストで実行される .NET アプリケーション コンポーネントが使用して実行時に構成情報を取得します標準 .NET **\<appSettings\>** でタグ付け、 **\<構成\>** タグ。</span><span class="sxs-lookup"><span data-stu-id="71b53-120">In addition to BizTalk-specific configuration information, the BTSNTSvc.exe.config file is also where .NET application components which run in the context of an orchestration, adapter or pipeline obtain their configuration information at run time using the standard .NET **\<appSettings\>** tag under the **\<configuration\>** tag.</span></span> <span data-ttu-id="71b53-121">BizTalk が既にカスタム アダプターとパイプライン コンポーネントの構成情報を取得するためのメカニズムを提供するため、 **\<appSettings\>** BTSNTSvc.exe.config ファイル内のタグは通常はオーケストレーション内から呼び出されるカスタムの .NET コンポーネントで使用されます。</span><span class="sxs-lookup"><span data-stu-id="71b53-121">Because BizTalk already provides a mechanism for custom adapters and pipeline components to obtain configuration information, the **\<appSettings\>** tag in the BTSNTSvc.exe.config file would typically be used by custom .NET components called from within an orchestration.</span></span> <span data-ttu-id="71b53-122">例 :</span><span class="sxs-lookup"><span data-stu-id="71b53-122">For example:</span></span>  
  
```  
<appSettings>  
     <add key="configParamName" value="configParamValue" />  
</appSettings>  
```  
  
## <a name="throttling-messages-per-orchestration"></a><span data-ttu-id="71b53-123">オーケストレーションごとのメッセージの制限</span><span class="sxs-lookup"><span data-stu-id="71b53-123">Throttling Messages Per Orchestration</span></span>  
 <span data-ttu-id="71b53-124">このプロパティは、btsntsvc.exe.config ファイルで指定により、オーケストレーションが保持できる未処理のメッセージの数を制限することによって過度のメモリを消費できなくなります。</span><span class="sxs-lookup"><span data-stu-id="71b53-124">This property, specified in the btsntsvc.exe.config file, will prevent an orchestration from consuming too much memory by limiting the number of outstanding messages it can have.</span></span> <span data-ttu-id="71b53-125">。 メッセージ ボックス データベースに配信されるすべてのメッセージが引き続きただし、キューに置かれたメッセージは配信されませんをオーケストレーションに未処理のメッセージの一部が処理されるまでです。</span><span class="sxs-lookup"><span data-stu-id="71b53-125">All messages will continue to be delivered to the MessageBox; however, queued messages will not be delivered to the orchestration until it processes some of its outstanding messages.</span></span>  
  
 <span data-ttu-id="71b53-126">Btsntsvc.exe.config ファイルでこのプロパティを指定する (内にある、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ルート ディレクトリ)、アプリケーション ノードの下の次のパラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="71b53-126">To specify this property in the btsntsvc.exe.config file (located in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] root directory), add the following parameter under Application node:</span></span>  
  
```  
<configuration>  
            <application>  
                        <Throttling PauseAt="100" ResumeAt="50" />  
            </application>  
</configuration>  
```  
  
 <span data-ttu-id="71b53-127">この例では、オーケストレーションがある 100 件の未解決のメッセージとメッセージ ボックスは停止追加メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="71b53-127">In this example, once an orchestration has 100 outstanding messages, the MessageBox will stop sending additional messages.</span></span> <span data-ttu-id="71b53-128">オーケストレーションの未処理のメッセージ数が 50 件まで下がると、メッセージを送信するメッセージ ボックス データベースを再開できることを指定します。</span><span class="sxs-lookup"><span data-stu-id="71b53-128">When the orchestration's number of outstanding messages is down to 50, it will specify the MessageBox can resume sending messages.</span></span> <span data-ttu-id="71b53-129">その他の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="71b53-129">You can specify other values.</span></span>  
  
 <span data-ttu-id="71b53-130">また、この機能が有効にする必要があります、ホスト、データベースにします。</span><span class="sxs-lookup"><span data-stu-id="71b53-130">You must also enable this feature, per-host, in the database.</span></span> <span data-ttu-id="71b53-131">メッセージをホストの数の制限を有効にするには、dbo を編集する必要があります。BizTalkMsgBoxDb データベース内のテーブルをアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="71b53-131">To enable message throttling for a host, you must edit the dbo.Applications table in the BizTalkMsgBoxDb database.</span></span> <span data-ttu-id="71b53-132">、メッセージがオーケストレーションごとに調整を有効にする各ホストに対して、fAttributes フラグのビットを 1 に設定します。</span><span class="sxs-lookup"><span data-stu-id="71b53-132">For each host you want to enable message throttling per orchestration, set the fAttributes flag bit to 1.</span></span> <span data-ttu-id="71b53-133">1 に設定されたホストのみにより、メッセージがオーケストレーションごとに調整できます。</span><span class="sxs-lookup"><span data-stu-id="71b53-133">Only those hosts with the fAttribute set to 1 will allow message throttling per orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71b53-134">参照</span><span class="sxs-lookup"><span data-stu-id="71b53-134">See Also</span></span>  
 <span data-ttu-id="71b53-135">[オーケストレーションのデバッグ](../core/debugging-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="71b53-135">[Debugging Orchestrations](../core/debugging-orchestrations.md) </span></span>  
 [<span data-ttu-id="71b53-136">XLANG-s 言語</span><span class="sxs-lookup"><span data-stu-id="71b53-136">XLANG-s Language</span></span>](../core/xlang-s-language.md)
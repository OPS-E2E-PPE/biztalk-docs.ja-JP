---
title: "オーケストレーション エンジンの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestration engine, examples
- orchestration engine, code sample
- orchestration engine, dehydration
- orchestration engine, configuring
ms.assetid: d4f253c3-317d-4b52-bf54-81d50f03eeb3
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbf64565534a368f7bfe084c6901cde62405fb62
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="orchestration-engine-configuration"></a>オーケストレーション エンジンの構成
オーケストレーション エンジンでは、特定の動作を決定するために、BTSNTSvc.exe.config という XML ファイルが使用されます。 たとえば、退避プロパティとその既定値は、BTSNTSvc.exe.config ファイルで XML として構成され、オーケストレーションを含んでいるすべてのホスト インスタンスが開始されると読み取られます。 詳細については、次を参照してください。[オーケストレーションの退避と復元](../core/orchestration-dehydration-and-rehydration.md)です。  
  
 サービスは、開始時にこれらの構成情報を 1 回読み取ります。 サービスが停止され、再開されない限り、構成情報に加えられた変更は一切取得されません。  
  
 ノードごとに設定できる値については、下のサンプルを参照してください。  
  
## <a name="example-all-validations-on"></a>例: 上のすべての検証  
  
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
  
## <a name="example-assembly-validation-only"></a>例: アセンブリの検証のみ  
  
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
  
## <a name="example-remote-debugging-enabled"></a>例: リモート デバッグを有効になっています。  
  
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
  
## <a name="example-appdomain-configuration"></a>例: AppDomain の構成  
 アセンブリは、割り当て規則によって名前付きドメインに割り当てられます。詳細については下のサンプルを参照してください。 規則が指定されないアセンブリが存在する場合、そのアセンブリはアド ホック ドメインに割り当てられます。 1 つのアド ホック ドメインに対してこのように割り当てられるアセンブリの数は、AssembliesPerDomain の値によって決まります。  
  
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
  
## <a name="modifying-other-sections-of-the-btsntsvcexeconfig-file"></a>BTSNTSvc.exe.config ファイルの他のセクションの変更  
 BTSNTSvc.exe.config における退避値を変更する方法については、次を参照してください。[既定の退避プロパティ](../core/dehydration-default-properties.md)です。  
  
 BTSNTSvc.exe 構成ファイルには、「.NET Framework 全般リファレンス」で説明するその他のセクションもいくつか含まれています。 これらのセクションの変更の詳細については、次を参照してください。、**構成ファイル スキーマ**、.NET Framework 全般リファレンスの[http://go.microsoft.com/FWLink/?LinkID=52964](http://go.microsoft.com/FWLink/?LinkID=52964)です。  
  
 BizTalk 固有の構成情報に加えて、BTSNTSvc.exe.config ファイルも、オーケストレーション、アダプターまたはパイプラインのコンテキストで実行される .NET アプリケーション コンポーネントが使用して実行時に構成情報を取得します標準 .NET  **\<appSettings >**下にあるタグ付け、 **\<構成 >**タグ。 BizTalk は、カスタム アダプターとパイプライン コンポーネントの構成情報を取得するためのメカニズムを既に提供されているため、  **\<appSettings >** BTSNTSvc.exe.config ファイル内のタグで通常使用されます。カスタム .NET コンポーネントは、オーケストレーション内から呼び出されます。 例:  
  
```  
<appSettings>  
     <add key="configParamName" value="configParamValue" />  
</appSettings>  
```  
  
## <a name="throttling-messages-per-orchestration"></a>オーケストレーションごとのメッセージの制限  
 このプロパティは BTSNTSvc.exe.config ファイル内で指定され、オーケストレーションが保持できる未処理のメッセージ数を制限することで、オーケストレーションによって過剰なメモリが消費されるのを防ぎます。 すべてのメッセージは引き続き; メッセージ ボックスに配信します。ただし、キューに置かれたメッセージは配信されませんをオーケストレーションに未処理のメッセージの一部が処理されるまでです。  
  
 BTSNTSvc.exe.config ファイル内でこのプロパティを指定するには、Application ノードの下に次のパラメーターを追加します。BTSNTSvc.exe.config ファイルは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のルート ディレクトリにあります。  
  
```  
<configuration>  
            <application>  
                        <Throttling PauseAt="100" ResumeAt="50" />  
            </application>  
</configuration>  
```  
  
 この例では、オーケストレーションにある未処理のメッセージが 100 件に到達すると、メッセージ ボックスからの追加メッセージの送信が停止します。 未処理のメッセージのオーケストレーションの数は 50 件まで下がるが、そのメッセージを送信するメッセージ ボックス データベースを再開できますを指定します。 他の値も指定できます。  
  
 また、この機能を有効にすることも必要があります。 ホスト単位で、データベースにします。 ホスト単位でメッセージ数の制限を有効にするには、BizTalkMsgBoxDb データベースの dbo.Applications テーブルを編集する必要があります。 メッセージがオーケストレーションごとに調整を有効にする各ホストに対して、fAttributes フラグのビットを 1 に設定します。 オーケストレーションごとに調整メッセージを 1 に設定されたホストのみが許可されます。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションのデバッグ](../core/debugging-orchestrations.md)   
 [XLANG の言語](../core/xlang-s-language.md)
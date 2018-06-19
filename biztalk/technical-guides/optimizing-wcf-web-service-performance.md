---
title: WCF Web サービスのパフォーマンスを最適化する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93947cef-469c-4126-85a5-06456fa37443
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 413642931fcf9580ade280c2e7b3472599859d8d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299418"
---
# <a name="optimizing-wcf-web-service-performance"></a>WCF Web サービスのパフォーマンスを最適化します。
WCF サービスは、パフォーマンスに影響するための多数の構成パラメーターを公開します。 このトピックでは、WCF サービスのパフォーマンスを向上させるためにこれらの構成パラメーターの最適な値の設定の一般的なガイダンスを提供します。  
  
## <a name="implement-servicethrottling-behavior-for-backend-wcf-services"></a>バックエンド WCF サービスの serviceThrottling 動作を実装します。  
 バックエンド WCF サービスの serviceThrottling 動作を実装します。 サービスの調整では、リソースの割り当てを適用して、バックエンド WCF サーバーの負荷を均等にできます。 バックエンド WCF サービスの serviceThrottling 動作がの値を変更することによって構成されて、 **maxConcurrentCalls**、 **maxConcurrentSessions**、および**maxConcurrentInstances** WCF サービスの構成ファイル内のパラメーターです。 設定**maxConcurrentCalls**、 **maxConcurrentSessions**、および**maxConcurrentInstances** 16 より大きい値に * Cpu または CPU の数のコアです。 たとえば、8 の CPU コアを備えたコンピューターで次のように設定します**maxConcurrentCalls**、 **maxConcurrentSessions**、および**maxConcurrentInstances** 128 (16 * 8 = 128) より大きい値に。次のようにします。  
  
```  
<serviceThrottling  
maxConcurrentCalls="200"  
maxConcurrentSessions="200"  
maxConcurrentInstances="200" />  
```  
  
## <a name="increase-the-default-values-for-the-nettcpbindinglistenbacklog-and-nettcpbindingmaxconnections-properties-in-the-backend-wcf-service-webconfig-file"></a>バックエンド WCF サービスの web.config ファイルで NetTcpBinding.ListenBacklog および NetTcpBinding.MaxConnections プロパティの既定値を増やす  
 **NetTcpBinding.ListenBacklog**プロパティ保留可能なキューに置かれた接続要求の最大数を制御する Web サービスです。 **NetTcpBinding.MaxConnections**プロパティは、クライアントでの後続の再利用のためにプールできる接続の最大数と、サーバー上でディスパッチを保留できる接続の最大数を制御します。 これらの各プロパティは、既定値のドキュメントを高スループットを必要とするシナリオを処理するために特別に、最適でない可能性のある 10 を使用します。  
  
 実装している WCF サービスを使用する高スループット、ドキュメント処理のシナリオでこれらのプロパティの既定値を増やすことを検討、 **netTcpBinding**クラスをバインドします。  
  
 次の例では、両方の**listenBacklog**と**maxConnections**パラメーターは、「200」の値に設定されます。  
  
```  
<netTcpBinding>  
   <binding name="netTcpBinding"  
      closeTimeout="00:10:00"  
      openTimeout="00:10:00"  
      receiveTimeout="00:10:00"  
      sendTimeout="00:10:00"  
      transactionFlow="false"  
      transferMode="Buffered"  
      transactionProtocol="OleTransactions"  
      hostNameComparisonMode="StrongWildcard"  
      listenBacklog="200"  
      maxBufferPoolSize="1048576"  
      maxBufferSize="10485760"  
      maxConnections="200"  
      maxReceivedMessageSize="10485760">  
      <readerQuotas  
         maxDepth="32"  
         maxStringContentLength="8192"  
         maxArrayLength="16384"  
         maxBytesPerRead="4096"  
         maxNameTableCharCount="16384" />  
      <reliableSession  
         ordered="true"  
         inactivityTimeout="00:10:00"  
         enabled="false" />  
      <security mode="None">  
         <transport clientCredentialType="Windows" protectionLevel="EncryptAndSign" />  
         <message clientCredentialType="Windows" />  
      </security>  
   </binding>  
</netTcpBinding>  
```  
  
 NetTcpBinding.ListenBacklog プロパティの詳細については、次を参照してください。 [NetTcpBinding.ListenBacklog プロパティ](http://go.microsoft.com/fwlink/?LinkId=157752)(http://go.microsoft.com/fwlink/?LinkId=157752) MSDN のです。  
  
 NetTcpBinding.MaxConnections プロパティの詳細については、次を参照してください。 [NetTcpBinding.MaxConnections プロパティ](http://go.microsoft.com/fwlink/?LinkID=157751)(http://go.microsoft.com/fwlink/?LinkID=157751) MSDN のです。  
  
## <a name="eliminate-aspnet-httpmodules-that-are-not-required-to-run-wcf-web-services"></a>WCF Web サービスを実行する必要はありません ASP.NET httpModules を排除します。  
 既定では、いくつかの ASP.NET httpModules は、要求パイプラインとクラシックまたは統合パイプライン IIS 7.5 または 7.0 の IIS 6.0 で定義されます。 これらのコンポーネントは、途中受信し、すべての着信要求を処理します。 既定のモジュールは、64 ビットの ASP の %windir%\Microsoft.NET\Framework64\v2.0.50727\CONFIG フォルダーと 32 ビット ASP.NET アプリケーションに対して %windir%\Microsoft.NET\Framework\v2.0.50727\CONFIG フォルダーに含まれる、web.config ファイルで定義されます。NET アプリケーションを次のスニペットで示すようにします。  
  
```  
<httpModules>  
<add name="OutputCache" type="System.Web.Caching.OutputCacheModule"/>  
<add name="Session" type="System.Web.SessionState.SessionStateModule"/>  
<add name="WindowsAuthentication" type="System.Web.Security.WindowsAuthenticationModule"/>  
<add name="FormsAuthentication" type="System.Web.Security.FormsAuthenticationModule"/>  
<add name="PassportAuthentication" type="System.Web.Security.PassportAuthenticationModule"/>  
<add name="RoleManager" type="System.Web.Security.RoleManagerModule"/>  
<add name="UrlAuthorization" type="System.Web.Security.UrlAuthorizationModule"/>  
<add name="FileAuthorization" type="System.Web.Security.FileAuthorizationModule"/>  
<add name="AnonymousIdentification" type="System.Web.Security.AnonymousIdentificationModule"/>  
<add name="Profile" type="System.Web.Profile.ProfileModule"/>  
<add name="ErrorHandlerModule" type="System.Web.Mobile.ErrorHandlerModule, System.Web.Mobile, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"/>  
<add name="ServiceModel" type="System.ServiceModel.Activation.HttpModule, System.ServiceModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
</httpModules>  
```  
  
 ほとんどのシナリオでは、これらのモジュールのすべてをロードする必要はありません。 したがって、可能であれば WCF Web サービスを実行するときに、次の Httpmodule を排除することでパフォーマンスを向上させる。  
  
-   Session  
  
-   WindowsAuthentication  
  
-   FormsAuthentication  
  
-   PassportAuthentication  
  
-   RoleManager  
  
-   AnonymousIdentification  
  
-   プロファイル  
  
## <a name="use-the-wcf-modulehandler-registration-tool-to-configure-wcf-moduleshandlers-and-improve-scalability-of-iis-7570-hosted-wcf-services"></a>ハンドラーの登録ツールを WCF モジュール/ハンドラーを構成し、IIS 7.5 または 7.0 のスケーラビリティを向上させるには、WCF サービスがホストされている/WCF モジュールを使用します。  
 WCF モジュールまたはハンドラーの登録ツールがダウンロード[http://go.microsoft.com/fwlink/?LinkId=157593](http://go.microsoft.com/fwlink/?LinkId=157593) (http://go.microsoft.com/fwlink/?LinkId=157593)。 このユーティリティを使用して、インストール、リスト、または、次の WCF モジュールを構成することができます。  
  
-   WCF 同期 HTTP モジュールとハンドラー  
  
-   WCF の非同期 HTTP モジュールとハンドラー  
  
-   WCF HTTP モジュールとハンドラー  
  
 詳細については、ハンドラーを使用して、非同期 WCF HTTP モジュール/IIS 7.5 または 7.0 のスケーラビリティを向上させるには、WCF サービスがホストされている、Wenlong Dong のブログを参照してください[Orcas SP1 の改善: 非同期 WCF HTTP モジュールとハンドラーより優れた IIS7 用サーバーのスケーラビリティ](http://go.microsoft.com/fwlink/?LinkId=157428)(http://go.microsoft.com/fwlink/?LinkId=157428)。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server WCF アダプターのパフォーマンスを最適化します。](../technical-guides/optimizing-biztalk-server-wcf-adapter-performance.md)
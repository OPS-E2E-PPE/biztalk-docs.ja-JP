---
title: WCF アダプターのセキュリティに関する推奨事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF adapters, security
- security, WCF adapters
ms.assetid: bbaaca56-9ad5-4122-a8e9-6e975d308230
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f871c68277c487efcc7400a3ae54db749090148e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993451"
---
# <a name="wcf-adapters-security-recommendations"></a>WCF アダプターのセキュリティに関する推奨事項
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、WCF アダプターを使用して WCF サービスを公開 (受信) および使用 (送信) します。 使用している環境内において WCF アダプターをセキュリティで保護して展開するには、次のガイドラインに従うことをお勧めします。  
  
 WCF アダプターに関する詳細については、[WCF アダプタ](../core/wcf-adapters.md)を参照してください。 WCF サービスの詳細については、次を参照してください。 [WCF サービスを使用する](../core/using-wcf-services.md)秒。  
  
## <a name="security-recommendations-for-all-wcf-adapters"></a>すべての WCF アダプターのセキュリティに関する推奨事項  
  
-   フロントエンド ユーザーのコンテンツをバックエンド システムの資格情報にマップする必要がある場合、エンタープライズ シングル サインオン (SSO) を使用できます。  
  
-   すべてのサービスでメタデータが公開されている必要はありません。 メタデータの公開を無効のままにすることで、サービスの攻撃対象領域が減り、意図しない情報公開の危険性が低くなります。 メタデータに関連するセキュリティの問題に関する詳細についてにある「Security Considerations with Metadata」を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=196671](http://go.microsoft.com/fwlink/?LinkId=196671)します。  
  
-   メタデータ エンドポイントのバインドとサービス エンドポイントのバインドのすべての組み合わせが有効であるとは限りません。 メタデータ エンドポイントのバインド構成がサービス エンドポイントのバインド構成と一致する必要がある場合もあります。 たとえば、メタデータが受信場所と同じ場所から提供されていて、その受信場所が HTTPS に依存するセキュリティ モードを使用している場合、メタデータ エンドポイントは、HTTP トランスポートを必要とするセキュリティ モードで構成することができません。  
  
    > [!NOTE]
    >  同じ場所が、BizTalk WCF 公開ウィザードによって生成される Web.config ファイルで、HTTPS トランスポートに依存するセキュリティ モードを必要とするサービス エンドポイント、HTTP トランスポートを通じてメタデータを発行するときに、の両方を設定する必要があります。**httpsGetEnabled**と**httpGetEnabled**属性を**true**します。  
  
-   WCF アダプターは、Windows Communication Foundation (WCF) のセキュリティ機能を利用して通信します。 セキュリティの観点から WCF の機能と制限事項を理解しておく必要があります。 WCF のセキュリティ機能に関する詳細についてで「Windows Communication Foundation Security」を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=87806](http://go.microsoft.com/fwlink/?LinkId=87806)します。  
  
## <a name="security-recommendations-for-the-isolated-wcf-adapters"></a>分離 WCF アダプターのセキュリティに関する推奨事項  
  
- Web サービスを公開するためのセキュリティの推奨事項については、[Web サービスを有効にする](../core/enabling-web-services.md)を参照してください。  
  
- WCF-CustomIsolated、WCF-BasicHttp、WCF-WSHttp などの分離 WCF アダプターは、HTTP (ハイパーテキスト転送プロトコル) を利用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] との間でメッセージを送受信します。 そのため、インターネット インフォメーション サービス (IIS) を保護するためのセキュリティの推奨事項に従う必要があります。  
  
- 分離 WCF 受信場所にアプリケーション プールを作成する場合は、WCF 受信アダプターを実行している分離ホストの [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] グループおよびインターネット インフォメーション サービスのワーカー プロセス グループ (IIS_WPG group) のメンバーであるアカウントで実行するように構成する必要があります。 その後、WCF 受信アダプターのホスト インスタンスを、このアカウントを使用するように構成してください。 IIS_WPG グループのアカウントを変更する場合は、新しいアカウントで実行するようにホスト インスタンスを更新する必要もあります。  
  
## <a name="security-recommendations-for-the-wcf-custom-adapter"></a>WCF-Custom アダプターのセキュリティに関する推奨事項  
  
-   HTTP カーネル モード ドライバー (HTTP.sys) を使用する場合は、Wcf-custom 受信場所、 **httpsTransport** Secure Sockets Layer (SSL) 通信、受信場所のバインド要素は、証明書が必要ソケット (IP アドレスとポートの組み合わせ) ごとに登録します。 SSL 証明書をコンピューター上のポートにバインドするには、HttpCfg.exe ツールを使用します。 詳細についてを参照してください「方法に::、ポートでの SSL 証明書の構成」 [ http://go.microsoft.com/fwlink/?LinkId=86384](http://go.microsoft.com/fwlink/?LinkId=86384)します。  
  
## <a name="security-recommendations-for-the-wcf-netmsmq-adapter"></a>WCF-NetMsmq アダプターのセキュリティに関する推奨事項  
  
-   Wcf-netmsmq アダプターを使用する場合と同じ方法で、Wcf-netmsmq アダプターの MSMQ セキュリティ設定を構成する必要がある、 [netMsmqBinding](http://go.microsoft.com/fwlink/?LinkId=87813)します。 MSMQ セキュリティ設定を構成する方法について、 **netMsmqBinding**、ある Troubleshooting Queued Messaging」を参照してください[ http://go.microsoft.com/fwlink/?LinkId=87816](http://go.microsoft.com/fwlink/?LinkId=87816)します。  
  
## <a name="wcf-adapters-use-the-chaintrust-mode-to-validate-certificates"></a>WCF アダプターでの ChainTrust モードを使用した証明書の検証  
  
-   標準の WCF 受信アダプターを使用しているため、 [ChainTrust](http://go.microsoft.com/fwlink/?LinkId=88960)モード クライアントとサービスの証明書を検証する X.509 証明書を検証する CA 証明書チェーンをインストールする必要があります。 WCF-Custom アダプターまたは WCF-CustomIsolated アダプターを使用すると、この既定の動作を変更できます。  
  
## <a name="security-auditing-for-the-wcf-adapters"></a>WCF アダプターのセキュリティ監査  
  
- 既定では、WCF アダプターは WCF セキュリティ監査機能を使用しません。 WCF アダプターの WCF セキュリティ監査機能を有効にするには、複数の方法があります。 WCF セキュリティ監査機能の詳細についてを参照してください「セキュリティ イベントを監査」 [ http://go.microsoft.com/fwlink/?LinkId=88975](http://go.microsoft.com/fwlink/?LinkId=88975)します。  
  
- WCF セキュリティ監査の Wcf-custom 受信アダプターを使用した機能を使用することができます、 **ServiceSecurityAuditBehavior**の受信場所。  
  
- インプロセス WCF アダプターの場合、パフォーマンス カウンターは BTSNTSvc.exe.config ファイルを使用して有効にすることができます。 分離 WCF アダプターの場合は、BizTalk WCF サービス公開ウィザードによって Web アプリケーション フォルダーに作成される Web.config ファイルを変更して WCF 追跡を有効にすることができます。 BTSNtSvc.exe.config または Web.config を変更するには、構成ファイルを開き、次の構成例に示すように WCF 追跡を構成します。  
  
  > [!NOTE]
  >  BTSNTSvc.exe.config ファイルは常に BTSNTSvc.exe ファイルと同じディレクトリ (通常は [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]) に配置されます。  
  > 
  > [!NOTE]
  >  BTSNTSvc.exe.config ファイルを変更した後、インプロセス WCF 受信場所を実行するホスト インスタンスを再起動する必要があります。  
  
  ```  
  <configuration>  
      <system.serviceModel>  
        <diagnostics performanceCounters="All" />  
        <behaviors>  
          <serviceBehaviors>  
            <behavior name="ServiceBehaviorConfiguration">  
              <serviceSecurityAudit  
                        auditLogLocation="Application"  
                        suppressAuditFailure="true"  
                        serviceAuthorizationAuditLevel="SuccessOrFailure"  
  messageAuthenticationAuditLevel="SuccessOrFailure" />  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
        <services>  
          <service name="Microsoft.BizTalk.Adapter.Wcf.Runtime.BizTalkServiceInstance" behaviorConfiguration="ServiceBehaviorConfiguration">  
          </service>  
        </services>        
      </system.serviceModel>  
  </configuration>  
  ```  
  
- さらに、"承認されていないセキュリティ呼び出し" などのセキュリティ関連のパフォーマンス カウンターを使用して WCF アダプターを監視することもできます。 WCF パフォーマンス カウンタを有効にする方法の詳細については、[WCF アダプターのパフォーマンス カウンター](../core/wcf-adapters-performance-counters.md)を参照してください。  
  
## <a name="see-also"></a>参照  
 [セキュリティの計画](../core/planning-for-security.md)
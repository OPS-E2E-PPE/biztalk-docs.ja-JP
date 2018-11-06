---
title: 'チェックリスト: セキュリティで保護された環境での操作の計画 |Microsoft Docs'
ms.custom: ''
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d6464df-6736-46e2-a0c7-cc2a256c5144
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb882531141114842983ca93be9d799898ecefdf
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50753114"
---
# <a name="checklist-planning-for-operations-in-a-secure-environment"></a>チェックリスト: セキュリティで保護された環境での操作の計画
実行している[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]セキュリティで保護された環境でのデプロイと構成の追加の手順が必要です。 オペレーティング システムの既定のインストールが必要になりませんこれらのアカウントが、シナリオに制限の厳しいセキュリティ ポリシーが適用されている、中に、このセクションの情報はアカウントに行う必要があります。 サーバーに適用される制限のレベルが異なる場合がありますが、以下の情報はほとんどの場合に対応する必要があり、適切な開始点となります。  

-   [BizTalk Server を実行しているコンピューターのセキュリティに関する考慮事項](../technical-guides/checklist-planning-for-operations-in-a-secure-environment.md#BKMK_BTSSec)  

-   [SQL Server を実行しているコンピューターのセキュリティに関する考慮事項](../technical-guides/checklist-planning-for-operations-in-a-secure-environment.md#BKMK_SQLServSec)  

-   [追加のセキュリティに関する考慮事項](../technical-guides/checklist-planning-for-operations-in-a-secure-environment.md#BKMK_AddSec)  

<a name="BKMK_BTSSec"></a>   
## <a name="security-considerations-for-computers-running-biztalk-server"></a>BizTalk Server を実行しているコンピューターのセキュリティに関する考慮事項  
 次の表は、実行しているコンピューターのセキュリティ関連の設定を示して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  

### <a name="user-rights-assignment"></a>ユーザー権利の割り当て  
 ユーザー権利の割り当ての MMC スナップインを開始するには、クリックして**開始**、 をクリックして**管理ツール**、 をクリックし、**ローカル セキュリティ ポリシー**。 **ローカル セキュリティ ポリシー** MMC スナップインで、展開**セキュリティ設定**、展開**ローカル ポリシー**、 をクリックし、**ユーザー権利の割り当て**.  

|ポリシーの設定|値|リファレンスと詳細|  
|--------------------|------------|---------------------------|  
|サービスとしてログオン|BizTalk Application Users|BizTalk ホスト インスタンスの実行に必要です。 別のユーザー アカウントの詳細については、次を参照してください。 [Windows グループと BizTalk Server でのユーザー アカウント](http://go.microsoft.com/fwlink/?LinkID=155755)(http://go.microsoft.com/fwlink/?LinkID=155755)します。|  
|サービスとしてログオン|ルール エンジン更新サービス アカウント|ルール エンジン更新サービスの実行に必要です。 別のユーザー アカウントの詳細については、次を参照してください。 [Windows グループと BizTalk Server でのユーザー アカウント](http://go.microsoft.com/fwlink/?LinkID=155755)(http://go.microsoft.com/fwlink/?LinkID=155755)します。|  
|サービスとしてログオン|SSO サービス アカウント|エンタープライズ シングル サインオン サービスの実行に必要です。 別のユーザー アカウントの詳細については、次を参照してください。 [Windows グループと BizTalk Server でのユーザー アカウント](http://go.microsoft.com/fwlink/?LinkID=155755)(http://go.microsoft.com/fwlink/?LinkID=155755)します。|  

### <a name="system-services"></a>システム サービス  
 サービス MMC スナップインを開始するには、クリックして**開始**、 をクリックして**実行**、し、**実行**ダイアログ ボックスに「 `services.msc` ENTER キーを押します。  


|                [サービス名]                 | スタートアップの種類<sup>1</sup> |                                                              詳細                                                               |       ユーザー<sup>2</sup>        | アクセス許可  |             詳細             |
|---------------------------------------------|--------------------------|------------------------------------------------------------------------------------------------------------------------------------|-------------------------------|--------------|---------------------------------|
|           COM+ System Application           |        自動         |                                                BizTalk が正常に実行するために必要な                                                 |           (既定値)。           |              |                                 |
|                 DHCP クライアント                 |        自動         |                                              IP アドレスは静的な場合でも必要です。                                              |           (既定値)。           |              |                                 |
|     分散トランザクション コーディネーター     |        自動         |                                                BizTalk が正常に実行するために必要な                                                 |      SSO サービス アカウント      | フル コントロール |  SSO サービスを開始するために必要  |
|                                             |                          |                                                                                                                                    | BizTalk ホスト サービス アカウント | フル コントロール | BizTalk ホストを開始するために必要 |
|                                             |                          |                                                                                                                                    |        Network Service        | フル コントロール |         IIS が必要です。         |
|            HTTP SSL<sup>3</sup>             |        自動         |                                                          IIS が必要です。                                                           |           (既定値)。           |              |                                 |
|         IPSEC サービス<sup>3</sup>          |        自動         |                                              IPSEC が使用されている場合、ネットワーク セキュリティを向上します。                                              |           (既定値)。           |              |                                 |
|                  Netlogon                   |        (既定値)。         |                                                                                                                                    |         Local Service         | フル コントロール |                                 |
| NT LM Security Support Provider<sup>3</sup> |        自動         | Kerberos 認証のために必要な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]sql |           (既定値)。           |              |                                 |
|      Remote Access Connection Manager       |        (既定値)。         |                                                                                                                                    |      SSO サービス アカウント      | フル コントロール |  SSO サービスを開始するために必要  |
|                                             |                          |                                                                                                                                    | BizTalk ホスト サービス アカウント | フル コントロール | BizTalk ホストを開始するために必要 |
|                                             |                          |                                                                                                                                    |        Network Service        | フル コントロール |         IIS が必要です。         |
|     リモート プロシージャ コール (RPC) ロケーター     |        自動         |                                                        BizTalk が必要です。                                                         |           (既定値)。           |              |                                 |
|  WinHTTP の Web プロキシ自動検出サービス   |        (既定値)。         |                                                                                                                                    |      SSO サービス アカウント      | フル コントロール |  SSO サービスを開始するために必要  |
|                                             |                          |                                                                                                                                    | BizTalk ホスト サービス アカウント | フル コントロール | BizTalk ホストを開始するために必要 |

 <sup>1</sup> (既定値) の値は、セキュリティ ポリシーによって適用される既定の設定が変更されていないことを意味  

 <sup>2</sup> (既定値) の値は、サービスの既定のユーザー アクセス許可が変更されていないことを意味  

### <a name="registry-settings"></a>レジストリ設定  
 レジストリ エディターを起動するには、次のようにクリックします。**開始**、 をクリック**実行**、し、**実行**ダイアログ ボックスに「 `regedit` ENTER キーを押します。  

|Key|ユーザー|アクセス許可|詳細|  
|---------|----------|-----------------|-------------|  
|Hklm \ SYSTEM\CurrentControlSet\Services\DHCP|Network Service|フル コントロール|DHCP クライアント サービスに必要な|  
|Hklm \ SYSTEM\CurrentControlSet\Services\TCPIP|Network Service|フル コントロール|DHCP クライアント サービスに必要な|  

<a name="BKMK_SQLServSec"></a>   
## <a name="security-considerations-for-computers-running-sql-server"></a>SQL Server を実行しているコンピューターのセキュリティに関する考慮事項  
 次の表は、実行しているコンピューターのセキュリティ関連の設定を示して[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。  

### <a name="user-rights-assignment"></a>ユーザー権利の割り当て  
 ユーザー権利の割り当ての MMC スナップインを開始するには、クリックして**開始**、 をクリックして**管理ツール**、 をクリックし、**ローカル セキュリティ ポリシー**。 **ローカル セキュリティ ポリシー** MMC スナップインで、展開**セキュリティ設定**、展開**ローカル ポリシー**、 をクリックし、**ユーザー権利の割り当て**.  


|                         ポリシーの設定                         |                                             値                                              |                                                                                                                             リファレンスと詳細                                                                                                                             |
|----------------------------------------------------------------|-------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|              オペレーティング システムの一部として機能               |                  SQL Server エージェント サービス アカウント、SQL Server サービス アカウント                   |         実行に必要な[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。 詳細については、次を参照してください。 [Windows サービス アカウントの設定を](http://go.microsoft.com/fwlink/?LinkId=157415)(<http://go.microsoft.com/fwlink/?LinkId=157415>)。          |
|               プロセスのメモリ クォータの調整               |                   SQL Server エージェント サービス アカウント、SQL Server サービス アカウント                   |         実行に必要な[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。 詳細については、次を参照してください。 [Windows サービス アカウントの設定を](http://go.microsoft.com/fwlink/?LinkId=157415)(<http://go.microsoft.com/fwlink/?LinkId=157415>)。          |
|                    走査チェックのバイパス                    |                   SQL Server エージェント サービス アカウント、SQL Server サービス アカウント                   |         実行に必要な[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。 詳細については、次を参照してください。 [Windows サービス アカウントの設定を](http://go.microsoft.com/fwlink/?LinkId=157415)(<http://go.microsoft.com/fwlink/?LinkId=157415>)。          |
|                     グローバル オブジェクトの作成                      |                                   [SQL Server サービス アカウント]                                    |                                          SSIS サービスで必要です。 詳細については、次を参照してください。 [Windows サービス アカウントの設定を](http://go.microsoft.com/fwlink/?LinkId=157415)(<http://go.microsoft.com/fwlink/?LinkId=157415>)。                                           |
| 委任に対して信頼されるコンピューターとユーザーのアカウントを有効にします。 | SQL Server サービス アカウント、SQL Server サーバーでは、BizTalk Server サーバー、SQL Server クラスター名 | BizTalk Server で必要です。 サーバー名が、 \<servername\>$。 詳細については、次を参照してください。[方法: SQL Server フェールオーバー クラスターで Kerberos 認証を有効にする](http://go.microsoft.com/fwlink/?LinkId=157417)(<http://go.microsoft.com/fwlink/?LinkId=157417>)。 |
|                      サービスとしてログオン                       |                   SQL Server エージェント サービス アカウント、SQL Server サービス アカウント                   |         実行に必要な[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。 詳細については、次を参照してください。 [Windows サービス アカウントの設定を](http://go.microsoft.com/fwlink/?LinkId=157415)(<http://go.microsoft.com/fwlink/?LinkId=157415>)。          |
|                      サービスとしてログオン                       |                                       SSO サービス アカウント                                       |       エンタープライズ シングル サインオン サービスの実行に必要です。 別のユーザー アカウントの詳細については、次を参照してください。 [Windows グループと BizTalk Server でのユーザー アカウント](http://go.microsoft.com/fwlink/?LinkID=155755)(<http://go.microsoft.com/fwlink/?LinkID=155755>)。       |
|                      バッチ ジョブとしてログオンします。                       |                   SQL Server エージェント サービス アカウント、SQL Server サービス アカウント                   |         実行に必要な[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。 詳細については、次を参照してください。 [Windows サービス アカウントの設定を](http://go.microsoft.com/fwlink/?LinkId=157415)(<http://go.microsoft.com/fwlink/?LinkId=157415>)。          |
|                 プロセス レベル トークンを置き換え                  |                   SQL Server エージェント サービス アカウント、SQL Server サービス アカウント                   |         実行に必要な[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。 詳細については、次を参照してください。 [Windows サービス アカウントの設定を](http://go.microsoft.com/fwlink/?LinkId=157415)(<http://go.microsoft.com/fwlink/?LinkId=157415>)。          |

### <a name="system-services"></a>システム サービス  
 サービス MMC スナップインを開始するには、クリックして**開始**、 をクリックして**実行**、し、**実行**ダイアログ ボックスに「 `services.msc` ENTER キーを押します。  


|                [サービス名]                 |     スタートアップの種類<sup>1</sup>      |                                                              詳細                                                               |             ユーザー<sup>2</sup>              | アクセス許可  |            詳細            |
|---------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------|--------------|-------------------------------|
|                 DHCP クライアント                 |             自動             |                                              IP アドレスは静的な場合でも必要です。                                              |                 (既定値)。                 |              |                               |
|     分散トランザクション コーディネーター     |              手動               |                                             クラスター サービスによって管理されるサービスのスタートアップ                                             |            SSO サービス アカウント            | フル コントロール | SSO サービスを開始するために必要 |
|                                             |                                   |                                                                                                                                    |              Network Service              | フル コントロール |        IIS が必要です。        |
|            HTTP SSL<sup>3</sup>             |             自動             |                                                          IIS が必要です。                                                           |                 (既定値)。                 |              |                               |
|         IPSEC サービス<sup>3</sup>          |             自動             |                                              IPSEC が使用されている場合、ネットワーク セキュリティを向上します。                                              |                 (既定値)。                 |              |                               |
|                  Netlogon                   |             (既定値)。             |                                                                                                                                    |               Local Service               | フル コントロール |                               |
| NT LM Security Support Provider<sup>3</sup> |             自動             | Kerberos 認証のために必要な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]sql |                 (既定値)。                 |              |                               |
|      Remote Access Connection Manager       |             (既定値)。             |                                                                                                                                    |            SSO サービス アカウント            | フル コントロール | SSO サービスを開始するために必要 |
|                                             |                                   |                                                                                                                                    |              Network Service              | フル コントロール |        IIS が必要です。        |
|                   [サーバー]                    |             自動             |                                              ファイル共有のクラスター化されたリソースの使用                                               |              Network Service              | フル コントロール |                               |
|  WinHTTP の Web プロキシ自動検出サービス   |             (既定値)。             |                                                                                                                                    |            SSO サービス アカウント            | フル コントロール | SSO サービスを開始するために必要 |
|                                             | World Wide Web Publishing サービス |                                                             自動                                                              | SQL Server Reporting Services で必要 |  (既定値)。   |                               |

 <sup>1</sup> (既定値) の値は、セキュリティ ポリシーによって適用される既定の設定が変更されていないことを意味  

 <sup>2</sup> (既定値) の値は、サービスの既定のユーザー アクセス許可が変更されていないことを意味  

### <a name="registry-settings"></a>レジストリ設定  
 レジストリ エディターを起動するには、次のようにクリックします。**開始**、 をクリック**実行**、し、**実行**ダイアログ ボックスに「 `regedit` ENTER キーを押します。  

|Key|ユーザー|アクセス許可|詳細|  
|---------|----------|-----------------|-------------|  
|Hklm \ SYSTEM\CurrentControlSet\Services\DHCP|Network Service|フル コントロール|DHCP クライアント サービスに必要な|  
|Hklm \ SYSTEM\CurrentControlSet\Services\TCPIP|Network Service|フル コントロール|DHCP クライアント サービスに必要な|  

<a name="BKMK_AddSec"></a>   
## <a name="additional-security-considerations"></a>追加のセキュリティに関する考慮事項  
 次の表は、その他の重要なセキュリティ関連の設定を示して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。  


|                                        成果物の影響を受ける                                        |                                 [変更]                                  |                                                                                                               リファレンスと詳細                                                                                                                |
|-------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                       SSO サービス アカウント                                       |       クラスター マネージャーでクラスターに対するフル コントロール権限を許可します。       |                                                                                             この変更は正常に動作するために SSO に必要なします。                                                                                              |
| SQL Server サービス アカウント、SQL Server サーバーでは、BizTalk Server サーバー、SQL Server クラスター名 |                Active Directory で委任に対して信頼                 | 適切な Kerberos 認証が必要です。 詳細については、次を参照してください。[方法: SQL Server フェールオーバー クラスターで Kerberos 認証を有効にする](http://go.microsoft.com/fwlink/?LinkId=157417)(<http://go.microsoft.com/fwlink/?LinkId=157417>)。 |
|                                   [SQL Server サービス アカウント]                                    |                 SPN のエントリを作成するアクセス許可を付与                  |            適切な Kerberos 認証が必要です。 詳細については、次を参照してください。 [SQL Server で Kerberos 認証を使用する方法](http://go.microsoft.com/fwlink/?LinkId=157420)(<http://go.microsoft.com/fwlink/?LinkId=157420>)。             |
|                               SQL Server ノードでは、SQL クラスターの名前                                |         SQL Server サービス アカウントのユーザーの SPN のエントリを作成します。          |            適切な Kerberos 認証が必要です。 詳細については、次を参照してください。 [SQL Server で Kerberos 認証を使用する方法](http://go.microsoft.com/fwlink/?LinkId=157420)(<http://go.microsoft.com/fwlink/?LinkId=157420>)。             |
|                               SQL ネットワーク名クラスター リソース                                |     DNS 登録する必要がありますの成功、Kerberos 認証の有効化      |                                                                                                    適切な Kerberos 認証に必要な                                                                                                     |
|                                SQL Server セキュリティ構成                                 |              管理者が直接リモート接続を有効にします。              |                                           SQL Server のインスタンスの名前を正しく特定するには、SQL クライアント (BizTalk/ASP.NET) で必要な適切に機能する SQL ブラウザー サービスで必要                                           |
|                                 BizTalk アプリケーション ユーザー グループ                                 | Grant Execute 権限を**sp_help_jobhistory**で**msdb**データベース |                                                                           要求者 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                           |

## <a name="see-also"></a>参照  
 [その他の重要なタスクのチェックリスト](~/technical-guides/checklists-for-other-important-tasks.md)

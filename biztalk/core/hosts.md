---
title: ホスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- host instances, servers
- hosts, isolated
- host instances, relationships
- hosts, in-process hosts
- servers, hosts
- hosts, host instances
- hosts, relationships
- In-Process BizTalk Host groups
- hosts, about hosts
- hosts, untrusted
- host instances, hosts
- hosts, servers
- hosts
- servers, host instances
- Isolated Host Users group
- hosts, trusted
ms.assetid: d96537e0-e679-407a-8870-34a663acfed9
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 790c839685e71dd1a88b637e5ca7811d62809cc0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980019"
---
# <a name="hosts"></a>Hosts
BizTalk ホスト オブジェクトとは、0 個以上のランタイム プロセスの論理セットであり、サービスやパイプラインなどの各種アイテムを展開する場所です。 ホスト オブジェクトは、展開されたアイテムが物理的に実行されるランタイム インスタンス (0 個以上) の集合でもあります。  
  
 ホスト (論理コンテナー) を作成した後、そのホストに対し、物理的な BizTalk Server (ホスト インスタンス) を追加できます。 BizTalk Server を 2 回以上同じホストに追加することはできません。 1 つのホスト インスタンスを複数のホストに追加できます。  
  
 項目-アダプター ハンドラー、受信場所 (パイプラインを含む)、およびオーケストレーションに含まれる BizTalk ホストは、次の関数を実行できます。  
  
- **受信**します。 受信場所から取得された後のメッセージに対して初期処理を実行します。 受信機能 (受信場所やパイプラインなど) をつかさどるホストはセキュリティの処理境界として機能し、メッセージのデコードや復号化は、そのホスト内のパイプラインで行われます。  
  
- **送信**します。 送信ポートに送られる前のメッセージに対して最終処理を実行します。 送信機能 (送信ポートやパイプラインなど) をつかさどるホストはセキュリティの処理境界として機能し、メッセージの署名や暗号化は、そのホスト内のパイプラインで行われます。  
  
- **処理**します。 オーケストレーションの命令に基づいてメッセージを処理します。  
  
  1 つの BizTalk ホストに、メッセージの受信、送信、および処理の機能をすべて割り当てることもできます。 ただし、セキュリティの処理境界を設け、管理を容易にするには、機能ごとに異なるホストを作成することをお勧めします。 特に、処理と送受信には異なるホストを使用し、信頼済みのアイテムとそうでないアイテムを分離してください。  
  
  次の図に、サーバー、ホスト、およびホスト インスタンスの関係を示します。  
  
  ![ホスト、ホスト インスタンス、およびサーバーの関係](../core/media/ebiz-ops-adm01.gif "ebiz_ops_adm01")  
  ホスト、ホスト インスタンス、およびサーバー間のリレーションシップ  
  
  ホスト インスタンスの詳細については、次を参照してください。[ホスト インスタンス](../core/host-instances.md)します。  
  
  物理的な構成とホストされているアダプターの種類に基づきはホストの 2 つの種類があります。 インプロセス ホストと分離ホスト。  
  
## <a name="in-process-hosts"></a>インプロセス ホスト  
 インプロセス ホストとは、管理者が Windows Management Instrumentation (WMI) および BizTalk 管理コンソールを使用して作成や削除を行い、完全に管理するサービス インスタンスです。  
  
 インプロセス ホストの特性は、次のとおりです。  
  
- インプロセス ホストには任意のオーケストレーションを参加させることができます。  
  
- インプロセス ホストは送信ハンドラーをホストできます。  
  
- インプロセス ホストでは、SOAP および HTTP を除く任意の受信ハンドラーをホストできます。  
  
  -   FILE  
  
  -   FTP  
  
  -   MQSeries  
  
  -   MSMQ (MSMQ)  
  
  -   POP3  
  
  -   SQL  
  
  -   Windows SharePoint Services  
  
- 作成する最初のインプロセス ホストを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]デプロイが、**既定ホスト**し、それを削除することはできません。 BizTalk メッセージ キュー アダプターでは、静的なハンドラー構成に既定のホストを使用します。 アダプターを追加すると、既定のホストの送受信ポートが自動的に作成されます。  
  
## <a name="isolated-hosts"></a>分離ホスト  
 分離ホストとは、ソリューション開発者がプログラムによって作成、削除、および管理を行うサービス インスタンスです。 管理者は WMI および BizTalk 管理コンソールを使用して、これらのホストを設定します (たとえば、ホスト サービス アカウントや信頼されている認証を設定します)。  
  
 分離ホストは主に、通常の BizTalk Server ランタイム プロセスの外部で実行する必要があるアダプターをホストします。 たとえば、分離ホストを使用して、ISAPI 拡張や ASP.NET などの外部プロセス用のアダプターをホストします。  
  
 分離ホストの特性は、次のとおりです。  
  
-   分離ホストには、オーケストレーションを参加させることができません。  
  
-   分離ホストは送信ハンドラーをホストできません。  
  
-   分離ホストは、HTTP/S アダプターおよび SOAP アダプター (分離タイプ アダプター) に関連付けられている受信ハンドラーのみをホストできます。  
  
-   分離ホストは追跡機能をホストできません。  
  
-   分離ホストは既定のホストとして使用できません。  
  
-   分離ホストの状態は常に**状態を確認できない**します。 これは、BizTalk Server から外部プロセスの状態情報にアクセスできないからです。  
  
> [!NOTE]
>  ホスト インスタンスは、同じセキュリティ設定 (信頼済みの認証) を共有している限り、同じサービス アカウントを共有できます。  
  
## <a name="trusted-and-untrusted-hosts"></a>信頼済みのホストと信頼されていないホスト  
 BizTalk Server では、認証が信頼済みであると確認されたホストは、メッセージ ボックス データベースへキュー送信するときに、メッセージの送信者がこのホスト以外のエンティティであると示すことができます。 信頼済み認証の主な目的は、パイプラインが製品 ID (PID) を解決し、認証や送信側の解決に使用されるサービスにその PID を渡して、オーケストレーション アクションの認証に使用されるサービスに送信者の Windows セキュリティ ID (SSID) を送信できるようにすることです。  
  
## <a name="see-also"></a>参照  
 [ホスト インスタンス](../core/host-instances.md)   
 [BizTalk ホストとホスト インスタンスの管理](../core/managing-biztalk-hosts-and-host-instances.md)  
 [エンティティ](../core/entities.md)
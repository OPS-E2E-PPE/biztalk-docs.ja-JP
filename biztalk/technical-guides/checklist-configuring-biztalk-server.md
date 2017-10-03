---
title: "チェックリスト: BizTalk Server の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: adfb5a5e-2a23-4f6c-865f-a3300bf3d01d
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11c1348ef4ce34676cd206c08530f66f20730378
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-configuring-biztalk-server"></a>チェックリスト: BizTalk Server を構成します。
次の手順を準備するときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で使用するため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実稼働環境。  
  
|手順|リファレンス|  
|-----------|---------------|  
|BizTalk ホストとホスト インスタンスを構成します。|送信、受信、処理、および複数のホストに追跡機能を区切ります。 これにより、ワークロードを構成するときに、柔軟性を提供し、その他のホストに影響を与えずに 1 つのホストを停止することができます。 詳細については、次を参照してください。[を構成するホストとホスト インスタンス](../technical-guides/configuring-hosts-and-host-instances.md)です。|  
|準拠して、BizTalk ホスト インスタンスのメモリ使用量の最大の実用的な制限を理解しておくことを確認してください。|[32 ビットの BizTalk ホスト インスタンスのメモリ使用量の最大の実用的な制限](../technical-guides/configuring-hosts-and-host-instances.md#BKMK_MemLimit)|  
|専用の追跡ホストを構成します。|ホストの追跡が何も実行しない専用のホストを使用します。 これにより、ホストしている同じホスト上で実行されているその他の BizTalk アイテムのパフォーマンスに影響を与えてから追跡します。 また、追跡を妨げることがなく他のホストを停止することもできます。 追跡ホストを実行するには、少なくとも 2 つのコンピューターで実行する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)](の場合に備えた冗長性のいずれかに失敗する)。 詳細については、次を参照してください。[専用追跡ホストの構成](../technical-guides/configuring-a-dedicated-tracking-host.md)です。|  
|SOAP、HTTP、HTTP ベースの WCF アダプターの同時接続の設定|[IIS 構成設定を適用します。](../technical-guides/apply-iis-configuration-settings.md)|  
|BizTalk アプリケーションのアップグレードおよびバージョン管理の戦略を実装します。|-長時間のオーケストレーションをサポートする必要がありますまたは、BizTalk アプリケーションのダウンタイムなしでの BizTalk アプリケーション展開を実行する必要があります、場合を実装し、信頼性の高い、エンド ツー エンドの練習[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]のバージョン管理の戦略、。異なるバージョン管理のシナリオです。<br />実行時間の長いオーケストレーション、サイド バイ サイド展開やダウンタイムのないアップグレードをサポートする必要がある場合は、アセンブリのバージョン管理とファクタリングを含むパッケージ戦略を実装する必要です。<br /><br /> 詳細については、次を参照してください。[のアップグレードとアプリケーションのバージョン管理方法](../technical-guides/upgrading-and-versioning-strategies-for-applications.md)です。|  
|BizTalk Server アプリケーションの展開をスクリプト。|可能な場合は、BizTalk アプリケーションの展開をスクリプト化する必要があります。 必要があります文書化する詳細な手順を実行するスクリプトを作成しないもの。 詳細については、以下をご覧ください。<br /><br /> -   [スクリプトを使用してアプリケーションを展開するには](../technical-guides/using-scripts-to-deploy-applications.md)<br />-   [アプリケーションを管理します。](../technical-guides/managing-applications.md)|  
|メッセージを再実行して、ワークフローを再起動するためのプロセスを事前に定義します。|確立して中断されたサービス インスタンスを確認し、適切なアクションを実行する手順を文書化します。 ほとんどの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境では、これは、毎日のメンテナンスの一環として実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。 毎日のメンテナンスのチェックを実行する方法の詳細については、次を参照してください。[チェックリスト: メンテナンスを毎日チェックを実行する](../technical-guides/checklist-performing-daily-maintenance-checks.md)です。|  
|検出される可能性がある問題についてのエスカレーションのパスを定義する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。|特定の役割と責任<br />-エスカレーション プロセスとパスを定義します。<br />-プロセスの「ショート サーキット」および「重大な状況」シナリオに必要な場合のパスを定義します。<br />パスを定義する、エスカレーション仕入先に関する問題について、マイクロソフト、その他のソフトウェアを含めてベンダー、ハードウェア ベンダー (たとえば、サーバー、SAN には、スイッチ)|  
|使用する場合は、特定の考慮事項に従う[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 ビット Windows オペレーティング システム|[64 ビット Windows オペレーティング システムで BizTalk Server を使用するときの考慮事項](../technical-guides/considerations-while-using-biztalk-server-on-a-64-bit-windows-operating-system.md)|  
|ベスト プラクティスに従う[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]設定します。|[BizTalk Server 設定のベスト プラクティス](../technical-guides/best-practices-for-biztalk-server-settings.md)|  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ホストとホスト インスタンスを構成します。](../technical-guides/configuring-hosts-and-host-instances.md)  
  
-   [専用の追跡ホストの構成](../technical-guides/configuring-a-dedicated-tracking-host.md)  
  
-   [IIS 構成設定を適用します。](../technical-guides/apply-iis-configuration-settings.md)  
  
-   [アップグレードとアプリケーションのバージョン管理方法](../technical-guides/upgrading-and-versioning-strategies-for-applications.md)  
  
-   [スクリプトを使用してアプリケーションを展開するには](../technical-guides/using-scripts-to-deploy-applications.md)  
  
-   [64 ビット Windows オペレーティング システムで BizTalk Server を使用するときの考慮事項](../technical-guides/considerations-while-using-biztalk-server-on-a-64-bit-windows-operating-system.md)  
  
-   [BizTalk Server 設定のベスト プラクティス](../technical-guides/best-practices-for-biztalk-server-settings.md)
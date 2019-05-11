---
title: SQL Server データベース ミラーリング、ボリューム シャドウ コピー サービス、および AlwaysOn |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b965cafc-cd34-4657-975d-0dedffd27333
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6dcf7ea68871d198ddf6a796d3022fc78647f925
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401784"
---
# <a name="sql-server-database-mirroring-volume-shadow-copy-service-and-alwayson"></a>SQL Server データベース ミラーリング、ボリューム シャドウ コピー サービス、および AlwaysOn
Microsoft SQL Server と呼ばれるソフトウェア ソリューションを提供する*データベース ミラーリング*と Windows ボリューム シャドウ コピー サービス (VSS) の特定のシナリオの高可用性を向上させます。 SQL Server*データベース ミラーリング*ボリューム シャドウ コピー サービス (VSS) には、ディザスター リカバリー用のバックアップと復元の機能が用意されています。 データベースが使用可能な確率が高くなります。 SQL Server の使用*データベース ミラーリング*または Windows ボリューム シャドウ コピー サービスが Microsoft の高可用性を確保するためのサポート対象ソリューション[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。  
  
## <a name="using-sql-server-database-mirroring-to-provide-high-availability-for-biztalk-server-databases"></a>SQL Server データベース ミラーリングを使用して、BizTalk Server データベースの高可用性を実現するには  
 SQL Server の使用*データベース ミラーリング*現在、Microsoft の高可用性を確保するためのサポートされているソリューションではない[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースでトランザクションの一貫性を維持する潜在的な問題のため、BizTalk Server データベース。 データベース ミラーリングと SQL Server データベースにまたがるトランザクションの詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=87977](http://go.microsoft.com/fwlink/?LinkId=87977)します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースをインストールする必要がありますのディザスター リカバリーの目的での高可用性と BizTalk 確保する SQL Server クラスターでログ配布を利用する必要があります。 BizTalk ログ配布の詳細については、次を参照してください。[ログ配布](../core/log-shipping.md)します。  
  
## <a name="using-the-volume-shadow-copy-service-to-provide-high-availability-for-biztalk-server-databases"></a>ボリューム シャドウ コピー サービスを使用して、BizTalk Server データベースの高可用性を実現するには  
 ボリューム シャドウ コピー サービスは、ディザスター リカバリー用のバックアップと復元の機能を提供します。 VSS の Microsoft 分散トランザクション コーディネーター (MS DTC) をサポートするため、ローカルの展開とトランザクション調整シナリオにも他の制限が適用) に制限は、現在のサポートされているソリューションが、VSS サービスの使用ではありません。Microsoft の高可用性を確保[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。 分散トランザクションでボリューム シャドウ コピー サービスのサポートの詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=139505](http://go.microsoft.com/fwlink/?LinkId=139505)します。  
  
## <a name="using-sql-server-alwayson"></a>SQL Server AlwaysOn を使用します。 
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] および [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] が別のコンピューターにインストールされている場合、Distributed Transaction Coordinator (MS DTC) がコンピューター間のトランザクションを処理します。 
 
SQL Server 2016 以降では、AlwaysOn は、MSDTC トランザクションをサポートします。 結果として、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]この SQL Server のバージョンを使用して、AlwaysOn 機能はサポートされています。 以前の SQL Server バージョンと、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] AlwaysOn 機能は、MSDTC トランザクションをサポートしていませんし、したがって AlwaysOn がサポートされていません。 

参照してください[SQL Server Always On 可用性グループを使用して高可用性](../core/high-availability-using-sql-server-always-on-availability-groups.md)します。
  
## <a name="see-also"></a>参照  
 [BizTalk Server データベースをクラスタ リング](../core/clustering-the-biztalk-server-databases1.md)   
 [バックアップおよび復元に関する詳細情報](../core/advanced-information-about-backup-and-restore1.md)
---
title: SQL Server データベース ミラーリング、ボリューム シャドウ コピー サービス、および AlwaysOn |Microsoft ドキュメント
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
ms.openlocfilehash: bea9d6063330e7af15ecb202513deb4def6571fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277994"
---
# <a name="sql-server-database-mirroring-volume-shadow-copy-service-and-alwayson"></a>SQL Server データベース ミラーリング、ボリューム シャドウ コピー サービス、および AlwaysOn の使用
Microsoft SQL Server と呼ばれるソフトウェア ソリューションを提供する*データベース ミラーリング*と Windows ボリューム シャドウ コピー サービス (VSS) の特定のシナリオの高可用性を高めるためです。 SQL Server*データベース ミラーリング*ボリューム シャドウ コピー サービス (VSS) は、障害回復のバックアップと復元の機能を提供します。 データベースが使用可能なである確率が高くなります。 SQL Server の使用*データベース ミラーリング*か Windows ボリューム シャドウ コピー サービスが Microsoft の高可用性を確保するためのソリューションをサポート[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。  
  
## <a name="using-sql-server-database-mirroring-to-provide-high-availability-for-biztalk-server-databases"></a>SQL Server データベース ミラーリングを使用した BizTalk Server データベースの高可用性の実現  
 SQL Server の使用*データベース ミラーリング*されていない、Microsoft の高可用性を確保するためのサポートされているソリューション[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースでトランザクションの一貫性を維持する潜在的な問題があるため、BizTalk Server データベース。 データベース ミラーリングと SQL Server のデータベースにまたがるトランザクションの詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=87977](http://go.microsoft.com/fwlink/?LinkId=87977)です。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースをインストールするように、高可用性と BizTalk SQL Server クラスターでログ配布を災害復旧の目的で利用必要があります。 BizTalk ログ配布の詳細については、次を参照してください。[ログ配布](../core/log-shipping.md)です。  
  
## <a name="using-the-volume-shadow-copy-service-to-provide-high-availability-for-biztalk-server-databases"></a>ボリューム シャドウ コピー サービスを使用した BizTalk Server データベースの高可用性の実現  
 ボリューム シャドウ コピー サービスは、ディザスター リカバリー用のバックアップと復元機能を提供します。 Microsoft 分散トランザクション コーディネーター (MS DTC) サポートので VSS の数は最大でローカルの展開とトランザクション調整シナリオにもその他の制限が適用)、現在のサポートされているソリューションが、VSS サービスの使用ではありません。Microsoft の高可用性を確保する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。 分散トランザクションでボリューム シャドウ コピー サービスのサポートの詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=139505](http://go.microsoft.com/fwlink/?LinkId=139505)です。  
  
## <a name="using-sql-server-alwayson"></a>SQL Server の AlwaysOn の使用 
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] および [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] が別のコンピューターにインストールされている場合、Distributed Transaction Coordinator (MS DTC) がコンピューター間のトランザクションを処理します。 
 
SQL Server 2016 以降では、AlwaysOn は、MSDTC トランザクションをサポートします。 その結果、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] AlwaysOn 機能がサポートされるは、この SQL Server のバージョンを使用する場合。 以前のバージョンの SQL Server で、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] AlwaysOn 機能は MSDTC トランザクションをサポートしておらず、したがって AlwaysOn がサポートされていません。 

参照してください[SQL Server Always On 可用性グループを使用して高可用性](../core/high-availability-using-sql-server-always-on-availability-groups.md)です。
  
## <a name="see-also"></a>参照  
 [BizTalk Server データベースをクラスタ リング](../core/clustering-the-biztalk-server-databases1.md)   
 [バックアップと復元に関する詳細情報](../core/advanced-information-about-backup-and-restore1.md)
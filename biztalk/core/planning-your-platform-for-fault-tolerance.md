---
title: プラットフォームのフォールト トレランスの計画 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, BizTalk Server
- MessageBox database, fault tolerance
- clustering, fault tolerance
- SQL Server RAID
- databases [BAM], fault tolerance
- BizTalk Server, planning
- fault tolerance
- clustering, fail-overs
- planning, fault tolerance
- Primary Import database [BAM]
- BizTalk Server, backing up
- fault tolerance, planning
- planning, BizTalk Server
- Primary Import database [BAM], fault tolerance
- fail-over clustering
ms.assetid: 512ed6b8-db1e-434a-8009-63e952cf5500
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5ddc4565449171c71685bcddd2c68b699f5113b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007491"
---
# <a name="planning-your-platform-for-fault-tolerance"></a>プラットフォームのフォールト トレランスの計画
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、Microsoft Windows プラットフォームおよび Microsoft SQL Server プラットフォームを基盤としています。 BizTalk Server の障害に対する耐性や回復力は、その基盤となるプラットフォームの耐性と回復力にかかっています。  
  
 ビジネス アクティビティ監視 (BAM) データベースと、メッセージ ボックス データベースは、次を行うお勧めします。  
  
- SQL Server Enterprise Edition のフェールオーバー クラスタリングを使用します。 フェールオーバー クラスターを使用することにより、サーバーで障害が発生した場合に、SQL Server インスタンスの処理を、稼働しているサーバーへと自動的に切り替えることができます。  
  
   BAM プライマリ インポート データベースは、イベント データを収集します。 障害が発生した場合、前回のバックアップ以降に BAM プライマリ インポート データベースに書き込まれたデータが失われます。 失われたイベント データを再生成することはできません。そのため、BAM プライマリ インポート データベースに対してフェールオーバー クラスタリングを有効にすることがきわめて重要となります。  
  
- SQL Server RAID (Redundant Array of Independent Disks) を使用します。メッセージ ボックス データベースおよび BAM プライマリ インポート データベースに関して、RAID の使用が特に重要となります。  
  
  フォールト トレラントな Windows and SQL Server 環境を設計するにあたっては、以下に示す情報を参照してください。 クラスタリングやディスク ミラー化など、サービス障害やデータ損失を防ぐためのハードウェアおよびサーバーの冗長性技術をしっかり習得する必要があります。  
  
- [ホワイト ペーパー: 高可用性-常時接続テクノロジ](http://go.microsoft.com/fwlink/?LinkId=130376)  
  
   "高可用性 – Always On Technologies"ホワイト ペーパーでは、SQL Server 2008 で利用できる高可用性機能について説明します。  
  
- [高可用性ソリューションの概要](http://go.microsoft.com/fwlink/?LinkId=130377)  
  
   サーバーまたはデータベースの可用性を向上させる SQL Server 2008 の高可用性ソリューションについて説明します。  
  
- [第 15 章「高可用性オプションでは、SQL Server リソース キット](http://go.microsoft.com/fwlink/?LinkId=24431)  
  
   Microsoft SQL Server リソース キットには、管理や配置計画に関する情報が広範囲にわたって記載されています。 第 15 章では、フォールト トレランスおよび復旧のための計画について説明しています。  
  
- [Windows Deployment Services Step-by-Step Guide](http://go.microsoft.com/fwlink/?LinkId=130379)  
  
   Windows 展開サービスの役割を Windows Server 2008 で使用する手順が示されています  
  
- [Windows Server 2003 導入ガイド: サーバーの展開を計画する](http://go.microsoft.com/fwlink/?LinkId=24433)します。  
  
   このドキュメントでは、サーバー ストレージの導入計画のほか、中規模から大規模な組織におけるファイル サーバー、プリント サーバー、およびターミナル サーバーの設計と導入について説明しています。  
  
   また、このドキュメントには、リモート サーバーの管理計画、サーバー クラスターの設計と導入、ネットワーク負荷分散クラスターの設計と導入に関するガイドラインが記載されています。このガイドラインに従うことによって、サーバーの可用性とスケーラビリティを最大限に高めることができます。  
  
## <a name="backing-up-your-platform"></a>プラットフォームのバックアップ  
 システムの構成を終えたら、サーバーの完全バックアップを行い、データが万一失われてしまっても迅速にサーバーを元の状態に復旧できるように準備します。  
  
 プラットフォームをバックアップするには、記載されたバックアップ手順を次の各テクノロジについて実行します。  
  
- Microsoft Windows Server Standard、Enterprise、または Datacenter Edition  
  
- インターネット インフォメーション サービス (IIS)  
  
- Microsoft SQL Server  
  
- Windows SharePoint Services。Windows SharePoint Services アダプターが使用します。  
  
  「BizTalk Server 運用ガイド」で"BizTalk Server のバックアップ"での推奨事項に従って[チェックリスト: ディザスター リカバリーによる可用性の向上](http://go.microsoft.com/fwlink/?LinkId=130498)します。  
  
  バックアップ手順および復元手順を十分にテストしたら、バックアップを安全かつ離れた場所に保管します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server データベースのバックアップと復元](../core/backing-up-and-restoring-the-biztalk-server-databases.md)
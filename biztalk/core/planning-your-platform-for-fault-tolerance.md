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
ms.openlocfilehash: 3564be0d8e49d64b3726f7aca360bfa4042343db
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394966"
---
# <a name="planning-your-platform-for-fault-tolerance"></a>プラットフォームのフォールト トレランスの計画
Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は、Microsoft Windows と Microsoft SQL Server プラットフォーム上に構築します。 存続または障害から回復する BizTalk Server の機能は、存続または回復する基になるプラットフォームの機能に依存します。  
  
 ビジネス アクティビティ監視 (BAM) データベースと、メッセージ ボックス データベースは、次を行うお勧めします。  
  
- SQL Server Enterprise Edition で提供されているフェールオーバー クラスタ リングを設定します。 フェールオーバー クラスタ リングでは、SQL Server が稼働中のサーバーに障害が発生したサーバーから SQL Server のインスタンスの処理を自動的に切り替えを使用できます。  
  
   BAM プライマリ インポート データベースは、イベント データを収集します。 障害が発生した場合、前回のバックアップ以降に BAM プライマリ インポート データベースに書き込まれたデータが失われます。 失われたイベントを再生成する方法はありません、ために、BAM プライマリ インポート データベースに対してフェールオーバー クラスタ リングの失敗を有効にすることは特に重要ですが。  
  
- 特に、メッセージ ボックス データベースおよび BAM プライマリ インポート データベースの SQL Server RAID (冗長アレイの独立したディスク) を使用します。  
  
  次のリソースを使用すると、フォールト トレランスのため、Windows および SQL Server の展開をデザインできます。 サービスの障害およびデータの損失を防ぐためにクラスタ リングやディスクがミラー化など、ハードウェアとサーバーの冗長性技術詳細については時間がかかります。  
  
- [ホワイト ペーパー:高可用性-常時接続テクノロジ](http://go.microsoft.com/fwlink/?LinkId=130376)  
  
   "高可用性 – Always On Technologies"ホワイト ペーパーでは、SQL Server 2008 で利用できる高可用性機能について説明します。  
  
- [高可用性ソリューションの概要](http://go.microsoft.com/fwlink/?LinkId=130377)  
  
   SQL Server 2008 のサーバーやデータベースの可用性を向上するにはいくつかの高可用性ソリューションについて説明します。  
  
- [第 15 章「高可用性オプションでは、SQL Server リソース キット](http://go.microsoft.com/fwlink/?LinkId=24431)  
  
   Microsoft SQL Server リソース キットには、さまざまな管理や配置計画について説明します。 第 15 章では、フォールト トレランスおよび復旧の計画について説明します。  
  
- [Windows Deployment Services Step-by-Step Guide](http://go.microsoft.com/fwlink/?LinkId=130379)  
  
   Windows Server 2008、Windows 展開サービス ロールを使用する方法についてステップ バイ ステップ ガイダンスが含まれています  
  
- [Windows Server 2003 展開キット:サーバーの導入計画](http://go.microsoft.com/fwlink/?LinkId=24433)します。  
  
   このドキュメントでは、サーバーの記憶域、および情報を設計し、ファイル サーバー、プリント サーバー、および中規模および大規模組織内のターミナル サーバーの配置に関する計画に関する情報を提供します。  
  
   この本でリモート サーバー管理の計画、設計しサーバーのクラスターを展開してデザインおよびネットワーク負荷分散クラスターをデプロイして、サーバーのスケーラビリティと可用性を最大化するのにガイドラインを使用することもできます。  
  
## <a name="backing-up-your-platform"></a>プラットフォームのバックアップ  
 システムを構成した後は、データの損失が発生した場合、同一のサーバーを迅速に復元できるように、サーバーの完全バックアップを準備します。  
  
 お使いのプラットフォームをバックアップするため、次のテクノロジのそれぞれの文書化されたバックアップの手順に従います。  
  
- Microsoft Windows Server Standard、Enterprise、または Datacenter Edition  
  
- インターネット インフォメーション サービス (IIS)  
  
- Microsoft SQL Server  
  
- Windows SharePoint Services、Windows SharePoint Services アダプターによって使用されます。  
  
  「BizTalk Server 運用ガイド」で"BizTalk Server のバックアップ"での推奨事項に従って[チェックリスト。ディザスター リカバリーによる可用性の向上](http://go.microsoft.com/fwlink/?LinkId=130498)します。  
  
  十分にテストしたら、バックアップと復元手順と、安全なリモートの場所に配置します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server データベースのバックアップと復元](../core/backing-up-and-restoring-the-biztalk-server-databases.md)
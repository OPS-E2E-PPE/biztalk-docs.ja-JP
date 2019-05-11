---
title: データベースの可用性の計画 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6aa74257-4159-46f6-b538-f7e9083d74ad
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b04a83c0e19c05f28a648cddd09ca8ebd4482a3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394632"
---
# <a name="planning-for-database-availability"></a>データベースの可用性の計画
BizTalk Server メッセージング エンジンはによりビジネス プロセスは、信頼性の高いされ、保存することで持続性の状態およびビジネス データを BizTalk メッセージ ボックス データベースと呼ばれる SQL Server データベースの処理です。 信頼性と永続化されたデータの持続性の機能は、基になるデータ ストアとして、BizTalk Server データベースの高可用性の計画は非常に重要です。  
  
## <a name="hardware-considerations"></a>ハードウェアについての注意事項  
 BizTalk Server データベースの高可用性を確保するには、ハードウェアを計画するとき、次を考慮します。  
  
1.  記憶域エリア ネットワーク (SAN)、BizTalk Server データベースを格納するための実装を検討します。 SAN ディスクは、RAID を使用して構成する必要があります最高のパフォーマンスと高可用性を実現可能であれば、1 + 0 (ミラー セットのストライプ) トポロジ。 
  
2.  BizTalk Server データベースを格納するための SQL Server を実行している複数のコンピューターにインストールする方法を計画します。 SQL Server を実行している複数のコンピューターは、SQL server (推奨) クラスタ リングや (もお勧めします)、独立した物理 SQL Server インスタンス上の特定の BizTalk Server データベースを格納している必要があります。  
  
3.  SQL Server ログ配布のディザスター リカバリーを実装するために SQL Server を実行している 1 つまたは複数のコンピューターにインストールする方法を計画します。 BizTalk Server が SQL Server を使用してデータベースのスタンバイ機能を実装してログ配布します。 データベースが実稼働サーバーが失敗したことに処理を再開するスタンバイ サーバーを許可するログ配布のバックアップと、データベースとトランザクション ログ ファイルの復元を自動化する SQL Server。 SQL Server ログ配布のディザスター リカバリーを実装する方法の詳細については、次を参照してください[内容は、BizTalk Server のログ配布しますか?。](../technical-guides/what-is-biztalk-server-log-shipping.md)  
  
## <a name="software-considerations"></a>ソフトウェアの考慮事項  
 BizTalk Server データベースの高可用性を確保するには、ソフトウェアを計画するとき、次を考慮します。バージョンおよびフェールオーバー クラスタ リングのサポートや BizTalk ログ配布のサポートをサポートする SQL Server のエディションをインストールする予定です。 SQL Server のエディションでサポートされる機能の完全な一覧を参照してください。[エディションとサポートされる機能](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016)します。
  
## <a name="high-availability-vs-disaster-recovery"></a>高可用性とします。災害復旧  
 BizTalk Server 環境の可用性を高めるための 2 つの異なるメソッドがある: フォールト トレランスや負荷分散、またはディザスター リカバリーを使用して可用性の実現を使用して高可用性を提供します。 各メソッドでは、可用性が向上、中にそれらの主な違いは、そのフォールト トレランスや、負荷分散を通常は、ディザスター リカバリーよりもはるかに高速の復旧時間を提供します。 そのため、フォールト トレランスのソリューションをビルドまたは負荷分散がより一般的な可用性を実現するだけではなく高可用性を提供するものとして考えます。 どちらの方法は、運用環境の BizTalk Server 環境で採用されている必要があります。  
  
 Windows クラスタ リングとフォールト トレランスを使用して、BizTalk Server データベースの高可用性を提供します。 詳細については、BizTalk Server データベースの高可用性を実現する、次を参照してください。[データベースの高可用性](../technical-guides/high-availability-for-databases.md)します。  
  
 災害と可用性を向上させる BizTalk Server を使用して復旧ログ配布します。 ディザスター リカバリーを使用して BizTalk Server データベースの可用性を上げるために、トピックの手順に従います[チェックリスト。ディザスター リカバリーによる可用性の向上](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)します。
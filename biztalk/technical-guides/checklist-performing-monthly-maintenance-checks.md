---
title: "チェックリスト: が毎月の保守チェックを行う |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 588b74fa-6bf5-43ad-aa15-3595adde76d1
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40f5e5d7d6c6732c203ac7a34308c546388206c3
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="checklist-complete-monthly-maintenance-checks-in-biztalk-server"></a>チェックリスト: BizTalk Server で確認の完了の毎月の保守
このトピックの内容が毎月の信頼性、管理、セキュリティ、およびパフォーマンスのメンテナンス チェックの実行に必要な手順について説明します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システムです。  

## <a name="checklist"></a>チェックリスト
|手順|リファレンス|  
|-----------|---------------|  
|マスター シークレット キーはバックアップをすぐに使用できる記憶域がオフライン (信頼性チェック) を確認します。|[マスター シークレットをバックアップする方法](../core/how-to-back-up-the-master-secret.md)|  
|すべてのクラスター化されたサービスを提供してがのフェールオーバーを確認してください (信頼性チェック) をテストします。|[フェールオーバー シナリオに備えた SQL Server クラスター構成のレビューとテスト](../technical-guides/reviewing-and-testing-sql-server-cluster-configuration-for-failover-scenarios.md)|  
|エンタープライズ SSO サービスがクラスター化されたことを確認してください (信頼性を確認) します。|[マスター シークレット サーバーのクラスタリング](../technical-guides/clustering-the-master-secret-server.md)|  
|BizTalk Server データベースが SQL Server サービス (信頼性チェック) の下にクラスター化されていることを確認します。|[BizTalk Server データベースのクラスタリング](../technical-guides/clustering-the-biztalk-server-databases2.md)|  
|少なくとも 2 つの物理的な BizTalk server が BizTalk グループ (信頼性を確認) の一部であることを確認します。|[BizTalk グループの一部である複数のサーバーを確保します。](../technical-guides/maintaining-reliability.md#BKMK_BTSGrp)|  
|個別のホスト (信頼性チェック) を使用して、場合は、不安定なコードが使用されているかどうかを判断します。|[BizTalk ホストの高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)|  
|すべての新しい BizTalk アプリケーション (信頼性を確認) の機能テストを実行します。|-   [アプリケーションのテスト](../technical-guides/testing-an-application.md)<br />-   [BizTalk アプリケーションの展開のステージング作業](../core/staging-tasks-for-biztalk-application-deployment.md)|  
|構成および BizTalk Server のバックアップ ジョブ (信頼性チェック) をスケジュールします。|-   [バックアップの BizTalk Server ジョブを構成する方法](../core/how-to-configure-the-backup-biztalk-server-job.md)<br />-   [バックアップの BizTalk Server のジョブをスケジュールする方法](../core/how-to-schedule-the-backup-biztalk-server-job.md)|  
|各 BizTalk コンピューター (整合性チェック) で、一連のアセンブリの正しいバージョンがインストールされていることを確認します。|使用して、 **BizTalk アセンブリ チェッカーとリモート GAC**ツール (BTSAssemblyChecker.exe)、BizTalk 管理データベースに展開されたアセンブリのバージョンを確認し、すべてのGACに正しく登録されていることを確認するには[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューター。 このツールを使用すると、特定の BizTalk アプリケーションのアイテムを含むすべてのアセンブリが BizTalk のすべてのノードにインストールされていることを確認します。 このツールは、サイド バイ サイド展開アプローチを使用する場合に特に各 BizTalk コンピューターで、一連のアセンブリの正しいバージョンがインストールされていることを確認する方法を純色のバージョン管理と組み合わせてに特に便利です。 このツールはで利用可能な[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]Support\Tools\x86\BTSAssemblyChecker.exe にあるインストール メディア。|  
|不要な BizTalk アプリケーション、成果物、および構成 (管理チェック) があるかどうかを決定します。|-すべて不要な BizTalk アプリケーション、成果物、および構成を削除します。<br />、BizTalk アプリケーションまたは成果物の削除の詳細については BTSTask コマンド ライン ツールを使用して参照してください[RemoveApp コマンド](../core/removeapp-command.md)です。<br />BizTalk Server 管理コンソールまたは BTSTask コマンド ライン ツールを使用してアプリケーションからアイテムを削除する方法の詳細については、次を参照してください。[アプリケーションからアイテムを削除する方法](../core/how-to-remove-an-artifact-from-an-application.md)です。|  
|BizTalk Server 管理コンソール、承認されていない変更 (管理チェック) を確認します。|[BizTalk Server 管理コンソールの使用](../core/using-the-biztalk-server-administration-console.md)|  
|承認されていない変更 (管理チェック) のためには、BTSNTSvc.exe.config を確認します。|[BTSNTSvc.exe.config ファイル](../core/btsntsvc-exe-config-file.md)|  
|承認されていない変更を加える (管理チェック) の BizTalk Server に関連するレジストリ キーを確認してください。|Microsoft サポート技術情報の記事 256986[上級ユーザー向けの Windows レジストリ情報](https://support.microsoft.com/kb/256986)|  
|BizTalk Server (管理チェック) のベスト プラクティス アナライザーを実行します。|[BizTalk Server ベスト プラクティス アナライザー](https://www.microsoft.com/download/details.aspx?id=43382)|  
|最新の service pack と更新プログラムがインストールされていることを確認してください (管理およびセキュリティ チェック)。|[Microsoft Update](https://support.microsoft.com/help/12373/windows-update-faq)|  
|別の取引先の成果物が、同じホスト (セキュリティ チェック) にインストールされていないことを確認します。|[ホストとホスト インスタンスの構成](../technical-guides/configuring-hosts-and-host-instances.md)|  
|BizTalk Server がドメイン レベルのみのユーザーおよびグループ (セキュリティ チェック) を使用していることを確認します。|[ドメイン グループ](../core/domain-groups.md)|  
|MSDTC セキュリティ構成が有効になっていることを確認してください (セキュリティ チェック)。|参照してください**、適切な MSDTC セキュリティ構成オプションを設定**で[MSDTC の問題のトラブルシューティング](../core/troubleshooting-problems-with-msdtc.md)です。|  
|判断 (パフォーマンス チェック) を増加する BizTalk Server のキャッシュ更新間隔をする必要があるかどうか。|[構成キャッシュ更新間隔を調整する方法](../technical-guides/how-to-adjust-the-configuration-cache-refresh-interval.md)|  
|判断 (パフォーマンス チェック) を調整する各ホストの調整のオプションが必要かどうか。|受信および送信ホストの制限については、次を参照してください。[ホスト制限とは何ですか?](../core/what-is-host-throttling.md)です。<br />-トリガー、アクション、および受信と送信制限の緩和方法についてを参照してください**条件の発生原因、アクション、および軽減戦略を調整**で[BizTalk Server を実装する方法ホストのスロットル](../core/how-biztalk-server-implements-host-throttling.md)です。|  
|オーケストレーション、形状、およびビジネス ルール エンジン (BRE) イベント (パフォーマンス チェック) を追跡など、不要な追跡が有効かどうかを決定します。|-   [追跡を無効にする方法](../technical-guides/how-to-disable-tracking.md)<br />-   [追跡の計画](../technical-guides/planning-for-tracking.md)<br />-   [追跡のベスト プラクティス](../technical-guides/planning-for-tracking.md#BKMK_TrackingBP)|  
|保守 (パフォーマンス チェック) を追跡するための専用のホストを使用しているかどうかを決定します。|[専用の追跡ホストの構成](../technical-guides/configuring-a-dedicated-tracking-host.md)|  
|上昇傾向 (パフォーマンス チェック) を BizTalk Server データベースのサイズを確認してください。|-追跡データベースのサイズ変更の詳細についてを参照してください[追跡データベースのサイジング ガイドライン](../core/tracking-database-sizing-guidelines.md)です。<br />-メッセージ ボックス データベース、BizTalkDTADb、BAMPrimaryImport データベースのサイズ変更の詳細についてを参照してください[パフォーマンスのボトルネックを特定する](../core/identifying-performance-bottlenecks.md)です。|  
  
## <a name="see-also"></a>参照  
 [定期メンテナンスのチェックリスト](../technical-guides/routine-maintenance-checklists.md)

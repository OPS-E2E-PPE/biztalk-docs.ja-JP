---
title: "チェックリスト: 毎月の保守チェックの実行 |Microsoft ドキュメント"
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
ms.openlocfilehash: 35b7b3aa9a9d6dfcea7dfc40f740defdeff2d45f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-performing-monthly-maintenance-checks"></a>チェックリスト: 毎月の保守チェックの実行
このトピックの内容が毎月の信頼性、管理、セキュリティ、およびパフォーマンスのメンテナンス チェックの実行に必要な手順について説明します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システムです。  
  
|手順|リファレンス|  
|-----------|---------------|  
|マスター シークレット キーはバックアップをすぐに使用できる記憶域がオフライン (信頼性チェック) を確認します。|[マスター シークレットをバックアップする方法](http://go.microsoft.com/fwlink/?LinkId=151395)(http://go.microsoft.com/fwlink/?LinkId=151395)。|  
|すべてのクラスター化されたサービスを提供してがのフェールオーバーを確認してください (信頼性チェック) をテストします。|[確認とテスト SQL Server のクラスターのフェールオーバーのシナリオに構成](../technical-guides/reviewing-and-testing-sql-server-cluster-configuration-for-failover-scenarios.md)グループのフェールオーバーをテストします。|  
|エンタープライズ SSO サービスがクラスター化されたことを確認してください (信頼性を確認) します。|[マスター シークレット サーバーをクラスタ リング](../technical-guides/clustering-the-master-secret-server.md)|  
|BizTalk Server データベースが SQL Server サービス (信頼性チェック) の下にクラスター化されていることを確認します。|[BizTalk Server Databases2 をクラスタ リング](../technical-guides/clustering-the-biztalk-server-databases2.md)|  
|少なくとも 2 つの物理的な BizTalk server が BizTalk グループ (信頼性を確認) の一部であることを確認します。|[BizTalk グループの一部である複数のサーバーを確保します。](../technical-guides/maintaining-reliability.md#BKMK_BTSGrp)|  
|個別のホスト (信頼性チェック) を使用して、場合は、不安定なコードが使用されているかどうかを判断します。|[BizTalk ホストの高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)|  
|すべての新しい BizTalk アプリケーション (信頼性を確認) の機能テストを実行します。|-   [アプリケーションのテスト](../technical-guides/testing-an-application.md)<br />-   [BizTalk アプリケーション展開のステージング作業](http://go.microsoft.com/fwlink/?LinkId=154686)(http://go.microsoft.com/fwlink/?LinkId=154686)。|  
|構成および BizTalk Server のバックアップ ジョブ (信頼性チェック) をスケジュールします。|-   [バックアップの BizTalk Server ジョブを構成する方法](http://go.microsoft.com/fwlink/?LinkID=153813)(http://go.microsoft.com/fwlink/?LinkID=153813)<br />-   [バックアップの BizTalk Server のジョブをスケジュールする方法](http://go.microsoft.com/fwlink/?LinkId=154674)(http://go.microsoft.com/fwlink/?LinkId=154674)|  
|各 BizTalk コンピューター (整合性チェック) で、一連のアセンブリの正しいバージョンがインストールされていることを確認します。|使用して、 **BizTalk アセンブリ チェッカーとリモート GAC**ツール (BTSAssemblyChecker.exe)、BizTalk 管理データベースに展開されたアセンブリのバージョンを確認し、すべてのGACに正しく登録されていることを確認するには[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューター。 このツールを使用すると、特定の BizTalk アプリケーションのアイテムを含むすべてのアセンブリが BizTalk のすべてのノードにインストールされていることを確認します。 このツールは、サイド バイ サイド展開アプローチを使用する場合に特に各 BizTalk コンピューターで、一連のアセンブリの正しいバージョンがインストールされていることを確認する方法を純色のバージョン管理と組み合わせてに特に便利です。 このツールはで利用可能な[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]Support\Tools\x86\BTSAssemblyChecker.exe にあるインストール メディア。|  
|不要な BizTalk アプリケーション、成果物、および構成 (管理チェック) があるかどうかを決定します。|-すべて不要な BizTalk アプリケーション、成果物、および構成を削除します。<br />、BizTalk アプリケーションまたは成果物の削除の詳細については BTSTask コマンド ライン ツールを使用して参照してください[RemoveApp コマンド](http://go.microsoft.com/fwlink/?LinkId=154687)(http://go.microsoft.com/fwlink/?LinkId=154687)。<br />BizTalk Server 管理コンソールまたは BTSTask コマンド ライン ツールを使用してアプリケーションからアイテムを削除する方法の詳細については、次を参照してください[アプリケーションからアイテムを削除する方法](http://go.microsoft.com/fwlink/?LinkId=154688)(http://。go.microsoft.com/fwlink/ しますか。LinkId = 154688)。|  
|BizTalk Server 管理コンソール、承認されていない変更 (管理チェック) を確認します。|[BizTalk Server 管理コンソールを使用して](http://go.microsoft.com/fwlink/?LinkId=154689)(http://go.microsoft.com/fwlink/?LinkId=154689)。|  
|承認されていない変更 (管理チェック) のためには、BTSNTSvc.exe.config を確認します。|[BTSNTSvc.exe.config ファイル](http://go.microsoft.com/fwlink/?LinkId=154690)(http://go.microsoft.com/fwlink/?LinkId=154690)。|  
|承認されていない変更を加える (管理チェック) の BizTalk Server に関連するレジストリ キーを確認してください。|Microsoft サポート技術情報の 256986[「上級ユーザー向けにレジストリ情報を Windows」](http://go.microsoft.com/fwlink/?LinkId=158859) (http://go.microsoft.com/fwlink/?LinkId=158859)。|  
|BizTalk Server (管理チェック) のベスト プラクティス アナライザーを実行します。|[BizTalk Server ベスト プラクティス アナライザー](http://go.microsoft.com/fwlink/?LinkId=83317) (http://go.microsoft.com/fwlink/?LinkId=83317)。|  
|最新の service pack と更新プログラムがインストールされていることを確認してください (管理およびセキュリティ チェック)。|[Microsoft Update](http://go.microsoft.com/fwlink/?LinkId=154691) (http://go.microsoft.com/fwlink/?LinkId=154691)。|  
|別の取引先の成果物が、同じホスト (セキュリティ チェック) にインストールされていないことを確認します。|[ホストとホスト インスタンスを構成します。](../technical-guides/configuring-hosts-and-host-instances.md)|  
|BizTalk Server がドメイン レベルのみのユーザーおよびグループ (セキュリティ チェック) を使用していることを確認します。|[ドメイン グループ](http://go.microsoft.com/fwlink/?LinkId=154692)(http://go.microsoft.com/fwlink/?LinkId=154692)。|  
|MSDTC セキュリティ構成が有効になっていることを確認してください (セキュリティ チェック)。|「Windows Server 2003 SP1、Windows XP SP2、Windows Server 2008、および Windows Vista で適切な MSDTC セキュリティ構成オプションを設定」のセクションのガイドラインに従う[MSDTC の問題のトラブルシューティング](http://go.microsoft.com/fwlink/?LinkId=154693)(http://go.microsoft.com/fwlink/ しますか。LinkId = 154693)。|  
|判断 (パフォーマンス チェック) を増加する BizTalk Server のキャッシュ更新間隔をする必要があるかどうか。|[構成キャッシュの更新間隔を調整する方法](../technical-guides/how-to-adjust-the-configuration-cache-refresh-interval.md)|  
|判断 (パフォーマンス チェック) を調整する各ホストの調整のオプションが必要かどうか。|受信および送信ホストの制限については、次を参照してください。[ホスト制限とは何ですか。](http://go.microsoft.com/fwlink/?LinkId=154694) (http://go.microsoft.com/fwlink/?LinkId=154694)。<br />-トリガー、アクション、および受信と送信制限の緩和方法についてを参照してください「条件の発生原因、アクション、および軽減戦略を調整」の[どのように BizTalk Server を実装してホスト制限](http://go.microsoft.com/fwlink/?LinkId=154695) (http://go.microsoft.com/fwlink/?LinkId=154695)。|  
|オーケストレーション、形状、およびビジネス ルール エンジン (BRE) イベント (パフォーマンス チェック) を追跡など、不要な追跡が有効かどうかを決定します。|-   [追跡を無効にする方法](../technical-guides/how-to-disable-tracking.md)<br />-   [追跡の計画](../technical-guides/planning-for-tracking.md)<br />-   [追跡のベスト プラクティス](../technical-guides/planning-for-tracking.md#BKMK_TrackingBP)|  
|保守 (パフォーマンス チェック) を追跡するための専用のホストを使用しているかどうかを決定します。|[専用の追跡ホストの構成](../technical-guides/configuring-a-dedicated-tracking-host.md)|  
|上昇傾向 (パフォーマンス チェック) を BizTalk Server データベースのサイズを確認してください。|-追跡データベースのサイズ変更の詳細についてを参照してください[追跡データベースのサイジング ガイドライン](http://go.microsoft.com/fwlink/?LinkId=154677)(http://go.microsoft.com/fwlink/?LinkId=154677)。<br />-メッセージ ボックス データベース、BizTalkDTADb、BAMPrimaryImport データベースのサイズ変更の詳細についてを参照してください[データベース層のボトルネックを識別する](http://go.microsoft.com/fwlink/?LinkId=154678)(http://go.microsoft.com/fwlink/?LinkId=154678)。|  
  
## <a name="see-also"></a>参照  
 [定期的なメンテナンスのチェックリスト](../technical-guides/routine-maintenance-checklists.md)
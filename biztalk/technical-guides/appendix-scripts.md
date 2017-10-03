---
title: "付録: スクリプト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b6394321-13c9-4b1d-b529-eba3d53b33c4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12df00876f6b2da9ebb98631016bd42947b4a40a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="appendix-scripts"></a>付録: スクリプト
この管理パックでは、次のスクリプトが含まれています。  
  
|[スクリプト]|用途|  
|------------|-------------|  
|Microsoft.BizTalk.Server.2013.ArtifactsDiscovery.vbs|このスクリプトは $Config に基づいてアプリケーションのアイテムを検出/パラメーターのオプションです。 オプションがあります。<br /><br /> -All により、送信ポート、送信ポート グループ、アプリケーション、そのホストの関連アプリケーションとの 送信ポート グループには、送信ポートが含まれています。 関係にします。<br />-すべてのオーケストレーション アプリケーションでは、アプリケーションにそれらのホスティング関係。<br />-すべての受信ポート、受信場所をアプリケーションでは、そのホスト関係 'をアプリケーションにし、' 受信ポートが含まれています受信場所' 関係します。|  
|Microsoft.BizTalk.Server.2013.ApplicationDiscovery.vbs|このスクリプトは、次を検出します。<br /><br /> のグループ内に 'ホスト アプリケーションをグループ化' のリレーションすべてのアプリケーションです。<br />-すべてのホスト グループ内に 'グループはホストをホスト' 関係します。|  
|Microsoft.BizTalk.Server.2013.BAMAnalysisDiscovery.vbs|このスクリプトは、BAM 分析を検出し、BAM ランタイムのコンポーネントが検出されたコンピューター上のコンポーネントに警告します。|  
|Microsoft.BizTalk.Server.2013.BAMPortalDiscovery.vbs|このスクリプトは、BAM ポータルのコンピューターの IIS 構成を検出します。 これは、BAM ロールと BAM ポータルの包含にも検出します。|  
|Microsoft.BizTalk.Server.2013.BAMRuntimeDiscovery.vbs|このスクリプトは $Config をパラメーターとして渡されるコンピューターで BAM ランタイムのコンポーネントを検出/ComputerName$ です。 コンピューター名が渡されない場合は、管理データベース内の最下位のサーバー ID を持つランタイム コンピューターで BAM を検出します。 これは、BAM ロールと BAM ランタイムの包含にも検出します。|  
|Microsoft.BizTalk.Server.2013.BizTalkApplicationServiceDiscovery.vbs|このスクリプトは、実行時ロールとそのホスティング関係と共にコンピューター上のすべての BizTalk アプリケーション サービスを検出します。|  
|Microsoft.BizTalk.Server.2013.BizTalkGroupDiscovery.vbs|このスクリプトは $Config をパラメーターとして渡されるコンピューターで BizTalk グループを検出/ComputerName$ です。 コンピューター名が渡されない場合に、管理データベース内の最下位のサーバー ID を持つランタイム コンピューター上のグループを検出します。|  
|Microsoft.BizTalk.Server.2013.BizTalkRoleDiscovery.vbs|このスクリプトは、パラメーターに基づく指定されたコンピューターで BizTalk サーバーの役割を検出します。 $Config/option$ です。 オプションを以下に示します。<br /><br /> BizTalk ランタイムの役割、BizTalk グループの展開およびグループの展開でのランタイムの包含します。<br />BizTalk ルール エンジンは、役割、BizTalk グループの展開、およびグループの展開でルール エンジンの抑制します。 BAM ロールは、オプション、およびグループの展開で、包含構造のいずれかと常に検出されます。|  
|BizTalkAnalysisDatabaseMonitor.vbs|このスクリプトは、接続の状態に基づいて SQL 分析データベースの可用性の監視データを生成します。 成功またはエラー状態の監視ができます。|  
|BizTalkArtifactConfigurationMonitor.vbs|このスクリプトは、BizTalk アプリケーションのアイテムの構成の監視データを生成します。 各成果物は、次の 3 つの監視状態成功、警告およびエラーのいずれかになります。|  
|BizTalkArtifactSuspendedInstancesMonitor.vbs|このスクリプトは、BizTalk アプリケーションのアイテム実行時の状態成果物ごとの中断されたインスタンスの数に基づいて監視データを生成します。 各成果物は、次の 3 つの監視状態成功、警告、およびエラーのいずれかになります。|  
|BizTalkBAMPortalMonitor.vbs|このスクリプトは、BAM ポータルの可用性の監視データを生成します。 成功またはエラー状態の監視ができます。|  
|BizTalkHostConfigurationMonitor.vbs|このスクリプトは、そのすべてのホスト インスタンス (BTSNTSvc.exe) の可用性に基づいて、BizTalk ホストの監視データを生成します。 モニター状態がいずれかの成功 (を実行している > = 成功した場合の制限)、警告 (を実行している > = 警告の上限と実行 < 成功制限) またはエラー。|  
|BizTalkDatabaseMonitor.vbs|このスクリプトは、接続の状態に基づいて SQL データベースの可用性の監視データを生成します。 成功またはエラー状態の監視ができます。|  
|BizTalkMultipleDatabaseMonitor.vbs|このスクリプトは、接続の状態に基づいて、単一のエンティティとして SQL データベースのグループの可用性の監視データを生成します。 モニターの状態がいずれかのエラー (プライマリ データベース使用不可) を指定できます (一部プライマリ以外のデータベース利用できません) の警告または成功した場合 (利用可能なすべてのデータベース)。|  
|BizTalkHostProbeAction.vbs|このスクリプトは、そのすべてのホスト インスタンス (BTSNTSvc.exe) の可用性に基づいて、BizTalk ホストの診断データを生成します。 エラーと警告状態は実行されていないホスト インスタンスが表示されます。|  
|Microsoft.BizTalk.Server.2013.HostAction.vbs|このスクリプトを使用する BizTalk ホストの開始/停止です。|  
|Microsoft.BizTalk.Server.2013.OrchestrationAction.vbs|このスクリプトを使用 (BizTalk アプリケーションのアイテム)、オーケストレーションの開始/停止にします。|  
|Microsoft.BizTalk.Server.2013.EnableReceiveLocation.vbs|このスクリプトは、受信場所 (BizTalk アプリケーションのアイテム) を有効または無効にするために使用します。|  
|Microsoft.BizTalk.Server.2013.SendPortAction.vbs|このスクリプトを使用する送信ポート (BizTalk アプリケーションのアイテム) の開始/停止です。|  
|Microsoft.BizTalk.Server.2013.SendPortGroupAction.vbs|このスクリプトを使用する送信ポート グループ (BizTalk アプリケーションのアイテム) の開始/停止です。|
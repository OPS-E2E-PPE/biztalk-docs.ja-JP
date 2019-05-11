---
title: '付録: スクリプト |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b6394321-13c9-4b1d-b529-eba3d53b33c4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c99c48018d7c4b5e7f9d6905611128a2cc2a8dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401342"
---
# <a name="appendix-scripts"></a>付録: スクリプト
この管理パックには、次のスクリプトが含まれます。  
  
|[スクリプト]|目的|  
|------------|-------------|  
|Microsoft.BizTalk.Server.2013.ArtifactsDiscovery.vbs|このスクリプトは、$Config に基づいてアプリケーションのアイテムを検出します。 オプション パラメーター。 オプションがあります。<br /><br /> -All により、送信ポート、送信ポート グループをアプリケーション、それらのホスト関係をアプリケーションと '送信ポート グループには、送信ポートが含まれています。' のリレーションにします。<br />-すべてのオーケストレーション アプリケーションでは、アプリケーションにそれらのホスティング関係。<br />の受信ポートすべては、アプリケーションのホスティングの関係での受信場所 'アプリケーションへと' 受信ポートが含まれています受信場所 ' 関係。|  
|Microsoft.BizTalk.Server.2013.ApplicationDiscovery.vbs|このスクリプトは、次を検出します。<br /><br /> -'ホスト アプリケーションをグループ化' のリレーションとグループすべてのアプリケーション。<br />のグループ内に 'ホストをホスト グループ' のリレーションすべてのホスト。|  
|Microsoft.BizTalk.Server.2013.BAMAnalysisDiscovery.vbs|このスクリプトでは、BAM 分析を検出し、BAM ランタイムのコンポーネントが検出された場所のコンピューター上のコンポーネントに警告します。|  
|Microsoft.BizTalk.Server.2013.BAMPortalDiscovery.vbs|このスクリプトでは、BAM ポータルのコンピューターの IIS 構成を検出します。 これは、BAM ロールと BAM ポータルの削減にも検出します。|  
|Microsoft.BizTalk.Server.2013.BAMRuntimeDiscovery.vbs|このスクリプトは $Config をパラメーターとして渡されるコンピューターで BAM ランタイムのコンポーネントを検出/ComputerName$。 コンピューター名が渡されない場合は、管理データベースに最も低いサーバー ID を持つランタイム コンピューターで BAM を検出します。 これは、BAM ロールとその中に BAM ランタイムの削減にも検出します。|  
|Microsoft.BizTalk.Server.2013.BizTalkApplicationServiceDiscovery.vbs|このスクリプトでは、実行時ロールでホスティングの関係と共にコンピューター上のすべての BizTalk アプリケーション サービスを検出します。|  
|Microsoft.BizTalk.Server.2013.BizTalkGroupDiscovery.vbs|このスクリプトは $Config をパラメーターとして渡されるコンピューターで BizTalk グループを検出/ComputerName$。 コンピューター名が渡されない場合は、管理データベースに最も低いサーバー ID を持つランタイム コンピューターのグループが検出します。|  
|Microsoft.BizTalk.Server.2013.BizTalkRoleDiscovery.vbs|このスクリプトでは、パラメーターに基づいて、指定したコンピューターで BizTalk サーバーの役割を検出します。 $Config$ オプション。 オプションを以下に示します。<br /><br /> -BizTalk ランタイム ロール、BizTalk グループの展開、およびグループのデプロイメントの実行時の包含。<br />BizTalk ルール エンジンの役割、BizTalk グループの展開、およびグループのデプロイメントのルール エンジンの包含します。 BAM ロールは、任意のオプション、およびグループのデプロイメントには、そのコンテインメントを常に検出されます。|  
|BizTalkAnalysisDatabaseMonitor.vbs|このスクリプトは、接続の状態に基づいて SQL 分析データベースの可用性の監視データを生成します。 モニターの状態は成功またはエラーのいずれかにできます。|  
|BizTalkArtifactConfigurationMonitor.vbs|このスクリプトは、BizTalk アプリケーションの成果物の構成の監視データを生成します。 各成果物は、次の 3 つの状態の監視の成功、警告およびエラーのいずれかになります。|  
|BizTalkArtifactSuspendedInstancesMonitor.vbs|このスクリプトは、成果物ごとに中断されたインスタンスの数に基づいて BizTalk アプリケーション成果物のランタイム状態の監視データを生成します。 各成果物は、次の 3 つの状態の監視の成功、警告、およびエラーのいずれかになります。|  
|BizTalkBAMPortalMonitor.vbs|このスクリプトは、BAM ポータルの可用性の監視データを生成します。 モニターの状態は成功またはエラーのいずれかにできます。|  
|BizTalkHostConfigurationMonitor.vbs|このスクリプトは、そのすべてのホスト インスタンス (BTSNTSvc.exe) の可用性に基づく BizTalk ホストの監視データを生成します。 モニター状態のいずれかの成功したことができます (を実行している > = 成功した場合の制限)、警告 (を実行している > = 警告制限を超えると実行 < 成功制限) またはエラー。|  
|BizTalkDatabaseMonitor.vbs|このスクリプトは、接続の状態に基づいて、SQL データベースの可用性の監視データを生成します。 モニターの状態は成功またはエラーのいずれかにできます。|  
|BizTalkMultipleDatabaseMonitor.vbs|このスクリプトは、接続の状態に基づいて 1 つのエンティティとして SQL データベースのグループの可用性の監視データを生成します。 モニターの状態がいずれかのエラー (プライマリ データベース利用できません) を指定できます (非プライマリ データベースによって使用できない) の警告、または成功 (使用可能なすべてのデータベース)。|  
|BizTalkHostProbeAction.vbs|このスクリプトでは、そのすべてのホスト インスタンス (BTSNTSvc.exe) の可用性に基づく BizTalk ホストの診断データを生成します。 エラーおよび警告の状態が実行されていないホスト インスタンスが表示されます。|  
|Microsoft.BizTalk.Server.2013.HostAction.vbs|このスクリプトを使用して、BizTalk ホストの開始/停止します。|  
|Microsoft.BizTalk.Server.2013.OrchestrationAction.vbs|このスクリプトを使用して、オーケストレーション (BizTalk アプリケーションのアイテム) の開始/停止します。|  
|Microsoft.BizTalk.Server.2013.EnableReceiveLocation.vbs|このスクリプトは、受信場所 (BizTalk アプリケーションの成果物) を有効または無効にするために使用します。|  
|Microsoft.BizTalk.Server.2013.SendPortAction.vbs|このスクリプトの使用を開始または停止 (BizTalk アプリケーションのアイテム) の送信ポート。|  
|Microsoft.BizTalk.Server.2013.SendPortGroupAction.vbs|このスクリプトを使用する送信ポート グループ (BizTalk アプリケーションのアイテム) の開始/停止します。|
---
title: BizTalk Server パフォーマンス設定を管理する |Microsoft ドキュメント
description: 設定ダッシュ ボードを使用して BizTalk グループ、ホスト、およびホスト インスタンスが BizTalk Server での設定を更新
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ca56a981-a255-4c4d-82f8-a57d390e425e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0660fd4aa130049d80de4a0c2ee239ef5cae0068
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="manage-biztalk-server-performance-settings"></a>BizTalk Server パフォーマンス設定を管理します。
  
 [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]を BizTalk Server のパフォーマンス設定を収集し、これらの設定を管理する中央コンソールを提供します。 これに役立ちます。  
  
-   設定できるプロパティの探索可能性を向上させる
  
-   すべての設定を 1 か所でがアクセスできるよう、エクスポート/インポートできる簡単にするために、解決に時間を削減します。
  
-   特定の BizTalk 展開の実行のパフォーマンス チューニング レベルの全体像を提供しています
  
## <a name="why-use-it"></a>使用する理由にしますか。  
 [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]は、パフォーマンス最適化のために [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の設定を幅広く調整する必要のある IT 管理者向けのものです。  
  
 [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]を使用すると、BizTalk グループと、そのグループに含まれるすべての BizTalk ホストおよび BizTalk ホスト インスタンスの設定を変更できます。  
  
 グループ、ホスト、およびホスト インスタンスの設定については、次を参照してください。 [グループ設定を変更する方法](../core/how-to-modify-group-settings.md), 、[ホスト設定を変更する方法](../core/how-to-modify-host-settings.md), 、および [ホスト インスタンス設定を変更する方法](../core/how-to-modify-host-instance-settings.md)します。  
  
## <a name="prerequisites"></a>前提条件 
 [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]は [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールから起動できます。 管理する方法の詳細について [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] パフォーマンス設定を使用して、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを参照してください [、BizTalk Server 管理コンソールを使用して](../core/using-the-biztalk-server-administration-console.md)します。  
  
## <a name="where-do-i-start"></a>どのように開始しますか。  
 [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]には、次のいずれかの方法でアクセスすることができます。  
  
-   開始、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、右クリックし **BizTalk グループ** クリックしてコンソール ツリーで **設定**します。  
  
-   下にあるすべてのホストを右クリックして、 **プラットフォームの設定** MMC とのクリックのノードの **設定**します。 これによって [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]が起動し、ホストに関連する設定を変更できます。  
  
-   任意のホスト インスタンスを右クリックして、 **プラットフォームの設定** MMC とのクリックのノードの **設定**します。 これによって [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]が起動し、ホスト インスタンスに関連する設定を変更できます。  
  
## <a name="export-and-import-settings"></a>エクスポートし、インポートの設定  
 [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]では、ある [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境から設定をエクスポートして別の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境にインポートすることで、問題解決までの全体的な時間を短縮できます。 この機能は、管理者がテスト環境で [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のパフォーマンスを調整するシナリオで特に役立ちます。管理者は、希望の結果を達成すると同時に、その設定を運用環境にインポートできます。  
  
 インポート/エクスポートを使用する方法については、[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]ユーザー インターフェイスを参照してください[インポートまたはエクスポート BizTalk の設定を使用して設定のダッシュ ボード](how-to-import-biztalk-settings-using-settings-dashboard.md)です。
  
## <a name="scripting-support"></a>スクリプトのサポート
 [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]では、BizTalk の設定を管理するための集中型のユーザー インターフェイスを利用できるだけでなく、すべての設定およびインポート/エクスポートのタスクに API とコマンドライン オプションをとおしてアクセスすることもできます。 これによって BizTalk Server 管理者は、BizTalk Server の設定に関連したタスクを自動化できます。 スクリプトのサポートによって、次のことも可能になります。  
  
-   すべてのグループ設定は、WMI クラス `MSBTS_GroupSetting` をとおしてアクセスおよび変更できます。  
  
-   すべてのホスト設定は、WMI クラス `MSBTS_HostSetting` をとおしてアクセスおよび変更できます。  
  
-   すべてのホスト インスタンス設定は、WMI クラス `MSBTS_HostInstanceSetting` をとおしてアクセスおよび変更できます。  
  
-   インポートとエクスポート操作経由でアクセスできる **BTSTask.exe** コマンド: `ExportSettings` と `ImportSettings`  
  
 BTSTask.exe コマンドライン ユーティリティを使用してインポート/エクスポートする方法の詳細については、「[インポートまたはエクスポート BizTalk の設定を使用して BTSTask](how-to-import-biztalk-settings-using-btstask.md)です。  
  
## <a name="next"></a>Next  
  
-   [BizTalk Server パフォーマンス チューニングのための設定ダッシュボードの使用](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)  
  
-   [BizTalk Server パフォーマンス チューニングの自動化](../core/automating-biztalk-server-performance-tuning.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk Server の管理](../core/use-groups-create-artifacts-optimize-performance-and-more-in-biztalk-server.md)
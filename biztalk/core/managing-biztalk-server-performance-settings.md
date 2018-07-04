---
title: BizTalk Server パフォーマンス設定の管理 |Microsoft Docs
description: 設定ダッシュ ボードを使用して、BizTalk グループ、ホスト、およびホスト インスタンスが BizTalk Server での設定を更新するには
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
ms.openlocfilehash: 19acfa50ecbcaf46cb796630e88d292283f4631e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999771"
---
# <a name="manage-biztalk-server-performance-settings"></a>BizTalk Server パフォーマンス設定を管理します。
  
 [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]を BizTalk Server のパフォーマンスの設定を収集し、これらの設定を管理する中央コンソールを提供します。 これに役立ちます。  
  
-   設定できるプロパティの探索可能性を向上させる
  
-   すべての設定は、1 か所でアクセスできるようになりましたし、エクスポート/インポートできる簡単にするために、ソリューションに時間を削減します。
  
-   特定の BizTalk 展開の実行のパフォーマンス チューニング レベルの全体像を提供しています
  
## <a name="why-use-it"></a>使用する理由ですか。  
 [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]は、パフォーマンス最適化のために [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の設定を幅広く調整する必要のある IT 管理者向けのものです。  
  
 [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]を使用すると、BizTalk グループと、そのグループに含まれるすべての BizTalk ホストおよび BizTalk ホスト インスタンスの設定を変更できます。  
  
 グループ、ホスト、およびホスト インスタンスの設定の詳細については、次を参照してください[グループ設定を変更する方法](../core/how-to-modify-group-settings.md)、[ホスト設定の変更方法](../core/how-to-modify-host-settings.md)、および[にホストインスタンス設定を変更する方法](../core/how-to-modify-host-instance-settings.md).  
  
## <a name="prerequisites"></a>前提条件 
 [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]は [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールから起動できます。 管理する方法については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンスの設定を使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを参照してください[、BizTalk Server 管理コンソールを使用して](../core/using-the-biztalk-server-administration-console.md)します。  
  
## <a name="where-do-i-start"></a>どこから始めるか。  
 [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]には、次のいずれかの方法でアクセスすることができます。  
  
- 開始、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリック**BizTalk グループ**クリックしてコンソール ツリーで**設定**します。  
  
- 下にあるすべてのホストを右クリックして、**プラットフォームの設定**MMC でクリックするとノード**設定**します。 これによって [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]が起動し、ホストに関連する設定を変更できます。  
  
- 任意のホスト インスタンスを右クリックして、**プラットフォームの設定**MMC でクリックするとノード**設定**します。 これによって [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]が起動し、ホスト インスタンスに関連する設定を変更できます。  
  
## <a name="export-and-import-settings"></a>エクスポートし、インポートの設定  
 [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]では、ある [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境から設定をエクスポートして別の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境にインポートすることで、問題解決までの全体的な時間を短縮できます。 この機能は、管理者がテスト環境で [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のパフォーマンスを調整するシナリオで特に役立ちます。管理者は、希望の結果を達成すると同時に、その設定を運用環境にインポートできます。  
  
 インポート/エクスポートを使用する方法については、[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]ユーザー インターフェイスを参照してください[インポートまたはエクスポート BizTalk の設定を使用して設定のダッシュ ボード](how-to-import-biztalk-settings-using-settings-dashboard.md)します。
  
## <a name="scripting-support"></a>スクリプトのサポート
 [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]では、BizTalk の設定を管理するための集中型のユーザー インターフェイスを利用できるだけでなく、すべての設定およびインポート/エクスポートのタスクに API とコマンドライン オプションをとおしてアクセスすることもできます。 これによって BizTalk Server 管理者は、BizTalk Server の設定に関連したタスクを自動化できます。 スクリプトのサポートによって、次のことも可能になります。  
  
- すべてのグループ設定は、WMI クラス `MSBTS_GroupSetting` をとおしてアクセスおよび変更できます。  
  
- すべてのホスト設定は、WMI クラス `MSBTS_HostSetting` をとおしてアクセスおよび変更できます。  
  
- すべてのホスト インスタンス設定は、WMI クラス `MSBTS_HostInstanceSetting` をとおしてアクセスおよび変更できます。  
  
- インポートおよびエクスポート操作を介してアクセスできる**BTSTask.exe**コマンド:`ExportSettings`と `ImportSettings`  
  
  インポート/エクスポートの BTSTask.exe コマンドライン ユーティリティを使用する方法の詳細については、次を参照してください。[インポートまたはエクスポート BizTalk の設定を使用して BTSTask](how-to-import-biztalk-settings-using-btstask.md)します。  
  
## <a name="next"></a>Next  
  
-   [BizTalk Server パフォーマンス チューニングのための設定ダッシュボードの使用](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)  
  
-   [BizTalk Server パフォーマンス チューニングの自動化](../core/automating-biztalk-server-performance-tuning.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk Server の管理](../core/use-groups-create-artifacts-optimize-performance-and-more-in-biztalk-server.md)
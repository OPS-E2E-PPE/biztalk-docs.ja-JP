---
title: ホスト インスタンスの設定の更新 |Microsoft Docs
description: ホスト インスタンス設定では、BizTalk Server 管理者を変更します。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2338255b-cc13-4f6a-86c3-9ecc666c43e5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e5b2eec6b252417f73f917f1293ffc925f0e1a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336086"
---
# <a name="update-biztalk-host-instance-settings"></a>BizTalk ホスト インスタンス設定を更新します。

## <a name="overview"></a>概要
使用して、 [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]、BizTalk グループ全体で、特定のホスト インスタンスの構成情報を変更することができます。 ここでは、ホスト インスタンス レベルのパフォーマンス設定を変更するための手順では[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
 多くの場合、XML ファイルとして保存 (ソース環境の場合) から BizTalk 設定があります。 XML ファイルには、ターゲット コンピューターの設定をレプリケートできるようにする情報が含まれています。 新しい値を設定するのではなく、設定ダッシュ ボードにこれらの設定をインポートできます。 新しい値を設定した後は、その一方で、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、別のコンピューターで使用する XML ファイルにエクスポートすることができます。  
  
 インポートする方法についての[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]設定を参照してください[インポートまたはエクスポート BizTalk の設定を使用して設定のダッシュ ボード](how-to-import-biztalk-settings-using-settings-dashboard.md)と[インポートまたはエクスポート BizTalk の設定を使用して BTSTask](how-to-import-biztalk-settings-using-btstask.md)します。 
  
## <a name="prerequisites"></a>前提条件  
 この操作を実行するには、BizTalk Server 管理者グループのメンバーとしてサインインする必要があります。  
  
## <a name="update-the-host-instance-level-settings"></a>ホスト インスタンス レベルの設定を更新します。  
  
1. **BizTalk Server 管理コンソール**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を右クリックして**BizTalk グループ**、 をクリックし、**設定**します。  
  
2. **BizTalk 設定ダッシュ ボード** ダイアログ ボックスの 、**ホスト インスタンス** タブで、次のいずれかの操作を行います。  
  
   -   ホスト インスタンスの .NET CLR 設定を変更します。 参照してください[.NET CLR 設定を変更する](../core/how-to-modify-net-clr-settings.md)します。  
  
   -   オーケストレーション メモリ制限の設定を変更します。 参照してください[オーケストレーション メモリ制限の設定を変更する](../core/how-to-modify-orchestration-memory-throttling-settings.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server パフォーマンス チューニングのための設定ダッシュボードの使用](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)
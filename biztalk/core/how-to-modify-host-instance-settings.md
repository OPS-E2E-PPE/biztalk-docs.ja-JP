---
title: ホスト インスタンスの設定の更新 |Microsoft ドキュメント
description: ホスト インスタンスの設定では、BizTalk Server 管理者の変更します。
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
ms.openlocfilehash: d85635f7f7a3b2cfe05abaf041cac07913b36f96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254378"
---
# <a name="update-biztalk-host-instance-settings"></a>BizTalk ホスト インスタンス設定を更新します。

## <a name="overview"></a>概要
[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] を使用すると、BizTalk グループ全体にわたって、特定のホスト インスタンスの構成情報を変更することができます。 このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でホスト インスタンス レベルのパフォーマンスを変更するための手順を説明します。  
  
 多くの場合、送信元の環境の BizTalk 設定は XML ファイルとして保存されています。 この XML ファイルには、設定を送信先コンピューターにレプリケートできるようにする情報が含まれています。 新しい値を設定する代わりに、これらの設定を設定ダッシュボードにインポートできます。 一方、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用の新しい値を設定した後に、その値を XML ファイルにエクスポートし、別のコンピューターで使用することができます。  
  
 インポートする方法について、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]設定を参照してください[インポートまたはエクスポート BizTalk の設定を使用して設定のダッシュ ボード](how-to-import-biztalk-settings-using-settings-dashboard.md)と[インポートまたはエクスポート BizTalk の設定を使用して BTSTask](how-to-import-biztalk-settings-using-btstask.md)です。 
  
## <a name="prerequisites"></a>前提条件  
 この操作を実行するには、BizTalk Server 管理者グループのメンバーとしてサインインする必要があります。  
  
## <a name="update-the-host-instance-level-settings"></a>ホスト インスタンス レベルの設定を更新します。  
  
1.  **BizTalk Server 管理コンソール**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を右クリックして**BizTalk グループ**、クリックして**設定**です。  
  
2.  **BizTalk 設定ダッシュ ボード** ダイアログ ボックスで、**ホスト インスタンス** タブで、次のいずれかの操作します。  
  
    -   ホスト インスタンスの .NET CLR 設定を変更する。 参照してください[.NET CLR 設定を変更する](../core/how-to-modify-net-clr-settings.md)です。  
  
    -   オーケストレーション メモリ制限の設定を変更する。 参照してください[オーケストレーション メモリ制限の設定を変更する](../core/how-to-modify-orchestration-memory-throttling-settings.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk server 設定ダッシュ ボードを使用してパフォーマンス チューニング](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)
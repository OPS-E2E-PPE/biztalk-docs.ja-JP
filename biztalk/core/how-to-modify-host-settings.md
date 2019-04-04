---
title: ホストの設定を変更する方法 |Microsoft Docs
description: パフォーマンスと調整を向上させるために BizTalk Server 管理コンソールでの BizTalk ホストの設定を変更します。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0759b3a0-560e-4a11-92e6-9de0e15f463b
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93b2ea993e044d1cb18efcc73f631e8ba3fcb8ff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975843"
---
# <a name="update-biztalk-host-settings"></a>BizTalk ホストの設定を更新します。

## <a name="overview"></a>概要
設定ダッシュボードを使用して、1 つの BizTalk グループ全体で使用する特定のホストの構成情報を変更できます。 このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でホストレベルのパフォーマンス設定を変更する手順を説明します。  
  
> [!NOTE]
>  グループとホスト インスタンスの設定を変更することもできます。 設定を変更する方法については、[設定ダッシュ ボードの BizTalk Server のパフォーマンス チューニングを使用して](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)を参照してください。  
  
 BizTalk Server の現在の設定は XML ファイルにエクスポートできます。 後で、新しい値を設定する代わりに、これらの設定を設定ダッシュボードにインポートできます。 インポートする方法についての[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]設定を参照してください[インポートまたはエクスポート BizTalk の設定を使用して設定のダッシュ ボード](how-to-import-biztalk-settings-using-settings-dashboard.md)と[インポートまたはエクスポート BizTalk の設定を使用して BTSTask](how-to-import-biztalk-settings-using-btstask.md)します。 
  
## <a name="prerequisites"></a>前提条件  
 この操作を実行するには、BizTalk Server 管理者グループのメンバーとしてサインインする必要があります。  
  
## <a name="update-the-host-level-settings"></a>ホスト レベルの設定を更新します。  
  
1. **BizTalk Server 管理コンソール**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を右クリックして**BizTalk グループ**、 をクリックし、**設定**します。  
  
2. **BizTalk 設定ダッシュ ボード** ダイアログ ボックスで、**ホスト**ページで、次の 1 つ以上の操作を行います。  
  
   -   BizTalk ホストのパフォーマンスの全般的な設定を変更します。 参照してください[全般設定を変更する方法](../core/how-to-modify-general-settings.md)します。  
  
   -   BizTalk ホストのリソースベースでの制限の設定を変更します。 参照してください[ベースの制限の設定をリソースを変更する方法](../core/how-to-modify-resource-based-throttling-settings.md)します。  
  
   -   BizTalk ホストの比率ベースのスロットル設定を変更します。 参照してください[レートを変更する方法は、制限の設定をベース](../core/how-to-modify-rate-based-throttling-settings.md)します。  
  
   -   BizTalk ホストのオーケストレーション制限の設定を変更します。 参照してください[オーケストレーション制限の設定を変更する方法](../core/how-to-modify-orchestration-throttling-settings.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server パフォーマンス チューニングのための設定ダッシュボードの使用](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)
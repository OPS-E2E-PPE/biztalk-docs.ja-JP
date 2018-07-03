---
title: Operations Manager 2007 で監視するためのベスト プラクティス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67a5026c-ef59-498b-9bef-ea0f1c932eae
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d099ba9ea60fd8f553d4eaf2011e93a054f59e68
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018706"
---
# <a name="best-practices-for-monitoring-with-operations-manager-2007"></a>Operations Manager 2007 で監視するためのベスト プラクティス
Operations Manager 2007 を使用してアプリケーションを効果的に監視するには、このトピックに記載のベスト プラクティスに従います。  
  
 **完全なカバレッジの追加の管理パックをインストールします。**  
  
- Operations Manager 2007 での主要なアプリケーションを監視できるようにする、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境では、次の管理パックをインストールする必要があります。  
  
  - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] (必須)  
  
  - Windows Server オペレーティング システム (省略可能)  
  
  - Microsoft Windows Server フェールオーバー クラスター (クラスターが場合に使用される、省略可能)  
  
  - SQL Server の監視  
  
  - インターネット インフォメーション サービス 7  
  
  - メッセージ キュー (MSMQ) 5.0 (省略可能)  
  
  **確認し、日常的にアラートの優先順位を付ける**  
  
- 確認して、日常的にアラートの優先順位付けは、適切なタイミングで問題が解決されることを確認するのに役立ちます。  
  
  **いることを確認[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が Operations Manager 2007 サーバーと通信します。**  
  
- 実行しているサーバー間の通信が失敗した場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と監視のインフラストラクチャでは、アラートが受信できなくします。  
  
  **有効にして、必要に応じてルールを無効にします。**  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理パックのルールのいくつかは、既定で無効に設定されています。 これらの無効化されたルールは、次の種類: 規則のカスタマイズ、テンプレートとして機能するルールおよび監視のルールを追加しなくて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]イベント。 確認して、関連するルール[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境が有効にします。  
  
  **環境内での必要に応じてルールをカスタマイズします。**  
  
- 使用している [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の展開に応じて、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理パックのルールをカスタマイズする必要があります。 一部のルールでは、使用している特定の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の展開に基づいて適切に定義された監視のしきい値または時間のしきい値が必要です。  
  
  **必要に応じて、追加の規則を作成するに含まれるルールに基づいて、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パック**  
  
- など、作成するアイテムのテンプレートとして使用するためのルールが提供されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホスト。 これらのテンプレート ルールは、次のようなアイテム固有のルールを作成するときに参照として使用してください。  
  
  -   ホストに固有のルールは、たとえば、キューの監視をホストし、調整の監視をホストします。  
  
  -   メッセージ ボックスに固有のルール  
  
  -   MQSeries アダプターなど、追加のサード パーティ コンポーネント用のルール  
  
  **すべてを監視、BizTalk Server 関連のコンポーネント**  
  
  コンポーネント、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実行されていることを確認する必要がありますを監視する環境などが、必ずしもに制限はありません。  
  
- BizTalk ホスト インスタンス  
  
- [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] インストールされているエージェント ジョブ [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
- BizTalk ソリューション用に開発されたカスタム サービス  
  
- すべてのカスタム データベースの状態は、BizTalk ソリューションの開発  
  
- 関連するすべてのカスタム イベント ログ エントリ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境  
  
## <a name="see-also"></a>参照  
 [System Center Operations Manager 2007 による BizTalk Server の監視](../technical-guides/monitoring-biztalk-server-with-system-center-operations-manager-2007.md)
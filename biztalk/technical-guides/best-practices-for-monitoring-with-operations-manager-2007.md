---
title: "Operations Manager 2007 で監視するためのベスト プラクティス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 67a5026c-ef59-498b-9bef-ea0f1c932eae
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29d83f647c40801260890a99cef4b0b2bfa0551b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-for-monitoring-with-operations-manager-2007"></a>Operations Manager 2007 で監視のベスト プラクティス
Operations Manager 2007 を使用してアプリケーションを効果的に監視するには、このトピックに記載のベスト プラクティスに従います。  
  
 **完全なカバレッジの追加の管理パックをインストールします。**  
  
-   Operations Manager 2007 での主要なアプリケーションを監視できるように、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境では、次の管理パックをインストールする必要があります。  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)](必須)  
  
    -   Windows Server オペレーティング システム (省略可能)  
  
    -   Microsoft Windows Server フェールオーバー クラスター (クラスターが場合に使用される、省略可能)  
  
    -   SQL Server の監視  
  
    -   インターネット インフォメーション サービス 7  
  
    -   メッセージ キュー (MSMQ) 5.0 (省略可能)  
  
 **確認し、1 日 1 回のアラートの優先順位を設定**  
  
-   確認して、1 日 1 回のアラートの優先順位付けは、適切なタイミングで問題が解決されることを確認するは役立ちます。  
  
 **いることを確認[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が Operations Manager 2007 サーバーと通信します。**  
  
-   実行中のサーバー間の通信が失敗した場合は[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と監視インフラストラクチャでは、警告が表示されません。  
  
 **有効にして、必要に応じてルールを無効にします。**  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理パックのルールのいくつかは、既定で無効に設定されています。 これらの無効化されたルールは、次の種類: が必要なルールのカスタマイズ、テンプレートとして機能するルールおよび監視のルール追加[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]イベント。 確認、関連するルール[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境が有効にします。  
  
 **環境に必要に応じてルールをカスタマイズします。**  
  
-   使用している [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の展開に応じて、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理パックのルールをカスタマイズする必要があります。 一部のルールでは、使用している特定の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の展開に基づいて適切に定義された監視のしきい値または時間のしきい値が必要です。  
  
 **含まれるルールに基づいて、必要に応じて追加の規則を作成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パック**  
  
-   ルールはそのまま使用するテンプレートを作成するなどの成果物を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホストします。 これらのテンプレート ルールは、次のようなアイテム固有のルールを作成するときに参照として使用してください。  
  
    -   ホストに固有のルールは、たとえば、キューの監視をホストし、スロットルの監視をホスト  
  
    -   メッセージ ボックス固有の規則  
  
    -   MQSeries アダプターなど、追加のサード パーティ コンポーネント用のルール  
  
 **すべての監視、BizTalk Server 関連コンポーネント**  
  
 コンポーネント、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が実行されていることを確認する必要がありますを監視する環境などが、必ずしもに制限はありません。  
  
-   BizTalk ホスト インスタンス  
  
-   [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]と共にインストールされるエージェント ジョブ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
-   BizTalk ソリューション用に開発されたカスタム サービス  
  
-   すべてのカスタム データベースの状態は、BizTalk ソリューションの開発  
  
-   関連するすべてのカスタム イベント ログ エントリ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境  
  
## <a name="see-also"></a>参照  
 [System Center Operations Manager 2007 での BizTalk Server の監視](../technical-guides/monitoring-biztalk-server-with-system-center-operations-manager-2007.md)
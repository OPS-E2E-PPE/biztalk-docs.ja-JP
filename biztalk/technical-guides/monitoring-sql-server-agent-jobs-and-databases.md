---
title: SQL Server エージェント ジョブおよびデータベースの監視 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2eb5f318-10d3-4f43-991d-9bff2ebc20e2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6c9991e7ebd61c72bbeb6a090b0497244da63e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299202"
---
# <a name="monitoring-sql-server-agent-jobs-and-databases"></a>SQL Server エージェント ジョブとデータベースの監視
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]複数含まれています[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]動作状況と状態、サーバーを保つために重要な機能を実行するエージェント ジョブ。 これらのジョブの状態を監視し、エラーが発生せずに動作していることを確認する必要があります。 Microsoft[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]管理パックには、SQL データベースなどの項目を監視するためのルールが含まれています。 および[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]エージェント ジョブ。 構成する必要があります、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]すべての包括的な監視用管理パック[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースおよび[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]エージェント ジョブ。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パックには、2 つの最も重要な BizTalk のヘルスを監視するための 2 つの無効化されたルールが含まれています。[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]エージェント ジョブ。  
  
-   重大なエラー: BizTalk SQL Server エージェント ジョブに失敗しました - BizTalk Server のバックアップ  
  
-   重大なエラー: BizTalk SQL Server エージェント ジョブが失敗しました: メッセージのコピーを追跡  
  
 すべての BizTalk Server を監視する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]内からのエージェント ジョブ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パックは、これらの規則を有効にし、追加の規則を使用して、次のプロセスを監視する他のジョブを作成する必要があります。  
  
-   Operations Manager 管理者コンソールでの 2 つの前述の規則のいずれかのコピーを作成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コア ルール グループ化、およびルールを適切に名前を変更します。  
  
-   ルールの [条件] セクションで適切にパラメーター 1 に対するワイルドカード比較を変更します。  
  
-   場合によっては、ジョブ名はデータベース名、ユーザーが作成、たとえば、メッセージ ボックス データベースの名前に依存します。  
  
-   ルールのターゲットとなるジョブの方向にいずれかに関連付けられている 1 つのメッセージ ボックス データベースまたはすべてのメッセージ ボックスです。  
  
## <a name="see-also"></a>参照  
 [SQL Server エージェントを開始する方法](../technical-guides/how-to-start-the-sql-server-agent.md)
---
title: SQL Server エージェント ジョブの監視 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 60d0a377-c86d-429b-9e48-c37bd5b0f912
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 489e9e8e8b5bf5b00125036d71ff5fa0f37f3545
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298962"
---
# <a name="monitoring-sql-server-agent-jobs"></a>SQL Server エージェント ジョブの監視
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には、サーバーの動作状況と状態を維持するための重要な機能を実行する複数の SQL Server エージェント ジョブが含まれます。 これらのジョブの状態を監視し、エラーが発生せずに動作していることを確認する必要があります。  
  
## <a name="guidelines-for-monitoring-the-sql-server-agent-jobs"></a>SQL Server エージェント ジョブを監視するためのガイドライン  
 ジョブを監視するためのガイドラインを次に示します。  
  
-   **SQL Server エージェント サービスが実行されていることを確認してください。**  
  
-   **BizTalk Server によってインストールされる SQL Server エージェント ジョブが実行されていて正常を確認してください。**  
  
     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SQL Server エージェント ジョブがきわめて重要です。 時間の経過と共に実行されていない場合システムのパフォーマンスが低下します。  
  
-   **適切なタイミングで、BizTalk Server SQL Server エージェント ジョブが完了することを確認してください。**  
  
     Microsoft System Center Operations Manager を設定すると、ジョブを監視します。  
  
     特定のジョブを特定のスケジュールの注意する必要があります。  
  
    -   MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb ジョブは、既定では継続的に実行されます。 監視ソフトウェアと、このスケジュールを考慮する必要があります、警告を生成されません。  
  
    -   MessageBox_Message_Cleanup_BizTalkMsgBoxDb ジョブは有効になっているスケジュールも 10 秒ごと、MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb ジョブによって起動されました。 そのため、このジョブ有効になっている、スケジュール、したりしないでを手動で開始します。  
  
-   **SQL Server エージェント サービスのスタートアップの種類が正しく構成されていることを確認してください。**  
  
     SQL Server エージェント サービスが構成されていることを確認してください、 **Startuptype**の**自動**SQL Server エージェント サービスが、Windows Server クラスターでクラスター リソースとして構成されている場合を除き、します。 SQL Server エージェント サービスがクラスター リソースとして構成されているかどうかは、構成する必要があります、 **Startuptype**として**手動**サービスは、クラスター サービスによって管理するためです。  
  
## <a name="additional-resources"></a>その他のリソース  
  
-   監視の詳細については、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SQL エージェント ジョブ, を参照してください[SQL Server エージェント ジョブの監視とデータベース](../technical-guides/monitoring-sql-server-agent-jobs-and-databases.md)です。  
  
-   含まれている SQL Server エージェント ジョブの詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[データベース構造と「ジョブ」](http://go.microsoft.com/fwlink/?LinkID=153451) (http://go.microsoft.com/fwlink/?LinkID=153451)。
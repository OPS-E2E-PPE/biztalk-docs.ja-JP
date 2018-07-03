---
title: SQL Server エージェント ジョブの監視 |Microsoft Docs
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
ms.openlocfilehash: 6fb4026b95a5f368c265b49425ab1d3e1ec776cd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015393"
---
# <a name="monitoring-sql-server-agent-jobs"></a>SQL Server エージェント ジョブの監視
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には、サーバーの動作状況と状態を維持するための重要な機能を実行する複数の SQL Server エージェント ジョブが含まれます。 これらのジョブの状態を監視し、エラーが発生せずに動作していることを確認する必要があります。  

## <a name="guidelines-for-monitoring-the-sql-server-agent-jobs"></a>SQL Server エージェントのジョブを監視するためのガイドライン  
 ジョブを監視するためのガイドラインを次に示します。  

- **SQL Server エージェント サービスが実行されていることを確認します。**  

- **BizTalk Server によってインストールされる SQL Server エージェント ジョブが実行されていて正常に確認します**  

   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SQL Server エージェント ジョブが非常に重要です。 時間の経過と共に実行されていない場合、システムのパフォーマンスが低下します。  

- **適切なタイミングで、BizTalk Server SQL Server エージェント ジョブが完了することを確認します。**  

   Microsoft System Center Operations Manager を設定すると、ジョブを監視します。  

   特定のジョブを特定のスケジュールの注意する必要があります。  

  -   既定では、MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb ジョブが継続的に実行されます。 ソフトウェアを監視、このスケジュールを考慮に入れてし、警告を生成しない必要があります。  

  -   MessageBox_Message_Cleanup_BizTalkMsgBoxDb ジョブは有効、またはスケジュール設定をされませんが、10 秒ごと、MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb ジョブによって起動されました。 そのため、このジョブする必要がありますいない有効、スケジュールまたは手動で開始されました。  

- **SQL Server エージェント サービスのスタートアップの種類が正しく構成されていることを確認します。**  

   SQL Server エージェント サービスが構成されていることを確認、**のスタートアップの種類**の**自動**SQL Server エージェント サービスが Windows Server クラスターでクラスター リソースとして構成されていない場合。 SQL Server エージェント サービスがクラスター リソースとして構成されているかどうかは、構成する必要があります、 **Startuptype**として**手動**サービスは、クラスター サービスによって管理されるためです。  

## <a name="additional-resources"></a>その他のリソース  

- 監視の詳細については、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SQL エージェント ジョブ, を参照してください[SQL Server エージェント ジョブの監視とデータベース](../technical-guides/monitoring-sql-server-agent-jobs-and-databases.md)します。  

- 含まれている SQL Server エージェント ジョブの詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[「データベースの構造とジョブ」](http://go.microsoft.com/fwlink/?LinkID=153451) (<http://go.microsoft.com/fwlink/?LinkID=153451>)。

---
title: 主要業績評価指標 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 298d639a-7adf-4f04-b097-a17f4c77ee50
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fc0d89c7d6bb72cf68611d1a6eaccffa11dbe0d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395835"
---
# <a name="key-performance-indicators"></a>主要業績評価指標
このトピックでは、次のスケール アウト メソッドを使用する場合、BizTalk Server 製品グループが観察されたテスト結果を示します。  
  
- 業績評価指標 (Kpi) をキーの数を増やしたときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]内のコンピューター、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。 これらのテストが 1 つだけ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベース用に構成された、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。 これらのテストへの影響の詳細を追加するだけに重点を置いた[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]にコンピューターを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。  
  
- Kpi の数を増やしたときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]によって使用されるメッセージ ボックス データベース、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。 これらのテストへの影響の詳細を追加するだけに重点を置いた[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベースを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。  
  
- 両方の数を増やしたときに、Kpi[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターと[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]によって使用されるメッセージ ボックス データベース、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。 これらのテストの両方を追加の影響を測定する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターと[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベースを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。  
  
## <a name="analysis-of-key-performance-indicators"></a>主要業績評価指標の分析  
  
### <a name="messaging-scenario-biztalk-server-scale-out--biztalk-and-sql-kpi"></a>メッセージング シナリオでは、BizTalk Server のスケール アウト – BizTalk と SQL の KPI  
 BizTalk Server を実行している 2 つ目のコンピューターを追加しても、全体的なスループットに大きな影響を与えるは表示されません。  25% で、BizTalk Server の CPU の負荷が低くなります。 SQL Server の cpu 使用率もわずかから増加 59% 59.8% に BizTalk Server を実行している 2 つ目のコンピューターが、BizTalk Server グループに追加されるとします。 これ以降は、さらにパフォーマンス上の利点を得たない BizTalk 処理サーバーの数を増やすことで。  
  
 各 BizTalk ホスト インスタンスは、メッセージ ボックスで、適切なキューを定期的にポーリングします。 ホストのキューで参照されているすべてのメッセージはメッセージ ボックス データベース内のテーブルの共有のセット内で実際に格納されます。 スループットになると BizTalk Server を実行している複数のコンピューターを追加するときに、一般的な原因は、メッセージ ボックス データベース内の共有、テーブルに対するアクティビティが多すぎるです。 これらのテーブルを特定のファイル グループに割り当てることで、これらのテーブルに、SQL Server の専用 I/O パスを作成できます。  
  
 [Databases2 のファイルグループの最適化](../technical-guides/optimizing-filegroups-for-the-databases2.md)にテーブルを特定のファイル グループに割り当てる方法について説明します。 含まれるスクリプト[BizTalk Server メッセージ ボックス データベースのファイル グループの SQL スクリプト](../technical-guides/biztalk-server-messagebox-database-filegroups-sql-script.md)ガイドのこれを実現する方法を示します。 複数のメッセージ ボックスの構成をスケール アウトは、複数のファイル グループとすべての他の SQL に関連する最適化が適用された後、メッセージ ボックス オブジェクトを配布後にのみ検討してください。  
  
 **BizTalk Server と SQL Server の CPU 使用率の割合**  
  
 ![M&#45;SingleMsgBox](../technical-guides/media/m-singlemsgbox.gif "M SingleMsgBox")  
  
### <a name="messaging-scenario-biztalk-server-and-sql-server-scale-out--biztalk-and-sql-kpi"></a>メッセージング シナリオでは、BizTalk Server と SQL Server スケール アウト – BizTalk と SQL の KPI  
 このテストは、4 つのメッセージ ボックス データベースを追加するスケール アウト、SQL Server 層の有効性を判断する実行されました。 このシナリオで BizTalk Server を実行している最大で 2 つのコンピューターを追加する 1 秒あたりの 2,790 メッセージの最大持続可能スループットが有効になります。 これは、メッセージ ボックスは 1 つのみを使用する場合、取得可能な最大のスループットよりも高い 118%。 これ以降は、メッセージ ボックスの 1 つのシナリオと同様の方法でパフォーマンスの低下処理能力を BizTalk Server 層に追加します。  
  
 キーのメッセージング シナリオのテスト結果は、スケール アウトは、BizTalk Server が SQL Server での競合がボトルネックでない場合は、全体的なスループットを向上のための効果的な手法であることです。 メッセージ ボックス データベースには、競合ポイントになると、最初に記載された最適化に適用[データベースのパフォーマンスの最適化](../technical-guides/optimizing-database-performance.md)で説明されているファイル グループの最適化スクリプトでは特に[BizTalk Serverメッセージ ボックス データベースのファイル グループの SQL スクリプト](../technical-guides/biztalk-server-messagebox-database-filegroups-sql-script.md)I/O 負荷を分散します。 まだ、目的のスループットを実現できない場合は、メッセージ ボックス データベースを追加することでスケール アウトを検討してください。  
  
 **BizTalk Server と SQL Server の CPU 使用率の割合**  
  
 ![M&#45;MultipleMsgBox](../technical-guides/media/m-multiplemsgbox.gif "M MultipleMsgBox")  
  
### <a name="orchestration-scenario-biztalk-server-scale-out--sql-server-and-biztalk-server-kpi"></a>オーケストレーション シナリオでは、BizTalk Server のスケール アウト: SQL Server と BizTalk Server の KPI  
 BizTalk Server を実行している 2 つ目のコンピューターを追加しても、全体的なスループットに大きな影響を与えるは表示されません。 BizTalk Server の CPU の負荷は 23% が低下します。 SQL Server の cpu 使用率が 66.5% から 68.5 パーセントに BizTalk Server を実行している追加のコンピューターが追加されたときにします。  
  
 **BizTalk Server と SQL Server の CPU 使用率の割合**  
  
 ![O&#45;SingleMsgBox](../technical-guides/media/o-singlemsgbox.gif "O SingleMsgBox")  
  
### <a name="orchestration-scenario-biztalk-server-and-sql-server-scale-out--sql-server-and-biztalk-server-kpi"></a>オーケストレーション シナリオでは、BizTalk Server と SQL Server スケール アウト: SQL Server と BizTalk Server の KPI  
 このテストは、BizTalk Server とオーケストレーション シナリオでは、メッセージ ボックス データベースを実行している複数のコンピューターを追加するスケール アウト、BizTalk Server と SQL Server 層の有効性を判断する実行されました。 このシナリオで BizTalk Server を実行している最大で 2 つのコンピューターを追加する 1,487 オーケストレーション 1 秒あたりの最大持続可能スループットが有効になります。 これは、1 つのメッセージ ボックスに対して取得可能な最大結果よりも高い 116% です。 別の SQL Server コンピューターで 4 つのメッセージ ボックス データベースをスケール アウトには、追加の処理能力が原因のスループットの向上やデータベースの負荷を複数のメッセージ ボックス データベースに分散させることが対応しています。 この方針を使用には、1 つのメッセージ ボックス環境でボトルネックが、共有テーブルでの競合も解放します。 メッセージング シナリオと同様のメッセージ ボックス データベースの数を増やすことと専用の SQL インスタンス間でこれらを配布するには、BizTalk Server グループに複数の BizTalk Server コンピューターの追加ことができます。  
  
 **BizTalk Server と SQL Server の CPU 使用率の割合**  
  
 ![O&#45;MultipleMsgBox](../technical-guides/media/o-multiplemsgbox.gif "O MultipleMsgBox")  
  
## <a name="see-also"></a>参照  
 [BizTalk Server の運用環境のスケーリング](../technical-guides/scaling-a-production-biztalk-server-environment.md)
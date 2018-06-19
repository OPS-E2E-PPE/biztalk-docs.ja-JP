---
title: 主要業績評価指標 |Microsoft ドキュメント
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
ms.openlocfilehash: 8a03bf76c725f22567d5e884ca22e3a862b15ce3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298290"
---
# <a name="key-performance-indicators"></a>主要業績評価指標
このトピックでは、以下のスケール アウト方法を使用する場合、BizTalk Server 製品のグループが観察されたテスト結果を示します。  
  
-   業績評価指標 (Kpi) をキーの数を増やすとき[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]内のコンピューター、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。 これらのテストが 1 つだけ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベース用に構成された、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。 これらのテストが追加の影響の情報だけを頼りに重点を置いて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。  
  
-   Kpi の数を増やすとき[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]によって使用されるメッセージ ボックス データベース、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。 これらのテストが追加の影響の情報だけを頼りに重点を置いて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベースを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。  
  
-   両方の数を増やすときに Kpi[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターおよび[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]によって使用されるメッセージ ボックス データベース、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。 これらのテストの両方を追加する影響を測定する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターおよび[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベースを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。  
  
## <a name="analysis-of-key-performance-indicators"></a>主要業績評価指標の分析  
  
### <a name="messaging-scenario-biztalk-server-scale-out--biztalk-and-sql-kpi"></a>メッセージング シナリオでは、BizTalk Server のスケール アウト – BizTalk と SQL の KPI  
 BizTalk Server を実行している 2 つ目のコンピューターを追加することも、全体的なスループットに大きな影響は表示されません。  25% で、BizTalk Server の CPU の負荷が低くなります。 SQL Server の CPU わずかから増加 59% 59.8% に 2 番目の BizTalk Server を実行しているコンピューターが、BizTalk Server グループに追加されるとします。 これ以降では、さらにパフォーマンス上の利点を得たありません BizTalk 処理サーバーの数を増やすことで。  
  
 各 BizTalk ホスト インスタンスは、メッセージ ボックスに適切なキューを定期的にポーリングします。 ホストのキューで参照されているすべてのメッセージは、メッセージ ボックス データベース内のテーブルの共有のセット内で実際に格納されます。 スループットは、BizTalk Server を実行している複数のコンピューターを追加するときに削除、一般的な原因が、メッセージ ボックス データベース内の共有のテーブルに対して利用が多すぎます。 これらのテーブルに、SQL Server の専用 I/O パスは、これらのテーブルを特定のファイル グループに割り当てることによって作成できます。  
  
 [ファイル グループを Databases2 の最適化](../technical-guides/optimizing-filegroups-for-the-databases2.md)テーブルを特定のファイル グループに割り当てる方法について説明します。 スクリプトに含まれて[BizTalk Server メッセージ ボックス データベースのファイル グループの SQL スクリプト](../technical-guides/biztalk-server-messagebox-database-filegroups-sql-script.md)ガイドのこれを実現する方法を示します。 複数のメッセージ ボックス データベースの構成にスケール アウトは、複数のファイル グループとすべての他の SQL 関連の最適化が適用された後、メッセージ ボックス オブジェクトを配布後にのみ考慮してください。  
  
 **BizTalk Server と SQL Server の CPU 使用率の割合**  
  
 ![M &#45;SingleMsgBox](../technical-guides/media/m-singlemsgbox.gif "M SingleMsgBox")  
  
### <a name="messaging-scenario-biztalk-server-and-sql-server-scale-out--biztalk-and-sql-kpi"></a>メッセージング シナリオでは、BizTalk Server および SQL Server スケール アウト – BizTalk と SQL の KPI  
 このテストは、4 つのメッセージ ボックス データベースを追加することで、SQL Server 層をスケーリングの効果を判断に行われました。 このシナリオで BizTalk Server を実行する最大 2 つのコンピューターを追加する 1 秒あたりの 2,790 メッセージの最大のスループットが有効になります。 これは、メッセージ ボックスは 1 つのみを使用する場合、118% が取得可能な最大のスループットよりも高い。 これ以降では、BizTalk Server 層に高い処理能力を追加する 1 つのメッセージ ボックス シナリオと同様の方法でパフォーマンスの低下します。  
  
 メッセージング シナリオ テストのキーの結果は、スケール アウトは、BizTalk Server が SQL Server での競合がボトルネックでない場合は、全体的なスループットを増加させるのに効果的な手法であることです。 メッセージ ボックス データベースには、競合ポイントになると、最初に詳細な最適化に適用[データベースのパフォーマンスの最適化](../technical-guides/optimizing-database-performance.md)に記載されているファイル グループの最適化スクリプトでは特に[BizTalk Serverメッセージ ボックス データベースのファイル グループの SQL スクリプト](../technical-guides/biztalk-server-messagebox-database-filegroups-sql-script.md)I/O 負荷を分散します。 目的のスループットを実現できない場合は、メッセージ ボックス データベースを追加することでスケール アウトを検討してください。  
  
 **BizTalk Server と SQL Server の CPU 使用率の割合**  
  
 ![M &#45;MultipleMsgBox](../technical-guides/media/m-multiplemsgbox.gif "M MultipleMsgBox")  
  
### <a name="orchestration-scenario-biztalk-server-scale-out--sql-server-and-biztalk-server-kpi"></a>オーケストレーション シナリオでは、BizTalk Server のスケール アウト – SQL Server と BizTalk Server KPI  
 BizTalk Server を実行している 2 つ目のコンピューターを追加することも、全体的なスループットに大きな影響は表示されません。 23% で、BizTalk Server の CPU の負荷が低くなります。 SQL Server の CPU が 66.5% から 68.5 パーセントに BizTalk Server を実行しているその他のコンピューターが追加されるとします。  
  
 **BizTalk Server と SQL Server の CPU 使用率の割合**  
  
 ![O &#45;SingleMsgBox](../technical-guides/media/o-singlemsgbox.gif "O SingleMsgBox")  
  
### <a name="orchestration-scenario-biztalk-server-and-sql-server-scale-out--sql-server-and-biztalk-server-kpi"></a>オーケストレーション シナリオでは、BizTalk Server および SQL Server スケール アウト – SQL Server と BizTalk Server KPI  
 このテストは、BizTalk Server と、オーケストレーションのシナリオのメッセージ ボックス データベースを実行するコンピューターを追加して、BizTalk Server と SQL Server の両方の層をスケーリングの効果を判断に行われました。 このシナリオで BizTalk Server を実行する最大 2 つのコンピューターを追加する 1,487 オーケストレーション 1 秒あたりの最大のスループットが有効になります。 これは、単一のメッセージ ボックスに対して取得可能な結果の最大よりも高い 116% です。 別の SQL Server コンピュータ上の 4 つのメッセージ ボックス データベースをスケール アウトには、追加の処理能力のための高スループットとデータベースの負荷を複数のメッセージ ボックス データベースに分散させることが対応しています。 この方針は、共有のテーブルでの競合もされますが、1 つのメッセージ ボックス環境でのボトルネックであった。 メッセージ ボックス データベースの数を増やすと専用の SQL インスタンス間でこれらの配布は、メッセージング シナリオと同様、BizTalk Server グループに複数の BizTalk Server コンピューターの追加を使用できます。  
  
 **BizTalk Server と SQL Server の CPU 使用率の割合**  
  
 ![O &#45;MultipleMsgBox](../technical-guides/media/o-multiplemsgbox.gif "O MultipleMsgBox")  
  
## <a name="see-also"></a>参照  
 [運用環境の BizTalk Server 環境のスケーリング](../technical-guides/scaling-a-production-biztalk-server-environment.md)
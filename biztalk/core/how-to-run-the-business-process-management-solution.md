---
title: ビジネス プロセス管理ソリューションを実行する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, validating
- process management solution tutorial, submitting orders
- process management solution tutorial, stopping orders
- process management solution tutorial, updating orders
ms.assetid: cb77651e-e16c-49dc-9f8a-88584cd68a8b
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3997fb18e7498ab2bc5f8c77b53740fb87ab6f93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257626"
---
# <a name="how-to-run-the-business-process-management-solution"></a>ビジネス プロセス管理ソリューションの実行方法
次の手順では、単一のコンピュータでビジネス プロセス管理ソリューションを実行および検証する方法について説明します。  
  
-   [ビジネス プロセス管理ソリューションを開始します。](#step1)  
  
-   [実行し、ビジネス プロセス管理ソリューションの検証](#step3)  
  
## <a name="prerequisites"></a>前提条件  
 BPM ソリューションを実行する前に」の手順を実行する必要があります[ビジネス プロセス管理ソリューションをインストールする方法](../core/how-to-install-the-business-process-management-solution.md)です。  
  
##  <a name="step1"></a>ビジネス プロセス管理ソリューションを開始します。  
  
#### <a name="to-start-the-business-process-management-solution"></a>ビジネス プロセス管理ソリューションを開始するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**プラットフォームの設定**、展開**ホスト インスタンス**、右クリック**BizTalkServerApplication**、クリックして**開始**です。  
  
3.  **BizTalk Server 管理コンソール**、展開**BizTalk グループ**の順に展開および**アプリケーション**です。  
  
    1.  BTSScn.BPM.MessagingApp を右クリックし、をクリックして**開始**、順にクリック**開始**上、**アプリケーションの開始** ダイアログ ボックス。  
  
    2.  BTSScn.BPM.OrderBrokerApp を右クリックし、をクリックして**開始**、順にクリック**開始**上、**アプリケーションの開始** ダイアログ ボックス。  
  
    3.  BTSScn.BPM.CableOrderApp を右クリックし、をクリックして**開始**、順にクリック**開始**上、**アプリケーションの開始** ダイアログ ボックス。  
  
    4.  BTSScn.BPM.OrderBrokerApp.Test を右クリックし、をクリックして**停止**です。 **アプリケーションの停止**ダイアログ ボックスで、**完全停止 - インスタンスを終了**、クリックして**停止**です。  
  
    > [!NOTE]
    >  履歴データベースに情報を挿入します。 OrderBroker オーケストレーションは HistoryPort 送信ポートを使用して、**配信通知**プロパティが設定されて**送信**です。 送信ポートは、HistoryInsert-SP と HistoryInsert-Test-SP を含む HistoryInsert-SPG 送信グループにバインドされています。 これら 2 つの送信ポートの場合、メッセージ エンジンは OrderBroker オーケストレーションに 2 つの受信確認メッセージを公開します。 使用されないメッセージにより、オーケストレーションが保留になります。 このような状況を防ぐには、どちらか一方の送信ポートの参加を解除する必要があります。 このチュートリアルでは、BTSScn.BPM.OrderBrokerApp.Test アプリケーションを完全に停止して HistoryInsert-Test-SP 送信ポートを参加解除します。 OrderBroker オーケストレーションの詳細については、次を参照してください。 [OrderBroker オーケストレーションで処理](../core/processing-in-the-orderbroker-orchestration.md)です。 詳細については**配信通知**プロパティを参照してください[を使用して受信確認](../core/using-acknowledgments.md)です。  
  
4.  次に示すように、Facilities Simulator を実行します。  
  
    1.  コマンド プロンプトを開き、ディレクトリを %BTSSolutionsPath%\BPM\FacilitiesSimulator\bin\debug フォルダに変更します。  
  
    2.  型`BTSScnBPMFacilities.exe`、ENTER キーを押します。 FacilitiesSimulator は実行した状態にしておきます。 ここでは、Southridge Video のバックエンド システムを処理する場合をシミュレートします。  
  
    3.  FacilitiesSimulator で、次の受信キューおよび送信キューを入力します。  
  
        |名前|値|  
        |----------|-----------|  
        |**キューを受信します。**|`.\private$\ToFacilitiesQ`|  
        |**キューを送信します。**|`.\private$\FromFacilitiesQ`|  
  
    4.  FacilitiesSimulator で、をクリックして**開始**です。  
  
5.  次に示すように、Operation Server を実行します。  
  
    1.  新しいコマンド プロンプトを開き、現在のディレクトリを %BTSSolutionsPath%\BPM\OperationsServer\bin\debug フォルダに変更します。  
  
    2.  型`BTSScnBPMOperations.exe 8881`コマンド プロンプトとし、ENTER キーを押します。 Operation Server は実行した状態にしておきます。 Operation Server は TCP ポートの 8881 で Ops アダプタからのメッセージを受信待ちします。 Ops アダプタから受信したエラーメッセージが表示されます。  
  
6.  次に示すように、ケーブル プロビジョニング システムを実行します。  
  
    1.  新しいコマンド プロンプトを開き、現在のディレクトリを %BTSSolutionsPath%\BPM\CableProvisioningSystemServer\bin\debug フォルダに変更します。  
  
    2.  型`BTSScnBPMProvisioning.exe 8880`、ENTER キーを押します。 ケーブル プロビジョニング システムの実行は続けます。 Cable Provisioning System は、8880 TCP ポートでリッスンします。 このアプリケーションは、バックエンド注文システムをシミュレートし、最終的な注文を表示します。  
  
##  <a name="step3"></a>実行し、ビジネス プロセス管理ソリューションの検証  
  
#### <a name="to-submit-a-new-order-and-validate-the-solution"></a>新しい注文の送信とソリューションの検証  
  
1.  Internet Explorer での**アドレス**ボックスには次のようにカスタマー サービス Web アプリケーションの URL を入力します。  
  
    -   `http://localhost/CSRWebApp/CSRMainForm.aspx`  
  
2.  **Southridge Video Customer Service Rep Order Entry Form**  ページで、次の表に、新しい注文を入力してをクリックして**注文を送信します。**  
  
    |エントリ|値|  
    |-----------|-----------|  
    |Customer ID|1|  
    |Order ID|1|  
    |Sequence Number|1|  
    |Service Type Code|New Standard Service|  
  
3.  **Southridge Video Customer Service Rep Order Entry Form**  ページの結果メッセージ次のようにします。  
  
     **顧客 ID 1 Order ID 1 のシーケンス番号 1**  
  
4.  Cable Provisioning System の実行中にコマンド プロンプトから入力した注文を検証します。 送信された注文について、分析およびアクティブ化を終え、完了したことを示すメッセージがアプリケーションから表示されます。  
  
5.  Facilities Simulator でメッセージの合計数が 1 つ増えたことを確認します。  
  
#### <a name="to-submit-a-duplicate-while-the-biztalk-server-is-processing-the-original-order"></a>BizTalk Server が元の注文を処理している間に重複する注文を送信します。  
  
1.  Internet Explorer での**アドレス**ボックスには次のようにカスタマー サービス Web アプリケーションの URL を入力します。  
  
    -   `http://localhost/CSRWebApp/CSRMainForm.aspx`  
  
2.  FacilitiesSimulator で、をクリックして**停止**です。 これで送信された注文の処理が停止します。  
  
3.  **Southridge Video Customer Service Rep Order Entry Form**  ページで、次の表に、新しい注文を入力してをクリックして**Submit Order**注文の重複をシミュレートするには、2 回クリックします。  
  
    |エントリ|値|  
    |-----------|-----------|  
    |Customer ID|2|  
    |Order ID|1|  
    |Sequence Number|1|  
    |Service Type Code|New Standard Service|  
  
4.  **Southridge Video Customer Service Rep Order Entry Form**  ページの結果メッセージ次のようにします。  
  
     **顧客 ID 2 Order ID 1 のシーケンス番号 1**  
  
5.  FacilitiesSimulator で、をクリックして**開始**です。 Facilities Simulator からの応答を待っているオーケストレーションが処理を再開します。 1 番目の注文が処理されている間に重複する注文が送信された場合のシミュレーションになります。  
  
6.  Cable Provisioning System を実行しているコマンド プロンプトで送信した注文を確認します。 最初の注文のみについて、分析およびアクティブ化を終え、完了したことを示すメッセージがアプリケーションから表示されます。  
  
7.  Operation Server を実行しているコマンド プロンプトで重複注文に対するエラー メッセージを確認します。  
  
#### <a name="to-update-an-order-while-the-biztalk-server-is-processing-the-order"></a>BizTalk Server が処理中の注文を更新する方法  
  
1.  Internet Explorer での**アドレス**ボックスには次のようにカスタマー サービス Web アプリケーションの URL を入力します。  
  
    -   `http://localhost/CSRWebApp/CSRMainForm.aspx`  
  
2.  FacilitiesSimulator で、をクリックして**停止**です。  
  
3.  **Southridge Video Customer Service Rep Order Entry Form**  ページで、次の表に、新しい注文を入力してをクリックして**Submit Order**です。  
  
    |エントリ|値|  
    |-----------|-----------|  
    |Customer ID|3|  
    |Order ID|1|  
    |Sequence Number|1|  
    |Service Type Code|New Standard Service|  
  
4.  **Southridge Video Customer Service Rep Order Entry Form**  ページの結果メッセージ次のようにします。  
  
     **顧客 ID 3 Order ID 1 のシーケンス番号 1**  
  
5.  **Southridge Video Customer Service Rep Order Entry Form**  ページで、次の表に、更新された注文を入力してをクリックして**Submit Order**です。  
  
    |エントリ|値|  
    |-----------|-----------|  
    |Customer ID|3|  
    |Order ID|1|  
    |Sequence Number|2|  
    |Service Type Code|New Deluxe Service|  
  
6.  **Southridge Video Customer Service Rep Order Entry Form**  ページの結果メッセージ次のようにします。  
  
     **顧客 ID 3 Order ID 1 のシーケンス番号 2**  
  
7.  FacilitiesSimulator で、をクリックして**開始**  
  
8.  結果メッセージを確認して、 **Southridge Video Customer Service Rep Order Entry Form**ページ。  
  
9. Cable Provisioning System を実行しているコマンド プロンプトで送信した注文を確認します。 2 つの注文を分析し、更新された注文のみをアクティブ化し完了したことを示すメッセージが、アプリケーションから表示されます。  
  
10. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、 をクリックして**イベント ビューアー**と、新しい警告を確認し、元の注文が中断されました。  
  
11. Operation Server を実行しているコマンド プロンプトでルーティング エラーのエラーメッセージを確認します。  
  
    > [!NOTE]
    >  イベント ログと Operation Server にエラーが表示されます。 ビジネス プロセスのインスタンスがより高いシーケンス番号を持つ新しい注文によって中断され終了したため、Facilities System からの応答メッセージはビジネス プロセスのインスタンスへの関連付けを失っています。 したがって、応答メッセージは孤立し Operation Server に回送されます。 注文の更新の詳細については、次を参照してください。[注文プロセス マネージャでのフロー](../core/order-flow-through-the-process-manager.md)です。  
  
12. メモ帳で %SystemDrive%:\BPMTest\HistoryUpdate-SP フォルダーで、最新のメッセージを開きます。 確認**CustName**、 **OrderNum**、 **OrderSeqNum**、および**ステータス**フィールドを新しい順序のメッセージが作成されているかどうかに、**ステータス**フィールドは**完了**です。  
  
#### <a name="to-terminate-an-order-while-the-biztalk-server-is-processing-the-order"></a>BizTalk Server が処理中の注文を終了する方法  
  
1.  Internet Explorer での**アドレス**ボックスには次のようにカスタマー サービス Web アプリケーションの URL を入力します。  
  
    -   `http://localhost/CSRWebApp/CSRMainForm.aspx`  
  
2.  FacilitiesSimulator で、をクリックして**停止**です。  
  
3.  **Southridge Video Customer Service Rep Order Entry Form**  ページで、次の表に、新しい注文を入力してをクリックして**Submit Order**です。  
  
    |エントリ|値|  
    |-----------|-----------|  
    |Customer ID|4|  
    |Order ID|1|  
    |Sequence Number|1|  
    |Service Type Code|New Standard Service|  
  
4.  **Southridge Video Customer Service Rep Order Entry Form**  ページの結果メッセージ次のようにします。  
  
     **顧客 ID 4 Order ID 1 のシーケンス番号 1**  
  
5.  **Southridge Video Customer Service Rep Order Entry Form** ] ページで [ **Terminate Order**です。  
  
6.  **Southridge Video Customer Service Rep Order Entry Form**  ページの結果メッセージ次のようにします。  
  
     **顧客 ID 4 Order ID 1 のシーケンス番号 1**  
  
7.  FacilitiesSimulator で、をクリックして**開始**です。  
  
8.  Cable Provisioning System を実行しているコマンド プロンプトで送信した注文を確認します。 注文の分析およびアクティブ化のみを行ったことを示すメッセージが、アプリケーションから表示されます。  
  
9. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、 をクリックして**イベント ビューアー**と、新しい警告を確認し、順序は、ユーザーによって終了されました。  
  
    > [!NOTE]
    >  注文終了の詳細については、次を参照してください。[注文プロセス マネージャでのフロー](../core/order-flow-through-the-process-manager.md)です。  
  
10. Operation Server を実行しているコマンド プロンプトでルーティング エラーのエラーメッセージを確認します。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションをインストールする前に](../core/before-installing-the-business-process-management-solution.md)   
 [ビジネス プロセス管理ソリューションの開発者のコンピュータ設定](../core/developer-machine-setup-for-the-business-process-management-solution.md)
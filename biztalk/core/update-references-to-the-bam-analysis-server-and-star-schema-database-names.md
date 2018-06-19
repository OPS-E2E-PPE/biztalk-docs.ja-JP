---
title: BAM Analysis Server およびスター スキーマ データベース名への参照を更新する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- restoring [BAM], Analysis database
- Analysis database [BAM], restoring
- restoring, BAM
- restoring [BAM], updating references
- BAM, restoring
- Analysis database [BAM], updating references
ms.assetid: cbe5e500-0a25-427e-bc76-1eae24b3e5f3
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4f98129efd2f7c027ecb6c3e69d494ff2e96e8b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287450"
---
# <a name="how-to-update-references-to-the-bam-analysis-server-and-star-schema-database-names"></a>BAM Analysis Server およびスター スキーマ データベース名への参照を更新する方法
BAMAnalysis および BAMStarSchema データベースがバックアップされていれば、システムまたはデータに障害が発生したときには、別のコンピューターにバックアップを復元でき、さらにその名前を変更することができます。  
  
 BAM Analysis Server または BAMStarSchema データベースを復元する」の手順を実行[、データベースを復元する方法](../core/how-to-restore-your-databases.md)です。 さらに、BAM データ変換サービス (DTS) パッケージを新しいサーバー名およびデータベース名に更新する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 メンバーとしてログオンする必要があります、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators グループにこの手順を実行します。  
  
### <a name="to-update-references-to-the-bam-analysis-server-and-bam-star-schema-database-name-sql-server-2008-r2sp1"></a>BAM Analysis Server および BAM スター スキーマ データベース名への参照を更新するには (SQL Server 2008 R2/SP1)  
  
1.  すべての BAM キューブ更新およびデータ保守 SSIS パッケージを停止するか、BAMAnalysis または BAMStarSchema データベースの復元が完了するまで実行されないように措置を講じます。  
  
2.  BizTalk アプリケーション サービス (BAM イベント バス サービスを含む) を停止することにより、データベースにデータがそれ以上インポートされないようにします。  
  
    1.  をクリックして**開始**、 をクリックして**実行**、し、入力**services.msc**です。  
  
    2.  右クリックし、 **BizTalk Service BizTalk Group: BizTalkServerApplication**サービスを提供し、クリックして**停止**です。  
  
    > [!TIP]
    >  サービスを停止する別の方法は、使用する、 **Net Stop**コマンド。 Net Stop を使用して BizTalk サービスを停止するを開き、**コマンド プロンプト**(Windows Server 2008 または Windows Vista を使用して場合、は、コマンド プロンプトを使用して、起動**管理者として実行**) と入力します: `Net Stop BTSSvc$BizTalkServerApplication`キーを押します**Enter**です。  
  
3.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 R2**、クリックして**SQL Server Business Intelligence Development Studio**.  
  
4.  SQL Server Business Intelligence Development Studio で、プロジェクトを新規作成します。 をクリックして**ファイル**、 をクリックして**新規**、クリックして**プロジェクト**です。  
  
5.  **新しいプロジェクト**ダイアログ ボックスで、**テンプレート**、 をクリックして**Integration Services プロジェクト**、クリックして**ok**です。  
  
6.  **Integration Services プロジェクト**ダイアログ ボックスで、**ソリューション エクスプ ローラー**を右クリックして**SSIS パッケージ**、順にクリック**の既存パッケージの追加**.  
  
7.  **既存のパッケージのコピーを追加** ダイアログ ボックスで、**サーバー**ドロップダウン リスト ボックスで、BAM_AN パッケージを含むサーバーを選択します。  
  
8.  **パッケージ パス**、省略記号ボタンをクリックします。  
  
9. **SSIS パッケージ** ダイアログ ボックスで BAM_AN パッケージを選択して、をクリックして**ok**、順にクリック**OK**です。  
  
     これで、パッケージがソリューション エクスプローラにリストされました。  
  
10. **ソリューション エクスプ ローラー**、BAM_AN パッケージをダブルクリックします。 **接続マネージャー**、データベース番号 3 (MSDB データベース) をダブルクリックします。  
  
11. **接続マネージャー**  ダイアログ ボックスで、**サーバー名**ボックスで、MSDB サーバーの名前を入力し、をクリックして**OK**です。  
  
12. クリックして、**パッケージ エクスプ ローラー**  タブをダブルクリックして、**変数**フォルダー、およびプライマリ インポート サーバー名と主キーの値をインポートし、更新プログラムのデータベース名。  
  
13. をクリックして**ファイル**、クリックして**すべてを保存**です。  
  
14. **Microsoft SQL Server Management Studio**をクリックして**接続**です。  
  
15. をクリックして**Integration Services**をダブルクリックして**格納されたパッケージ**、 をクリックして**MSDB**BAM_AN パッケージを右クリックし、クリックして**パッケージのインポート**.  
  
16. **パッケージのインポート**ダイアログ ボックスで、**パッケージの場所****ファイル システム**です。  
  
17. **パッケージ パス**、保存したプロジェクトに移動し、BAM_AN を選択\*.dtsx ファイル、およびクリック**開く**です。  
  
18. 内をクリックし、**パッケージ名**ボックスに自動的に入力します。  
  
19. をクリックして **[ok]**、順にクリック**はい**を上書きします。  
  
20. BizTalk Server アプリケーション サービスを再起動します。  
  
    1.  をクリックして**開始**、 をクリックして**実行**、し、入力**services.msc**です。  
  
    2.  右クリックし、 **BizTalk Service BizTalk Group: BizTalkServerApplication**サービスを提供し、クリックして**開始**です。  
  
21. すべての BAM キューブ更新およびデータ保守 SSIS パッケージを有効にします。  
  
## <a name="see-also"></a>参照  
 [バックアップおよび BAM を復元します。](../core/backing-up-and-restoring-bam.md)
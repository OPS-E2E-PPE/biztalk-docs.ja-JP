---
title: BAM アーカイブ データベース名への参照を更新する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Archive database [BAM], restoring
- restoring, BAM
- restoring [BAM], Archive database
- restoring [BAM], updating references
- Archive database [BAM], updating references
- BAM, restoring
ms.assetid: a0b8543e-6fc1-412e-b74e-683352d9c49e
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3fcba19a3852a70c402276fed1ca56ea1b8f0c4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333713"
---
# <a name="how-to-update-references-to-the-bam-archive-database-name"></a>BAM アーカイブ データベース名への参照を更新する方法
BAMArchive データベースがバックアップされていれば、システムまたはデータの障害が発生したときに、バックアップを復元し、さらに、その名前を変更することができます。  
  
 BAMArchive データベースを復元する」の手順を実行[、データベースを復元する方法](../core/how-to-restore-your-databases.md)です。 これらの手順を実行したうえで、次の手順を実行します (詳細な手順については後述)。  
  
-   BAM DTS パッケージを、新しいサーバー名およびデータベース名で更新します。  
  
## <a name="prerequisites"></a>前提条件  
 メンバーとしてログオンする必要があります、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators グループにこの手順を実行します。  
  
### <a name="to-update-references-to-the-bam-archive-database-name-sql-server-2008-r2sp1"></a>BAM アーカイブ データベース名への参照を更新するには (SQL Server 2008 R2/SP1)  
  
1.  すべての BAM キューブ更新およびデータ保守 DTS パッケージを停止するか、BAMArchive データベースの復元が完了するまで実行されないように措置を講じます。  
  
2.  (を BAM イベント バス サービスを含む)、BizTalk アプリケーション サービスを停止するため、データベースに多くのデータをインポートするのには試行されません。  
  
    1.  をクリックして**開始**、 をクリックして**実行**、し、入力**services.msc**です。  
  
    2.  右クリックし、 **BizTalk Service BizTalk Group:[Biztalkserverapplication]** サービスをクリックして**停止**します。  
  
3.  をクリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft SQL Server 2008 R2**、クリックして**SQL Server Business Intelligence Development Studio**.  
  
4.  SQL Server Business Intelligence Development Studio で、プロジェクトを新規作成します。 をクリックして**ファイル**、 をクリックして**新規**、クリックして**プロジェクト**です。  
  
5.  **新しいプロジェクト**ダイアログ ボックスで、**テンプレート**、 をクリックして**Integration Services プロジェクト**、クリックして**ok**です。  
  
6.  **Integration Services プロジェクト**ダイアログ ボックスで、**ソリューション エクスプ ローラー**を右クリックして**SSIS パッケージ**、順にクリック**の既存パッケージの追加**.  
  
7.  **既存のパッケージのコピーを追加** ダイアログ ボックスで、**サーバー**ドロップダウン リスト ボックスで、BAM_DM パッケージを含むサーバーを選択します。  
  
8.  **パッケージ パス**、省略記号ボタンをクリックします。  
  
9. **SSIS パッケージ** ダイアログ ボックスで、BAM_DM パッケージを選択して、をクリックして**ok**、順にクリック**OK**です。  
  
     これで、パッケージがソリューション エクスプローラにリストされました。  
  
10. **ソリューション エクスプ ローラー**、BAM_DM パッケージをダブルクリックします。 **接続マネージャー**、データベース番号 3 (MSDB データベース) をダブルクリックします。  
  
11. **接続マネージャー**  ダイアログ ボックスで、**サーバー名**ボックスで、MSDB サーバーの名前を入力し、をクリックして**OK**です。  
  
12. クリックして、**パッケージ エクスプ ローラー**  タブをダブルクリックして、**変数**フォルダー、およびプライマリ インポート サーバー名と主キーの値をインポートし、更新プログラムのデータベース名。  
  
13. をクリックして**ファイル**、クリックして**すべてを保存**です。  
  
14. **Microsoft SQL Server Management Studio**をクリックして**接続**です。  
  
15. をクリックして**Integration Services**をダブルクリックして**格納されたパッケージ**、 をクリックして**MSDB**、BAM_DM パッケージを右クリックし、クリックして**パッケージのインポート**.  
  
16. **パッケージのインポート**ダイアログ ボックスで、**パッケージの場所** **ファイル システム**です。  
  
17. **パッケージのパス**、保存したプロジェクトに移動し、選択、BAM_DM\*.dtsx ファイル、およびクリック**開く**です。  
  
18. 内をクリックし、**パッケージ名**ボックスに自動的に入力します。  
  
19. をクリックして **[ok]** 、順にクリック**はい**を上書きします。  
  
20. BizTalk Server アプリケーション サービスを再起動します。  
  
    1.  をクリックして**開始**、 をクリックして**実行**、し、入力**services.msc**です。  
  
    2.  右クリックし、 **BizTalk Service BizTalk Group:[Biztalkserverapplication]** サービスをクリックして**開始**します。  
  
21. すべての BAM キューブ更新およびデータ保守 SSIS パッケージを有効にします。  
  
## <a name="see-also"></a>参照  
 [BAM のバックアップと復元](../core/backing-up-and-restoring-bam.md)
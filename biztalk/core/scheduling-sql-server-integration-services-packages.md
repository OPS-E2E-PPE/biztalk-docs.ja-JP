---
title: スケジュール SQL Server Integration Services パッケージ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 037ae2cf-c352-4823-95df-9a723f2b5a81
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8cbdb19b5b1f8ae7d800742c0dd211e772f98c7c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308004"
---
# <a name="scheduling-sql-server-integration-services-packages"></a>スケジュール SQL Server Integration Services パッケージ
ユーザーは、オンライン分析処理 (OLAP) キューブに格納されたデータに基づいている BAM ビューを作成します。 キューブ更新 Integration Services パッケージは、OLAP ビューに正しいデータが反映されるように、キューブ内のデータを更新します。  
  
 OLAP ビューを利用するのに少なくとも 1 回は、このパッケージを実行する必要があります。 継続的なメンテナンスは、パッケージを定期的に実行をスケジュールする必要があります。  
  
> [!IMPORTANT]
>  BAM スター スキーマ データベースを復元または停止するかどうかは[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]キューブ更新 Integration Services パッケージを実行する前にデータ ソースを更新する必要があります[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]分析マネージャーまたはパッケージを実行する前に、OLAP サービスを再起動します正常にします。  
  
 1 回または一定の間隔では、特定の時点で実行する保存されたパッケージをスケジュールすることができます。 以下に例を示します。  
  
- 毎日の午前 0 時です。  
  
- 毎週日曜日 06:00 です。  
  
- 月の初日または最終日。  
  
  スケジュールされたパッケージによって実行されます[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]をジョブとして。  
  
  実行する方法についての[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、パッケージを参照してください[ http://go.microsoft.com/fwlink/?LinkId=125738](http://go.microsoft.com/fwlink/?LinkId=125738)します。  
  
> [!NOTE]
>  既定では、アーカイブとキューブ作成の BAM SSIS パッケージのログ記録は有効になってし、msdb データベースに格納されます。 超過、BAM アクティビティの数が多いによる SSIS イベント ログ データの重要なボリュームがあります。 または頻繁に実行して BAM の SSIS パッケージを所有しています。 これを解決するには、これらのエントリは主にデバッグに使用されるため、古いログ エントリを削除できます。  
  
## <a name="prerequisites"></a>前提条件  
 これらの手順を実行する BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-run-the-cube-update-integration-services-package"></a>キューブ更新 Integration Services パッケージを実行するには  
  
1.  クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 SP1**または**Microsoft SQL Server 2008 R2**順にクリックします**SQL Server Management Studio**します。  
  
2.  **サーバーへの接続** ダイアログ ボックスで、**サーバーの種類**ドロップダウン リストで、 **Integration Services**します。  
  
3.  **サーバー名**ドロップダウン リストで、パッケージを実行しているサーバーの名前を選択します。  
  
4.  **認証**ドロップダウン リストで、サーバーへの接続に使用する認証の種類を選択します。  
  
5.  必要に応じて、ユーザー名とパスワードを入力します。  
  
6.  **[接続]** をクリックします。  
  
7.  コンソール ツリーで、展開**Integration Services**、展開**格納されたパッケージ**、 をクリックし、 **MSDB**します。  
  
8.  右クリックし、 **bam_an _\<ビュー名\>** パッケージ化、およびクリックして**パッケージの実行**します。  
  
### <a name="to-run-the-maintaining-bam-data-integration-services-package"></a>BAM データの管理 Integration Services パッケージを実行するには  
  
1.  クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 SP1**または**Microsoft SQL Server 2008 R2**順にクリックします**SQL Server Management Studio**します。  
  
2.  **サーバーへの接続** ダイアログ ボックスで、**サーバーの種類**ドロップダウン リストで、 **Integration Services**します。  
  
3.  **サーバー名**ドロップダウン リストで、パッケージを実行しているサーバーの名前を選択します。  
  
4.  **認証**ドロップダウン リストで、サーバーへの接続に使用する認証の種類を選択します。  
  
5.  必要に応じて、ユーザー名とパスワードを入力します。  
  
6.  **[接続]** をクリックします。  
  
7.  コンソール ツリーで、展開**Integration Services**、展開**格納されたパッケージ**、 をクリックし、 **MSDB**します。  
  
8.  右クリックし、 **bam_dm _\<アクティビティ名\>** パッケージ化、およびクリックして**パッケージの実行**します。  
  
### <a name="to-schedule-the-packages-to-run-regularly"></a>定期的に実行するパッケージをスケジュールするには  
  
1.  クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 SP1**または**Microsoft SQL Server 2008 R2**順にクリックします**SQL Server Management Studio**します。  
  
2.  **サーバーへの接続** ダイアログ ボックスで、**サーバーの種類**ドロップダウン リストで、**データベース エンジン**します。  
  
3.  **サーバー名**ドロップダウン リストで、パッケージを実行しているサーバーの名前を選択します。  
  
4.  **認証**ドロップダウン リストで、サーバーへの接続に使用する認証の種類を選択します。  
  
5.  必要に応じて、ユーザー名とパスワードを入力します。  
  
6.  **[接続]** をクリックします。  
  
7.  コンソール ツリーで、サーバーを展開し、選択**SQL Server エージェント**します。  
  
8.  場合**SQL Server エージェント**は右クリックし、無効になっています。 **SQL Server エージェント**、し、**開始**します。  
  
9. 右クリック**SQL Server エージェント**、選び**新しいジョブ**します。  
  
10. **新しいジョブ**ダイアログ ボックスで、ジョブの名前を入力、**名前**テキスト ボックス。  
  
11. **ページの選択**ウィンドウで、をクリックして**手順**、順にクリックします**新規**します。 開き、**新しいジョブ ステップ** ダイアログ ボックス。  
  
12. **ステップ名**テキスト ボックスに、ステップの識別名を入力します。  
  
13. **型**ドロップダウン リストで、 **SQL Server Integration Services パッケージ**し、**パッケージ ソース**ドロップダウン リストで、 **SSIS パッケージ ストア**.  
  
14. **Server**ドロップダウン リストで、ジョブを実行しているサーバーを選択します。  
  
15. ファイル セレクター ボタンをクリックして、**パッケージ**テキスト ボックスに、スケジュールを設定するパッケージを選択します (いずれか、 **bam_dm _\<アクティビティ名\>** または**bam_an _\<ビュー名\>** パッケージ)、順にクリックします**OK**します。  
  
16. **ページの選択**ウィンドウで、をクリックして**スケジュール**、順にクリックします**新規**します。 開き、**新しいジョブ スケジュール** ダイアログ ボックス。  
  
17. **名前**テキスト ボックスに、スケジュールの名前を入力します。  
  
18. 頻度のフィールドを使用してスケジュールを作成します。  
  
19. **[OK]** をクリックしてジョブを保存します。  
  
    > [!NOTE]
    >  SQL Server の既定以外のインスタンスに BAM を構成する場合、BAM_AN_POCube DTSPackage は取得しませんスケジュール/実行正確に。 継続して実行するパッケージを許可する構成ファイルを変更する必要があります。 詳細については、ある「変更の内容の構成ファイル」セクションを参照してください[ http://go.microsoft.com/fwlink/?LinkId=196768](http://go.microsoft.com/fwlink/?LinkId=196768)します。  
  
## <a name="see-also"></a>参照  
 [BAM データベースの管理](../core/managing-bam-databases.md)
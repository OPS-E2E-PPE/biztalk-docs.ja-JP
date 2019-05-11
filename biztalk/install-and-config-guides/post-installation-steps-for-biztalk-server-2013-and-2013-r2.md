---
title: BizTalk Server 2013 および 2013 R2 のインストール後のステップ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c3b47843-9da5-4144-8b84-135494b8ab43
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cae3a9705e776d8f01e5659341378240eb2fcde1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394001"
---
# <a name="post-installation-steps-for-biztalk-server-2013-and-2013-r2"></a>BizTalk Server 2013 および 2003 R2 のインストール後の手順
  
##  <a name="BKMK_NamedPipes"></a> 有効にする TCP/IP および名前付きパイプ  
  
1. **[SQL Server 構成マネージャー]** を開きます。  
  
2. 展開**SQL Server ネットワーク構成**、選び**MSSQLSERVER のプロトコル**します。  
  
3. いることを確認両方**TCP/IP**と**名前付きパイプ**を有効にします。 有効な場合は、次の手順に進みます。  
  
    有効になっていない: 場合  
  
   -   プロトコルを右クリックし、**を有効にする**します。  
  
   -   必要に応じて、他のプロトコルを有効にするを繰り返します。  
  
   -   左側のウィンドウで次のようにクリックします。 **SQL Server サービス**します。  
  
   -   右側のウィンドウで右クリックして**SQL Server (MSSQLSERVER)**、 をクリック**停止**します。  
  
   -   右クリックし、サービスが停止したら、 **SQL Server (MSSQLSERVER)**、 をクリック**開始**します。  
  
   > [!IMPORTANT]
   >  使用する場合[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]、 **NS$ BAMAlerts**サービスを停止する可能性があります。 サービスを再起動します。  
  
4. 閉じる、 **Configuration Manager**します。  
  
##  <a name="BKMK_DTC"></a> ローカル ホスト サーバー上の DTC を有効にします。  
  
1. コンポーネント サービスを開きます。  
  
    **[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]**:Windows の選択 ボタン、および種類**コンポーネント サービス**します。 結果ウィンドウで次のように選択します。**コンポーネント サービス**します。  
  
    **Windows 8.1**:Windows の選択 ボタン、および種類**管理ツール**します。 [検索] ウィンドウで、次のように選択します。**設定**します。 結果ウィンドウで次のようにクリックします。**管理ツール**します。 ダブルクリック**コンポーネント サービス**します。  
  
    **Windows 7 SP1**:**[スタート]** を選択します。 **検索**テキスト ボックスに「**コンポーネント サービス** をクリックして開きます。  
  
2. コンソール ツリーで、**[コンポーネント サービス]**、**[コンピューター]**、**[マイ コンピューター]**、**[分散トランザクション コーディネーター]** の順に展開し、**[ローカル DTC]** をクリックします。  
  
3. 右クリック**ローカル DTC**選択**プロパティ**を開く、**ローカル DTC のプロパティ**します。  
  
4. **[セキュリティ]** タブをクリックします。  
  
5. 次のオプションがオンになってを確認します。  
  
   - **ネットワーク DTC アクセス**  
  
   - **受信を許可する**  
  
   - **送信を許可する**  
  
   - **認証を必要としない**  
  
     追加の設定が必要な場合、「[MSDTC を使用した問題のトラブルシューティング](../core/troubleshooting-problems-with-msdtc.md)」を参照してください。  
  
6. 選択**OK**を閉じる、**ローカル DTC のプロパティ** ダイアログ ボックス。 求められた場合は、MSDTC サービスを再起動します。  
  
7. **[コンポーネント サービス]** を閉じます。  
  
##  <a name="BKMK_Firewall"></a> DTC を有効にするための Windows ファイアウォールを構成します。  
  
1. 開いている**Windows ファイアウォール**:  
  
    **[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]**:Windows をクリックします ボタン、および種類**Windows ファイアウォール**します。 結果ウィンドウで次のようにクリックします。 **Windows ファイアウォール**します。  
  
    **Windows 8.1**:Windows をクリックします ボタン、および種類**Windows ファイアウォール**します。 [検索] ウィンドウで、次のようにクリックします。**設定**します。 結果ウィンドウで次のようにクリックします。 **Windows ファイアウォール**します。  
  
    **Windows 7 SP1**:クリックして**開始**します。 **検索**テキスト ボックスに「 **Windows ファイアウォール** をクリックして開きます。  
  
2. クリックして**詳細設定** をクリック**受信の規則**します。  
  
3. **受信の規則**ウィンドウで、右クリックして**分散トランザクション コーディネーター** \* (必要に応じて)、順にクリックします**規則の有効化**します。  
  
4. クリックして**送信の規則**します。  
  
5. **送信の規則**ウィンドウで、右クリックして**分散トランザクション コーディネーター** \* (必要に応じて)、順にクリックします**規則の有効化**します。  
  
6. **コントロール パネルの **、アイコンをリストに、ビューを変更しをダブルクリックします**管理ツール**します。  
  
7. ダブルクリック**サービス**します。  
  
8. 右クリックして**COM + システム アプリケーション**、 をクリックして**再起動**、し、サービスを再起動するまで待ちます。  
  
9. **[分散トランザクション コーディネーター]** サービスを右クリックして再起動します。  
  
10. **[SQL Server (MSSQLSERVER)]** サービスを右クリックして再起動します。  
  
11. **[サービス (ローカル)]** を閉じ、**[管理ツール]** を閉じます。  
  
##  <a name="BKMK_SQLAgent"></a> SQL エージェント ジョブを構成します。  
  
|            [ジョブ]            |                                                                                                                                                                                                                                                                                                                     説明                                                                                                                                                                                                                                                                                                                     |                                                                                                                                                                                                 理由を構成します。                                                                                                                                                                                                  |
|---------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **BizTalk Server をバックアップします。** |                                     この SQL エージェント ジョブのバックアップ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースとログ ファイル。 ジョブを構成するときは、頻度とファイルの場所などのパラメーターを指定します。<br /><br /> 次のリンクでは、SQL エージェント ジョブとそのパラメーターについて説明します。<br /><br /> [バックアップおよび BizTalk Server データベースを復元します。](http://msdn.microsoft.com/library/aa561125\(v=bts.80\).aspx)<br /><br /> [BizTalk Server のバックアップ ジョブを構成する方法](http://msdn.microsoft.com/library/aa546765\(v=bts.80\).aspx)                                      | この SQL エージェント ジョブには、パフォーマンスを向上させることができます、トランザクション ログも切り捨てます。<br /><br /> **Backup BizTalk Server**ジョブが削除または古いなど、バックアップ ファイルを削除してされません。 バックアップ ファイルを削除するを参照してください["Backup BizTalk Server"ジョブ失敗時に、バックアップ ファイルは、Microsoft BizTalk Server データベース サーバーでの時間の経過と共に蓄積](http://support.microsoft.com/kb/982546)します。 |
| **DTA Purge and Archive** | この SQL エージェント ジョブの切り捨てし、アーカイブ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]追跡データベース (BizTalkDTADb)。 完了したインスタンスを保持する日数などのパラメーターを決定するジョブを構成するときに、すべてのデータを保持する日数。<br /><br /> 次のリンクでは、SQL エージェント ジョブとそのパラメーターについて説明します。<br /><br /> [BizTalk 追跡データベースのアーカイブおよび削除](http://msdn.microsoft.com/library/aa560754\(v=bts.80\).aspx)<br /><br /> [構成の DTA Purge and Archive ジョブをする方法](http://msdn.microsoft.com/library/aa558715\(v=bts.80\).aspx) |              この SQL エージェント ジョブは、追跡ホストの管理と追跡イベントを削除して、パフォーマンスを直接影響します。<br /><br /> パフォーマンスに関するトピックは次のとおりです。<br /><br /> [保守および BizTalk Server データベースをトラブルシューティングする方法](http://support.microsoft.com/kb/952555)<br /><br /> [追跡データベースのサイズに関するガイドライン](http://msdn.microsoft.com/library/aa559162\(v=bts.80\).aspx)              |
  
 **その他**  
  
- ときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]がインストールされている場合、いくつかの SQL エージェント ジョブが自動的に作成、ように、次のリンクで説明されています。  
  
   [BizTalk Server で SQL Server エージェント ジョブの説明](http://support.microsoft.com/kb/919776)  
  
   [データベース構造とジョブ](http://msdn.microsoft.com/library/aa561960\(v=bts.80\).aspx)  
  
##  <a name="BKMK_InstallCU"></a> 累積的な更新プログラムをインストールします。  
 インストールした後[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、いずれかがインストール[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Windows 更新プログラムに累積的更新プログラムが一覧表示します。 利用可能なサービス パックおよび累積的な更新プログラムの一覧は、[KB 文書 2555976](http://support.microsoft.com/kb/2555976) をご覧ください。  
  
## <a name="next"></a>Next  
[BizTalk Server の構成](../install-and-config-guides/configure-biztalk-server.md)
  
## <a name="see-also"></a>参照  
 [付録 a:サイレント インストール](../install-and-config-guides/appendix-a-silent-installation.md) 
 
[付録 b:Microsoft SharePoint アダプターをインストールします。](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)  

[付録 c:再頒布可能 CAB ファイル](../install-and-config-guides/appendix-c-redistributable-cab-files.md)  

[付録 d:SMTP サーバーを作成します。](../install-and-config-guides/appendix-d-create-the-smtp-server.md)

[アンインストールし、それを削除する BizTalk Server の構成を解除](../install-and-config-guides/uninstall-and-unconfigure-biztalk-server-to-remove-it.md)

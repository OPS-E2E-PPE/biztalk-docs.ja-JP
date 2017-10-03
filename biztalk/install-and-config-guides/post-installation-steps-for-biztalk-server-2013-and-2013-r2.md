---
title: "BizTalk Server 2013 および 2013 R2 のインストール後の手順 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c3b47843-9da5-4144-8b84-135494b8ab43
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b86d8c4c1e1a22dad349c2cc8c2be5ca4b206b2c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="post-installation-steps-for-biztalk-server-2013-and-2013-r2"></a>BizTalk Server 2013 および 2003 R2 のインストール後の手順
  
##  <a name="BKMK_NamedPipes"></a> TCP/IP と名前付きパイプの有効化  
  
1.  **[SQL Server 構成マネージャー]** を開きます。  
  
2.  **[SQL Server ネットワークの構成]** を展開し、**[MSSQLSERVER のプロトコル]** を選択します。  
  
4.  **[TCP/IP]** と **[名前付きパイプ]** の両方が有効であることを確認します。 有効である場合は、次の手順に進みます。  
  
     有効でない場合:  
  
    -   プロトコルを右クリックして **[有効]** をクリックします。  
  
    -   他方のプロトコルも、有効になっていない場合は同じ手順を実行して有効にします。  
  
    -   左側のウィンドウで、**[SQL Server のサービス]** をクリックします。  
  
    -   右側のウィンドウで、**[SQL Server (MSSQLSERVER)]** を右クリックして **[停止]** をクリックします。  
  
    -   サービスが停止したら、**[SQL Server (MSSQLSERVER)]** を右クリックして **[開始]** をクリックします。  
  
    > [!IMPORTANT]
    >  [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] を使用している場合は、**NS$BAMAlerts** サービスが停止する可能性があります。 サービスを再起動します。  
  
5.  **構成マネージャー**を閉じます。  
  
##  <a name="BKMK_DTC"></a> ローカル ホスト サーバー上の DTC の有効化  
  
1.  [コンポーネント サービス] を開きます。  
  
     **[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]**: Windows ボタンを選択して「**コンポーネント サービス**」と入力します。 [検索結果] ウィンドウで、[**コンポーネント サービス**] をクリックします。  
  
     **Windows 8.1**: Windows ボタンを選択して「**管理ツール**」と入力します。 [検索] ウィンドウで、[**設定**] を選択します。 [検索結果] ウィンドウで、**[管理ツール]** をクリックします。 **[コンポーネント サービス]** をダブルクリックします。  
  
     **Windows 7 SP1**: **[スタート]** を選択します。 **[検索]** テキスト ボックスに「**コンポーネント サービス**」と入力し、クリックして開きます。  
  
2.  コンソール ツリーで、**[コンポーネント サービス]**、**[コンピューター]**、**[マイ コンピューター]**、**[分散トランザクション コーディネーター]** の順に展開し、**[ローカル DTC]** をクリックします。  
  
3.  **[ローカル DTC]** を右クリックし、**[プロパティ]** を選択して、**[ローカル DTC のプロパティ]** を開きます。  
  
4.  **[セキュリティ]** タブをクリックします。  
  
5.  次のオプションがオンになっていることを確認します。  
  
    -   **ネットワーク DTC アクセス**  
  
    -   **受信を許可する**  
  
    -   **送信を許可する**  
  
    -   **認証を必要としない**  
  
     追加の設定が必要な場合、「[MSDTC を使用した問題のトラブルシューティング](../core/troubleshooting-problems-with-msdtc.md)」を参照してください。  
  
6.  **[OK]** を選択して **[ローカル DTC のプロパティ]** ダイアログ ボックスを閉じます。 MSDTC サービスの再起動が求められたら再起動します。  
  
7.  **[コンポーネント サービス]** を閉じます。  
  
##  <a name="BKMK_Firewall"></a> Windows ファイアウォールで DTC を有効にする  
  
1.  **[Windows ファイアウォール]** を開きます。  
  
     **[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]** : キーボードの Windows ボタンをクリックして「**Windows ファイアウォール**」と入力します。 [検索結果] ウィンドウで、**[Windows ファイアウォール]** をクリックします。  
  
     **Windows 8.1**: キーボードの Windows ボタンをクリックして「**Windows ファイアウォール**」と入力します。 [検索] ウィンドウで、**[設定]** をクリックします。 [検索結果] ウィンドウで、**[Windows ファイアウォール]** をクリックします。  
  
     **Windows 7 SP1**: **[スタート]** をクリックします。 **[検索]** テキスト ボックスに「**Windows ファイアウォール**」と入力し、クリックして開きます。  
  
2.  **[詳細設定]** をクリックして、**[受信の規則]** をクリックします。  
  
3.  **[受信の規則]** ウィンドウで、**[分散トランザクション コーディネーター]** \* を右クリックし (必要に応じて)、**[規則の有効化]** をクリックします。  
  
4.  **[送信の規則]** をクリックします。  
  
5.  **[送信の規則]** ペインで、**[分散トランザクション コーディネーター]** \* を右クリックして (必要な場合)、**[規則の有効化]** をクリックします。  
  
6.  **[コントロール パネル]** で、ビューをアイコンのリストに変更し、**[管理ツール]** をダブルクリックします。  
  
7.  **[サービス]** をダブルクリックします。  
  
8.  **[COM+ システム アプリケーション]** を右クリックし、**[再起動]** をクリックしてサービスが再起動するのを待ちます。  
  
9. **[分散トランザクション コーディネーター]** サービスを右クリックして再起動します。  
  
10. **[SQL Server (MSSQLSERVER)]** サービスを右クリックして再起動します。  
  
11. **[サービス (ローカル)]** を閉じ、**[管理ツール]** を閉じます。  
  
##  <a name="BKMK_SQLAgent"></a> SQL エージェント ジョブを構成する  
  
|[ジョブ]|説明|構成の理由|  
|---------|-----------------|-------------------|  
|**Backup BizTalk Server**|この SQL エージェント ジョブでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースとログ ファイルのバックアップを行います。 このジョブを構成するときに、回数やファイルの場所などのパラメーターを指定します。<br /><br /> 以下のリンクで、SQL エージェント ジョブとそのパラメーターについて説明しています。<br /><br /> [BizTalk Server データベースのバックアップと復元](http://msdn.microsoft.com/library/aa561125\(v=bts.80\).aspx)<br /><br /> [BizTalk Server のバックアップ ジョブを構成する方法](http://msdn.microsoft.com/library/aa546765\(v=bts.80\).aspx)|この SQL エージェント ジョブでは、トランザクション ログの切り捨ても行います。これによりパフォーマンスが向上します。<br /><br /> **Backup BizTalk Server** ジョブでは、バックアップ ファイルは削除されません。古いファイルも削除されません。 バックアップ ファイルを削除する方法については、「[Microsoft BizTalk Server データベース サーバーでバックアップ ファイルが長期的に蓄積すると、"Backup BizTalk Server" ジョブが失敗する](http://support.microsoft.com/kb/982546)」を参照してください。|  
|**DTA Purge and Archive**|この SQL エージェント ジョブでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 追跡データベース (BizTalkDTADb) の切り捨てとアーカイブを行います。 このジョブを構成するときに、完了したインスタンスを保持する日数や全データを保持する日数などのパラメーターを指定します。<br /><br /> 以下のリンクで、SQL エージェント ジョブとそのパラメーターについて説明しています。<br /><br /> [BizTalk 追跡データベースのアーカイブおよび削除](http://msdn.microsoft.com/library/aa560754\(v=bts.80\).aspx)<br /><br /> [DTA Purge and Archive ジョブを構成する方法](http://msdn.microsoft.com/library/aa558715\(v=bts.80\).aspx)|この SQL エージェント ジョブは、追跡ホストを維持し、追跡イベントを削除することで、パフォーマンスに直接影響を及ぼします。<br /><br /> 次のパフォーマンスに関するトピックがあります。<br /><br /> [BizTalk Server データベースのメンテナンスとトラブルシューティングの方法](http://support.microsoft.com/kb/952555)<br /><br /> [追跡データベースのサイズに関するガイドライン](http://msdn.microsoft.com/library/aa559162\(v=bts.80\).aspx)|  
  
 **追加情報**  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がインストールされると、次のリンクで説明するように、複数の SQL エージェント ジョブが自動的に作成されます。  
  
     [BizTalk Server での SQL Server エージェント ジョブの説明](http://support.microsoft.com/kb/919776)  
  
     [データベース構造とジョブ](http://msdn.microsoft.com/library/aa561960\(v=bts.80\).aspx)  
  
##  <a name="BKMK_InstallCU"></a> 累積的な更新プログラムのインストール  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールした後、Windows Update にあるすべての [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の累積的な更新プログラムをインストールします。 利用可能なサービス パックおよび累積的な更新プログラムの一覧は、[KB 文書 2555976](http://support.microsoft.com/kb/2555976) をご覧ください。  
  
## <a name="next"></a>Next  
[BizTalk Server の構成](../install-and-config-guides/configure-biztalk-server.md)
  
## <a name="see-also"></a>参照  
 [付録 A: サイレント インストール](../install-and-config-guides/appendix-a-silent-installation.md) 
 
[付録 B: Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)  

[付録 C: 再配布可能な CAB ファイル](../install-and-config-guides/appendix-c-redistributable-cab-files.md)  

[付録 D: SMTP サーバーの作成](../install-and-config-guides/appendix-d-create-the-smtp-server.md)

[BizTalk Server の削除 (アンインストールおよび構成の解除)](../install-and-config-guides/uninstall-and-unconfigure-biztalk-server-to-remove-it.md)

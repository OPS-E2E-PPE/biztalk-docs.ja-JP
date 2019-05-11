---
title: BAM ポータルを復旧する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2a5df99-6d03-4f1f-8540-1700d3a0b9db
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7f0d9a813b2a8cee115ba782131c2492ea14fff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335593"
---
# <a name="how-to-recover-the-bam-portal"></a>BAM ポータルを復旧する方法
ビジネス アクティビティ監視 (BAM) を使用している場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の復旧処理の一環として、BAM ポータルを復旧する必要があります。 BAM を使用していない場合は、この手順を省略できます。  
  
 BAM ポータル構成の復旧手順は、使用している IIS のバージョンによって大きく異なります。 IIS 7 の構成を復元する際に使用する**Appcmd.exe**、全体の既定の Web サイト、BAM ポータルだけでなく、構成を復元するとします。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、管理者グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-recover-the-bam-portal-configuration-iis-70"></a>BAM ポータル構成 (IIS 7.0) を復旧するには  
  
1.  実行 ダイアログ ボックスで、名前 ボックスで、以下を入力: `runas /user:` *computername*`\`*accountname* `cmd`、クリックして**OK**またはキーを押して**Enter**です。  
  
     *Accountname*ローカル コンピューターの administrators グループのメンバーである必要があります。  
  
2.  パスワードを入力メッセージが表示されたら、 *accountname*、キーを押します**Enter**です。  
  
3.  型`cd %windir%\system32\inetsrv`、キーを押します**Enter**です。  
  
4.  型`appcmd restore backup “`*バックアップ名*`”`、キーを押します**Enter**です。  
  
     *バックアップ名*を使用して以前作成したバックアップの名前を指定**Appcmd.exe**です。 このバックアップが存在する必要があります、 **%windir%\system32\inetsrv\backup**ディレクトリ。 バックアップを使用して別のコンピューターで作成されたパスワードを復元することはできません。 BAMAppPool が既定以外の id で実行するよう構成かどうか**NetworkService**アカウント、別途、次の手順で説明されているアカウントとパスワードを構成する必要があります。  
  
5.  使用して、**インターネット インフォメーション サービス (IIS) マネージャー****アプリケーション プール**で、**接続**ウィンドウです。  
  
6.  **アプリケーション プール** ウィンドウを右クリックし、 **BAMAppPool**をクリックし、**詳細設定**  
  
7.  **高度な設定**s ダイアログ ボックスで、下にスクロール、**プロセス モデル**セクションです。 クリックして、 **Identity**ボックス。 ボックスの右側に省略記号ボタンが表示されます。 クリックして、**楕円**ボタンをクリックします。  
  
8.  **アプリケーション プール Id**ダイアログ ボックスで、をクリックして、**カスタム アカウント** ボタン、をクリックして、**設定**ボタンをクリックします。  
  
9. **資格情報の設定** ダイアログ ボックスで、BAMAppPool で使用するパスワードとアカウントの名前を入力します。 として、アカウント名を入力する必要があります*コンピューター名*`\`*accountname*、または*ドメイン*`\`*accountname*. をクリックして**OK**を閉じる、**資格情報の設定**ダイアログ。  
  
10. をクリックして**OK**を閉じる、**アプリケーション プール Id**ダイアログ。  
  
11. をクリックして**OK**を閉じる、**詳細設定**ダイアログ。  
  
12. いることを確認、 **BAMAppPool**アプリケーション プールの一覧で選択されています。 **アクション**の右側のペイン、**インターネット インフォメーション サービス (IIS) マネージャー**画面で、**アプリケーション プールのタスク**をクリックして**の開始**.  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を実行しているコンピューターの回復](../core/recovering-a-computer-running-biztalk-server.md)   
 [BAM ポータル](../core/bam-portal.md)
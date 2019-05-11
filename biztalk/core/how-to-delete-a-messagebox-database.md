---
title: メッセージ ボックス データベースを削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, MessageBox database
- managing [MessageBox database], deleting
- MessageBox database, deleting
ms.assetid: 51f91fcb-8b97-4b00-9056-6d216c8ccb58
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38b5191d051e460217eccba93c0318a94357515b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338773"
---
# <a name="how-to-delete-a-messagebox-database"></a>メッセージ ボックス データベースを削除する方法
BizTalk グループからメッセージ ボックス データベースを削除するには、BizTalk 管理コンソールまたは Windows Management Instrumentation (WMI) を使用します。 メッセージ ボックス データベースは BizTalk グループから削除するか、または BizTalk Server の展開から完全に削除することができます。  
  
 たとえば、テスト目的に使用したデータベースなど、使用しなくなったメッセージ ボックス データベースを削除することができます。  
  
 BizTalk Server の展開からメッセージ ボックス データベースを完全に削除するには、次の 8 つの手順を実行します。  
  
1.  新しいメッセージの公開を無効にします。  
  
     メッセージ ボックス データベースを削除する前に、新しいメッセージの公開を無効にする必要があります。 新しいメッセージの公開を無効にする方法については、次を参照してください。[新しいメッセージの公開を無効にする方法](../core/how-to-disable-new-message-publication.md)します。  
  
2.  キャッシュ更新間隔に指定した時間が経過するまで待ちます。  
  
     新しいメッセージの公開を無効にした後、データベースをすぐに削除することはできず、待機時間が発生します。 待機時間は、CacheRefreshInterval の 2 倍の長さとして定義されています。 CacheRefreshInterval の既定値は 60 秒です。 使用する、**グループ プロパティ**キャッシュ更新間隔を変更するダイアログ ボックス。  
  
3.  BizTalk グループからメッセージ ボックス データベースを削除します。  
  
     BizTalk グループからメッセージ ボックス データベースを削除すると、BizTalk 管理データベースからメッセージ ボックス データベースの参照が削除されます。  
  
4.  削除したメッセージ ボックス データベースへのキャッシュされた接続を含むホスト インスタンスを再起動します。  
  
     ホスト インスタンスにランタイム エンジンからキャッシュされたデータベースへの接続がある場合、データベースを SQL Server から物理的に削除する前に、ホスト インスタンスを再起動する必要があります。 ホスト インスタンスの開始方法の詳細については、次を参照してください。[ホスト インスタンスを開始する方法](../core/how-to-start-a-host-instance.md)します。  
  
5.  データベースにアクセスする、実行中のホスト インスタンスをすべて停止します。 実行中のホスト インスタンスを停止する方法の詳細については、次を参照してください。[ホスト インスタンスを停止する方法](../core/how-to-stop-a-host-instance.md)します。  
  
     プライマリ以外のメッセージ ボックス データベースを削除する場合は、実行中のホスト インスタンスを停止する前に、そのメッセージ ボックスへの新しいメッセージの公開を無効にして、次の点を確認する必要があります。  
  
    -   メッセージ ボックスに実行中のサービス インスタンスがないこと。  
  
    -   メッセージ ボックスに中断されたインスタンスやその他のインスタンスが残っていないこと。  
  
    -   BAM 追跡データが BizTalk 追跡 (BizTalkDTADb) データベースに移動されている (TrackingData テーブルが空になっている) こと。  
  
    -   追跡メッセージ本文が BizTalk 追跡 (BizTalkDTADb) データベースに移動されていること。  
  
6.  バックグラウンドで実行されている SQL Server エージェントのジョブが完了していることを確認します。  
  
     メッセージ ボックス データベースを BizTalk Server の展開から完全に削除する前に、バックグラウンドで実行中の SQL Server エージェントのジョブが追跡されたメッセージ本文をすべて TrackingSpool テーブルに転送し終えたことを確認し、TrackingSpool テーブルをバックアップする必要があります。 バックグラウンドで実行中の SQL Server エージェントのジョブの状態を確認する方法の詳細については、SQL Server Books Online を参照してください。  
  
7.  TrackingSpool テーブルをバックアップします。  
  
     追跡されたメッセージ本文は、TrackingSpool テーブルを外部の記憶域にバックアップするまで、メッセージ ボックス データベースから削除されません。 バックアップを行う前に、バックグラウンドで実行中の SQL Server エージェントのジョブにより、Spool テーブルから TrackingSpool テーブルにメッセージ本文が転送されます。 手動による SQL Server テーブルのバックアップの詳細については、SQL Server Books Online を参照してください。  
  
8.  SQL Server からデータベースを削除します。  
  
     メッセージ ボックス データベースは、BizTalk グループから削除しても、Microsoft SQL Server から物理的に削除されるわけではありません。 メッセージ ボックス データベースを完全に削除するには、BizTalk グループからデータベースを削除した後に SQL Server Enterprise Manager または SQL Server Management Studio を使用してデータベースを削除します。  
  
## <a name="prerequisites"></a>前提条件  
 メッセージ ボックス データベースを管理する管理者は、必要なユーザー権利が必要です。 メッセージ ボックス データベースの管理と新しいメッセージの公開の無効化には、次のユーザー権利が必要です。  
  
-   BizTalk Server Administrators グループのメンバーとしてログオンする必要があります。  
  
-   データベースが存在するコンピューターの SQL Server 管理者である必要があります。  
  
### <a name="to-delete-a-messagebox-database-from-a-biztalk-group"></a>BizTalk グループからメッセージ ボックス データベースを削除するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)][BizTalk グループ]、をクリックして**プラットフォームの設定**、 をクリックし、**メッセージ ボックス**します。  
  
3. 詳細ウィンドウで、削除、およびクリックするメッセージ ボックス データベースを右クリックして**プロパティ**します。  
  
4. **メッセージ ボックスのプロパティ**ダイアログ ボックスで、**新しいメッセージの公開を無効にする**チェック ボックスをオンします。  
  
5. BizTalk Server 管理コンソールの [グループ ハブ] ページを使用して、削除するメッセージ ボックス データベースに退避または中断されたメッセージ インスタンスがないことを確認します。  
  
6. CacheRefreshInterval の 2 倍 の長さの時間待機します。 CacheRefreshInterval の既定値は 60 秒です。  
  
7. 詳細ウィンドウで、削除、およびをクリックするメッセージ ボックス データベースを右クリックして**削除**します。  
  
8. 警告メッセージを読み、次のようにクリックします。 **OK**します。  
  
9. コンソール ツリーで BizTalk グループ、をクリックして**プラットフォームの設定**、 をクリックし、**ホスト インスタンス**します。  
  
10. 詳細ペインで、実行中のホスト インスタンスを右クリックし、停止してから再起動します (この操作は、実行中のすべてのホスト インスタンスに対して行います)。  
  
11. メッセージ ボックス データベースが存在するサーバーで、使用している SQL Server のバージョンに応じて SQL Server Enterprise Manager または SQL Server Management Studio を開き、データベースを削除します。  
  
     SQL Server でデータベースを削除する方法の詳細については、SQL Server Books Online を参照してください。  
  
## <a name="see-also"></a>参照  
 [メッセージ ボックス データベースの管理](../core/managing-messagebox-databases.md)   
 [新しいメッセージ ボックス データベースを追加する方法](../core/how-to-add-a-new-messagebox-database.md)   
 [新しいメッセージの公開を無効にする方法](../core/how-to-disable-new-message-publication.md)   
 [メッセージ ボックス データベース](../core/the-messagebox-database.md)
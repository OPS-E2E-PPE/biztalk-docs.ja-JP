---
title: 新しいメッセージ ボックス データベースを追加する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adding, MessageBox database
- MessageBox database, adding
- managing [MessageBox database], adding
ms.assetid: 98d850dc-fe3e-43dd-8b5d-9b8c23c006ae
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cab4fd370aab2d85519b3fd52e0dadcd9583275e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247242"
---
# <a name="how-to-add-a-new-messagebox-database"></a>新しいメッセージ ボックス データベースを追加する方法
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用すると、BizTalk Server 環境に新しいメッセージ ボックス データベースを追加できます。 メッセージ ボックス データベースは、協調動作するサーバー間で作業項目の負荷分散を行う基盤です。 システムで処理可能なメッセージの数を増加するには、新しいメッセージ ボックス データベースの追加が必要になることがあります。  
  
 新しいメッセージ ボックス データベースの作成時に、オーケストレーション、送信ポート、または送信ポート グループを参加させることはできません。 オーケストレーション、送信ポート、または送信ポート グループを参加させると、BizTalk Server により新しいメッセージ ボックス データベースにコピーすべきデータに対して、アクセスが生じます。 このデータへのアクセスが発生している間、BizTalk Server では、そのデータを新しいメッセージ ボックス データベースにコピーすることができません。  
  
 メッセージ ボックス データベースとして指定するデータベースは、ローカルでもリモートでもかまいません。 BizTalk Server データベースについては、次を参照してください。 [BizTalk Server でのデータベース](../core/databases-in-biztalk-server.md)です。  
  
> [!IMPORTANT]
>  新しいメッセージ ボックスを追加するすべての SQL Server コンピューターで、SQL Server エージェントが実行されている必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 メッセージ ボックス データベースを管理する管理者は、必要なユーザー権利が必要です。 メッセージ ボックス データベースの管理と新しいメッセージの公開の無効化には、次のユーザー権利が必要です。  
  
-   BizTalk Server Administrators グループのメンバーとしてログオンする必要があります。  
  
-   データベースが存在するコンピューターの SQL Server 管理者である必要があります。  
  
### <a name="to-add-a-new-messagebox-database"></a>新しいメッセージ ボックス データベースを追加するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]BizTalk グループを展開し、クリックして**プラットフォームの設定**です。  
  
3.  右クリック**メッセージ ボックス**をクリックして**新規**、順にクリック**メッセージ ボックス**です。  
  
4.  **メッセージ ボックスのプロパティ**ダイアログ ボックスで、次のように行い、クリックして**OK**:  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**SQL Server**|メッセージ ボックス データベースをホストする SQL Server の名前を表示します。|  
    |**データベース**|メッセージ ボックス データベースの名前を表示します。|  
    |**マスター サブスクリプション メッセージ ボックス**|選択したメッセージ ボックス データベースがマスターかどうかを示します。 現在のメッセージ ボックス データベースがマスターの場合、このチェック ボックスはオンになっており、操作できません。 既定では、構成ウィザードを実行したとき最初に作成したメッセージ ボックス データベースがマスターになります。|  
    |**新しいメッセージの公開を無効にします。**|このメッセージ ボックス データベースでアクティベーション メッセージを受信しない場合、このチェック ボックスをオンにします。|  
  
## <a name="see-also"></a>参照  
 [メッセージ ボックス データベースの管理](../core/managing-messagebox-databases.md)   
 [新しいメッセージの公開を無効にする方法](../core/how-to-disable-new-message-publication.md)   
 [メッセージ ボックス データベースを削除する方法](../core/how-to-delete-a-messagebox-database.md)   
 [バックアップおよび BizTalk Server データベースを復元します。](../core/backing-up-and-restoring-biztalk-server-databases.md)   
 [メッセージ ボックス データベース](../core/the-messagebox-database.md)
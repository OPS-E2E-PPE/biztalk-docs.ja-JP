---
title: BizTalk 追跡データベースに追跡されるメッセージをコピーする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, copying between servers
- MessageBox database, Tracking database
- Tracking database, linking servers
- MessageBox database, copying messages
- linking, servers
- Tracking database, archiving
- archiving [Tracking database], linking servers
- Tracking database, MessageBox database
- Tracking database, copying messages
- archiving [Tracking database], MessageBox database
- MessageBox database, linking servers
- MessageBox database, archiving
ms.assetid: 369e972a-efbe-4ad5-a68f-aa3bbfb9ad54
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23aaa8e3bea3405d51a18da1778d420550ad4584
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
ms.locfileid: "22248130"
---
# <a name="how-to-copy-tracked-messages-into-the-biztalk-tracking-database"></a>追跡メッセージを BizTalk 追跡データベースにコピーする方法
アーカイブおよび削除プロセスでは、さまざまな SQL Server データベースに対するアクセスや更新が行われる可能性があるため、関連する SQL Server インスタンス間にリンク サーバーを設定する必要があります。 リンク サーバーを使用すると、追跡メッセージを BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベース サーバーから BizTalk 追跡 (BizTalkDTADb) データベースに直接コピーできます。 次のそれぞれのインスタンス間にリンク サーバーを設定してください。  
  
-   各 BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベースと BizTalk 追跡 (BizTalkDTADb) データベース  
  
-   BizTalk 追跡 (BizTalkDTADb) データベースとアーカイブ検証用の検証サーバー。  
  
-   BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベースをホストしているコンピューター上の SQL Server エージェントのサービス アカウントは、リンク サーバー上の BizTalk 追跡 (BizTalkDTADb) データベースの db_datareader 権限および db_datawriter 権限を持っている必要があります。  
  
> [!NOTE]
>  SQL Server エージェントで、コピー ジョブの実行時にエラーが発生しないことを確認してください。 エラーが発生すると、データが追跡データベースに移動されない場合があります。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。  
  
### <a name="to-copy-tracked-messages-into-the-biztalk-tracking-database-sql-server-2008"></a>追跡メッセージを BizTalk 追跡データベース (SQL Server 2008) にコピーするには  
  
1.  クリックして **開始**, 、 をクリックして **すべてのプログラム**, 、 をクリックして **Microsoft SQL Server 2008 R2**, 、順にクリック **SQL Server Management Studio**します。  
  
2.  **サーバーへの接続**  ダイアログ ボックスが BizTalk 追跡 (BizTalkDTADb) データベースが存在する SQL server と、適切な認証の種類の名前を指定し、クリックして **接続** 対象の SQL server に接続します。  
  
3.  **Microsoft SQL Server Management Studio**, をダブルクリックして **SQL Server エージェント**, 、クリックして **ジョブ**します。  
  
4.  詳細ペインで右クリック **TrackedMessages_Copy_BizTalkMsgBoxDb**, 、クリックして **プロパティ**します。  
  
5.  **ジョブのプロパティ - TrackedMessages_Copy_BizTalkMsgBoxDb** ダイアログ ボックスで、 **ページの選択**, をクリックして **手順**します。  
  
6.  **ジョブ ステップの一覧**, 、 をクリックして **パージ**, 、 をクリックし、 **編集**します。  
  
7.  **コマンド** ボックス、追跡サーバーと、必要に応じてデータベース名のパラメーターを編集し、クリックして **OK**します。  
  
8.  **ジョブのプロパティ - TrackedMessages_Copy_BizTalkMsgBoxDb** ダイアログ ボックスで、 **ページの選択**, 、 をクリックして **全般**,を選択、 **有効** チェック ボックスをオンにし **ok**します。  
  
     メッセージが BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベースから BizTalk 追跡 (BizTalkDTADb) データベースにコピーされます。  
  
> [!IMPORTANT]
>  新しいメッセージ ボックス データベースを追加する場合は、新しいメッセージ ボックス データベースに対して上記の手順を再実行する必要があります。  
  
## <a name="see-also"></a>参照  
 [BizTalk 追跡データベースのアーカイブおよび削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)
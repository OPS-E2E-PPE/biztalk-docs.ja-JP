---
title: 追跡メッセージを BizTalk 追跡データベースにコピーする方法 |Microsoft Docs
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
ms.openlocfilehash: 0db85ded3ae545ebc0a4648d6324515484765d01
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340132"
---
# <a name="how-to-copy-tracked-messages-into-the-biztalk-tracking-database"></a>追跡メッセージを BizTalk 追跡データベースにコピーする方法
アーカイブおよび削除のプロセスは可能性のあるアクセスや、別の SQL server でデータベースを更新するため、関連する SQL Server インスタンス間のリンク サーバーを設定する必要があります。 リンク サーバーを使用して BizTalk 追跡 (BizTalkDTADb) データベースに、BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベース サーバーから追跡メッセージを直接コピーできます。 間にリンク サーバーを設定する必要があります。  
  
-   各 BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベースと BizTalk 追跡 (BizTalkDTADb) データベース。  
  
-   BizTalk 追跡 (BizTalkDTADb) データベースとアーカイブ検証用の検証サーバー。  
  
-   BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベースをホストするコンピューター上の SQL Server エージェント サービス アカウント、リンク サーバーで、BizTalk 追跡 (BizTalkDTADb) データベースの db_datareader と db_datawriter 権限が必要です。  
  
> [!NOTE]
>  SQL Server エージェントでは、コピー ジョブがエラーなく実行することを確認します。 それ以外の場合、エラーは、追跡データベースに移動してからデータを防止する可能性があります。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。  
  
### <a name="to-copy-tracked-messages-into-the-biztalk-tracking-database-sql-server-2008"></a>追跡メッセージを BizTalk 追跡データベース (SQL Server 2008) にコピーするには  
  
1.  クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 R2**、順にクリックします**SQL Server Management Studio**します。  
  
2.  **サーバーへの接続**ダイアログ ボックスで、SQL server が BizTalk 追跡 (BizTalkDTADb) データベースが存在し、適切な認証の種類の名前を指定し、順にクリックします**Connect**に適切な SQL server に接続します。  
  
3.  **Microsoft SQL Server Management Studio**、ダブルクリックして**SQL Server エージェント**、順にクリックします**ジョブ**します。  
  
4.  詳細ペインで右クリックして**TrackedMessages_Copy_BizTalkMsgBoxDb**、 をクリックし、**プロパティ**します。  
  
5.  **ジョブのプロパティ - TrackedMessages_Copy_BizTalkMsgBoxDb**ダイアログ ボックスで、**ページの選択**、 をクリックして**手順**します。  
  
6.  **ジョブ ステップの一覧**、 をクリックして**パージ**、 をクリックし、**編集**。  
  
7.  **コマンド**ボックス、追跡サーバーおよび必要に応じて、データベース名のパラメーターを編集し、クリックして**OK**します。  
  
8.  **ジョブのプロパティ - TrackedMessages_Copy_BizTalkMsgBoxDb**ダイアログ ボックスで、**ページの選択**、 をクリックして**全般**を選択、**有効**チェック ボックスをオンにして**OK**します。  
  
     メッセージは、BizTalk 追跡 (BizTalkDTADb) データベースを BizTalk メッセージ ボックス (BizTalkMsgBoxDb) からコピーされます。  
  
> [!IMPORTANT]
>  新しいメッセージ ボックス データベースを追加する場合は、新しいメッセージ ボックス データベースのこの手順をもう一度実行する必要があります。  
  
## <a name="see-also"></a>参照  
 [BizTalk 追跡データベースのアーカイブおよび削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)
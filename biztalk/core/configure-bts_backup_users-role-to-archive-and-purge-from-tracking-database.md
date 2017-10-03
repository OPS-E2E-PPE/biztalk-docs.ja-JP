---
title: "アーカイブおよび BizTalk 追跡データベースからデータを削除するために BTS_BACKUP_USERS ロールを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- purging, BTS_BACKUP_USERS role
- Tracking database, purging
- BTS_BACKUP_USERS role
- DTA Purge and Archive job
- archiving [Tracking database], BTS_BACKUP_USERS role
- archiving [Tracking database], DTA Purge and Archive job
- Tracking database, BTS_BACKUP_USERS role
- Tracking database, archiving
- purging, DTA Purge and Archive job
ms.assetid: c27aad2a-5788-4236-b5eb-ca730bf79851
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 923fb083f3755259ab2176541213d1637ce872c6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-btsbackupusers-role-for-archiving-and-purging-data-from-the-biztalk-tracking-database"></a>BizTalk 追跡データベースのデータをアーカイブおよび削除するための BTS_BACKUP_USERS ロールの構成方法
DTA Purge and Archive (BizTAlkDTADb) ジョブの実行には、通常はログオン中の SQL Server エージェント サービス アカウントのユーザーの資格情報が使用されます。 ただし、セキュリティを高めるため、BTS_BACKUP_USERS ロールのメンバーであるアカウントの資格情報で実行されるように DTA Purge and Archive (BizTalkDTADb) ジョブを構成できます。 その結果、最低限必要なアクセス許可しかないアカウントで SQL Server エージェントのジョブが実行され、特権の昇格を防ぐことができます。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。  
  
### <a name="to-configure-the-btsbackupusers-role-for-archiving-and-purging-data-from-the-biztalk-tracking-database"></a>BizTalk 追跡データベースのデータをアーカイブおよび削除するために BTS_BACKUP_USERS ロールを構成するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 SP2**、順にクリック**SQL Server Management Studio**です。  
  
2.  **サーバーへの接続**ダイアログ ボックスでは、BizTalk 追跡 (BizTalkDTADb) データベースが存在する SQL server および適切な認証の種類の名前を指定し、をクリックして**接続**に適切な SQL Server に接続します。  
  
3.  **Microsoft SQL Server Management Studio**をダブルクリックして**BizTalkDTADb**をダブルクリックして**セキュリティ**をダブルクリックして**ロール**、およびダブルクリックし、**データベース ロール**です。  
  
4.  **オブジェクト エクスプ ローラーの詳細** ウィンドウをダブルクリックして**BTS_BACKUP_USERS**です。  
  
5.  **データベース ロールのプロパティ-BTS_BACKUP_USERS**ダイアログ ボックスで、**このロールのメンバー**をクリックして**追加**です。  
  
6.  **データベース ユーザーまたはロール**ダイアログ ボックスでは、SQL Server エージェント サービスの資格情報を持つユーザー アカウントを入力し、をクリックして**OK**です。  
  
## <a name="see-also"></a>参照  
 [BizTalk 追跡データベースのアーカイブおよび削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)
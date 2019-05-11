---
title: アーカイブおよび BizTalk 追跡データベースからデータを削除のために BTS_BACKUP_USERS ロールを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3717372e4c421636c601f7b34d1a6b2667a4a1ca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391457"
---
# <a name="how-to-configure-the-btsbackupusers-role-for-archiving-and-purging-data-from-the-biztalk-tracking-database"></a>アーカイブおよび BizTalk 追跡データベースからデータを削除のために BTS_BACKUP_USERS ロールを構成する方法
DTA Purge and Archive (BizTAlkDTADb) ジョブの正常ログオンしている SQL Server エージェント サービス アカウントのユーザーの資格情報を使用して実行します。 セキュリティの強化、ただし、構成できます DTA Purge and Archive (BizTalkDTADb) ジョブ、BTS_BACKUP_USERS ロールのメンバーであるアカウントの資格情報を使用して実行します。 これは、重要なアクセス許可を持つアカウントで SQL Server エージェント ジョブを実行して特権の昇格を防ぐのに役立ちます。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。  
  
### <a name="to-configure-the-btsbackupusers-role-for-archiving-and-purging-data-from-the-biztalk-tracking-database"></a>アーカイブおよび BizTalk 追跡データベースからデータを削除のために BTS_BACKUP_USERS ロールを構成するには  
  
1.  クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 SP2**、順にクリックします**SQL Server Management Studio**します。  
  
2.  **サーバーへの接続**ダイアログ ボックスで、SQL server が BizTalk 追跡 (BizTalkDTADb) データベースが存在し、適切な認証の種類の名前を指定し、順にクリックします**Connect**に適切な SQL Server に接続します。  
  
3.  **Microsoft SQL Server Management Studio**、 をダブルクリックします**BizTalkDTADb**、 をダブルクリックします**セキュリティ**、ダブルクリックして**ロール**とダブルクリックし、**データベース ロール**します。  
  
4.  **オブジェクト エクスプ ローラーの詳細**ウィンドウで、ダブルクリックして**BTS_BACKUP_USERS**します。  
  
5.  **データベース ロールのプロパティ-BTS_BACKUP_USERS**ダイアログ ボックスで、**このロールのメンバー**、 をクリックして**追加**します。  
  
6.  **データベース ユーザーまたはロール**ダイアログ ボックスで、SQL Server エージェント サービスの資格情報を持つユーザー アカウントを入力し、順にクリックします**OK**します。  
  
## <a name="see-also"></a>参照  
 [BizTalk 追跡データベースのアーカイブおよび削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)
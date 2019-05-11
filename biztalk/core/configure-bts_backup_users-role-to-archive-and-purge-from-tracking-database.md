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
# <a name="how-to-configure-the-btsbackupusers-role-for-archiving-and-purging-data-from-the-biztalk-tracking-database"></a><span data-ttu-id="32176-102">アーカイブおよび BizTalk 追跡データベースからデータを削除のために BTS_BACKUP_USERS ロールを構成する方法</span><span class="sxs-lookup"><span data-stu-id="32176-102">How to Configure the BTS_BACKUP_USERS Role for Archiving and Purging Data from the BizTalk Tracking Database</span></span>
<span data-ttu-id="32176-103">DTA Purge and Archive (BizTAlkDTADb) ジョブの正常ログオンしている SQL Server エージェント サービス アカウントのユーザーの資格情報を使用して実行します。</span><span class="sxs-lookup"><span data-stu-id="32176-103">The DTA Purge and Archive (BizTAlkDTADb) job normally runs using the credentials of the logged-on SQL Server Agent service account user.</span></span> <span data-ttu-id="32176-104">セキュリティの強化、ただし、構成できます DTA Purge and Archive (BizTalkDTADb) ジョブ、BTS_BACKUP_USERS ロールのメンバーであるアカウントの資格情報を使用して実行します。</span><span class="sxs-lookup"><span data-stu-id="32176-104">For added security, however, you can configure the DTA Purge and Archive (BizTalkDTADb) job to run using the credentials of an account which is a member of the BTS_BACKUP_USERS role.</span></span> <span data-ttu-id="32176-105">これは、重要なアクセス許可を持つアカウントで SQL Server エージェント ジョブを実行して特権の昇格を防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="32176-105">This helps to prevent elevation of privileges by running SQL Server Agent jobs under accounts with essential permissions.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="32176-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="32176-106">Prerequisites</span></span>  
 <span data-ttu-id="32176-107">この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="32176-107">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-configure-the-btsbackupusers-role-for-archiving-and-purging-data-from-the-biztalk-tracking-database"></a><span data-ttu-id="32176-108">アーカイブおよび BizTalk 追跡データベースからデータを削除のために BTS_BACKUP_USERS ロールを構成するには</span><span class="sxs-lookup"><span data-stu-id="32176-108">To configure the BTS_BACKUP_USERS role for archiving and purging data from the BizTalk Tracking database</span></span>  
  
1.  <span data-ttu-id="32176-109">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 SP2**、順にクリックします**SQL Server Management Studio**します。</span><span class="sxs-lookup"><span data-stu-id="32176-109">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 SP2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="32176-110">**サーバーへの接続**ダイアログ ボックスで、SQL server が BizTalk 追跡 (BizTalkDTADb) データベースが存在し、適切な認証の種類の名前を指定し、順にクリックします**Connect**に適切な SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="32176-110">In the **Connect to Server** dialog box, specify the name of the SQL server where the BizTalk Tracking (BizTalkDTADb) database resides and the appropriate authentication type, and then click **Connect** to connect to the appropriate SQL Server.</span></span>  
  
3.  <span data-ttu-id="32176-111">**Microsoft SQL Server Management Studio**、 をダブルクリックします**BizTalkDTADb**、 をダブルクリックします**セキュリティ**、ダブルクリックして**ロール**とダブルクリックし、**データベース ロール**します。</span><span class="sxs-lookup"><span data-stu-id="32176-111">In **Microsoft SQL Server Management Studio**, double-click **BizTalkDTADb**, double-click **Security**, double-click **Roles**, and then double-click **Database Roles**.</span></span>  
  
4.  <span data-ttu-id="32176-112">**オブジェクト エクスプ ローラーの詳細**ウィンドウで、ダブルクリックして**BTS_BACKUP_USERS**します。</span><span class="sxs-lookup"><span data-stu-id="32176-112">In the **Object Explorer Details** pane, double-click **BTS_BACKUP_USERS**.</span></span>  
  
5.  <span data-ttu-id="32176-113">**データベース ロールのプロパティ-BTS_BACKUP_USERS**ダイアログ ボックスで、**このロールのメンバー**、 をクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="32176-113">In the **Database Role Properties – BTS_BACKUP_USERS** dialog box, under **Members of this role**, click **Add**.</span></span>  
  
6.  <span data-ttu-id="32176-114">**データベース ユーザーまたはロール**ダイアログ ボックスで、SQL Server エージェント サービスの資格情報を持つユーザー アカウントを入力し、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="32176-114">In the **Select Database User or Role** dialog box, enter a user account with SQL Server Agent Service credentials, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32176-115">参照</span><span class="sxs-lookup"><span data-stu-id="32176-115">See Also</span></span>  
 [<span data-ttu-id="32176-116">BizTalk 追跡データベースのアーカイブおよび削除</span><span class="sxs-lookup"><span data-stu-id="32176-116">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)
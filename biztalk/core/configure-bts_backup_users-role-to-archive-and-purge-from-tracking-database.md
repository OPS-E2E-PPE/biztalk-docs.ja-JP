---
title: アーカイブおよび BizTalk 追跡データベースからデータを削除するために BTS_BACKUP_USERS ロールを構成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 923fb083f3755259ab2176541213d1637ce872c6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232450"
---
# <a name="how-to-configure-the-btsbackupusers-role-for-archiving-and-purging-data-from-the-biztalk-tracking-database"></a><span data-ttu-id="12928-102">BizTalk 追跡データベースのデータをアーカイブおよび削除するための BTS_BACKUP_USERS ロールの構成方法</span><span class="sxs-lookup"><span data-stu-id="12928-102">How to Configure the BTS_BACKUP_USERS Role for Archiving and Purging Data from the BizTalk Tracking Database</span></span>
<span data-ttu-id="12928-103">DTA Purge and Archive (BizTAlkDTADb) ジョブの実行には、通常はログオン中の SQL Server エージェント サービス アカウントのユーザーの資格情報が使用されます。</span><span class="sxs-lookup"><span data-stu-id="12928-103">The DTA Purge and Archive (BizTAlkDTADb) job normally runs using the credentials of the logged-on SQL Server Agent service account user.</span></span> <span data-ttu-id="12928-104">ただし、セキュリティを高めるため、BTS_BACKUP_USERS ロールのメンバーであるアカウントの資格情報で実行されるように DTA Purge and Archive (BizTalkDTADb) ジョブを構成できます。</span><span class="sxs-lookup"><span data-stu-id="12928-104">For added security, however, you can configure the DTA Purge and Archive (BizTalkDTADb) job to run using the credentials of an account which is a member of the BTS_BACKUP_USERS role.</span></span> <span data-ttu-id="12928-105">その結果、最低限必要なアクセス許可しかないアカウントで SQL Server エージェントのジョブが実行され、特権の昇格を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="12928-105">This helps to prevent elevation of privileges by running SQL Server Agent jobs under accounts with essential permissions.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="12928-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="12928-106">Prerequisites</span></span>  
 <span data-ttu-id="12928-107">この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="12928-107">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-configure-the-btsbackupusers-role-for-archiving-and-purging-data-from-the-biztalk-tracking-database"></a><span data-ttu-id="12928-108">BizTalk 追跡データベースのデータをアーカイブおよび削除するために BTS_BACKUP_USERS ロールを構成するには</span><span class="sxs-lookup"><span data-stu-id="12928-108">To configure the BTS_BACKUP_USERS role for archiving and purging data from the BizTalk Tracking database</span></span>  
  
1.  <span data-ttu-id="12928-109">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 SP2**、順にクリック**SQL Server Management Studio**です。</span><span class="sxs-lookup"><span data-stu-id="12928-109">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 SP2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="12928-110">**サーバーへの接続**ダイアログ ボックスでは、BizTalk 追跡 (BizTalkDTADb) データベースが存在する SQL server および適切な認証の種類の名前を指定し、をクリックして**接続**に適切な SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="12928-110">In the **Connect to Server** dialog box, specify the name of the SQL server where the BizTalk Tracking (BizTalkDTADb) database resides and the appropriate authentication type, and then click **Connect** to connect to the appropriate SQL Server.</span></span>  
  
3.  <span data-ttu-id="12928-111">**Microsoft SQL Server Management Studio**をダブルクリックして**BizTalkDTADb**をダブルクリックして**セキュリティ**をダブルクリックして**ロール**、およびダブルクリックし、**データベース ロール**です。</span><span class="sxs-lookup"><span data-stu-id="12928-111">In **Microsoft SQL Server Management Studio**, double-click **BizTalkDTADb**, double-click **Security**, double-click **Roles**, and then double-click **Database Roles**.</span></span>  
  
4.  <span data-ttu-id="12928-112">**オブジェクト エクスプ ローラーの詳細** ウィンドウをダブルクリックして**BTS_BACKUP_USERS**です。</span><span class="sxs-lookup"><span data-stu-id="12928-112">In the **Object Explorer Details** pane, double-click **BTS_BACKUP_USERS**.</span></span>  
  
5.  <span data-ttu-id="12928-113">**データベース ロールのプロパティ-BTS_BACKUP_USERS**ダイアログ ボックスで、**このロールのメンバー**をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="12928-113">In the **Database Role Properties – BTS_BACKUP_USERS** dialog box, under **Members of this role**, click **Add**.</span></span>  
  
6.  <span data-ttu-id="12928-114">**データベース ユーザーまたはロール**ダイアログ ボックスでは、SQL Server エージェント サービスの資格情報を持つユーザー アカウントを入力し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="12928-114">In the **Select Database User or Role** dialog box, enter a user account with SQL Server Agent Service credentials, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12928-115">参照</span><span class="sxs-lookup"><span data-stu-id="12928-115">See Also</span></span>  
 [<span data-ttu-id="12928-116">BizTalk 追跡データベースのアーカイブおよび削除</span><span class="sxs-lookup"><span data-stu-id="12928-116">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)
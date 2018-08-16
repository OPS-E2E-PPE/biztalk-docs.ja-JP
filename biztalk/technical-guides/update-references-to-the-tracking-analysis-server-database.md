---
title: 追跡分析サーバー データベースへの参照の更新 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a403325-1394-4668-946f-01b610cb686e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 417569d99b7326b435422b5fa0dff28019006116
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014707"
---
# <a name="update-references-to-the-tracking-analysis-server-database"></a><span data-ttu-id="1eab8-102">追跡分析サーバー データベースへの参照を更新します。</span><span class="sxs-lookup"><span data-stu-id="1eab8-102">Update References to the Tracking Analysis Server Database</span></span>
<span data-ttu-id="1eab8-103">Tracking Analysis Server データベースであり、省略可能なオンライン分析処理 (OLAP) キューブが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1eab8-103">The Tracking Analysis Server database is an optional and contains the online analytical processing (OLAP) cubes.</span></span> <span data-ttu-id="1eab8-104">これらの OLAP キューブは、BizTalk 追跡データベースに含まれるデータの集計です。</span><span class="sxs-lookup"><span data-stu-id="1eab8-104">These OLAP cubes are aggregations of data contained in the BizTalk Tracking database.</span></span>  
  
 <span data-ttu-id="1eab8-105">Tracking Analysis Server データベースを復元する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]分析マネージャー、MessageMetrics キューブおよび ServiceMetrics キューブを処理します。</span><span class="sxs-lookup"><span data-stu-id="1eab8-105">To restore the Tracking Analysis Server database, use [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Manager to process the MessageMetrics and ServiceMetrics cubes.</span></span> <span data-ttu-id="1eab8-106">手順については、次を参照してください。[管理バックアップと復元 (Analysis Services)](http://go.microsoft.com/fwlink/?LinkId=130939) (<http://go.microsoft.com/fwlink/?LinkId=130939>) で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]オンライン ブックの「します。</span><span class="sxs-lookup"><span data-stu-id="1eab8-106">For instructions, see [Managing Backing Up and Restoring (Analysis Services)](http://go.microsoft.com/fwlink/?LinkId=130939) (<http://go.microsoft.com/fwlink/?LinkId=130939>) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="1eab8-107">Tracking Analysis Server データベースを別のコンピューターを復元するには、次の手順を使用して、BizTalk 管理データベースにデータベース名への参照を更新することも必要があります。</span><span class="sxs-lookup"><span data-stu-id="1eab8-107">To restore the Tracking Analysis Server database to an alternate computer, you must also update references to the database name in the BizTalk Management database by using the following procedure.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1eab8-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="1eab8-108">Prerequisites</span></span>  
 <span data-ttu-id="1eab8-109">メンバーとしてログオンする必要があります、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators グループにこの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1eab8-109">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group to perform this procedure.</span></span>  
  
### <a name="to-update-references-to-the-tracking-analysis-server-database-name"></a><span data-ttu-id="1eab8-110">Tracking Analysis Server データベース名への参照を更新するには</span><span class="sxs-lookup"><span data-stu-id="1eab8-110">To update references to the Tracking Analysis Server database name</span></span>  
  
1.  <span data-ttu-id="1eab8-111">送信先システムで、をクリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft SQL Server 2008**、 をクリックし、 **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="1eab8-111">On the destination system, click **Start**, click **Programs**, click **Microsoft SQL Server 2008**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="1eab8-112">**サーバーへの接続**ダイアログ ボックスで、**サーバーの種類**として**データベース エンジン**サーバー名を指定、サーバー、ot の接続に資格情報を提供し、クリックして**Connect**します。</span><span class="sxs-lookup"><span data-stu-id="1eab8-112">In the **Connect to Server** dialog box, select the **Server type** as **Database Engine**, provide a server name, provide the credentials to connect ot the server, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="1eab8-113">ダブルクリックするをクリックして、適切なサーバーを開く**データベース**、 **BizTalkMgmtDb**、 をクリックし、**テーブル**します。</span><span class="sxs-lookup"><span data-stu-id="1eab8-113">Open the appropriate server by clicking it, double-clicking **Databases**, double-clicking **BizTalkMgmtDb**, and then clicking **Tables**.</span></span>  
  
4.  <span data-ttu-id="1eab8-114">詳細ペインで右クリックして**adm_Group**、順にポイント**テーブルを開く**します。</span><span class="sxs-lookup"><span data-stu-id="1eab8-114">In the details pane, right-click **adm_Group**, and then point to **Open Table**.</span></span>  
  
5.  <span data-ttu-id="1eab8-115">新しいデータベースの適切な値を参照するように、元のデータベースに対応する列を変更します。</span><span class="sxs-lookup"><span data-stu-id="1eab8-115">Modify the columns corresponding to the original database to reference the appropriate values for the new database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1eab8-116">*\<DBType\>*  DBServerName および*\<DBType\>* DBName は、データベースの場所を示す、 *\<DBType\>* 、データベースは、TrackingAnalysis の型に対応します。</span><span class="sxs-lookup"><span data-stu-id="1eab8-116">*\<DBType\>* DBServerName and *\<DBType\>* DBName indicate the location of the database, where *\<DBType\>* corresponds to the type of the database, for example, TrackingAnalysis.</span></span>  
  
6.  <span data-ttu-id="1eab8-117">テーブルを閉じて新しい値を保存します。</span><span class="sxs-lookup"><span data-stu-id="1eab8-117">Close the table to save the new values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eab8-118">参照</span><span class="sxs-lookup"><span data-stu-id="1eab8-118">See Also</span></span>  
 [<span data-ttu-id="1eab8-119">データベース参照の更新</span><span class="sxs-lookup"><span data-stu-id="1eab8-119">Updating Database References</span></span>](../technical-guides/updating-database-references.md)
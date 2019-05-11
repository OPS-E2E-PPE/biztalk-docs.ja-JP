---
title: BAM 警告を復旧する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 56c477b4-4605-4763-b20a-3baf4529f13f
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fc3e51593b0a01fb43111f58f01ec07efdc09f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335618"
---
# <a name="how-to-recover-bam-alerts"></a><span data-ttu-id="fae1e-102">BAM 警告を復旧する方法</span><span class="sxs-lookup"><span data-stu-id="fae1e-102">How to Recover BAM Alerts</span></span>
<span data-ttu-id="fae1e-103">復旧処理の一環として[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、ビジネス アクティビティ監視 (BAM) を使用している場合は、BAM 警告も復旧する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fae1e-103">As a part of recovering [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], if you are using Business Activity Monitoring (BAM), you must also recover the BAM alerts.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fae1e-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="fae1e-104">Prerequisites</span></span>  
 <span data-ttu-id="fae1e-105">メンバーとしてログオンする必要があります、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators グループにこの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fae1e-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group to perform this procedure.</span></span>  
  
### <a name="to-recover-bam-alerts-sql-server-2008"></a><span data-ttu-id="fae1e-106">BAM 警告 (SQL Server 2008) を復旧するには</span><span class="sxs-lookup"><span data-stu-id="fae1e-106">To recover BAM alerts (SQL Server 2008)</span></span>  
  
1.  <span data-ttu-id="fae1e-107">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008**、 をクリックして**構成ツール**をクリックして**Notification Services コマンド プロンプト**します。</span><span class="sxs-lookup"><span data-stu-id="fae1e-107">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008**, click **Configuration Tools**, and then click **Notification Services Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="fae1e-108">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="fae1e-108">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="fae1e-109">**nscontrol register-name BamAlerts-サーバー***\<ServerName\>***-service - serviceusername"** *\<ServiceUserName\>* **"-servicepassword"** *\<ServicePassword\>* **"** </span><span class="sxs-lookup"><span data-stu-id="fae1e-109">**nscontrol register -name BamAlerts -server**  *\<ServerName\>*  **-service -serviceusername "** *\<ServiceUserName\>* **" -servicepassword "** *\<ServicePassword\>* **"**</span></span>  
  
     <span data-ttu-id="fae1e-110">これにより、Notification Services が適切なデータベース (この情報は、nscontrol により、サービス コンピューターのレジストリに保持) にログオンできます。</span><span class="sxs-lookup"><span data-stu-id="fae1e-110">This enables Notification Services to log on to the correct database (this information is maintained in the registry of the service computer by nscontrol).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="fae1e-111">新しい Notification Services データベース サーバーを使用して、忘れず、 **-サーバー**サービスを再登録するときのオプションします。</span><span class="sxs-lookup"><span data-stu-id="fae1e-111">Remember to use the new Notification Services databases server in the **-server** option when re-registering the service.</span></span> <span data-ttu-id="fae1e-112">さらに、古いものと、新しい Notification Services サービスの同じユーザー名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fae1e-112">In addition, you should use the same user name for the new Notification Services service as the old one.</span></span>  
  
3.  <span data-ttu-id="fae1e-113">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="fae1e-113">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="fae1e-114">コマンド プロンプトで「:**開始 NS$ BamAlerts を net**します。</span><span class="sxs-lookup"><span data-stu-id="fae1e-114">At the command prompt, type: **net start NS$BamAlerts**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fae1e-115">参照</span><span class="sxs-lookup"><span data-stu-id="fae1e-115">See Also</span></span>  
 [<span data-ttu-id="fae1e-116">BizTalk Server を実行しているコンピューターの復旧</span><span class="sxs-lookup"><span data-stu-id="fae1e-116">Recovering a Computer Running BizTalk Server</span></span>](../core/recovering-a-computer-running-biztalk-server.md)
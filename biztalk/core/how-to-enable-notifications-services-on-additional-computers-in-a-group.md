---
title: グループの他のコンピューターで通知サービスを有効にする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 571d6b45-b0cc-47f2-bed3-7c6f3e70decc
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fd8a1a49be2416fb8b7fe5d160dd5228a95e94f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983395"
---
# <a name="how-to-enable-notifications-services-on-additional-computers-in-a-group"></a><span data-ttu-id="5dd8b-102">グループ内の別のコンピューターで通知サービスを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="5dd8b-102">How to Enable Notifications Services on Additional Computers In A Group</span></span>
<span data-ttu-id="5dd8b-103">複数コンピューター環境で BAM を実行するときに、各コンピューターを実行するアクティビティを展開する BAM 管理ユーティリティで Notification Services を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5dd8b-103">When running BAM in a multi-computer environment, you must enable Notification Services on each computer on which you will run the BAM Management Utility to deploy an activity.</span></span>  
  
 <span data-ttu-id="5dd8b-104">以下のシナリオについて考えてみます。</span><span class="sxs-lookup"><span data-stu-id="5dd8b-104">Consider the following scenario:</span></span>  
  
- <span data-ttu-id="5dd8b-105">グループ A は、次のコンピューターで構成されます。</span><span class="sxs-lookup"><span data-stu-id="5dd8b-105">Group A consists of the following computers:</span></span>  
  
  - <span data-ttu-id="5dd8b-106">コンピューター 1 は、BAM 管理コンピューターとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="5dd8b-106">Computer 1 is used as a BAM administration computer.</span></span>  
  
  - <span data-ttu-id="5dd8b-107">コンピューター 2 は、BAM PIT およびスター スキーマ データベースをホストします。</span><span class="sxs-lookup"><span data-stu-id="5dd8b-107">Computer 2 hosts the BAM PIT and Star Schema database.</span></span>  
  
  - <span data-ttu-id="5dd8b-108">コンピューター 3 は、BAM アーカイブ データベースおよび分析データベースをホストします。</span><span class="sxs-lookup"><span data-stu-id="5dd8b-108">Computer 3 hosts the BAM Archive and Analysis databases.</span></span>  
  
  - <span data-ttu-id="5dd8b-109">コンピューター 4 は、BAM 警告データベースをホストします。</span><span class="sxs-lookup"><span data-stu-id="5dd8b-109">Computer 4 hosts the BAM Alerts database.</span></span>  
  
  - <span data-ttu-id="5dd8b-110">コンピューター 5 は、それ以外の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースをホストします。</span><span class="sxs-lookup"><span data-stu-id="5dd8b-110">Computer 5 hosts the rest of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span>  
  
- <span data-ttu-id="5dd8b-111">グループ B:</span><span class="sxs-lookup"><span data-stu-id="5dd8b-111">Group B:</span></span>  
  
  -   <span data-ttu-id="5dd8b-112">コンピューター 6 は、BAM 管理コンピューターとして使用され、すべてのデータベースをグループ A と共有します。</span><span class="sxs-lookup"><span data-stu-id="5dd8b-112">Computer 6 is used as a BAM administration computer on which all the databases are shared with Group A.</span></span>  
  
  <span data-ttu-id="5dd8b-113">グループ B のコンピューターからグループ A のデータベースにアクティビティを展開するには、最初に、Notification Services をホストする [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] に Notification Services を登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5dd8b-113">To be able to deploy an activity to the databases in group A from the computer in group B, you must first register the Notification Services with the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] hosting the notifications services.</span></span> <span data-ttu-id="5dd8b-114">Notification Services が登録されていない場合は、次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dd8b-114">If the Notification Services are not registered, you will receive the following error:</span></span>  
  
  <span data-ttu-id="5dd8b-115">Deploying Alert...エラー: BAM を展開できませんでした。</span><span class="sxs-lookup"><span data-stu-id="5dd8b-115">Deploying Alert... ERROR: The BAM deployment failed.</span></span>  
  
  <span data-ttu-id="5dd8b-116">警告は展開されませんでした。</span><span class="sxs-lookup"><span data-stu-id="5dd8b-116">The alerts were not deployed.</span></span>  
  
  <span data-ttu-id="5dd8b-117">呼び出しのターゲットが例外をスローしました。</span><span class="sxs-lookup"><span data-stu-id="5dd8b-117">Exception has been thrown by the target of an invocation.</span></span>  
  
  <span data-ttu-id="5dd8b-118">指定した Notification Services のインスタンスのレジストリ エントリが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="5dd8b-118">The registry entries for the specified instance of Notification Services could not be found.</span></span>  
  
### <a name="to-register-notifications-services-additional-computers"></a><span data-ttu-id="5dd8b-119">通知サービスの追加コンピューターを登録するには</span><span class="sxs-lookup"><span data-stu-id="5dd8b-119">To register notifications services additional computers</span></span>  
  
1.  <span data-ttu-id="5dd8b-120">コンピューター別のグループで、次のようにクリックします**開始**、 をポイント**すべてのプログラム**、 をクリック**Microsoft SQL Server 2005**、 をクリック**構成ツール。**、 をクリックし、 **Notification Services コマンド プロンプト**します。</span><span class="sxs-lookup"><span data-stu-id="5dd8b-120">On the computer in the additional group, click **Start**, point to **All Programs**, click **Microsoft SQL Server 2005**, click **Configuration Tools**, and then click **Notification Services Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="5dd8b-121">コマンド プロンプトで「: **nscontrol register 名前\<構成に選択した NS プレフィックス名\>-サーバー \<ns db の sql server\>** します。</span><span class="sxs-lookup"><span data-stu-id="5dd8b-121">At the command prompt, type: **nscontrol register -name \<NS Prefix name chosen at config\> -server \<ns db sql server\>**.</span></span> <span data-ttu-id="5dd8b-122">これにより、Notification Services が適切なデータベースに接続できるようになります。この情報は、nscontrol により、サービス コンピューターのレジストリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="5dd8b-122">This enables Notification Services to log on to the correct database (this information is maintained in the registry of the service machine by nscontrol).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dd8b-123">参照</span><span class="sxs-lookup"><span data-stu-id="5dd8b-123">See Also</span></span>  
 <span data-ttu-id="5dd8b-124">[BAM ランタイムの設定を変更します。](../core/changing-bam-runtime-settings.md) </span><span class="sxs-lookup"><span data-stu-id="5dd8b-124">[Changing BAM Runtime Settings](../core/changing-bam-runtime-settings.md) </span></span>  
 [<span data-ttu-id="5dd8b-125">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="5dd8b-125">BAM Management Utility</span></span>](../core/bam-management-utility.md)
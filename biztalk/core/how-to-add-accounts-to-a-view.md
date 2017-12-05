---
title: "ビューにアカウントを追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Excel add-in [BAM], security
- Add-Account command [BAM]
- managing [BAM], adding accounts to views
ms.assetid: 0875796c-82a4-4165-9bed-88e8ba466548
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 808d5395452733d43337e0883b306b7757a7da08
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-add-accounts-to-a-view"></a><span data-ttu-id="8d11a-102">アカウントをビューに追加する方法</span><span class="sxs-lookup"><span data-stu-id="8d11a-102">How to Add Accounts to a View</span></span>
<span data-ttu-id="8d11a-103">管理者を使用して、**アカウントの追加**ユーザーを BAM ビューに関連付けるし、BAM Excel ワークシート ビューを不正アクセスから保護するコマンド。</span><span class="sxs-lookup"><span data-stu-id="8d11a-103">Administrators use the **add-account** command to associate users with BAM views and protect BAM Excel Spreadsheet views from unauthorized access.</span></span> <span data-ttu-id="8d11a-104">ユーザーが BAM ビューを保存するときに、ビューはブック内で非表示になっている SQL 接続文字列を参照します。</span><span class="sxs-lookup"><span data-stu-id="8d11a-104">When users save BAM views, the views reference a SQL connection string that is hidden within the workbook.</span></span> <span data-ttu-id="8d11a-105">ブックは保護されていますが、さらにドキュメントが確実に保護されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d11a-105">The workbook is protected, but you must ensure that the document is protected.</span></span>  
  
 <span data-ttu-id="8d11a-106">ユーザーを BAM ビューに関連付けるときに、アクセスを許可したユーザーまたはグループのみにビューへのアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="8d11a-106">When you associate users with BAM views, you restrict access to the views to only the users or groups to whom you grant access.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8d11a-107">リアルタイム集計 (Rta) を使用している場合で追加されたユーザー**アカウントの追加**SQL Server を実行しているコンピューターへのログオン権限を自動的に付与することはできません。</span><span class="sxs-lookup"><span data-stu-id="8d11a-107">If you are using real-time aggregations (RTAs), users added with **add-account** are not automatically granted logon rights to the computer running SQL Server.</span></span> <span data-ttu-id="8d11a-108">RTA を使用している場合は、RTA のビューを表示しなければならないすべてのユーザーを含む、Windows ユーザー グループの作成を検討してください。</span><span class="sxs-lookup"><span data-stu-id="8d11a-108">If you are using RTAs, consider establishing a Windows user group that contains all of the users that need to see views of the RTAs.</span></span> <span data-ttu-id="8d11a-109">そのグループ、BAM プライマリ インポート データベースをホストする SQL server で SQL Server ログオン権限を明示的に許可します。</span><span class="sxs-lookup"><span data-stu-id="8d11a-109">Grant that group explicit SQL Server logon rights on the SQL server hosting the BAM Primary Import database.</span></span>  
  
 <span data-ttu-id="8d11a-110">BAM ビューを表示する方法については、次を参照してください。[リスト BAM ビューの表示方法](../core/how-to-list-bam-views.md)です。</span><span class="sxs-lookup"><span data-stu-id="8d11a-110">For information about viewing BAM views, see [How to List BAM Views](../core/how-to-list-bam-views.md).</span></span>  
  
### <a name="to-add-an-account-to-a-view"></a><span data-ttu-id="8d11a-111">アカウントをビューに追加するには</span><span class="sxs-lookup"><span data-stu-id="8d11a-111">To add an account to a view</span></span>  
  
1.  <span data-ttu-id="8d11a-112">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="8d11a-112">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="8d11a-113">コマンド プロンプトで「[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking」と入力して、追跡フォルダーに移動し、</span><span class="sxs-lookup"><span data-stu-id="8d11a-113">Navigate to the tracking folder by typing [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking at the command prompt.</span></span> <span data-ttu-id="8d11a-114">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8d11a-114">Press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="8d11a-115">型**bm アカウントの追加-accountname:\<アカウント名\>-ビュー:\<ビュー名\>**です。</span><span class="sxs-lookup"><span data-stu-id="8d11a-115">Type **bm add-account -AccountName:\<account name\> -View:\<view name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8d11a-116">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="8d11a-116">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="8d11a-117">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8d11a-117">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d11a-118">参照</span><span class="sxs-lookup"><span data-stu-id="8d11a-118">See Also</span></span>  
 <span data-ttu-id="8d11a-119">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="8d11a-119">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 [<span data-ttu-id="8d11a-120">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="8d11a-120">BAM Management Utility</span></span>](../core/bam-management-utility.md)
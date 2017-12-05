---
title: "ビューにアクセス権を持つアカウントのユーザーを一覧表示する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- user accounts, BAM
- managing [BAM], user accounts
- Get-Accounts utility [BAM]
ms.assetid: 690fb45a-6de0-489e-9ddd-e88e29413c16
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c80a01aa9b4bd19581cb97f7fee127fc244322d4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-list-user-accounts-with-access-to-a-view"></a><span data-ttu-id="24768-102">ビューへのアクセス権を持つユーザー アカウントを一覧表示する方法</span><span class="sxs-lookup"><span data-stu-id="24768-102">How to List User Accounts With Access to a View</span></span>
<span data-ttu-id="24768-103">管理者を使用して、 **get アカウント**BAM 管理ユーティリティのコマンド一覧を取得する、すべてのユーザー アカウントのビュー ロールの場合、指定されたビューへのアクセス権を持つすべてのユーザー アカウントを意味します。</span><span class="sxs-lookup"><span data-stu-id="24768-103">Administrators use the **get-accounts** BAM Management utility command to get a list all user accounts for a view role, meaning all user accounts with access to the specified view.</span></span>  
  
 <span data-ttu-id="24768-104">BAM ビューを表示する方法については、次を参照してください。[リスト BAM ビューの表示方法](../core/how-to-list-bam-views.md)です。</span><span class="sxs-lookup"><span data-stu-id="24768-104">For information about viewing BAM views, see [How to List BAM Views](../core/how-to-list-bam-views.md).</span></span>  
  
### <a name="to-list-user-accounts-with-access-to-a-view"></a><span data-ttu-id="24768-105">ビューへのアクセス権を持つユーザー アカウントを一覧表示するには</span><span class="sxs-lookup"><span data-stu-id="24768-105">To list user accounts with access to a view</span></span>  
  
1.  <span data-ttu-id="24768-106">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="24768-106">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="24768-107">移動[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]追跡</span><span class="sxs-lookup"><span data-stu-id="24768-107">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking</span></span>  
  
3.  <span data-ttu-id="24768-108">型**bm get-アカウントの表示:\<ビュー名\>**です。</span><span class="sxs-lookup"><span data-stu-id="24768-108">Type **bm get-accounts -View:\<view name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="24768-109">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="24768-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="24768-110">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="24768-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24768-111">参照</span><span class="sxs-lookup"><span data-stu-id="24768-111">See Also</span></span>  
 <span data-ttu-id="24768-112">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="24768-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 [<span data-ttu-id="24768-113">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="24768-113">BAM Management Utility</span></span>](../core/bam-management-utility.md)
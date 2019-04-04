---
title: ビューにアクセス権を持つアカウントのユーザーの一覧を表示する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- user accounts, BAM
- managing [BAM], user accounts
- Get-Accounts utility [BAM]
ms.assetid: 690fb45a-6de0-489e-9ddd-e88e29413c16
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b8e27f1f48846c1eb134c2ee71bf9c00c72d4a2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981707"
---
# <a name="how-to-list-user-accounts-with-access-to-a-view"></a><span data-ttu-id="d5923-102">ビューへのアクセス権を持つユーザー アカウントを一覧表示する方法</span><span class="sxs-lookup"><span data-stu-id="d5923-102">How to List User Accounts With Access to a View</span></span>
<span data-ttu-id="d5923-103">管理者を使用して、 **get アカウント**ビュー ロールの場合、指定されたビューへのアクセスを持つすべてのユーザー アカウントを意味するすべてのユーザー アカウントの一覧を取得する BAM 管理ユーティリティ コマンド。</span><span class="sxs-lookup"><span data-stu-id="d5923-103">Administrators use the **get-accounts** BAM Management utility command to get a list all user accounts for a view role, meaning all user accounts with access to the specified view.</span></span>  
  
 <span data-ttu-id="d5923-104">BAM ビューを表示する方法については、[BAM ビューをリストする方法](../core/how-to-list-bam-views.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5923-104">For information about viewing BAM views, see [How to List BAM Views](../core/how-to-list-bam-views.md).</span></span>  
  
### <a name="to-list-user-accounts-with-access-to-a-view"></a><span data-ttu-id="d5923-105">ビューへのアクセス権を持つユーザー アカウントを一覧表示するには</span><span class="sxs-lookup"><span data-stu-id="d5923-105">To list user accounts with access to a view</span></span>  
  
1. <span data-ttu-id="d5923-106">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="d5923-106">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="d5923-107">移動します[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]追跡</span><span class="sxs-lookup"><span data-stu-id="d5923-107">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking</span></span>  
  
3. <span data-ttu-id="d5923-108">型**bm get-アカウントのビュー:\<ビュー名\>** します。</span><span class="sxs-lookup"><span data-stu-id="d5923-108">Type **bm get-accounts -View:\<view name\>**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d5923-109">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="d5923-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4. <span data-ttu-id="d5923-110">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d5923-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5923-111">参照</span><span class="sxs-lookup"><span data-stu-id="d5923-111">See Also</span></span>  
 <span data-ttu-id="d5923-112">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="d5923-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 [<span data-ttu-id="d5923-113">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="d5923-113">BAM Management Utility</span></span>](../core/bam-management-utility.md)
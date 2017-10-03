---
title: "ビューからアカウントを削除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Excel add-in [BAM], security
- managing [BAM], deleting accounts from views
- Remove-Account command [BAM]
ms.assetid: b74a64a0-ddb3-45d2-add7-6261c31be0f0
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80c0909a5544334cd9f0f8540ff5a4c357b851e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-accounts-from-a-view"></a><span data-ttu-id="2cc03-102">ビューからアカウントを削除する方法</span><span class="sxs-lookup"><span data-stu-id="2cc03-102">How to Remove Accounts from a View</span></span>
<span data-ttu-id="2cc03-103">管理者を使用して、**削除アカウント**コマンドを BAM ビューからユーザーを削除して、BAM Excel ワークシート ビューを不正アクセスから保護します。</span><span class="sxs-lookup"><span data-stu-id="2cc03-103">Administrators use the **remove-account** command to remove users from BAM views and protect BAM Excel Spreadsheet views from unauthorized access.</span></span>  
  
 <span data-ttu-id="2cc03-104">BAM ビューを表示する方法については、次を参照してください。[リスト BAM ビューの表示方法](../core/how-to-list-bam-views.md)です。</span><span class="sxs-lookup"><span data-stu-id="2cc03-104">For information about viewing BAM views, see [How to List BAM Views](../core/how-to-list-bam-views.md).</span></span>  
  
### <a name="to-remove-an-account-from-a-view"></a><span data-ttu-id="2cc03-105">ビューからアカウントを削除するには</span><span class="sxs-lookup"><span data-stu-id="2cc03-105">To remove an account from a view</span></span>  
  
1.  <span data-ttu-id="2cc03-106">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="2cc03-106">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="2cc03-107">移動[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]追跡</span><span class="sxs-lookup"><span data-stu-id="2cc03-107">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking</span></span>  
  
3.  <span data-ttu-id="2cc03-108">型**bm 削除アカウント-accountname:\<アカウント名 >-ビュー:\<ビュー名 >**です。</span><span class="sxs-lookup"><span data-stu-id="2cc03-108">Type **bm remove-account -AccountName:\<account name> -View:\<view name>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2cc03-109">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="2cc03-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="2cc03-110">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2cc03-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cc03-111">参照</span><span class="sxs-lookup"><span data-stu-id="2cc03-111">See Also</span></span>  
 <span data-ttu-id="2cc03-112">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="2cc03-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 [<span data-ttu-id="2cc03-113">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="2cc03-113">BAM Management Utility</span></span>](../core/bam-management-utility.md)
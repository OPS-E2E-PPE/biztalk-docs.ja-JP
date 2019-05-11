---
title: SSO を使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO]
- SSO, managing
ms.assetid: e7245632-9c71-4b1f-836d-a4ea1dd6e5ee
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b4ad2e75e8d66f0563e9bda2996383ab294970d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65321393"
---
# <a name="using-sso"></a><span data-ttu-id="2162d-102">SSO を使用してください。</span><span class="sxs-lookup"><span data-stu-id="2162d-102">Using SSO</span></span>
<span data-ttu-id="2162d-103">MMC スナップインまたはコマンドライン管理ユーティリティ (ssomanage) を使用して、SSO システムを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="2162d-103">You can use either the MMC Snap-in or the command line management utility (ssomanage) to manage the SSO system.</span></span> <span data-ttu-id="2162d-104">これには、SSO データベースを更新、追加すると、削除、および管理アプリケーションの場合、ユーザー マッピングの管理などのアクティビティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2162d-104">This includes activities such as updating the SSO database, adding, deleting, and managing applications, and administering user mappings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2162d-105">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を持つ SSO コマンド ライン ツールを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2162d-105">On a system that supports User Account Control (UAC), you may need to run the SSO command line tools with Administrative privileges.</span></span>  
  
 <span data-ttu-id="2162d-106">シングル サインオン管理者だけでは、これらのタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="2162d-106">Only Single Sign-On Administrators can perform these tasks.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2162d-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2162d-107">In This Section</span></span>  
  
-   [<span data-ttu-id="2162d-108">SSO サーバーを設定する方法</span><span class="sxs-lookup"><span data-stu-id="2162d-108">How to Set the SSO Server</span></span>](../core/how-to-set-the-sso-server.md)  
  
-   [<span data-ttu-id="2162d-109">SSO を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="2162d-109">How to Enable SSO</span></span>](../core/how-to-enable-sso.md)  
  
-   [<span data-ttu-id="2162d-110">マスター シークレット サーバーを変更する方法</span><span class="sxs-lookup"><span data-stu-id="2162d-110">How to Change the Master Secret Server</span></span>](../core/how-to-change-the-master-secret-server.md)  
  
-   [<span data-ttu-id="2162d-111">SSO を無効にする方法</span><span class="sxs-lookup"><span data-stu-id="2162d-111">How to Disable SSO</span></span>](../core/how-to-disable-sso.md)  
  
-   [<span data-ttu-id="2162d-112">SSO データベースを更新する方法</span><span class="sxs-lookup"><span data-stu-id="2162d-112">How to Update the SSO Database</span></span>](../core/how-to-update-the-sso-database.md)  
  
-   [<span data-ttu-id="2162d-113">SSO データベース情報を表示する方法</span><span class="sxs-lookup"><span data-stu-id="2162d-113">How to Display the SSO Database Information</span></span>](../core/how-to-display-the-sso-database-information.md)  
  
-   [<span data-ttu-id="2162d-114">SSO チケットを構成する方法</span><span class="sxs-lookup"><span data-stu-id="2162d-114">How to Configure the SSO Tickets</span></span>](../core/how-to-configure-the-sso-tickets.md)  
  
-   [<span data-ttu-id="2162d-115">SSO を監査する方法</span><span class="sxs-lookup"><span data-stu-id="2162d-115">How to Audit SSO</span></span>](../core/how-to-audit-sso.md)  
  
-   [<span data-ttu-id="2162d-116">SSO の SSL を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="2162d-116">How to Enable SSL for SSO</span></span>](../core/how-to-enable-ssl-for-sso.md)  
  
-   [<span data-ttu-id="2162d-117">マスター シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="2162d-117">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)  
  
-   [<span data-ttu-id="2162d-118">SSO 管理者を指定し、関連管理者アカウントの方法</span><span class="sxs-lookup"><span data-stu-id="2162d-118">How to Specify SSO Administrators and Affiliate Administrators Accounts</span></span>](../core/how-to-specify-sso-administrators-and-affiliate-administrators-accounts.md)  
  
-   [<span data-ttu-id="2162d-119">関連アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="2162d-119">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)  
  
-   [<span data-ttu-id="2162d-120">ユーザー マッピングの管理</span><span class="sxs-lookup"><span data-stu-id="2162d-120">Managing User Mappings</span></span>](../core/managing-user-mappings.md)  
  
-   [<span data-ttu-id="2162d-121">ホスト側開始 SSO</span><span class="sxs-lookup"><span data-stu-id="2162d-121">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)
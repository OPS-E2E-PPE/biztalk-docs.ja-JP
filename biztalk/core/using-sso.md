---
title: SSO を使用して |Microsoft ドキュメント
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
ms.openlocfilehash: 850425f140b526baf251568f09ab47db9115e8ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287818"
---
# <a name="using-sso"></a><span data-ttu-id="36db2-102">SSO の使用</span><span class="sxs-lookup"><span data-stu-id="36db2-102">Using SSO</span></span>
<span data-ttu-id="36db2-103">SSO システムは、MMC スナップインまたはコマンド ライン管理ユーティリティ (ssomanage) を使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="36db2-103">You can use either the MMC Snap-in or the command line management utility (ssomanage) to manage the SSO system.</span></span> <span data-ttu-id="36db2-104">管理作業には、データベースの更新、アプリケーションの追加、削除、管理、およびユーザー マッピングの管理などのアクティビティがあります。</span><span class="sxs-lookup"><span data-stu-id="36db2-104">This includes activities such as updating the SSO database, adding, deleting, and managing applications, and administering user mappings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36db2-105">ユーザー アカウント制御 (UAC) をサポートするシステムでは、SSO コマンドライン ツールを管理者特権で実行する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="36db2-105">On a system that supports User Account Control (UAC), you may need to run the SSO command line tools with Administrative privileges.</span></span>  
  
 <span data-ttu-id="36db2-106">これらの作業を実行できるのは、シングル サインオン管理者だけです。</span><span class="sxs-lookup"><span data-stu-id="36db2-106">Only Single Sign-On Administrators can perform these tasks.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="36db2-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="36db2-107">In This Section</span></span>  
  
-   [<span data-ttu-id="36db2-108">SSO サーバーを設定する方法</span><span class="sxs-lookup"><span data-stu-id="36db2-108">How to Set the SSO Server</span></span>](../core/how-to-set-the-sso-server.md)  
  
-   [<span data-ttu-id="36db2-109">SSO を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="36db2-109">How to Enable SSO</span></span>](../core/how-to-enable-sso.md)  
  
-   [<span data-ttu-id="36db2-110">マスター シークレット サーバーを変更する方法</span><span class="sxs-lookup"><span data-stu-id="36db2-110">How to Change the Master Secret Server</span></span>](../core/how-to-change-the-master-secret-server.md)  
  
-   [<span data-ttu-id="36db2-111">SSO を無効にする方法</span><span class="sxs-lookup"><span data-stu-id="36db2-111">How to Disable SSO</span></span>](../core/how-to-disable-sso.md)  
  
-   [<span data-ttu-id="36db2-112">SSO データベースを更新する方法</span><span class="sxs-lookup"><span data-stu-id="36db2-112">How to Update the SSO Database</span></span>](../core/how-to-update-the-sso-database.md)  
  
-   [<span data-ttu-id="36db2-113">SSO データベース情報を表示する方法</span><span class="sxs-lookup"><span data-stu-id="36db2-113">How to Display the SSO Database Information</span></span>](../core/how-to-display-the-sso-database-information.md)  
  
-   [<span data-ttu-id="36db2-114">SSO チケットを構成する方法</span><span class="sxs-lookup"><span data-stu-id="36db2-114">How to Configure the SSO Tickets</span></span>](../core/how-to-configure-the-sso-tickets.md)  
  
-   [<span data-ttu-id="36db2-115">SSO を監査する方法</span><span class="sxs-lookup"><span data-stu-id="36db2-115">How to Audit SSO</span></span>](../core/how-to-audit-sso.md)  
  
-   [<span data-ttu-id="36db2-116">SSO の SSL を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="36db2-116">How to Enable SSL for SSO</span></span>](../core/how-to-enable-ssl-for-sso.md)  
  
-   [<span data-ttu-id="36db2-117">マスタ シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="36db2-117">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)  
  
-   [<span data-ttu-id="36db2-118">SSO 管理者を指定し、関連管理者アカウント方法</span><span class="sxs-lookup"><span data-stu-id="36db2-118">How to Specify SSO Administrators and Affiliate Administrators Accounts</span></span>](../core/how-to-specify-sso-administrators-and-affiliate-administrators-accounts.md)  
  
-   [<span data-ttu-id="36db2-119">関連アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="36db2-119">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)  
  
-   [<span data-ttu-id="36db2-120">ユーザー マッピングを管理します。</span><span class="sxs-lookup"><span data-stu-id="36db2-120">Managing User Mappings</span></span>](../core/managing-user-mappings.md)  
  
-   [<span data-ttu-id="36db2-121">ホスト側開始 SSO</span><span class="sxs-lookup"><span data-stu-id="36db2-121">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)
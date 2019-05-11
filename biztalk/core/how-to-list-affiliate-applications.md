---
title: 関連アプリケーションの一覧を表示する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO applications], listing applications
- applications [SSO], listing applications
ms.assetid: b51ff597-824e-4488-a47f-3a9b3d4437c6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b254be21078a53f7efa7291606bdd0038466bb3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336930"
---
# <a name="how-to-list-affiliate-applications"></a><span data-ttu-id="ae960-102">関連アプリケーションの一覧を表示する方法</span><span class="sxs-lookup"><span data-stu-id="ae960-102">How to List Affiliate Applications</span></span>
<span data-ttu-id="ae960-103">このコマンドを使用して、すべての関連アプリケーションの一覧します。</span><span class="sxs-lookup"><span data-stu-id="ae960-103">Use this command to list all the affiliate applications.</span></span> <span data-ttu-id="ae960-104">ユーザーがアプリケーション管理者アカウントのメンバーである場合は、このコマンドは、ユーザーが管理者アプリケーションをしか表示されません。</span><span class="sxs-lookup"><span data-stu-id="ae960-104">If the user is a member of the Application Administrators account, this command will only display the application for which the user is an administrator.</span></span>  
  
### <a name="to-list-affiliate-applications-using-the-administration-utility"></a><span data-ttu-id="ae960-105">管理ユーティリティを使用して関連アプリケーションの一覧表示する</span><span class="sxs-lookup"><span data-stu-id="ae960-105">To list affiliate applications using the administration utility</span></span>  
  
1.  <span data-ttu-id="ae960-106">**開始** メニューのをクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="ae960-106">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="ae960-107">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="ae960-107">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="ae960-108">既定のインストール ディレクトリは\<*ドライブ*\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="ae960-108">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="ae960-109">型**ssomanage-listapps [all]** 場所**すべて**省略可能なパラメーターで、構成ストアの機能を使用してアプリケーションにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae960-109">Type **ssomanage -listapps [all]** where **all** is an optional parameter that will also display applications using the Configuration Store feature.</span></span> <span data-ttu-id="ae960-110">このコマンドを実行しているユーザーがアプリケーション管理者である場合は、それらが管理者アプリケーションのみが一覧されます。</span><span class="sxs-lookup"><span data-stu-id="ae960-110">If the user running this command is an Application administrator, it will only list the applications for which they are an administrator.</span></span> <span data-ttu-id="ae960-111">このコマンドを実行しているユーザーが関連管理者または SSO 管理者の場合は、すべての関連アプリケーションが一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="ae960-111">If the user running this command is an Affiliate Administrator or an SSO Administrator, it will list all the affiliate applications.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ae960-112">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="ae960-112">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-list-affiliate-applications-using-the-client-utility"></a><span data-ttu-id="ae960-113">クライアント ユーティリティを使用して関連アプリケーションの一覧表示する</span><span class="sxs-lookup"><span data-stu-id="ae960-113">To list affiliate applications using the client utility</span></span>  
  
1.  <span data-ttu-id="ae960-114">**開始** メニューのをクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="ae960-114">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="ae960-115">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="ae960-115">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="ae960-116">既定のインストール ディレクトリは\<*ドライブ*\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="ae960-116">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="ae960-117">型**ssoclient – listapps**を関連アプリケーションを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="ae960-117">Type **ssoclient –listapps** to list the affiliate applications.</span></span> <span data-ttu-id="ae960-118">つまりに、このタスクを実行するユーザーのメンバーである関連アプリケーションのみを一覧表示これは、その関連アプリケーションのアプリケーション ユーザー グループ アカウントが所属する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae960-118">This will list only the affiliate applications that the user performing this task is a member of, i.e., they need to belong the application user group account for that affiliate application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ae960-119">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="ae960-119">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae960-120">参照</span><span class="sxs-lookup"><span data-stu-id="ae960-120">See Also</span></span>  
 <span data-ttu-id="ae960-121">[SSO 関連アプリケーション](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="ae960-121">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="ae960-122">[関連アプリケーションを作成する方法](../core/how-to-create-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="ae960-122">[How to Create an Affiliate Application](../core/how-to-create-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="ae960-123">[ユーザー マッピングの管理](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="ae960-123">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="ae960-124">関連アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="ae960-124">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)
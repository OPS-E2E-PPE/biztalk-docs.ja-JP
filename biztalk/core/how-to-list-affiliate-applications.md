---
title: "関連アプリケーションを一覧表示する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [SSO applications], listing applications
- applications [SSO], listing applications
ms.assetid: b51ff597-824e-4488-a47f-3a9b3d4437c6
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f6c4d4e4118bfe5f5cab7a9c44e770dd12656c7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-list-affiliate-applications"></a><span data-ttu-id="d90cf-102">関連アプリケーションを一覧表示する方法</span><span class="sxs-lookup"><span data-stu-id="d90cf-102">How to List Affiliate Applications</span></span>
<span data-ttu-id="d90cf-103">ここで示すコマンドを使用すると、関連アプリケーションをすべて一覧表示できます。</span><span class="sxs-lookup"><span data-stu-id="d90cf-103">Use this command to list all the affiliate applications.</span></span> <span data-ttu-id="d90cf-104">ユーザーがアプリケーション管理者アカウントのメンバーである場合、このコマンドを実行すると、そのユーザーが管理者であるアプリケーションだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d90cf-104">If the user is a member of the Application Administrators account, this command will only display the application for which the user is an administrator.</span></span>  
  
### <a name="to-list-affiliate-applications-using-the-administration-utility"></a><span data-ttu-id="d90cf-105">管理ユーティリティを使用して関連アプリケーションを一覧表示するには</span><span class="sxs-lookup"><span data-stu-id="d90cf-105">To list affiliate applications using the administration utility</span></span>  
  
1.  <span data-ttu-id="d90cf-106">**開始** メニューのをクリックして**実行**、し、入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="d90cf-106">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="d90cf-107">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="d90cf-107">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="d90cf-108">既定のインストール ディレクトリは\<*ドライブ*\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="d90cf-108">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="d90cf-109">型**ssomanage-listapps [all]**場所**すべて**省略可能なパラメーターで、構成ストアの機能を使用してアプリケーションにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="d90cf-109">Type **ssomanage -listapps [all]** where **all** is an optional parameter that will also display applications using the Configuration Store feature.</span></span> <span data-ttu-id="d90cf-110">このコマンドを実行するユーザーがアプリケーション管理者である場合、そのユーザーが管理者であるアプリケーションだけが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="d90cf-110">If the user running this command is an Application administrator, it will only list the applications for which they are an administrator.</span></span> <span data-ttu-id="d90cf-111">このコマンドを実行するユーザーが関連管理者または SSO 管理者である場合、すべての関連アプリケーションが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="d90cf-111">If the user running this command is an Affiliate Administrator or an SSO Administrator, it will list all the affiliate applications.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d90cf-112">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="d90cf-112">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-list-affiliate-applications-using-the-client-utility"></a><span data-ttu-id="d90cf-113">クライアント ユーティリティを使用して関連アプリケーションを一覧表示するには</span><span class="sxs-lookup"><span data-stu-id="d90cf-113">To list affiliate applications using the client utility</span></span>  
  
1.  <span data-ttu-id="d90cf-114">**開始** メニューのをクリックして**実行**、し、入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="d90cf-114">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="d90cf-115">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="d90cf-115">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="d90cf-116">既定のインストール ディレクトリは\<*ドライブ*\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="d90cf-116">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="d90cf-117">型**ssoclient – listapps**関連アプリケーションを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="d90cf-117">Type **ssoclient –listapps** to list the affiliate applications.</span></span> <span data-ttu-id="d90cf-118">これによって一覧表示されるのは、このタスクを実行しているユーザーがメンバーである関連アプリケーションだけです。つまり、ユーザーは一覧表示する関連アプリケーションのアプリケーション ユーザー グループ アカウントに属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d90cf-118">This will list only the affiliate applications that the user performing this task is a member of, i.e., they need to belong the application user group account for that affiliate application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d90cf-119">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="d90cf-119">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d90cf-120">参照</span><span class="sxs-lookup"><span data-stu-id="d90cf-120">See Also</span></span>  
 <span data-ttu-id="d90cf-121">[SSO 関連アプリケーション](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="d90cf-121">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="d90cf-122">[関連アプリケーションを作成する方法](../core/how-to-create-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="d90cf-122">[How to Create an Affiliate Application](../core/how-to-create-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="d90cf-123">[ユーザー マッピングを管理します。](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="d90cf-123">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="d90cf-124">関連アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="d90cf-124">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)
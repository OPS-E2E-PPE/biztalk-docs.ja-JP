---
title: ユーザー マッピングを一覧表示する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO maps], listing maps
- maps [SSO], listing maps
ms.assetid: f9b73785-3a59-45c8-9e88-d2d16b5a46aa
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04f988e9f63cccf27c42a33727d86452d34915aa
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972152"
---
# <a name="how-to-list-user-mappings"></a><span data-ttu-id="b62ba-102">ユーザー マッピングを一覧表示する方法</span><span class="sxs-lookup"><span data-stu-id="b62ba-102">How to List User Mappings</span></span>
<span data-ttu-id="b62ba-103">ここで示すコマンドを使用すると、指定したユーザーの既存のマッピングすべてを一覧表示できます。</span><span class="sxs-lookup"><span data-stu-id="b62ba-103">Use this command to list all the existing mappings for the specified user.</span></span>  
  
 <span data-ttu-id="b62ba-104">この作業を行うには、SSO 管理者、アプリケーション管理者、SSO 関連管理者、またはユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b62ba-104">You must be an SSO administrator, application administrator, SSO affiliate administrator, or user to do this task.</span></span>  
  
 <span data-ttu-id="b62ba-105">(E) として表示される有効なユーザー マッピング\<*ドメイン*\>\\*\<username\>* 無効になっているときに、(D)としてユーザーマッピングが表示されます\<*ドメイン*\>\\*\<username\>* です。</span><span class="sxs-lookup"><span data-stu-id="b62ba-105">Enabled user mappings appear as (E) \<*domain*\>\\*\<username\>*, while disabled user mappings appear as (D) \<*domain*\>\\*\<username\>*.</span></span>  
  
### <a name="to-list-user-mappings-using-the-administration-utility"></a><span data-ttu-id="b62ba-106">管理ユーティリティを使用してユーザー マッピングを一覧表示するには</span><span class="sxs-lookup"><span data-stu-id="b62ba-106">To list user mappings using the administration utility</span></span>  
  
1.  <span data-ttu-id="b62ba-107">**開始** メニューのをクリックして**実行**、し、入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="b62ba-107">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="b62ba-108">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="b62ba-108">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="b62ba-109">既定のインストール ディレクトリは\<*ドライブ*\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="b62ba-109">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="b62ba-110">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b62ba-110">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="b62ba-111">型**ssomanage – listmappings *\<ドメイン\>\\< ユーザー名\>*** 関連アプリケーション内の特定のユーザーがすべてのマッピングを一覧表示登録したが属している、where *\<ドメイン\>* は、Microsoft Windows ドメイン ユーザー アカウントと *\<username\>* は、ユーザー マッピングを一覧表示する Windows ユーザー名。</span><span class="sxs-lookup"><span data-stu-id="b62ba-111">Type **ssomanage –listmappings *\<domain\>\\<username\>*** to list all the mappings a given user has in the affiliate applications he/she belongs to, where *\<domain\>* is the Microsoft Windows domain for the user account, and *\<username\>* is the Windows user name for which you want to list the user mappings.</span></span> <span data-ttu-id="b62ba-112">ユーザーが関連管理者または SSO 管理者である場合にこのコマンドを実行すると、すべての関連アプリケーションを対象に、そのユーザーのすべてのマッピングが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="b62ba-112">If the user is an Affiliate Administrator or an SSO Administrator, this command will list all the mappings for that user in all the affiliate applications.</span></span>  
  
         <span data-ttu-id="b62ba-113">または</span><span class="sxs-lookup"><span data-stu-id="b62ba-113">Or</span></span>  
  
    -   <span data-ttu-id="b62ba-114">型**ssomanage – listmappings *\<アプリケーション名\>*** 特定のアプリケーションのすべてのユーザー マッピングを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="b62ba-114">Type **ssomanage –listmappings *\<application name\>*** to list all the user mappings for a given application.</span></span>  
  
         <span data-ttu-id="b62ba-115">または</span><span class="sxs-lookup"><span data-stu-id="b62ba-115">Or</span></span>  
  
    -   <span data-ttu-id="b62ba-116">アプリケーション管理者の場合は、入力**ssomanage – listmappings *\<ドメイン\>\\< ユーザー名\>*  *\<アプリケーション名\>*** 特定のユーザーが管理者になっている関連アプリケーションがすべてのマッピングを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="b62ba-116">If you are an application administrator, type **ssomanage –listmappings *\<domain\>\\<username\>* *\<application name\>*** to list all the mappings a given user has in the affiliate applications for which you are an administrator.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b62ba-117">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="b62ba-117">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-list-user-mappings-using-the-client-utility"></a><span data-ttu-id="b62ba-118">クライアント ユーティリティを使用してユーザー マッピングを一覧表示するには</span><span class="sxs-lookup"><span data-stu-id="b62ba-118">To list user mappings using the client utility</span></span>  
  
1.  <span data-ttu-id="b62ba-119">**開始** メニューのをクリックして**実行**、し、入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="b62ba-119">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="b62ba-120">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="b62ba-120">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="b62ba-121">既定のインストール ディレクトリは\<*ドライブ*\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="b62ba-121">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="b62ba-122">型**ssoclient – listmappings**があるすべてのマッピングを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="b62ba-122">Type **ssoclient –listmappings** to list all the mappings you have.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b62ba-123">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="b62ba-123">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b62ba-124">参照</span><span class="sxs-lookup"><span data-stu-id="b62ba-124">See Also</span></span>  
 <span data-ttu-id="b62ba-125">[ユーザー マッピングを作成する方法](../core/how-to-create-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="b62ba-125">[How to Create User Mappings](../core/how-to-create-user-mappings.md) </span></span>  
 <span data-ttu-id="b62ba-126">[SSO マッピング](../core/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="b62ba-126">[SSO Mappings](../core/sso-mappings.md) </span></span>  
 <span data-ttu-id="b62ba-127">[関連アプリケーションの管理](../core/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="b62ba-127">[Managing Affiliate Applications](../core/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="b62ba-128">ユーザー マッピングの管理</span><span class="sxs-lookup"><span data-stu-id="b62ba-128">Managing User Mappings</span></span>](../core/managing-user-mappings.md)
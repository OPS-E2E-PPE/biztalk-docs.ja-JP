---
title: SSO サーバーを設定する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- servers, selecting [SSO]
- SSO, selecting servers
- managing [SSO], selecting servers
- SSOManage [SSO]
ms.assetid: a0b0176d-b426-4ab1-8a7e-1f96f4214683
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 804c1da3cec2fa13d82d6b0c9a7ae5f2e33989ed
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334119"
---
# <a name="how-to-set-the-sso-server"></a><span data-ttu-id="0978c-102">SSO サーバーを設定する方法</span><span class="sxs-lookup"><span data-stu-id="0978c-102">How to Set the SSO Server</span></span>
<span data-ttu-id="0978c-103">Ssomanage を使用するたびに接続するシングル サインオン サーバーにユーザーをまずポイントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0978c-103">Each time you use ssomanage, you must first point the user to the Single Sign-On server you want to connect to.</span></span>  
  
 <span data-ttu-id="0978c-104">2 つの方法のいずれかでこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0978c-104">You can do this in one of two ways:</span></span>  
  
-   <span data-ttu-id="0978c-105">個々 のユーザーは、正しいシングル サインオン サーバーをそれ自体をポイントできます。</span><span class="sxs-lookup"><span data-stu-id="0978c-105">Individual users can point themselves to the correct Single Sign-On Server.</span></span>  
  
-   <span data-ttu-id="0978c-106">シングル サインオン サーバーのローカル コンピューターの管理者は、このサーバーをシングル サインオン ユーザー アカウントのすべてのメンバーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0978c-106">A local computer administrator for the Single Sign-On server can point all the members of the Single Sign-On Users account to this server.</span></span>  
  
### <a name="to-set-the-enterprise-single-sign-on-server-using-the-mmc-snap-in"></a><span data-ttu-id="0978c-107">エンタープライズ シングル サインオン サーバー MMC スナップインを使用して設定するには</span><span class="sxs-lookup"><span data-stu-id="0978c-107">To set the Enterprise Single Sign-On Server using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="0978c-108">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、順にクリックします**SSO 管理**します。</span><span class="sxs-lookup"><span data-stu-id="0978c-108">Click **Start**, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="0978c-109">MMC スナップインで、**コンソール ルート**を右クリックして**エンタープライズ シングル サインオン**、 をクリック**選択**します。</span><span class="sxs-lookup"><span data-stu-id="0978c-109">In the MMC Snap-In under the **Console Root**, right-click **Enterprise Single Sign-On**, and click **Select**.</span></span>  
  
3.  <span data-ttu-id="0978c-110">目的のサーバーに移動します。</span><span class="sxs-lookup"><span data-stu-id="0978c-110">Browse to the desired server.</span></span>  
  
4.  <span data-ttu-id="0978c-111">必要に応じて、、**すべてのユーザーの SSO サーバーを設定**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="0978c-111">If appropriate, select the **Set SSO Server for all users** check box.</span></span>  
  
5.  <span data-ttu-id="0978c-112">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0978c-112">Click **OK**.</span></span>  
  
### <a name="to-set-the-enterprise-single-sign-on-server-for-a-single-user-using-the-command-line"></a><span data-ttu-id="0978c-113">コマンドラインを使用して 1 人のユーザーのエンタープライズ シングル サインオン サーバーを設定するには</span><span class="sxs-lookup"><span data-stu-id="0978c-113">To set the Enterprise Single Sign-On Server for a single user using the command line</span></span>  
  
1.  <span data-ttu-id="0978c-114">**開始** メニューのをクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="0978c-114">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="0978c-115">コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="0978c-115">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="0978c-116">既定のインストール ディレクトリは**\<ドライブ\>**: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="0978c-116">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="0978c-117">型**ssomanage – server \<SSO サーバー名\>** ここで、  **\<SSO サーバー名\>** シングル サインオン サーバーのコンピューター名をユーザーには接続しようとしています。</span><span class="sxs-lookup"><span data-stu-id="0978c-117">Type **ssomanage –server \<SSO server name\>**, where **\<SSO server name\>** is the computer name of the Single Sign-On Server the user wants to connect to.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0978c-118">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="0978c-118">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-set-the-enterprise-single-sign-on-server-for-all-users-using-the-command-line"></a><span data-ttu-id="0978c-119">コマンドラインを使用してすべてのユーザーに対してエンタープライズ シングル サインオン サーバーを設定するには</span><span class="sxs-lookup"><span data-stu-id="0978c-119">To set the Enterprise Single Sign-On Server for all users using the command line</span></span>  
  
1.  <span data-ttu-id="0978c-120">**開始** メニューのをクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="0978c-120">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="0978c-121">コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="0978c-121">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="0978c-122">既定のインストール ディレクトリは**\<ドライブ\>**: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="0978c-122">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="0978c-123">型**ssomanage – serverall \<SSO サーバー名\>** ここで、  **\<SSO サーバー名\>** はシングル サインオン サーバーのすべてのコンピューター名ですシングル サインオン ユーザー アカウントのメンバーが指すされます。</span><span class="sxs-lookup"><span data-stu-id="0978c-123">Type **ssomanage –serverall \<SSO server name\>**, where **\<SSO server name\>** is the computer name of the Single Sign-On Server all members of the Single Sign-On Users account will be pointed to.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0978c-124">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="0978c-124">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-determine-the-enterprise-single-sign-on-server-to-which-a-user-is-connected-using-the-command-line"></a><span data-ttu-id="0978c-125">エンタープライズ シングル サインオン サーバーのコマンドラインを使用して、ユーザーの接続先を決定するには</span><span class="sxs-lookup"><span data-stu-id="0978c-125">To determine the Enterprise Single Sign-On Server to which a user is connected using the command line</span></span>  
  
1.  <span data-ttu-id="0978c-126">**開始** メニューのをクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="0978c-126">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="0978c-127">コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="0978c-127">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="0978c-128">既定のインストール ディレクトリは**\<ドライブ\>**: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="0978c-128">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="0978c-129">型**ssomanage – showserver**します。</span><span class="sxs-lookup"><span data-stu-id="0978c-129">Type **ssomanage –showserver**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0978c-130">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="0978c-130">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0978c-131">このコマンドは、存在する場合、現在のユーザーも他のユーザーの設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="0978c-131">This command displays the settings for the current user as well as for other users if they exist.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0978c-132">参照</span><span class="sxs-lookup"><span data-stu-id="0978c-132">See Also</span></span>  
 <span data-ttu-id="0978c-133">[SSO を有効にする方法](../core/how-to-enable-sso.md) </span><span class="sxs-lookup"><span data-stu-id="0978c-133">[How to Enable SSO](../core/how-to-enable-sso.md) </span></span>  
 <span data-ttu-id="0978c-134">[SSO を無効にする方法](../core/how-to-disable-sso.md) </span><span class="sxs-lookup"><span data-stu-id="0978c-134">[How to Disable SSO](../core/how-to-disable-sso.md) </span></span>  
 <span data-ttu-id="0978c-135">[SSO データベース情報を表示する方法](../core/how-to-display-the-sso-database-information.md) </span><span class="sxs-lookup"><span data-stu-id="0978c-135">[How to Display the SSO Database Information](../core/how-to-display-the-sso-database-information.md) </span></span>  
 [<span data-ttu-id="0978c-136">SSO の使用</span><span class="sxs-lookup"><span data-stu-id="0978c-136">Using SSO</span></span>](../core/using-sso.md)
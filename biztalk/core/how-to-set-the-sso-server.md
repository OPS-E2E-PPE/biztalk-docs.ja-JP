---
title: SSO サーバーを設定する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: c7dab9df7b5444b437f12737c37036b592a70aad
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972168"
---
# <a name="how-to-set-the-sso-server"></a><span data-ttu-id="33769-102">SSO サーバーを設定する方法</span><span class="sxs-lookup"><span data-stu-id="33769-102">How to Set the SSO Server</span></span>
<span data-ttu-id="33769-103">ssomanage を使用するたびに、まず、ユーザーが接続先のシングル サインオン サーバーを参照するように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33769-103">Each time you use ssomanage, you must first point the user to the Single Sign-On server you want to connect to.</span></span>  
  
 <span data-ttu-id="33769-104">これは、次の 2 つの方法のいずれかで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="33769-104">You can do this in one of two ways:</span></span>  
  
-   <span data-ttu-id="33769-105">各ユーザーが、自分自身が正しいシングル サインオン サーバーを参照するように設定します。</span><span class="sxs-lookup"><span data-stu-id="33769-105">Individual users can point themselves to the correct Single Sign-On Server.</span></span>  
  
-   <span data-ttu-id="33769-106">シングル サインオン サーバーのローカルのコンピューター管理者が、シングル サインオン ユーザーのすべてのメンバーがこのサーバーを参照するように設定します。</span><span class="sxs-lookup"><span data-stu-id="33769-106">A local computer administrator for the Single Sign-On server can point all the members of the Single Sign-On Users account to this server.</span></span>  
  
### <a name="to-set-the-enterprise-single-sign-on-server-using-the-mmc-snap-in"></a><span data-ttu-id="33769-107">MMC スナップインでエンタープライズ シングル サインオン サーバーを設定するには</span><span class="sxs-lookup"><span data-stu-id="33769-107">To set the Enterprise Single Sign-On Server using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="33769-108">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、順にクリック**SSO 管理**です。</span><span class="sxs-lookup"><span data-stu-id="33769-108">Click **Start**, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="33769-109">MMC スナップインで、**コンソール ルート**を右クリックして**エンタープライズ シングル サインオン**、 をクリック**選択**です。</span><span class="sxs-lookup"><span data-stu-id="33769-109">In the MMC Snap-In under the **Console Root**, right-click **Enterprise Single Sign-On**, and click **Select**.</span></span>  
  
3.  <span data-ttu-id="33769-110">対象のサーバーを参照します。</span><span class="sxs-lookup"><span data-stu-id="33769-110">Browse to the desired server.</span></span>  
  
4.  <span data-ttu-id="33769-111">必要に応じて、、**すべてのユーザーの SSO サーバーの設定**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="33769-111">If appropriate, select the **Set SSO Server for all users** check box.</span></span>  
  
5.  <span data-ttu-id="33769-112">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33769-112">Click **OK**.</span></span>  
  
### <a name="to-set-the-enterprise-single-sign-on-server-for-a-single-user-using-the-command-line"></a><span data-ttu-id="33769-113">コマンド ラインで 1 人のユーザーに対してエンタープライズ シングル サインオン サーバーを設定するには</span><span class="sxs-lookup"><span data-stu-id="33769-113">To set the Enterprise Single Sign-On Server for a single user using the command line</span></span>  
  
1.  <span data-ttu-id="33769-114">**開始** メニューのをクリックして**実行**、し、入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="33769-114">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="33769-115">コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="33769-115">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="33769-116">既定のインストール ディレクトリは**\<ドライブ\>**: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="33769-116">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="33769-117">型**ssomanage – server \<SSO サーバー名\>** ここで、  **\<SSO サーバー名\>** シングル サインオン サーバーのコンピューター名をユーザーには接続しようとしています。</span><span class="sxs-lookup"><span data-stu-id="33769-117">Type **ssomanage –server \<SSO server name\>**, where **\<SSO server name\>** is the computer name of the Single Sign-On Server the user wants to connect to.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="33769-118">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="33769-118">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-set-the-enterprise-single-sign-on-server-for-all-users-using-the-command-line"></a><span data-ttu-id="33769-119">コマンド ラインですべてのユーザーに対してエンタープライズ シングル サインオン サーバーを設定するには</span><span class="sxs-lookup"><span data-stu-id="33769-119">To set the Enterprise Single Sign-On Server for all users using the command line</span></span>  
  
1.  <span data-ttu-id="33769-120">**開始** メニューのをクリックして**実行**、し、入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="33769-120">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="33769-121">コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="33769-121">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="33769-122">既定のインストール ディレクトリは**\<ドライブ\>**: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="33769-122">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="33769-123">型**ssomanage – serverall \<SSO サーバー名\>** ここで、  **\<SSO サーバー名\>** シングル サインオン サーバーのすべてのコンピューター名にはシングル サインオン ユーザー アカウントのメンバーが指すされます。</span><span class="sxs-lookup"><span data-stu-id="33769-123">Type **ssomanage –serverall \<SSO server name\>**, where **\<SSO server name\>** is the computer name of the Single Sign-On Server all members of the Single Sign-On Users account will be pointed to.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="33769-124">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="33769-124">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-determine-the-enterprise-single-sign-on-server-to-which-a-user-is-connected-using-the-command-line"></a><span data-ttu-id="33769-125">コマンド ラインでユーザーが接続されているエンタープライズ シングル サインオン サーバーを特定するには</span><span class="sxs-lookup"><span data-stu-id="33769-125">To determine the Enterprise Single Sign-On Server to which a user is connected using the command line</span></span>  
  
1.  <span data-ttu-id="33769-126">**開始** メニューのをクリックして**実行**、し、入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="33769-126">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="33769-127">コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="33769-127">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="33769-128">既定のインストール ディレクトリは**\<ドライブ\>**: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="33769-128">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="33769-129">型**ssomanage – showserver**です。</span><span class="sxs-lookup"><span data-stu-id="33769-129">Type **ssomanage –showserver**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="33769-130">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="33769-130">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33769-131">このコマンドでは、現在のユーザーの設定だけでなく、存在する場合は他のユーザーの設定も表示されます。</span><span class="sxs-lookup"><span data-stu-id="33769-131">This command displays the settings for the current user as well as for other users if they exist.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33769-132">参照</span><span class="sxs-lookup"><span data-stu-id="33769-132">See Also</span></span>  
 <span data-ttu-id="33769-133">[SSO を有効にする方法](../core/how-to-enable-sso.md) </span><span class="sxs-lookup"><span data-stu-id="33769-133">[How to Enable SSO](../core/how-to-enable-sso.md) </span></span>  
 <span data-ttu-id="33769-134">[SSO を無効にする方法](../core/how-to-disable-sso.md) </span><span class="sxs-lookup"><span data-stu-id="33769-134">[How to Disable SSO](../core/how-to-disable-sso.md) </span></span>  
 <span data-ttu-id="33769-135">[SSO データベース情報を表示する方法](../core/how-to-display-the-sso-database-information.md) </span><span class="sxs-lookup"><span data-stu-id="33769-135">[How to Display the SSO Database Information](../core/how-to-display-the-sso-database-information.md) </span></span>  
 [<span data-ttu-id="33769-136">SSO の使用</span><span class="sxs-lookup"><span data-stu-id="33769-136">Using SSO</span></span>](../core/using-sso.md)
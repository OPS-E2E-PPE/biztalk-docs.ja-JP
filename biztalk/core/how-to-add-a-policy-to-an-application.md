---
title: "アプリケーションにポリシーを追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [policies], adding to applications
- policies, applications
- applications, policies
- policies, adding to applications
ms.assetid: 93b3ce5e-8c63-4c64-9bdc-1747541ba9a8
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ad9eaf1e2f14e51e60ad3f18e31cdaa72fa906a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-policy-to-an-application"></a><span data-ttu-id="2a231-102">ポリシーをアプリケーションに追加する方法</span><span class="sxs-lookup"><span data-stu-id="2a231-102">How to Add a Policy to an Application</span></span>
<span data-ttu-id="2a231-103">このトピックでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、BizTalk アプリケーションにポリシーを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2a231-103">This topic describes how to use the BizTalk Server Administration console or the command line to add a policy to a BizTalk application.</span></span> <span data-ttu-id="2a231-104">管理コンソールを使用する場合は、一度に複数のポリシーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="2a231-104">When using the administration console, you can add more than one policy at a time.</span></span> <span data-ttu-id="2a231-105">ポリシーをアプリケーションに追加すると、そのアプリケーションおよびそれを参照する他のアプリケーションでポリシーを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2a231-105">Adding a policy to an application makes it available for use by that application as well as any other applications that reference it.</span></span>  
  
 <span data-ttu-id="2a231-106">ポリシーをアプリケーションに追加する際には、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="2a231-106">When adding a policy to an application, bear in mind the following important points:</span></span>  
  
-   <span data-ttu-id="2a231-107">前に、ポリシーを追加するには、アプリケーションに、ポリシーが BizTalk グループのルール エンジン データベースに存在する必要があります発行して、」の説明に従って[ポリシーをインポートする方法](../core/how-to-import-a-policy.md)です。</span><span class="sxs-lookup"><span data-stu-id="2a231-107">Before you can add a policy to an application, the policy must exist in the Rule Engine database for the BizTalk group, and it must be published, as described in [How to Import a Policy](../core/how-to-import-a-policy.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2a231-108">ルール エンジン展開ウィザードを使用してルール エンジン データベースからポリシーを削除すると、そのポリシーは、管理コンソールでは表示されたままになりますが、公開することはできません。</span><span class="sxs-lookup"><span data-stu-id="2a231-108">When you remove a policy from the Rule Engine database by using the Rule Engine Deployment Wizard, it will still display in the administration console, but, you will not be able to publish it.</span></span> <span data-ttu-id="2a231-109">ルール エンジン展開ウィザードの詳細については、次を参照してください。[展開と展開解除ポリシーとボキャブラリを方法](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)です。</span><span class="sxs-lookup"><span data-stu-id="2a231-109">For more information about the Rule Engine Deployment Wizard, see [How to Deploy and Undeploy Policies and Vocabularies](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md).</span></span>  
  
-   <span data-ttu-id="2a231-110">ポリシーは、BizTalk グループの別のアプリケーションに存在することはできません。</span><span class="sxs-lookup"><span data-stu-id="2a231-110">The policy cannot already exist in another application in the BizTalk group.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="2a231-111">複数のアプリケーションでポリシーを共有するには、ポリシーを格納する独立したアプリケーションを作成した後、そのポリシーを使用する別のアプリケーションからポリシーを格納するアプリケーションへの参照を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a231-111">If a policy is shared across two or more applications, you should create a separate application to contain the policy and then create references from the applications that use the policy to the application containing the policy.</span></span> <span data-ttu-id="2a231-112">これは、ポリシーを含むアプリケーションを停止すると、ポリシーが自動的に展開解除され、ポリシーを使用するアプリケーションで機能しなくなるためです。</span><span class="sxs-lookup"><span data-stu-id="2a231-112">This is because if you stop an application that contains a policy, the policy is automatically undeployed and no longer functions for any of the applications that use it.</span></span> <span data-ttu-id="2a231-113">参照を追加する方法の詳細については、次を参照してください。[を別のアプリケーションへの参照を追加する方法](../core/how-to-add-a-reference-to-another-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="2a231-113">For instructions on adding a reference, see [How to Add a Reference to Another Application](../core/how-to-add-a-reference-to-another-application.md).</span></span>  
  
-   <span data-ttu-id="2a231-114">ポリシーを有効にして機能させるには、ポリシーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a231-114">For the policy to take effect and begin functioning, it must also be deployed.</span></span> <span data-ttu-id="2a231-115">ポリシーは、アプリケーションの起動時に自動的に展開または手動で展開する」の説明に従って[またはポリシーを展開解除方法](../core/how-to-deploy-or-undeploy-a-policy.md)です。</span><span class="sxs-lookup"><span data-stu-id="2a231-115">Policies are automatically deployed when the application starts, or you can manually deploy them as described in [How to Deploy or Undeploy a Policy](../core/how-to-deploy-or-undeploy-a-policy.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2a231-116">前提条件</span><span class="sxs-lookup"><span data-stu-id="2a231-116">Prerequisites</span></span>  
 <span data-ttu-id="2a231-117">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a231-117">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="2a231-118">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="2a231-118">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-add-a-policy-to-an-application"></a><span data-ttu-id="2a231-119">ポリシーをアプリケーションに追加するには</span><span class="sxs-lookup"><span data-stu-id="2a231-119">To add a policy to an application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="2a231-120">BizTalk Server 管理コンソールの使用</span><span class="sxs-lookup"><span data-stu-id="2a231-120">Using the BizTalk Server Administration console</span></span>  
  
1.  <span data-ttu-id="2a231-121">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="2a231-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="2a231-122">コンソール ツリーで [[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]]、BizTalk グループの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="2a231-122">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] and the BizTalk group.</span></span>  
  
3.  <span data-ttu-id="2a231-123">アプリケーションを展開し、ポリシーを追加し、右クリックするアプリケーション**ポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="2a231-123">Expand Applications, expand the application to which you want to add a policy, and then right-click **Policies**.</span></span>  
  
4.  <span data-ttu-id="2a231-124">指す**追加** をクリック**ポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="2a231-124">Point to **Add** and click **Policy**.</span></span>  
  
5.  <span data-ttu-id="2a231-125">各ポリシーおよびをクリックし、追加のバージョンのチェック ボックスをオン**OK**です。</span><span class="sxs-lookup"><span data-stu-id="2a231-125">Select the check box of each policy and version to add, and then click **OK**.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="2a231-126">コマンドラインを使用</span><span class="sxs-lookup"><span data-stu-id="2a231-126">Using the command line</span></span>  
  
1.  <span data-ttu-id="2a231-127">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="2a231-127">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="2a231-128">次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="2a231-128">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
     <span data-ttu-id="2a231-129">**BTSTask AddResource** [**/applicationname は:***値*] **/Type:System.BizTalk:Rules** [**上書き**] **/名:***値***/Version:***値*[**/Server:***値*] [**/Database:***値*]</span><span class="sxs-lookup"><span data-stu-id="2a231-129">**BTSTask AddResource** [**/ApplicationName:***value*] **/Type:System.BizTalk:Rules** [**Overwrite**] **/Name:***value***/Version:***value* [**/Server:***value*] [**/Database:***value*]</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2a231-130">パラメーター値は大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="2a231-130">Parameter values are case sensitive.</span></span> <span data-ttu-id="2a231-131">パラメーター名では大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="2a231-131">Parameter names are not case sensitive.</span></span> <span data-ttu-id="2a231-132">このコマンドを使ってポリシーをアプリケーションに追加した場合、ポリシーで使用されているボキャブラリもすべて自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="2a231-132">Also, when you add a policy to an application by using this command, any vocabularies used by the policy are automatically added as well.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2a231-133">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="2a231-133">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
     <span data-ttu-id="2a231-134">例:</span><span class="sxs-lookup"><span data-stu-id="2a231-134">Example:</span></span>  
  
     <span data-ttu-id="2a231-135">**BTSTask AddResource applicationname: myapplication/Type:System.BizTalk:Rules/overwrite/Name:MyPolicy/Version:1.0/Server:MyDatabaseServer/Database:BizTalkMgmtDb**</span><span class="sxs-lookup"><span data-stu-id="2a231-135">**BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:Rules /Overwrite /Name:MyPolicy /Version:1.0 /Server:MyDatabaseServer /Database:BizTalkMgmtDb**</span></span>  
  
    |<span data-ttu-id="2a231-136">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2a231-136">Parameter</span></span>|<span data-ttu-id="2a231-137">値</span><span class="sxs-lookup"><span data-stu-id="2a231-137">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="2a231-138">**/ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="2a231-138">**/ApplicationName**</span></span>|<span data-ttu-id="2a231-139">ポリシーを追加する BizTalk アプリケーションの名前。</span><span class="sxs-lookup"><span data-stu-id="2a231-139">Name of the BizTalk application to which to add the policy.</span></span> <span data-ttu-id="2a231-140">アプリケーション名が指定されなかった場合、グループの既定の BizTalk アプリケーションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="2a231-140">If the application name is not specified, the default BizTalk application for the group is used.</span></span> <span data-ttu-id="2a231-141">スペースが含まれる名前は、二重引用符 (") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a231-141">Names that include spaces must be enclosed in double quotation marks (").</span></span>|  
    |<span data-ttu-id="2a231-142">**/型**</span><span class="sxs-lookup"><span data-stu-id="2a231-142">**/Type**</span></span>|<span data-ttu-id="2a231-143">**System.BizTalk:Rules**</span><span class="sxs-lookup"><span data-stu-id="2a231-143">**System.BizTalk:Rules**</span></span>|  
    |<span data-ttu-id="2a231-144">**/上書き**</span><span class="sxs-lookup"><span data-stu-id="2a231-144">**/Overwrite**</span></span>|<span data-ttu-id="2a231-145">既存のポリシーを更新するためのオプション。</span><span class="sxs-lookup"><span data-stu-id="2a231-145">Option to update an existing policy.</span></span> <span data-ttu-id="2a231-146">指定しなかった場合、追加するポリシーと同じ名前のポリシーが既にアプリケーションに存在した場合、AddResource 操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="2a231-146">If not specified, and a policy already exists in the application that has the same name as the policy being added, the AddResource operation fails.</span></span>|  
    |<span data-ttu-id="2a231-147">**/名前**</span><span class="sxs-lookup"><span data-stu-id="2a231-147">**/Name**</span></span>|<span data-ttu-id="2a231-148">ポリシーの名前。</span><span class="sxs-lookup"><span data-stu-id="2a231-148">Name of the policy.</span></span>|  
    |<span data-ttu-id="2a231-149">**/バージョン**</span><span class="sxs-lookup"><span data-stu-id="2a231-149">**/Version**</span></span>|<span data-ttu-id="2a231-150">ポリシーのバージョン番号です。</span><span class="sxs-lookup"><span data-stu-id="2a231-150">Version number of the policy.</span></span>|  
    |<span data-ttu-id="2a231-151">**/サーバー**</span><span class="sxs-lookup"><span data-stu-id="2a231-151">**/Server**</span></span>|<span data-ttu-id="2a231-152">BizTalk 管理データベースをホストする SQL Server インスタンスの名前です。</span><span class="sxs-lookup"><span data-stu-id="2a231-152">Name of the SQL Server instance hosting the BizTalk Management database.</span></span> <span data-ttu-id="2a231-153">Database パラメーターを指定する場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="2a231-153">Required if you specify the Database parameter.</span></span> <span data-ttu-id="2a231-154">Server パラメーターおよび Database パラメーターを指定しなかった場合、グループの既定の BizTalk 管理データベースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="2a231-154">If Server and Database parameters are not specified, the default BizTalk Management database for the group is used.</span></span>|  
    |<span data-ttu-id="2a231-155">**/データベース**</span><span class="sxs-lookup"><span data-stu-id="2a231-155">**/Database**</span></span>|<span data-ttu-id="2a231-156">BizTalk 管理データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="2a231-156">Name of the BizTalk Management database.</span></span> <span data-ttu-id="2a231-157">Server パラメーターを指定する場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="2a231-157">Required if you specify the Server parameter.</span></span> <span data-ttu-id="2a231-158">Server パラメーターおよび Database パラメーターを指定しなかった場合、グループの既定の BizTalk 管理データベースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="2a231-158">If Server and Database parameters are not specified, the default BizTalk Management database for the group is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2a231-159">参照</span><span class="sxs-lookup"><span data-stu-id="2a231-159">See Also</span></span>  
 <span data-ttu-id="2a231-160">[ポリシーの管理](../core/managing-policies.md) </span><span class="sxs-lookup"><span data-stu-id="2a231-160">[Managing Policies](../core/managing-policies.md) </span></span>  
 <span data-ttu-id="2a231-161">[作成して、BizTalk アプリケーションの変更](../core/creating-and-modifying-biztalk-applications.md) </span><span class="sxs-lookup"><span data-stu-id="2a231-161">[Creating and Modifying BizTalk Applications](../core/creating-and-modifying-biztalk-applications.md) </span></span>  
 [<span data-ttu-id="2a231-162">AddResource コマンド: ポリシー</span><span class="sxs-lookup"><span data-stu-id="2a231-162">AddResource Command: Policy</span></span>](../core/addresource-command-policy.md)
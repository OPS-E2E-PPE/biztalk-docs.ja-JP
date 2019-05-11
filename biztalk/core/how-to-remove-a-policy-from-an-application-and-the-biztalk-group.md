---
title: アプリケーションおよび BizTalk グループからポリシーを削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, policies
- managing [policies], applications
- managing [policies], deleting
- groups, policies
- managing [policies], groups
- applications, policies
ms.assetid: e9882cb3-8808-4258-a107-a24905290288
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: beca719538949bd82b1d9ea442fb12c61c607e14
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335065"
---
# <a name="how-to-remove-a-policy-from-an-application-and-the-biztalk-group"></a><span data-ttu-id="aad67-102">アプリケーションおよび BizTalk グループからポリシーを削除する方法</span><span class="sxs-lookup"><span data-stu-id="aad67-102">How to Remove a Policy from an Application and the BizTalk Group</span></span>
<span data-ttu-id="aad67-103">このトピックでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、BizTalk グループのアプリケーションおよびルール エンジン データベースからポリシーを削除する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="aad67-103">This topic describes how to use the BizTalk Server Administration console or the command-line to remove a policy from an application and the Rule Engine database for the BizTalk group.</span></span>  
  
 <span data-ttu-id="aad67-104">ポリシーを削除する前に、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="aad67-104">Before removing a policy, bear in mind the following important points:</span></span>  
  
-   <span data-ttu-id="aad67-105">展開済みのポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="aad67-105">You cannot remove a deployed policy.</span></span> <span data-ttu-id="aad67-106">ポリシーを解除する必要がありますまず[展開またはポリシーを展開解除する方法](../core/how-to-deploy-or-undeploy-a-policy.md)します。</span><span class="sxs-lookup"><span data-stu-id="aad67-106">You must first undeploy the policy, as described in [How to Deploy or Undeploy a Policy](../core/how-to-deploy-or-undeploy-a-policy.md).</span></span> <span data-ttu-id="aad67-107">ポリシーは、展開解除すると非アクティブとなり、BizTalk グループ内でそれを使用しているすべてのアプリケーションで動作しなくなります。</span><span class="sxs-lookup"><span data-stu-id="aad67-107">Undeploying a policy makes it inactive so that it no longer functions in any application that uses it in the BizTalk group.</span></span>  
  
-   <span data-ttu-id="aad67-108">ポリシーを削除すると、ポリシーはルール データベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="aad67-108">Removing a policy deletes it from the Rule Engine database.</span></span> <span data-ttu-id="aad67-109">このポリシーを再度使用する場合は、ポリシーを削除する前に .xml ファイルにインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="aad67-109">If you want to use this policy again, you should export it to an .xml file before removing it.</span></span> <span data-ttu-id="aad67-110">手順については、次を参照してください。[ポリシーをエクスポートする方法](../core/how-to-export-a-policy.md)します。</span><span class="sxs-lookup"><span data-stu-id="aad67-110">For instructions, see [How to Export a Policy](../core/how-to-export-a-policy.md).</span></span>  
  
-   <span data-ttu-id="aad67-111">ポリシーが他のアプリケーションで使用されている場合、削除したポリシーはそのアプリケーションでも無効になります。</span><span class="sxs-lookup"><span data-stu-id="aad67-111">If the policy is used by other applications, it will no longer be in effect for the other applications.</span></span> <span data-ttu-id="aad67-112">ポリシーを削除する前に、そのポリシーを参照している他のアプリケーションでポリシーを使用する必要がないか確認してください。</span><span class="sxs-lookup"><span data-stu-id="aad67-112">Verify that you no longer want to use the policy for any other applications that reference it before you remove it.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="aad67-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="aad67-113">Prerequisites</span></span>  
 <span data-ttu-id="aad67-114">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="aad67-114">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="aad67-115">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="aad67-115">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-remove-a-policy"></a><span data-ttu-id="aad67-116">ポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="aad67-116">To remove a policy</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="aad67-117">BizTalk Server 管理コンソールの使用</span><span class="sxs-lookup"><span data-stu-id="aad67-117">Using the BizTalk Server Administration console</span></span>  
  
1. <span data-ttu-id="aad67-118">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="aad67-118">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="aad67-119">コンソール ツリーで、展開**BizTalk Server 管理**、削除するには、ポリシーが含まれる BizTalk グループを展開し、ポリシーを含むアプリケーションを展開</span><span class="sxs-lookup"><span data-stu-id="aad67-119">In the console tree, expand  **BizTalk Server Administration**, expand the BizTalk group containing the policy to remove, and then expand the application containing the policy</span></span>  
  
3. <span data-ttu-id="aad67-120">クリックして**ポリシー**ポリシーを右クリックし、クリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="aad67-120">Click **Policies**, right-click the policy, and then click **Remove**.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="aad67-121">コマンドラインを使用</span><span class="sxs-lookup"><span data-stu-id="aad67-121">Using the command line</span></span>  
  
1. <span data-ttu-id="aad67-122">次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="aad67-122">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="aad67-123">次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="aad67-123">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
    <span data-ttu-id="aad67-124">**BTSTask RemoveResource** [**/ApplicationName:**<em>value</em>] **/Luid:**<em>value</em> [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span><span class="sxs-lookup"><span data-stu-id="aad67-124">**BTSTask RemoveResource** [**/ApplicationName:**<em>value</em>] **/Luid:**<em>value</em> [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
    <span data-ttu-id="aad67-125">例:</span><span class="sxs-lookup"><span data-stu-id="aad67-125">Example:</span></span>  
  
    <span data-ttu-id="aad67-126">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"Rule/Policy1/1.0"**</span><span class="sxs-lookup"><span data-stu-id="aad67-126">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"Rule/Policy1/1.0"**</span></span>  
  
   |<span data-ttu-id="aad67-127">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aad67-127">Parameter</span></span>|<span data-ttu-id="aad67-128">説明</span><span class="sxs-lookup"><span data-stu-id="aad67-128">Description</span></span>|  
   |---------------|-----------------|  
   |<span data-ttu-id="aad67-129">**/ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="aad67-129">**/ApplicationName**</span></span>|<span data-ttu-id="aad67-130">削除するポリシーが存在する BizTalk アプリケーションの名前。</span><span class="sxs-lookup"><span data-stu-id="aad67-130">Name of the BizTalk application containing the policy to delete.</span></span> <span data-ttu-id="aad67-131">このパラメーターを指定しなかった場合、既定のアプリケーションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="aad67-131">If this parameter is not specified, the default application is used.</span></span>|  
   |<span data-ttu-id="aad67-132">**/Luid**</span><span class="sxs-lookup"><span data-stu-id="aad67-132">**/Luid**</span></span>|<span data-ttu-id="aad67-133">ポリシーのローカル一意識別子 (LUID)。</span><span class="sxs-lookup"><span data-stu-id="aad67-133">Locally unique identifier (LUID) of the policy.</span></span> <span data-ttu-id="aad67-134">LUID を取得するにを使用して、 **ListApp** 」の説明に従って、コマンド[ListApp コマンド](../core/listapp-command.md)します。</span><span class="sxs-lookup"><span data-stu-id="aad67-134">You can obtain the LUID by using the **ListApp** command, as described in [ListApp Command](../core/listapp-command.md).</span></span>|  
   |<span data-ttu-id="aad67-135">**/サーバー**</span><span class="sxs-lookup"><span data-stu-id="aad67-135">**/Server**</span></span>|<span data-ttu-id="aad67-136">BizTalk 管理データベースをホストする SQL Server インスタンスの名前です。</span><span class="sxs-lookup"><span data-stu-id="aad67-136">Name of the SQL Server instance hosting the BizTalk Management database.</span></span> <span data-ttu-id="aad67-137">Database パラメーターを指定する場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="aad67-137">Required if you specify the Database parameter.</span></span> <span data-ttu-id="aad67-138">Server パラメーターおよび Database パラメーターを指定しなかった場合、グループの既定の BizTalk 管理データベースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="aad67-138">If Server and Database parameters are not specified, the default BizTalk Management database for the group is used.</span></span>|  
   |<span data-ttu-id="aad67-139">**/Database**</span><span class="sxs-lookup"><span data-stu-id="aad67-139">**/Database**</span></span>|<span data-ttu-id="aad67-140">BizTalk 管理データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="aad67-140">Name of the BizTalk Management database.</span></span> <span data-ttu-id="aad67-141">Server パラメーターを指定する場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="aad67-141">Required if you specify the Server parameter.</span></span> <span data-ttu-id="aad67-142">Server パラメーターおよび Database パラメーターを指定しなかった場合、グループの既定の BizTalk 管理データベースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="aad67-142">If Server and Database parameters are not specified, the default BizTalk Management database for the group is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aad67-143">参照</span><span class="sxs-lookup"><span data-stu-id="aad67-143">See Also</span></span>  
 [<span data-ttu-id="aad67-144">ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="aad67-144">Managing Policies</span></span>](../core/managing-policies.md)
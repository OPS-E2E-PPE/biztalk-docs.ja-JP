---
title: 展開またはポリシーを展開解除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [policies], undeploying
- deploying, policies
- policies, deploying
- managing [policies], deploying
- policies, undeploying
- undeploying, policies
ms.assetid: 9d26d4fe-9673-4baa-9927-02efda56b7a4
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a5470c96bfb768528c255325681ce45a9af36c1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338504"
---
# <a name="how-to-deploy-or-undeploy-a-policy"></a><span data-ttu-id="7e5e4-102">展開またはポリシーを展開解除する方法</span><span class="sxs-lookup"><span data-stu-id="7e5e4-102">How to Deploy or Undeploy a Policy</span></span>
<span data-ttu-id="7e5e4-103">このトピックでは、BizTalk Server 管理コンソールを使用して、展開または手動でポリシーを展開解除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7e5e4-103">This topic describes how to use the BizTalk Server Administration console to deploy or undeploy a policy manually.</span></span> <span data-ttu-id="7e5e4-104">さらに、それに含まれるすべてのポリシーを展開するアプリケーションを自動的に起動し、そのポリシーを展開解除、アプリケーションを自動的に停止します。</span><span class="sxs-lookup"><span data-stu-id="7e5e4-104">In addition, starting an application automatically deploys any policies it contains, and stopping an application automatically undeploys its policies.</span></span> <span data-ttu-id="7e5e4-105">ポリシーの展開に使用するアプリケーション内で有効に配置します。</span><span class="sxs-lookup"><span data-stu-id="7e5e4-105">Deploying a policy puts it into effect in the application that uses it.</span></span> <span data-ttu-id="7e5e4-106">ポリシーは、展開解除すると非アクティブとなり、BizTalk グループ内でそれを使用しているすべてのアプリケーションで動作しなくなります。</span><span class="sxs-lookup"><span data-stu-id="7e5e4-106">Undeploying a policy makes it inactive so that it no longer functions in any application that uses it in the BizTalk group.</span></span>  
  
 <span data-ttu-id="7e5e4-107">展開またはポリシーを展開解除、ときに、次の点に注意してくださいにしてください。</span><span class="sxs-lookup"><span data-stu-id="7e5e4-107">When deploying or undeploying a policy, bear in mind the following important points:</span></span>  
  
-   <span data-ttu-id="7e5e4-108">ポリシーを展開するには、BizTalk グループのルール エンジン データベースに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e5e4-108">Before you can deploy a policy, it must exist in the Rule Engine database for the BizTalk group.</span></span> <span data-ttu-id="7e5e4-109">ポリシーを含むアプリケーションをインポートすると、ポリシーが、ルール エンジン データベースに自動的にインポートまたは明示的にポリシーをインポートするルール エンジン データベースに、管理コンソールまたは BTSTask を使用して、 」の説明に従って[ポリシーをインポートする方法](../core/how-to-import-a-policy.md)します。</span><span class="sxs-lookup"><span data-stu-id="7e5e4-109">If you import an application that contains a policy, the policy is automatically imported into the Rule Engine database, or you can explicitly import a policy into the Rule Engine database by using the administration console or BTSTask, as described in [How to Import a Policy](../core/how-to-import-a-policy.md).</span></span> <span data-ttu-id="7e5e4-110">または、追加できますポリシーをルール エンジン データベースに、ルール エンジン展開ウィザードを使用して」の説明に従って[とボキャブラリを展開およびポリシーの展開を解除する方法](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)します。</span><span class="sxs-lookup"><span data-stu-id="7e5e4-110">Alternatively, you can add a policy to the Rule Engine database by using the Rule Engine Deployment Wizard, as described in [How to Deploy and Undeploy Policies and Vocabularies](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md).</span></span>  
  
-   <span data-ttu-id="7e5e4-111">ポリシーを展開する前に発行して、」の説明に従って[ポリシーを公開する方法](../core/how-to-publish-a-policy.md)します。</span><span class="sxs-lookup"><span data-stu-id="7e5e4-111">Before you can deploy a policy, it must be published, as described in [How to Publish a Policy](../core/how-to-publish-a-policy.md).</span></span>  
  
-   <span data-ttu-id="7e5e4-112">展開済みのポリシーを変更できません。</span><span class="sxs-lookup"><span data-stu-id="7e5e4-112">A deployed policy cannot be modified.</span></span> <span data-ttu-id="7e5e4-113">展開済みのポリシーを変更する場合は、最初に解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e5e4-113">If you want to modify a deployed policy, you must first undeploy it.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7e5e4-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="7e5e4-114">Prerequisites</span></span>  
 <span data-ttu-id="7e5e4-115">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e5e4-115">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="7e5e4-116">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="7e5e4-116">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-deploy-or-undeploy-a-policy"></a><span data-ttu-id="7e5e4-117">展開またはポリシーを展開解除するには</span><span class="sxs-lookup"><span data-stu-id="7e5e4-117">To deploy or undeploy a policy</span></span>  
  
1. <span data-ttu-id="7e5e4-118">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="7e5e4-118">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="7e5e4-119">コンソール ツリーで、展開**BizTalk Server 管理**、展開または展開解除、および順に展開するポリシーが含まれる BizTalk グループを展開**\<すべての成果物\>**.</span><span class="sxs-lookup"><span data-stu-id="7e5e4-119">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the policy that you want to deploy or undeploy, and then expand **\<All Artifacts\>**.</span></span>  
  
3. <span data-ttu-id="7e5e4-120">クリックして**ポリシー**ポリシーを右クリックし、クリックして**デプロイ**または**Undeploy**します。</span><span class="sxs-lookup"><span data-stu-id="7e5e4-120">Click **Policies**, right-click the policy, and then click **Deploy** or **Undeploy**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e5e4-121">参照</span><span class="sxs-lookup"><span data-stu-id="7e5e4-121">See Also</span></span>  
 <span data-ttu-id="7e5e4-122">[ポリシーの管理](../core/managing-policies.md) </span><span class="sxs-lookup"><span data-stu-id="7e5e4-122">[Managing Policies](../core/managing-policies.md) </span></span>  
 [<span data-ttu-id="7e5e4-123">BizTalk アプリケーション開始および停止する方法</span><span class="sxs-lookup"><span data-stu-id="7e5e4-123">How to Start and Stop a BizTalk Application</span></span>](../core/how-to-start-and-stop-a-biztalk-application.md)
---
title: "ポリシーを公開する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- policies, publishing
- managing [policies], publishing
- publishing, policies
ms.assetid: 730c57a7-526f-40ca-8610-88216558e375
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d5e9604e950710911d4324d5b329173d184617b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-publish-a-policy"></a><span data-ttu-id="c501c-102">ポリシーを公開する方法</span><span class="sxs-lookup"><span data-stu-id="c501c-102">How to Publish a Policy</span></span>
<span data-ttu-id="c501c-103">このトピックでは、BizTalk Server 管理コンソールを使用して、BizTalk グループでポリシーを公開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c501c-103">This topic describes how to use the BizTalk Server Administration console to publish a policy in a BizTalk group.</span></span> <span data-ttu-id="c501c-104">公開したポリシーで使用できるように、BizTalk アプリケーションに追加する」の説明に従って[アプリケーションにポリシーを追加する方法](../core/how-to-add-a-policy-to-an-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="c501c-104">Publishing a policy makes it available to add to a BizTalk application, as described in [How to Add a Policy to an Application](../core/how-to-add-a-policy-to-an-application.md).</span></span>  
  
 <span data-ttu-id="c501c-105">ポリシーを公開するには、そのポリシーが BizTalk グループのルール エンジン データベースにあらかじめ存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c501c-105">Before you can publish a policy, it must exist in the Rule Engine database for the BizTalk group.</span></span> <span data-ttu-id="c501c-106">ルール エンジン データベースにポリシーをインポートするには、次の 3 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="c501c-106">There are three ways to import a policy into the Rule Engine database:</span></span>  
  
-   <span data-ttu-id="c501c-107">ポリシーを含むアプリケーションをインポートする方法。</span><span class="sxs-lookup"><span data-stu-id="c501c-107">You can import an application that contains a policy.</span></span> <span data-ttu-id="c501c-108">この方法では、ポリシーはルール エンジン データベースに自動的にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="c501c-108">When you do this, the policy is automatically imported into the Rule Engine database.</span></span>  
  
-   <span data-ttu-id="c501c-109">明示的にポリシーをインポートするルール エンジン データベースに、管理コンソールまたは BTSTask を使用して、」の説明に従って[ポリシーをインポートする方法](../core/how-to-import-a-policy.md)です。</span><span class="sxs-lookup"><span data-stu-id="c501c-109">You can explicitly import a policy into the Rule Engine database by using the administration console or BTSTask, as described in [How to Import a Policy](../core/how-to-import-a-policy.md).</span></span>  
  
-   <span data-ttu-id="c501c-110">追加できますポリシー ルール エンジン データベースにルール エンジン展開ウィザードを使用して」の説明に従って[展開と展開解除ポリシーとボキャブラリを方法](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)です。</span><span class="sxs-lookup"><span data-stu-id="c501c-110">You can add a policy to the Rule Engine database by using the Rule Engine Deployment Wizard, as described in [How to Deploy and Undeploy Policies and Vocabularies](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c501c-111">公開済みのポリシーはインポートした別のポリシーで上書きされる可能性がありますが、このオプションを指定すると、公開済みのボキャブラリは上書きされません。</span><span class="sxs-lookup"><span data-stu-id="c501c-111">While a published policy can be overwritten by another policy that you import, should you specify this option, a published vocabulary can never be overwritten.</span></span> <span data-ttu-id="c501c-112">公開済みのボキャブラリを更新するには、このボキャブラリをルール エンジン データベースから削除してから新しいバージョンをインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c501c-112">To update a published vocabulary, you must remove it from the Rule Engine database and then import the new version.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c501c-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="c501c-113">Prerequisites</span></span>  
 <span data-ttu-id="c501c-114">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c501c-114">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="c501c-115">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="c501c-115">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-publish-a-policy"></a><span data-ttu-id="c501c-116">ポリシーを公開するには</span><span class="sxs-lookup"><span data-stu-id="c501c-116">To publish a policy</span></span>  
  
1.  <span data-ttu-id="c501c-117">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="c501c-117">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="c501c-118">コンソール ツリーで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、公開、展開するポリシーを含む BizTalk グループを展開して**アプリケーション**、順に展開**\<すべての成果物\>**です。</span><span class="sxs-lookup"><span data-stu-id="c501c-118">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group containing the policy to publish, expand **Applications**, and then expand **\<All Artifacts\>**.</span></span>  
  
3.  <span data-ttu-id="c501c-119">をクリックして**ポリシー**ポリシーを右クリックし、クリックして**発行**です。</span><span class="sxs-lookup"><span data-stu-id="c501c-119">Click **Policies**, right-click the policy, and then click **Publish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c501c-120">ポリシーを公開するために、ポリシーによって参照されているすべてのアセンブリ必要がありますインストールのグローバル アセンブリ キャッシュ (GAC) に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を開く前にコンピューター **BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="c501c-120">In order to publish a policy, any assemblies that are referenced by the policy must be installed in the Global Assembly Cache (GAC) of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer before you open **BizTalk Server Administration**.</span></span> <span data-ttu-id="c501c-121">ときに**BizTalk Server 管理コンソール**が開くと、GAC にインストールされているアセンブリのキャッシュを保持します。</span><span class="sxs-lookup"><span data-stu-id="c501c-121">When **BizTalk Server Administration** is opened, it maintains a cache of the assemblies that are installed into the GAC.</span></span> <span data-ttu-id="c501c-122">までこのキャッシュは更新されません**BizTalk Server 管理コンソール**が閉じられ、再び開きます。</span><span class="sxs-lookup"><span data-stu-id="c501c-122">This cache is not updated until **BizTalk Server Administration** is closed and reopened.</span></span> <span data-ttu-id="c501c-123">ポリシーをパブリッシュしようとして、参照アセンブリが閉じる必要があります、GAC にインストールされていないために、パブリケーションが失敗した場合**BizTalk Server 管理コンソール**、開く、GAC に参照アセンブリをインストール**BizTalk Server 管理コンソール**、およびポリシーを公開します。</span><span class="sxs-lookup"><span data-stu-id="c501c-123">If you attempt to publish a policy and publication fails because a referenced assembly is not installed in the GAC you must close **BizTalk Server Administration**, install the referenced assembly into the GAC, open **BizTalk Server Administration**, and then publish the policy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c501c-124">参照</span><span class="sxs-lookup"><span data-stu-id="c501c-124">See Also</span></span>  
 [<span data-ttu-id="c501c-125">ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="c501c-125">Managing Policies</span></span>](../core/managing-policies.md)
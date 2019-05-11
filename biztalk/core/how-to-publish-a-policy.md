---
title: ポリシーを公開する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, publishing
- managing [policies], publishing
- publishing, policies
ms.assetid: 730c57a7-526f-40ca-8610-88216558e375
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8a3591c6f904db07f51610e0bcff7afae7b8e31
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335738"
---
# <a name="how-to-publish-a-policy"></a><span data-ttu-id="f8a65-102">ポリシーを公開する方法</span><span class="sxs-lookup"><span data-stu-id="f8a65-102">How to Publish a Policy</span></span>
<span data-ttu-id="f8a65-103">このトピックでは、BizTalk Server 管理コンソールを使用して、BizTalk グループにポリシーを公開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f8a65-103">This topic describes how to use the BizTalk Server Administration console to publish a policy in a BizTalk group.</span></span> <span data-ttu-id="f8a65-104">公開したポリシーで使用できるように、BizTalk アプリケーションに追加する」の説明に従って[アプリケーションにポリシーを追加する方法](../core/how-to-add-a-policy-to-an-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="f8a65-104">Publishing a policy makes it available to add to a BizTalk application, as described in [How to Add a Policy to an Application](../core/how-to-add-a-policy-to-an-application.md).</span></span>  
  
 <span data-ttu-id="f8a65-105">ポリシーを発行するには、BizTalk グループのルール エンジン データベースに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8a65-105">Before you can publish a policy, it must exist in the Rule Engine database for the BizTalk group.</span></span> <span data-ttu-id="f8a65-106">ルール エンジン データベースにポリシーをインポートする次の 3 つの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="f8a65-106">There are three ways to import a policy into the Rule Engine database:</span></span>  
  
-   <span data-ttu-id="f8a65-107">ポリシーを含むアプリケーションをインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="f8a65-107">You can import an application that contains a policy.</span></span> <span data-ttu-id="f8a65-108">これを行うときに、ポリシーはルール エンジン データベースに自動的にインポートされません。</span><span class="sxs-lookup"><span data-stu-id="f8a65-108">When you do this, the policy is automatically imported into the Rule Engine database.</span></span>  
  
-   <span data-ttu-id="f8a65-109">明示的にインポートできますポリシーをルール エンジン データベース、管理コンソールまたは BTSTask を使用して、」の説明に従って[ポリシーをインポートする方法](../core/how-to-import-a-policy.md)します。</span><span class="sxs-lookup"><span data-stu-id="f8a65-109">You can explicitly import a policy into the Rule Engine database by using the administration console or BTSTask, as described in [How to Import a Policy](../core/how-to-import-a-policy.md).</span></span>  
  
-   <span data-ttu-id="f8a65-110">追加できますポリシーをルール エンジン データベースに、ルール エンジン展開ウィザードを使用して」の説明に従って[とボキャブラリを展開およびポリシーの展開を解除する方法](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)します。</span><span class="sxs-lookup"><span data-stu-id="f8a65-110">You can add a policy to the Rule Engine database by using the Rule Engine Deployment Wizard, as described in [How to Deploy and Undeploy Policies and Vocabularies](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8a65-111">公開済みのポリシーをインポートすると、別のポリシーで上書きできますこのオプションを指定する必要があります、公開済みのボキャブラリは上書きされません。</span><span class="sxs-lookup"><span data-stu-id="f8a65-111">While a published policy can be overwritten by another policy that you import, should you specify this option, a published vocabulary can never be overwritten.</span></span> <span data-ttu-id="f8a65-112">公開済みのボキャブラリを更新するには、ルール エンジン データベースから削除し、新しいバージョンをインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8a65-112">To update a published vocabulary, you must remove it from the Rule Engine database and then import the new version.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f8a65-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="f8a65-113">Prerequisites</span></span>  
 <span data-ttu-id="f8a65-114">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8a65-114">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="f8a65-115">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="f8a65-115">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-publish-a-policy"></a><span data-ttu-id="f8a65-116">ポリシーを公開するには</span><span class="sxs-lookup"><span data-stu-id="f8a65-116">To publish a policy</span></span>  
  
1. <span data-ttu-id="f8a65-117">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="f8a65-117">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="f8a65-118">コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、公開、展開するポリシーが含まれる BizTalk グループ**アプリケーション**、順に展開**\<すべての成果物\>** します。</span><span class="sxs-lookup"><span data-stu-id="f8a65-118">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group containing the policy to publish, expand **Applications**, and then expand **\<All Artifacts\>**.</span></span>  
  
3. <span data-ttu-id="f8a65-119">クリックして**ポリシー**ポリシーを右クリックし、クリックして**発行**します。</span><span class="sxs-lookup"><span data-stu-id="f8a65-119">Click **Policies**, right-click the policy, and then click **Publish**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="f8a65-120">ポリシーを公開するには、ポリシーが参照するすべてのアセンブリ必要がありますインストールのグローバル アセンブリ キャッシュ (GAC) に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を開く前にコンピューター **BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="f8a65-120">In order to publish a policy, any assemblies that are referenced by the policy must be installed in the Global Assembly Cache (GAC) of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer before you open **BizTalk Server Administration**.</span></span> <span data-ttu-id="f8a65-121">ときに**BizTalk Server 管理**が開かれるを GAC にインストールされているアセンブリのキャッシュを保持します。</span><span class="sxs-lookup"><span data-stu-id="f8a65-121">When **BizTalk Server Administration** is opened, it maintains a cache of the assemblies that are installed into the GAC.</span></span> <span data-ttu-id="f8a65-122">このキャッシュはまで更新されません**BizTalk Server 管理**を閉じています。</span><span class="sxs-lookup"><span data-stu-id="f8a65-122">This cache is not updated until **BizTalk Server Administration** is closed and reopened.</span></span> <span data-ttu-id="f8a65-123">ポリシーを公開しようとして、参照アセンブリが閉じる必要があります、GAC にインストールされていないために、パブリケーションが失敗した場合**BizTalk Server 管理**、GAC、オープンに参照アセンブリをインストール**BizTalk Server 管理**ポリシーを公開するとします。</span><span class="sxs-lookup"><span data-stu-id="f8a65-123">If you attempt to publish a policy and publication fails because a referenced assembly is not installed in the GAC you must close **BizTalk Server Administration**, install the referenced assembly into the GAC, open **BizTalk Server Administration**, and then publish the policy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8a65-124">参照</span><span class="sxs-lookup"><span data-stu-id="f8a65-124">See Also</span></span>  
 [<span data-ttu-id="f8a65-125">ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="f8a65-125">Managing Policies</span></span>](../core/managing-policies.md)
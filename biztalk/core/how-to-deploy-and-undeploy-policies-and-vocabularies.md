---
title: 展開およびポリシーとボキャブラリを展開解除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, policies
- policies, deploying
- deploying, vocabularies
- policies, undeploying
- vocabularies, deploying
ms.assetid: 9a7e3310-54b7-482c-8210-b4b11fde4c49
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a2c6200f41a4b473175528ac6d2c8ee75c17894
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013067"
---
# <a name="how-to-deploy-and-undeploy-policies-and-vocabularies"></a><span data-ttu-id="2de75-102">ポリシーとボキャブラリを展開および展開解除する方法</span><span class="sxs-lookup"><span data-stu-id="2de75-102">How to Deploy and Undeploy Policies and Vocabularies</span></span>
<span data-ttu-id="2de75-103">ポリシーの展開と展開解除には、ビジネス ルール エンジン展開ウィザードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2de75-103">You can use the Rule Engine Deployment Wizard to deploy or undeploy a policy.</span></span>  
  
 <span data-ttu-id="2de75-104">ビジネス ルール エンジン展開ウィザードで展開作業を行う際、公開されたポリシー バージョンだけがドロップダウン リストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2de75-104">In the Rule Engine Deployment Wizard, when you try to deploy, only published policy versions are shown in the drop-down list.</span></span> <span data-ttu-id="2de75-105">展開を解除しようとするときにのみのバージョンがドロップダウン リストで示すようにポリシーを配置します。</span><span class="sxs-lookup"><span data-stu-id="2de75-105">When you try to undeploy, only deployed policy versions are shown in the drop-down list.</span></span>  
  
### <a name="to-deploy-or-undeploy-a-policy"></a><span data-ttu-id="2de75-106">ポリシーを展開または展開解除するには</span><span class="sxs-lookup"><span data-stu-id="2de75-106">To deploy or undeploy a policy</span></span>  
  
1. <span data-ttu-id="2de75-107">をクリックして**開始**、 をポイント**Program Files**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**ビジネス ルール エンジン展開ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="2de75-107">Click **Start**, point to **Program Files**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Business Rules Engine Deployment Wizard**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="2de75-108">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="2de75-108">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="2de75-109">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="2de75-109">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2. <span data-ttu-id="2de75-110">**ルール エンジン展開ウィザード**ようこそ ページで、**次**します。</span><span class="sxs-lookup"><span data-stu-id="2de75-110">On the **Rules Engine Deployment Wizard** welcome page, click **Next**.</span></span>  
  
3. <span data-ttu-id="2de75-111">いずれかを選択**ポリシーの展開**または**ポリシーの展開解除**、 をクリックし、**次**。</span><span class="sxs-lookup"><span data-stu-id="2de75-111">Select either **Deploy Policy** or **Undeploy Policy**, and then click **Next**.</span></span>  
  
4. <span data-ttu-id="2de75-112">ドロップダウン リストから、使用可能な SQL Server コンピューターと、データベースを選択し、クリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="2de75-112">From the drop-down lists, select an available SQL Server computer and database, and then click **Next**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="2de75-113">展開先には、ルール ストア データベースのみ選択できます。</span><span class="sxs-lookup"><span data-stu-id="2de75-113">You can only deploy to the rule store database that you are configured against.</span></span> <span data-ttu-id="2de75-114">それ以外のデータベースに対して展開しようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="2de75-114">An attempt to deploy to a different DB will give an error.</span></span>  
  
5. <span data-ttu-id="2de75-115">ドロップダウン リストからポリシーを選択し、**次**します。</span><span class="sxs-lookup"><span data-stu-id="2de75-115">From the drop-down list, select a policy, and then click **Next**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="2de75-116">展開するときは、公開されたポリシー バージョンだけがドロップダウン リストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2de75-116">When you try to deploy, only published policy versions are shown in the drop-down list.</span></span> <span data-ttu-id="2de75-117">展開を解除しようとするときにのみのバージョンがドロップダウン リストで示すようにポリシーを配置します。</span><span class="sxs-lookup"><span data-stu-id="2de75-117">When you try to undeploy, only deployed policy versions are shown in the drop-down list.</span></span>  
  
6. <span data-ttu-id="2de75-118">サーバー、データベース、およびポリシーの情報を確認し、クリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="2de75-118">Review the server, database, and policy information, and then click **Next**.</span></span>  
  
7. <span data-ttu-id="2de75-119">展開または展開解除の進捗状況が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2de75-119">Watch the progress of the deployment or undeployment.</span></span> <span data-ttu-id="2de75-120">完了したら、クリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="2de75-120">When it is finished, click **Next**.</span></span>  
  
8. <span data-ttu-id="2de75-121">展開または展開解除、完了ステータスを確認し、クリックして**完了**します。</span><span class="sxs-lookup"><span data-stu-id="2de75-121">Review the completion status of the deployment or undeployment, and then click **Finish**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2de75-122">展開またはポリシーのバージョンを右クリックし、をクリックして、ビジネス ルール作成ツールから、ポリシー バージョンを展開解除することができますも**デプロイ**または**Undeploy**します。</span><span class="sxs-lookup"><span data-stu-id="2de75-122">You can also deploy or undeploy a policy version from within the Business Rule Composer by right-clicking the policy version and then clicking **Deploy** or **Undeploy**.</span></span>
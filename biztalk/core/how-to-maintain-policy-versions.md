---
title: "ポリシー バージョンを管理する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- policies, publishing
- publishing policies
- updating, policies
- versioning, policies
- policies, versioning
- policies, updating
ms.assetid: 6e35b2bd-1ecd-45ea-aff3-4ad2437568a4
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09c73b3575ec484ab611fccac920cef6d96d3800
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-maintain-policy-versions"></a><span data-ttu-id="584ff-102">ポリシー バージョンを管理する方法</span><span class="sxs-lookup"><span data-stu-id="584ff-102">How to Maintain Policy Versions</span></span>
<span data-ttu-id="584ff-103">ルールをポリシーのバージョンに追加することにより、将来の開発に備えて特定のバージョンをルール ストアに保存できます。また、そのバージョンを公開して、厳密に定義されたルールのセットを作成し、これらのルールをルール ベースのアプリケーション用に展開することができます。</span><span class="sxs-lookup"><span data-stu-id="584ff-103">After you add rules to a version of your policy, you can save the version to the rule store for further development, or you can publish it to create a well-defined, immutable set of rules that can be deployed for use in a rule-based application.</span></span>  
  
 <span data-ttu-id="584ff-104">このトピックでは、次の操作の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="584ff-104">This topic contains procedures for the following tasks:</span></span>  
  
-   <span data-ttu-id="584ff-105">ポリシーの空のバージョンを新規作成するには</span><span class="sxs-lookup"><span data-stu-id="584ff-105">To create an empty new version of a policy</span></span>  
  
-   <span data-ttu-id="584ff-106">ポリシーのバージョンを保存するには</span><span class="sxs-lookup"><span data-stu-id="584ff-106">To save a policy version</span></span>  
  
-   <span data-ttu-id="584ff-107">ポリシーのバージョンを公開するには</span><span class="sxs-lookup"><span data-stu-id="584ff-107">To publish a policy version</span></span>  
  
-   <span data-ttu-id="584ff-108">ポリシーの更新されたバージョンを作成するには</span><span class="sxs-lookup"><span data-stu-id="584ff-108">To create an updated version of a policy</span></span>  
  
-   <span data-ttu-id="584ff-109">ポリシーを更新して更新済みアセンブリを使用するには</span><span class="sxs-lookup"><span data-stu-id="584ff-109">To update a policy to use an updated assembly</span></span>  
  
### <a name="to-create-an-empty-new-version-of-a-policy"></a><span data-ttu-id="584ff-110">ポリシーの空のバージョンを新規作成するには</span><span class="sxs-lookup"><span data-stu-id="584ff-110">To create an empty new version of a policy</span></span>  
  
-   <span data-ttu-id="584ff-111">ポリシー フォルダーを右クリックし、をクリックして**新しいバージョンの追加**です。</span><span class="sxs-lookup"><span data-stu-id="584ff-111">Right-click the policy folder, and then click **Add New Version**.</span></span>  
  
### <a name="to-save-a-policy-version"></a><span data-ttu-id="584ff-112">ポリシーのバージョンを保存するには</span><span class="sxs-lookup"><span data-stu-id="584ff-112">To save a policy version</span></span>  
  
-   <span data-ttu-id="584ff-113">ポリシーのバージョンを右クリックし、をクリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="584ff-113">Right-click the policy version, and then click **Save**.</span></span>  
  
### <a name="to-publish-a-policy-version"></a><span data-ttu-id="584ff-114">ポリシーのバージョンを公開するには</span><span class="sxs-lookup"><span data-stu-id="584ff-114">To publish a policy version</span></span>  
  
-   <span data-ttu-id="584ff-115">ポリシーのバージョンを右クリックし、をクリックして**発行**です。</span><span class="sxs-lookup"><span data-stu-id="584ff-115">Right-click the policy version, and then click **Publish**.</span></span>  
  
### <a name="to-create-an-updated-version-of-a-policy"></a><span data-ttu-id="584ff-116">ポリシーの更新されたバージョンを作成するには</span><span class="sxs-lookup"><span data-stu-id="584ff-116">To create an updated version of a policy</span></span>  
  
1.  <span data-ttu-id="584ff-117">既存のポリシーのバージョンを右クリックし、をクリックして**コピー**です。</span><span class="sxs-lookup"><span data-stu-id="584ff-117">Right-click an existing policy version, and then click **Copy**.</span></span>  
  
2.  <span data-ttu-id="584ff-118">ポリシー フォルダーを右クリックし、をクリックして**貼り付け**です。</span><span class="sxs-lookup"><span data-stu-id="584ff-118">Right-click the policy folder, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="584ff-119">コピー元と同じ要素を持つ新しいバージョンが作成されます。</span><span class="sxs-lookup"><span data-stu-id="584ff-119">A new version is created, with the same elements as the copied version.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="584ff-120">ポリシーが .NET アセンブリを使用する場合に、そのアセンブリが更新されているときは、ポリシーをアセンブリの新しいバージョンにバインドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="584ff-120">If your policy uses a .NET assembly, and the assembly is updated, you should bind your policy to the newer version of the assembly.</span></span>  
  
### <a name="to-update-a-policy-to-use-an-updated-assembly"></a><span data-ttu-id="584ff-121">ポリシーを更新して更新済みアセンブリを使用するには</span><span class="sxs-lookup"><span data-stu-id="584ff-121">To update a policy to use an updated assembly</span></span>  
  
1.  <span data-ttu-id="584ff-122">をクリックして**開始**、 をポイント**管理ツール**、 をポイント**.NET Framework 構成**、クリックして**アセンブリの構成**.</span><span class="sxs-lookup"><span data-stu-id="584ff-122">Click **Start**, point to **Administrative Tools**, point to **.NET Framework Configuration**, and then click **Configured Assemblies**.</span></span>  
  
2.  <span data-ttu-id="584ff-123">ターゲット アセンブリのプロパティに移動し、**バインド ポリシー**タブです。</span><span class="sxs-lookup"><span data-stu-id="584ff-123">Go to properties for the target assembly and click the **Binding Policy** tab.</span></span>  
  
3.  <span data-ttu-id="584ff-124">グローバル アセンブリ キャッシュで、バージョン番号を新しいバージョンに変更します。</span><span class="sxs-lookup"><span data-stu-id="584ff-124">In the global assembly cache, change the version number to the newer version.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="584ff-125">ポリシーが使用するアセンブリはすべて、グローバル アセンブリ キャッシュに追加されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="584ff-125">All assemblies used by policies should be added to the global assembly cache.</span></span>
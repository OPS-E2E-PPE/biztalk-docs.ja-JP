---
title: ポリシーのバージョンを管理する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, publishing
- publishing policies
- updating, policies
- versioning, policies
- policies, versioning
- policies, updating
ms.assetid: 6e35b2bd-1ecd-45ea-aff3-4ad2437568a4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78750e9db681ad12b1a134ef27360a57a3163bc1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336829"
---
# <a name="how-to-maintain-policy-versions"></a><span data-ttu-id="69eae-102">ポリシーのバージョンを管理する方法</span><span class="sxs-lookup"><span data-stu-id="69eae-102">How to Maintain Policy Versions</span></span>
<span data-ttu-id="69eae-103">ポリシーのバージョンをルールを追加した後は、バージョンを保存するには、将来の開発をルール ストアにまたは明確に定義された、変更できない一連のルール ベースのアプリケーションで使用するためにデプロイできる規則の作成に発行することができます。</span><span class="sxs-lookup"><span data-stu-id="69eae-103">After you add rules to a version of your policy, you can save the version to the rule store for further development, or you can publish it to create a well-defined, immutable set of rules that can be deployed for use in a rule-based application.</span></span>  
  
 <span data-ttu-id="69eae-104">このトピックには、次のタスクの手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="69eae-104">This topic contains procedures for the following tasks:</span></span>  
  
-   <span data-ttu-id="69eae-105">ポリシーの空の新しいバージョンを作成するには</span><span class="sxs-lookup"><span data-stu-id="69eae-105">To create an empty new version of a policy</span></span>  
  
-   <span data-ttu-id="69eae-106">ポリシー バージョンを保存するには</span><span class="sxs-lookup"><span data-stu-id="69eae-106">To save a policy version</span></span>  
  
-   <span data-ttu-id="69eae-107">ポリシー バージョンを発行するには</span><span class="sxs-lookup"><span data-stu-id="69eae-107">To publish a policy version</span></span>  
  
-   <span data-ttu-id="69eae-108">ポリシーの更新バージョンを作成するには</span><span class="sxs-lookup"><span data-stu-id="69eae-108">To create an updated version of a policy</span></span>  
  
-   <span data-ttu-id="69eae-109">更新されたアセンブリを使用するポリシーを更新するには</span><span class="sxs-lookup"><span data-stu-id="69eae-109">To update a policy to use an updated assembly</span></span>  
  
### <a name="to-create-an-empty-new-version-of-a-policy"></a><span data-ttu-id="69eae-110">ポリシーの空の新しいバージョンを作成するには</span><span class="sxs-lookup"><span data-stu-id="69eae-110">To create an empty new version of a policy</span></span>  
  
-   <span data-ttu-id="69eae-111">ポリシー フォルダーを右クリックし、**新しいバージョンの追加**します。</span><span class="sxs-lookup"><span data-stu-id="69eae-111">Right-click the policy folder, and then click **Add New Version**.</span></span>  
  
### <a name="to-save-a-policy-version"></a><span data-ttu-id="69eae-112">ポリシー バージョンを保存するには</span><span class="sxs-lookup"><span data-stu-id="69eae-112">To save a policy version</span></span>  
  
-   <span data-ttu-id="69eae-113">ポリシーのバージョンを右クリックし、をクリックし、**保存**します。</span><span class="sxs-lookup"><span data-stu-id="69eae-113">Right-click the policy version, and then click **Save**.</span></span>  
  
### <a name="to-publish-a-policy-version"></a><span data-ttu-id="69eae-114">ポリシー バージョンを発行するには</span><span class="sxs-lookup"><span data-stu-id="69eae-114">To publish a policy version</span></span>  
  
-   <span data-ttu-id="69eae-115">ポリシーのバージョンを右クリックし、をクリックし、**発行**します。</span><span class="sxs-lookup"><span data-stu-id="69eae-115">Right-click the policy version, and then click **Publish**.</span></span>  
  
### <a name="to-create-an-updated-version-of-a-policy"></a><span data-ttu-id="69eae-116">ポリシーの更新バージョンを作成するには</span><span class="sxs-lookup"><span data-stu-id="69eae-116">To create an updated version of a policy</span></span>  
  
1.  <span data-ttu-id="69eae-117">既存のポリシーのバージョンを右クリックし、をクリックし、**コピー**します。</span><span class="sxs-lookup"><span data-stu-id="69eae-117">Right-click an existing policy version, and then click **Copy**.</span></span>  
  
2.  <span data-ttu-id="69eae-118">ポリシー フォルダーを右クリックし、**貼り付け**します。</span><span class="sxs-lookup"><span data-stu-id="69eae-118">Right-click the policy folder, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="69eae-119">コピーされるバージョンと同じ要素を新しいバージョンが作成されます。</span><span class="sxs-lookup"><span data-stu-id="69eae-119">A new version is created, with the same elements as the copied version.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="69eae-120">ポリシーは、.NET アセンブリを使用して、アセンブリが更新された場合は、アセンブリの新しいバージョンに、ポリシーをバインドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="69eae-120">If your policy uses a .NET assembly, and the assembly is updated, you should bind your policy to the newer version of the assembly.</span></span>  
  
### <a name="to-update-a-policy-to-use-an-updated-assembly"></a><span data-ttu-id="69eae-121">更新されたアセンブリを使用するポリシーを更新するには</span><span class="sxs-lookup"><span data-stu-id="69eae-121">To update a policy to use an updated assembly</span></span>  
  
1.  <span data-ttu-id="69eae-122">をクリックして**開始**、 をポイント**管理ツール**、 をポイント **.NET Framework 構成**、順にクリックします**構成アセンブリ**.</span><span class="sxs-lookup"><span data-stu-id="69eae-122">Click **Start**, point to **Administrative Tools**, point to **.NET Framework Configuration**, and then click **Configured Assemblies**.</span></span>  
  
2.  <span data-ttu-id="69eae-123">ターゲット アセンブリのプロパティに移動し、**バインド ポリシー**タブ。</span><span class="sxs-lookup"><span data-stu-id="69eae-123">Go to properties for the target assembly and click the **Binding Policy** tab.</span></span>  
  
3.  <span data-ttu-id="69eae-124">グローバル アセンブリ キャッシュより新しいバージョンに、バージョン番号を変更します。</span><span class="sxs-lookup"><span data-stu-id="69eae-124">In the global assembly cache, change the version number to the newer version.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="69eae-125">ポリシーによって使用されるすべてのアセンブリは、グローバル アセンブリ キャッシュに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69eae-125">All assemblies used by policies should be added to the global assembly cache.</span></span>
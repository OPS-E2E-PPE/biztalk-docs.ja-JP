---
title: サイド バイ サイド バージョン管理を使用してパイプラインを更新する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd884a76-71dd-4c90-b4ba-f1cd7f48eb04
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bf978b64876a91d06acfbe4c5d34278935cfa55
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970891"
---
# <a name="how-to-update-a-pipeline-using-side-by-side-versioning"></a><span data-ttu-id="04e4e-102">サイド バイ サイド バージョン管理を使用してパイプラインを更新する方法</span><span class="sxs-lookup"><span data-stu-id="04e4e-102">How to Update a Pipeline Using Side-by-Side Versioning</span></span>
<span data-ttu-id="04e4e-103">サイド バイ サイド バージョン管理によって追加された新しいパイプラインを使用する簡単な方法は、送信ポートで、新しく展開されたパイプライン バージョンを選択するか、受信場所にです。</span><span class="sxs-lookup"><span data-stu-id="04e4e-103">The simple way to use a new pipeline added by side-by-side versioning is to select the newly deployed pipeline version in the send port or receive location.</span></span> <span data-ttu-id="04e4e-104">古いパイプラインは、新しいこの置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="04e4e-104">This will replace the old pipeline with the new one.</span></span> <span data-ttu-id="04e4e-105">ただし、後方互換性のための本当のサイド バイ サイドでの機能を必要がある場合する必要がありますの新しい送信ポートを作成および受信場所し指定されたパイプラインの新しいバージョンにバインドします。</span><span class="sxs-lookup"><span data-stu-id="04e4e-105">However, if you need true side-by-side functionality for backwards-compatibility, then you must create new send ports and receive locations and bind them to the new pipeline version specified.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="04e4e-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="04e4e-106">Prerequisites</span></span>  
 <span data-ttu-id="04e4e-107">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="04e4e-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span>  
  
### <a name="to-add-a-new-version-of-a-pipeline-component"></a><span data-ttu-id="04e4e-108">パイプライン コンポーネントの新しいバージョンを追加するには</span><span class="sxs-lookup"><span data-stu-id="04e4e-108">To add a new version of a pipeline component</span></span>  
  
1. <span data-ttu-id="04e4e-109">Visual Studio で、パイプライン コンポーネントの新しいバージョンを作成し、アセンブリに署名します。</span><span class="sxs-lookup"><span data-stu-id="04e4e-109">In Visual Studio, create a new version of the pipeline component, and sign the assembly.</span></span>  
  
2. <span data-ttu-id="04e4e-110">パイプライン コンポーネントを追加、**パイプライン コンポーネント**フォルダー (\<*インストール フォルダー*\>\Pipeline Components)。</span><span class="sxs-lookup"><span data-stu-id="04e4e-110">Add the pipeline component in the **Pipeline Components** folder (\<*installation folder*\>\Pipeline Components).</span></span>  
  
3. <span data-ttu-id="04e4e-111">パイプライン コンポーネントをパイプラインに追加します。</span><span class="sxs-lookup"><span data-stu-id="04e4e-111">Add the pipeline component to your pipeline.</span></span>  
  
4. <span data-ttu-id="04e4e-112">パイプラインを構築しても、ソリューションの配置後からパイプライン コンポーネントの削除、**パイプライン コンポーネント**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="04e4e-112">After building the pipeline or deploying your solution, remove the pipeline component from the **Pipeline Components** folder.</span></span>  
  
5. <span data-ttu-id="04e4e-113">パイプライン コンポーネントをグローバル アセンブリ キャッシュ (GAC) に追加します。</span><span class="sxs-lookup"><span data-stu-id="04e4e-113">Add the pipeline component to the global assembly cache (GAC).</span></span>  
  
   <span data-ttu-id="04e4e-114">次の手順を完了すると、コンパイル済みのパイプライン アセンブリは、パイプライン コンポーネントの正しいバージョンを参照してくださいし、BizTalk Server で使用される AppDomain は、前の検索ではなく、GAC でパイプライン コンポーネントの新しいバージョンを検索パイプライン コンポーネント フォルダーでのパイプライン コンポーネントのバージョンです。</span><span class="sxs-lookup"><span data-stu-id="04e4e-114">After you have completed these steps, the compiled pipeline assembly will refer to the correct version of the pipeline component, and the AppDomain used by BizTalk Server will find the new version of the pipeline component in the GAC, rather than finding the previous version of the pipeline component in the Pipeline Components folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04e4e-115">参照</span><span class="sxs-lookup"><span data-stu-id="04e4e-115">See Also</span></span>  
 [<span data-ttu-id="04e4e-116">サイドバイサイドのバージョン管理を使用した更新</span><span class="sxs-lookup"><span data-stu-id="04e4e-116">Updating Using Side-by-Side Versioning</span></span>](../technical-guides/updating-using-side-by-side-versioning.md)
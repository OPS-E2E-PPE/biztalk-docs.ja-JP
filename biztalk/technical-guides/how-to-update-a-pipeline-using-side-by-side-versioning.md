---
title: サイド バイ サイドのバージョン管理を使用してパイプラインを更新する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 8a5b977d8f0d1964df33c2b2f549bd420d0d3179
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008379"
---
# <a name="how-to-update-a-pipeline-using-side-by-side-versioning"></a><span data-ttu-id="06525-102">サイド バイ サイドのバージョン管理を使用してパイプラインを更新する方法</span><span class="sxs-lookup"><span data-stu-id="06525-102">How to Update a Pipeline Using Side-by-Side Versioning</span></span>
<span data-ttu-id="06525-103">サイド バイ サイドのバージョン管理によって追加された新しいパイプラインを使用する簡単な方法は、送信ポートで、新しく展開されたパイプライン バージョンを選択または受信場所です。</span><span class="sxs-lookup"><span data-stu-id="06525-103">The simple way to use a new pipeline added by side-by-side versioning is to select the newly deployed pipeline version in the send port or receive location.</span></span> <span data-ttu-id="06525-104">これにより、古いパイプライン新しいと置き換わります。</span><span class="sxs-lookup"><span data-stu-id="06525-104">This will replace the old pipeline with the new one.</span></span> <span data-ttu-id="06525-105">ただし、本当のサイド バイ サイドの機能を旧バージョンとの互換性のため必要がある場合する必要がありますの新しい送信ポートを作成および受信場所と指定された新しいパイプライン バージョンにバインドします。</span><span class="sxs-lookup"><span data-stu-id="06525-105">However, if you need true side-by-side functionality for backwards-compatibility, then you must create new send ports and receive locations and bind them to the new pipeline version specified.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="06525-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="06525-106">Prerequisites</span></span>  
 <span data-ttu-id="06525-107">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="06525-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span>  
  
### <a name="to-add-a-new-version-of-a-pipeline-component"></a><span data-ttu-id="06525-108">パイプライン コンポーネントの新しいバージョンを追加するには</span><span class="sxs-lookup"><span data-stu-id="06525-108">To add a new version of a pipeline component</span></span>  
  
1.  <span data-ttu-id="06525-109">Visual Studio で、パイプライン コンポーネントの新しいバージョンを作成し、そのアセンブリに署名します。</span><span class="sxs-lookup"><span data-stu-id="06525-109">In Visual Studio, create a new version of the pipeline component, and sign the assembly.</span></span>  
  
2.  <span data-ttu-id="06525-110">パイプライン コンポーネントを追加、**パイプライン コンポーネント**フォルダー (\<*インストール フォルダー*\>\Pipeline Components)。</span><span class="sxs-lookup"><span data-stu-id="06525-110">Add the pipeline component in the **Pipeline Components** folder (\<*installation folder*\>\Pipeline Components).</span></span>  
  
3.  <span data-ttu-id="06525-111">パイプライン コンポーネントをパイプラインに追加します。</span><span class="sxs-lookup"><span data-stu-id="06525-111">Add the pipeline component to your pipeline.</span></span>  
  
4.  <span data-ttu-id="06525-112">パイプラインを構築またはソリューションを展開した後からパイプライン コンポーネントを削除、**パイプライン コンポーネント**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="06525-112">After building the pipeline or deploying your solution, remove the pipeline component from the **Pipeline Components** folder.</span></span>  
  
5.  <span data-ttu-id="06525-113">パイプライン コンポーネントをグローバル アセンブリ キャッシュ (GAC) に追加します。</span><span class="sxs-lookup"><span data-stu-id="06525-113">Add the pipeline component to the global assembly cache (GAC).</span></span>  
  
 <span data-ttu-id="06525-114">これらの手順を完了した、パイプラインのコンパイルされたアセンブリでは、パイプライン コンポーネントの正しいバージョンを参照し、BizTalk Server で使用される AppDomain は前を検索するのではなく、GAC、パイプライン コンポーネントの新しいバージョンを見つけパイプライン コンポーネント フォルダーでのパイプライン コンポーネントのバージョンです。</span><span class="sxs-lookup"><span data-stu-id="06525-114">After you have completed these steps, the compiled pipeline assembly will refer to the correct version of the pipeline component, and the AppDomain used by BizTalk Server will find the new version of the pipeline component in the GAC, rather than finding the previous version of the pipeline component in the Pipeline Components folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06525-115">参照</span><span class="sxs-lookup"><span data-stu-id="06525-115">See Also</span></span>  
 [<span data-ttu-id="06525-116">サイドバイサイドのバージョン管理を使用した更新</span><span class="sxs-lookup"><span data-stu-id="06525-116">Updating Using Side-by-Side Versioning</span></span>](../technical-guides/updating-using-side-by-side-versioning.md)
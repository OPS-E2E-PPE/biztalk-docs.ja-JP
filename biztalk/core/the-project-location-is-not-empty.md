---
title: プロジェクトの場所が空でない |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db353050-3662-4ab6-8898-4e4d3bd78ac1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2de1e1dd381a75f596b4980430ddcc5d6d8982b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278786"
---
# <a name="the-project-location-is-not-empty"></a><span data-ttu-id="ad77e-102">プロジェクトの場所は空ではありません</span><span class="sxs-lookup"><span data-stu-id="ad77e-102">The project location is not empty</span></span>
## <a name="details"></a><span data-ttu-id="ad77e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ad77e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ad77e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ad77e-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="ad77e-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ad77e-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="ad77e-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ad77e-106">Event ID</span></span>|<span data-ttu-id="ad77e-107">0</span><span class="sxs-lookup"><span data-stu-id="ad77e-107">0</span></span>|  
|<span data-ttu-id="ad77e-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ad77e-108">Event Source</span></span>|<span data-ttu-id="ad77e-109">0</span><span class="sxs-lookup"><span data-stu-id="ad77e-109">0</span></span>|  
|<span data-ttu-id="ad77e-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ad77e-110">Component</span></span>|<span data-ttu-id="ad77e-111">0</span><span class="sxs-lookup"><span data-stu-id="ad77e-111">0</span></span>|  
|<span data-ttu-id="ad77e-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ad77e-112">Symbolic Name</span></span>|<span data-ttu-id="ad77e-113">0</span><span class="sxs-lookup"><span data-stu-id="ad77e-113">0</span></span>|  
|<span data-ttu-id="ad77e-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ad77e-114">Message Text</span></span>|<span data-ttu-id="ad77e-115">プロジェクトの場所 "{0}" は空ではありません。</span><span class="sxs-lookup"><span data-stu-id="ad77e-115">The project location "{0}" is not empty.</span></span> <span data-ttu-id="ad77e-116">次のいずれかを実行する必要があります: 1。</span><span class="sxs-lookup"><span data-stu-id="ad77e-116">You need to do one of the following: 1.</span></span> <span data-ttu-id="ad77e-117">新しいプロジェクトを 2 に別の場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad77e-117">Choose a different location for the new project, 2.</span></span> <span data-ttu-id="ad77e-118">指定して、既存の場所または 3 を再利用する場合は上書きされます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-118">Specify overwrite to reuse the existing location, or 3.</span></span> <span data-ttu-id="ad77e-119">プロジェクトの場所の内容を手動で削除します。</span><span class="sxs-lookup"><span data-stu-id="ad77e-119">Manually delete the contents of the project location.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ad77e-120">説明</span><span class="sxs-lookup"><span data-stu-id="ad77e-120">Explanation</span></span>  
 <span data-ttu-id="ad77e-121">このエラーは、サービスを公開する予定の仮想ディレクトリが空ではないことを示します。</span><span class="sxs-lookup"><span data-stu-id="ad77e-121">This error indicates the virtual directory where the service is trying to be published is not empty.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ad77e-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ad77e-122">User Action</span></span>  
 <span data-ttu-id="ad77e-123">同じ場所を再利用するには、上書きの場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad77e-123">Select the overwrite location to reuse the same location.</span></span> <span data-ttu-id="ad77e-124">または、新しい場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="ad77e-124">Or specify a new location.</span></span>  <span data-ttu-id="ad77e-125">WCF サービス公開ウィザードで選択**既存の場所を上書き** をクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="ad77e-125">In the WCF Service Publishing Wizard, select **Overwrite Existing Location** and click **Next**.</span></span> <span data-ttu-id="ad77e-126">この手順で、場所が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-126">This step overwrites the location.</span></span>
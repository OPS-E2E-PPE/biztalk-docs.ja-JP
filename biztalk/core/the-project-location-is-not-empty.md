---
title: プロジェクトの場所が空でない |Microsoft Docs
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
ms.openlocfilehash: 6fd44cc0d9bfefb67b96558808e6b98a46c8afc2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394087"
---
# <a name="the-project-location-is-not-empty"></a><span data-ttu-id="9a572-102">プロジェクトの場所が空でないです。</span><span class="sxs-lookup"><span data-stu-id="9a572-102">The project location is not empty</span></span>
## <a name="details"></a><span data-ttu-id="9a572-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9a572-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="9a572-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9a572-104">Product Name</span></span>   |                                                                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                                 |
| <span data-ttu-id="9a572-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9a572-105">Product Version</span></span> |                                                                                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                                             |
|    <span data-ttu-id="9a572-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9a572-106">Event ID</span></span>     |                                                                                                                         <span data-ttu-id="9a572-107">0</span><span class="sxs-lookup"><span data-stu-id="9a572-107">0</span></span>                                                                                                                          |
|  <span data-ttu-id="9a572-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9a572-108">Event Source</span></span>   |                                                                                                                         <span data-ttu-id="9a572-109">0</span><span class="sxs-lookup"><span data-stu-id="9a572-109">0</span></span>                                                                                                                          |
|    <span data-ttu-id="9a572-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9a572-110">Component</span></span>    |                                                                                                                         <span data-ttu-id="9a572-111">0</span><span class="sxs-lookup"><span data-stu-id="9a572-111">0</span></span>                                                                                                                          |
|  <span data-ttu-id="9a572-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9a572-112">Symbolic Name</span></span>  |                                                                                                                         <span data-ttu-id="9a572-113">0</span><span class="sxs-lookup"><span data-stu-id="9a572-113">0</span></span>                                                                                                                          |
|  <span data-ttu-id="9a572-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9a572-114">Message Text</span></span>   | <span data-ttu-id="9a572-115">プロジェクトの場所"{0}"が空でないです。</span><span class="sxs-lookup"><span data-stu-id="9a572-115">The project location "{0}" is not empty.</span></span> <span data-ttu-id="9a572-116">次のいずれかを実行する必要があります。1.</span><span class="sxs-lookup"><span data-stu-id="9a572-116">You need to do one of the following: 1.</span></span> <span data-ttu-id="9a572-117">新しいプロジェクトに、2 の別の場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a572-117">Choose a different location for the new project, 2.</span></span> <span data-ttu-id="9a572-118">指定、既存の場所または 3 を再利用する場合は上書きします。</span><span class="sxs-lookup"><span data-stu-id="9a572-118">Specify overwrite to reuse the existing location, or 3.</span></span> <span data-ttu-id="9a572-119">プロジェクトの場所の内容を手動で削除します。</span><span class="sxs-lookup"><span data-stu-id="9a572-119">Manually delete the contents of the project location.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="9a572-120">説明</span><span class="sxs-lookup"><span data-stu-id="9a572-120">Explanation</span></span>  
 <span data-ttu-id="9a572-121">このエラーを示します、仮想サービスの発行先ディレクトリが空ではありません。</span><span class="sxs-lookup"><span data-stu-id="9a572-121">This error indicates the virtual directory where the service is trying to be published is not empty.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9a572-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9a572-122">User Action</span></span>  
 <span data-ttu-id="9a572-123">同じ場所を再利用する上書きの場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a572-123">Select the overwrite location to reuse the same location.</span></span> <span data-ttu-id="9a572-124">または、新しい場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="9a572-124">Or specify a new location.</span></span>  <span data-ttu-id="9a572-125">WCF サービス公開ウィザードで選択**既存の場所を上書き** をクリック**次**します。</span><span class="sxs-lookup"><span data-stu-id="9a572-125">In the WCF Service Publishing Wizard, select **Overwrite Existing Location** and click **Next**.</span></span> <span data-ttu-id="9a572-126">この手順では、場所を上書きします。</span><span class="sxs-lookup"><span data-stu-id="9a572-126">This step overwrites the location.</span></span>
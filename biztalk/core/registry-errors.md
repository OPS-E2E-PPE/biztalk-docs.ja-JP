---
title: レジストリ エラー |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a5bf2cd-f807-4083-8687-4416a2ee2908
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c84ec2a1082f431fef8e06357f14cc9b621c6a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268554"
---
# <a name="registry-errors"></a><span data-ttu-id="0c028-102">レジストリ エラー</span><span class="sxs-lookup"><span data-stu-id="0c028-102">Registry Errors</span></span>
<span data-ttu-id="0c028-103">診断および WCF のレジストリ エラーを解決するための情報です。</span><span class="sxs-lookup"><span data-stu-id="0c028-103">Information for diagnosing and resolving WCF Registry errors.</span></span>  

## <a name="failed-to-access-the-registry"></a><span data-ttu-id="0c028-104">レジストリにアクセスできませんでした</span><span class="sxs-lookup"><span data-stu-id="0c028-104">Failed to access the registry</span></span>
  
||<span data-ttu-id="0c028-105">エラーの詳細</span><span class="sxs-lookup"><span data-stu-id="0c028-105">Error details</span></span>|  
|-|-|  
|<span data-ttu-id="0c028-106">製品名</span><span class="sxs-lookup"><span data-stu-id="0c028-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="0c028-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0c028-107">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="0c028-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0c028-108">Event ID</span></span>|<span data-ttu-id="0c028-109">0</span><span class="sxs-lookup"><span data-stu-id="0c028-109">0</span></span>|  
|<span data-ttu-id="0c028-110">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0c028-110">Event Source</span></span>|<span data-ttu-id="0c028-111">0</span><span class="sxs-lookup"><span data-stu-id="0c028-111">0</span></span>|  
|<span data-ttu-id="0c028-112">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0c028-112">Component</span></span>|<span data-ttu-id="0c028-113">0</span><span class="sxs-lookup"><span data-stu-id="0c028-113">0</span></span>|  
|<span data-ttu-id="0c028-114">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0c028-114">Symbolic Name</span></span>|<span data-ttu-id="0c028-115">0</span><span class="sxs-lookup"><span data-stu-id="0c028-115">0</span></span>|  
|<span data-ttu-id="0c028-116">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0c028-116">Message Text</span></span>|<span data-ttu-id="0c028-117">HKLM を開けませんでした。\\{0}。</span><span class="sxs-lookup"><span data-stu-id="0c028-117">Failed to open HKLM\\{0}.</span></span>|  
  
### <a name="explanation"></a><span data-ttu-id="0c028-118">説明</span><span class="sxs-lookup"><span data-stu-id="0c028-118">Explanation</span></span>  
 <span data-ttu-id="0c028-119">このエラーは、レジストリへのアクセスの失敗を示します。</span><span class="sxs-lookup"><span data-stu-id="0c028-119">This error indicates a failure to access the registry.</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="0c028-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0c028-120">User Action</span></span>  
 <span data-ttu-id="0c028-121">レジストリの読み取りアクセス権があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0c028-121">Ensure you have read access to the registry.</span></span> <span data-ttu-id="0c028-122">レジストリにアクセスするには、管理者特権があることを確認します。管理者特権がない場合は、コンピューターの管理者に連絡してください。</span><span class="sxs-lookup"><span data-stu-id="0c028-122">To access the registry, ensure you have Administrator privileges or contact the administrator of the machine.</span></span>
 
## <a name="failed-to-obtain-biztalk-install-path"></a><span data-ttu-id="0c028-123">BizTalk のインストール パスを取得できませんでした</span><span class="sxs-lookup"><span data-stu-id="0c028-123">Failed to obtain BizTalk install path</span></span>
  
||<span data-ttu-id="0c028-124">エラーの詳細</span><span class="sxs-lookup"><span data-stu-id="0c028-124">Error Details</span></span>|  
|-|-|  
|<span data-ttu-id="0c028-125">製品名</span><span class="sxs-lookup"><span data-stu-id="0c028-125">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="0c028-126">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0c028-126">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="0c028-127">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0c028-127">Event ID</span></span>|<span data-ttu-id="0c028-128">0</span><span class="sxs-lookup"><span data-stu-id="0c028-128">0</span></span>|  
|<span data-ttu-id="0c028-129">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0c028-129">Event Source</span></span>|<span data-ttu-id="0c028-130">0</span><span class="sxs-lookup"><span data-stu-id="0c028-130">0</span></span>|  
|<span data-ttu-id="0c028-131">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0c028-131">Component</span></span>|<span data-ttu-id="0c028-132">0</span><span class="sxs-lookup"><span data-stu-id="0c028-132">0</span></span>|  
|<span data-ttu-id="0c028-133">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0c028-133">Symbolic Name</span></span>|<span data-ttu-id="0c028-134">0</span><span class="sxs-lookup"><span data-stu-id="0c028-134">0</span></span>|  
|<span data-ttu-id="0c028-135">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0c028-135">Message Text</span></span>|<span data-ttu-id="0c028-136">HKLM から BizTalk のインストール パスを取得できませんでした\\{0}\\{1}。</span><span class="sxs-lookup"><span data-stu-id="0c028-136">Failed to obtain BizTalk install path from HKLM\\{0}\\{1}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0c028-137">説明</span><span class="sxs-lookup"><span data-stu-id="0c028-137">Explanation</span></span>  
 <span data-ttu-id="0c028-138">このエラーは、レジストリへのアクセスに失敗し、キーの値が不適切であることを示します。</span><span class="sxs-lookup"><span data-stu-id="0c028-138">This error indicates a failure to access the registry, and that the key has an incorrect value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0c028-139">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0c028-139">User Action</span></span>  
 <span data-ttu-id="0c028-140">レジストリの読み取りアクセス権があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0c028-140">Ensure you have read access to the registry.</span></span> <span data-ttu-id="0c028-141">キーの値が正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="0c028-141">Ensure the key has the correct value.</span></span> <span data-ttu-id="0c028-142">レジストリにアクセスするには、管理者特権があることを確認します。管理者特権がない場合は、コンピューターの管理者に連絡してください。</span><span class="sxs-lookup"><span data-stu-id="0c028-142">To access the registry, ensure you have Administrator privileges or contact the administrator of the machine.</span></span> 
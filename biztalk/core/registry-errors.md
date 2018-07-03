---
title: レジストリ エラー |Microsoft Docs
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
ms.openlocfilehash: 62522299866748d92abf91d36a01444c3175b070
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975115"
---
# <a name="registry-errors"></a><span data-ttu-id="17b47-102">レジストリ エラー</span><span class="sxs-lookup"><span data-stu-id="17b47-102">Registry Errors</span></span>
<span data-ttu-id="17b47-103">診断および WCF のレジストリ エラーを解決するための情報です。</span><span class="sxs-lookup"><span data-stu-id="17b47-103">Information for diagnosing and resolving WCF Registry errors.</span></span>  

## <a name="failed-to-access-the-registry"></a><span data-ttu-id="17b47-104">レジストリにアクセスできませんでした</span><span class="sxs-lookup"><span data-stu-id="17b47-104">Failed to access the registry</span></span>
  
|                 |                                   <span data-ttu-id="17b47-105">エラーの詳細</span><span class="sxs-lookup"><span data-stu-id="17b47-105">Error details</span></span>                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="17b47-106">製品名</span><span class="sxs-lookup"><span data-stu-id="17b47-106">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="17b47-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="17b47-107">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="17b47-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="17b47-108">Event ID</span></span>     |                                         <span data-ttu-id="17b47-109">0</span><span class="sxs-lookup"><span data-stu-id="17b47-109">0</span></span>                                          |
|  <span data-ttu-id="17b47-110">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="17b47-110">Event Source</span></span>   |                                         <span data-ttu-id="17b47-111">0</span><span class="sxs-lookup"><span data-stu-id="17b47-111">0</span></span>                                          |
|    <span data-ttu-id="17b47-112">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="17b47-112">Component</span></span>    |                                         <span data-ttu-id="17b47-113">0</span><span class="sxs-lookup"><span data-stu-id="17b47-113">0</span></span>                                          |
|  <span data-ttu-id="17b47-114">シンボル名</span><span class="sxs-lookup"><span data-stu-id="17b47-114">Symbolic Name</span></span>  |                                         <span data-ttu-id="17b47-115">0</span><span class="sxs-lookup"><span data-stu-id="17b47-115">0</span></span>                                          |
|  <span data-ttu-id="17b47-116">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="17b47-116">Message Text</span></span>   |                             <span data-ttu-id="17b47-117">HKLM を開けませんでした。\\{0}します。</span><span class="sxs-lookup"><span data-stu-id="17b47-117">Failed to open HKLM\\{0}.</span></span>                              |
  
### <a name="explanation"></a><span data-ttu-id="17b47-118">説明</span><span class="sxs-lookup"><span data-stu-id="17b47-118">Explanation</span></span>  
 <span data-ttu-id="17b47-119">このエラーは、レジストリへのアクセスの失敗を示します。</span><span class="sxs-lookup"><span data-stu-id="17b47-119">This error indicates a failure to access the registry.</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="17b47-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="17b47-120">User Action</span></span>  
 <span data-ttu-id="17b47-121">レジストリの読み取りアクセス権があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="17b47-121">Ensure you have read access to the registry.</span></span> <span data-ttu-id="17b47-122">レジストリにアクセスするには、管理者特権があることを確認します。管理者特権がない場合は、コンピューターの管理者に連絡してください。</span><span class="sxs-lookup"><span data-stu-id="17b47-122">To access the registry, ensure you have Administrator privileges or contact the administrator of the machine.</span></span>
 
## <a name="failed-to-obtain-biztalk-install-path"></a><span data-ttu-id="17b47-123">BizTalk のインストール パスを取得できませんでした</span><span class="sxs-lookup"><span data-stu-id="17b47-123">Failed to obtain BizTalk install path</span></span>
  
|                 |                                   <span data-ttu-id="17b47-124">エラーの詳細</span><span class="sxs-lookup"><span data-stu-id="17b47-124">Error Details</span></span>                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="17b47-125">製品名</span><span class="sxs-lookup"><span data-stu-id="17b47-125">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="17b47-126">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="17b47-126">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="17b47-127">イベント ID</span><span class="sxs-lookup"><span data-stu-id="17b47-127">Event ID</span></span>     |                                         <span data-ttu-id="17b47-128">0</span><span class="sxs-lookup"><span data-stu-id="17b47-128">0</span></span>                                          |
|  <span data-ttu-id="17b47-129">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="17b47-129">Event Source</span></span>   |                                         <span data-ttu-id="17b47-130">0</span><span class="sxs-lookup"><span data-stu-id="17b47-130">0</span></span>                                          |
|    <span data-ttu-id="17b47-131">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="17b47-131">Component</span></span>    |                                         <span data-ttu-id="17b47-132">0</span><span class="sxs-lookup"><span data-stu-id="17b47-132">0</span></span>                                          |
|  <span data-ttu-id="17b47-133">シンボル名</span><span class="sxs-lookup"><span data-stu-id="17b47-133">Symbolic Name</span></span>  |                                         <span data-ttu-id="17b47-134">0</span><span class="sxs-lookup"><span data-stu-id="17b47-134">0</span></span>                                          |
|  <span data-ttu-id="17b47-135">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="17b47-135">Message Text</span></span>   |             <span data-ttu-id="17b47-136">HKLM から BizTalk のインストール パスを取得できませんでした。\\{0}\\{1}</span><span class="sxs-lookup"><span data-stu-id="17b47-136">Failed to obtain BizTalk install path from HKLM\\{0}\\{1}</span></span>              |
  
## <a name="explanation"></a><span data-ttu-id="17b47-137">説明</span><span class="sxs-lookup"><span data-stu-id="17b47-137">Explanation</span></span>  
 <span data-ttu-id="17b47-138">このエラーは、レジストリへのアクセスに失敗し、キーの値が不適切であることを示します。</span><span class="sxs-lookup"><span data-stu-id="17b47-138">This error indicates a failure to access the registry, and that the key has an incorrect value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="17b47-139">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="17b47-139">User Action</span></span>  
 <span data-ttu-id="17b47-140">レジストリの読み取りアクセス権があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="17b47-140">Ensure you have read access to the registry.</span></span> <span data-ttu-id="17b47-141">キーの値が正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="17b47-141">Ensure the key has the correct value.</span></span> <span data-ttu-id="17b47-142">レジストリにアクセスするには、管理者特権があることを確認します。管理者特権がない場合は、コンピューターの管理者に連絡してください。</span><span class="sxs-lookup"><span data-stu-id="17b47-142">To access the registry, ensure you have Administrator privileges or contact the administrator of the machine.</span></span> 
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
ms.openlocfilehash: afca0825ee04334385925d08e3edb0d0ed055c19
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398000"
---
# <a name="registry-errors"></a><span data-ttu-id="14bfc-102">レジストリ エラー</span><span class="sxs-lookup"><span data-stu-id="14bfc-102">Registry Errors</span></span>
<span data-ttu-id="14bfc-103">診断および WCF のレジストリ エラーを解決するための情報です。</span><span class="sxs-lookup"><span data-stu-id="14bfc-103">Information for diagnosing and resolving WCF Registry errors.</span></span>  

## <a name="failed-to-access-the-registry"></a><span data-ttu-id="14bfc-104">レジストリにアクセスできませんでした</span><span class="sxs-lookup"><span data-stu-id="14bfc-104">Failed to access the registry</span></span>
  
|                 |                                   <span data-ttu-id="14bfc-105">エラーの詳細</span><span class="sxs-lookup"><span data-stu-id="14bfc-105">Error details</span></span>                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="14bfc-106">製品名</span><span class="sxs-lookup"><span data-stu-id="14bfc-106">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="14bfc-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="14bfc-107">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="14bfc-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="14bfc-108">Event ID</span></span>     |                                         <span data-ttu-id="14bfc-109">0</span><span class="sxs-lookup"><span data-stu-id="14bfc-109">0</span></span>                                          |
|  <span data-ttu-id="14bfc-110">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="14bfc-110">Event Source</span></span>   |                                         <span data-ttu-id="14bfc-111">0</span><span class="sxs-lookup"><span data-stu-id="14bfc-111">0</span></span>                                          |
|    <span data-ttu-id="14bfc-112">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="14bfc-112">Component</span></span>    |                                         <span data-ttu-id="14bfc-113">0</span><span class="sxs-lookup"><span data-stu-id="14bfc-113">0</span></span>                                          |
|  <span data-ttu-id="14bfc-114">シンボル名</span><span class="sxs-lookup"><span data-stu-id="14bfc-114">Symbolic Name</span></span>  |                                         <span data-ttu-id="14bfc-115">0</span><span class="sxs-lookup"><span data-stu-id="14bfc-115">0</span></span>                                          |
|  <span data-ttu-id="14bfc-116">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="14bfc-116">Message Text</span></span>   |                             <span data-ttu-id="14bfc-117">HKLM を開けませんでした。\\{0}します。</span><span class="sxs-lookup"><span data-stu-id="14bfc-117">Failed to open HKLM\\{0}.</span></span>                              |
  
### <a name="explanation"></a><span data-ttu-id="14bfc-118">説明</span><span class="sxs-lookup"><span data-stu-id="14bfc-118">Explanation</span></span>  
 <span data-ttu-id="14bfc-119">このエラーは、レジストリへのアクセスに失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="14bfc-119">This error indicates a failure to access the registry.</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="14bfc-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="14bfc-120">User Action</span></span>  
 <span data-ttu-id="14bfc-121">レジストリに読み取りアクセス権があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="14bfc-121">Ensure you have read access to the registry.</span></span> <span data-ttu-id="14bfc-122">レジストリにアクセスするには、管理者特権があるか、コンピューターの管理者を確認してください。</span><span class="sxs-lookup"><span data-stu-id="14bfc-122">To access the registry, ensure you have Administrator privileges or contact the administrator of the machine.</span></span>
 
## <a name="failed-to-obtain-biztalk-install-path"></a><span data-ttu-id="14bfc-123">BizTalk のインストール パスを取得できませんでした</span><span class="sxs-lookup"><span data-stu-id="14bfc-123">Failed to obtain BizTalk install path</span></span>
  
|                 |                                   <span data-ttu-id="14bfc-124">エラーの詳細</span><span class="sxs-lookup"><span data-stu-id="14bfc-124">Error Details</span></span>                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="14bfc-125">製品名</span><span class="sxs-lookup"><span data-stu-id="14bfc-125">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="14bfc-126">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="14bfc-126">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="14bfc-127">イベント ID</span><span class="sxs-lookup"><span data-stu-id="14bfc-127">Event ID</span></span>     |                                         <span data-ttu-id="14bfc-128">0</span><span class="sxs-lookup"><span data-stu-id="14bfc-128">0</span></span>                                          |
|  <span data-ttu-id="14bfc-129">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="14bfc-129">Event Source</span></span>   |                                         <span data-ttu-id="14bfc-130">0</span><span class="sxs-lookup"><span data-stu-id="14bfc-130">0</span></span>                                          |
|    <span data-ttu-id="14bfc-131">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="14bfc-131">Component</span></span>    |                                         <span data-ttu-id="14bfc-132">0</span><span class="sxs-lookup"><span data-stu-id="14bfc-132">0</span></span>                                          |
|  <span data-ttu-id="14bfc-133">シンボル名</span><span class="sxs-lookup"><span data-stu-id="14bfc-133">Symbolic Name</span></span>  |                                         <span data-ttu-id="14bfc-134">0</span><span class="sxs-lookup"><span data-stu-id="14bfc-134">0</span></span>                                          |
|  <span data-ttu-id="14bfc-135">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="14bfc-135">Message Text</span></span>   |             <span data-ttu-id="14bfc-136">HKLM から BizTalk のインストール パスを取得できませんでした。\\{0}\\{1}</span><span class="sxs-lookup"><span data-stu-id="14bfc-136">Failed to obtain BizTalk install path from HKLM\\{0}\\{1}</span></span>              |
  
## <a name="explanation"></a><span data-ttu-id="14bfc-137">説明</span><span class="sxs-lookup"><span data-stu-id="14bfc-137">Explanation</span></span>  
 <span data-ttu-id="14bfc-138">このエラーは、レジストリへのアクセス失敗を示します、およびキー値が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="14bfc-138">This error indicates a failure to access the registry, and that the key has an incorrect value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="14bfc-139">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="14bfc-139">User Action</span></span>  
 <span data-ttu-id="14bfc-140">レジストリに読み取りアクセス権があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="14bfc-140">Ensure you have read access to the registry.</span></span> <span data-ttu-id="14bfc-141">キーが正しい値を確認します。</span><span class="sxs-lookup"><span data-stu-id="14bfc-141">Ensure the key has the correct value.</span></span> <span data-ttu-id="14bfc-142">レジストリにアクセスするには、管理者特権があるか、コンピューターの管理者を確認してください。</span><span class="sxs-lookup"><span data-stu-id="14bfc-142">To access the registry, ensure you have Administrator privileges or contact the administrator of the machine.</span></span> 
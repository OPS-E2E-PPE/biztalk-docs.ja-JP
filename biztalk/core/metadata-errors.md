---
title: メタデータ エラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccb60c91-5905-4852-813b-586b82de4825
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7699aa162044e13b5f3176e38cf858a5268e25f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324942"
---
# <a name="metadata-errors"></a><span data-ttu-id="6351d-102">メタデータ エラー</span><span class="sxs-lookup"><span data-stu-id="6351d-102">Metadata Errors</span></span>
<span data-ttu-id="6351d-103">診断と WCF メタデータのエラーの解決に関する情報。</span><span class="sxs-lookup"><span data-stu-id="6351d-103">Information for diagnosing and resolving WCF Metadata errors.</span></span>  
  
## <a name="error-consuming-wcf-service-metadata"></a><span data-ttu-id="6351d-104">WCF サービスのメタデータを使用中にエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="6351d-104">Error consuming WCF service metadata</span></span>

|                 |                                   <span data-ttu-id="6351d-105">エラーの詳細</span><span class="sxs-lookup"><span data-stu-id="6351d-105">Error details</span></span>                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="6351d-106">製品名</span><span class="sxs-lookup"><span data-stu-id="6351d-106">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="6351d-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6351d-107">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="6351d-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6351d-108">Event ID</span></span>     |                                         <span data-ttu-id="6351d-109">0</span><span class="sxs-lookup"><span data-stu-id="6351d-109">0</span></span>                                          |
|  <span data-ttu-id="6351d-110">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6351d-110">Event Source</span></span>   |                                         <span data-ttu-id="6351d-111">0</span><span class="sxs-lookup"><span data-stu-id="6351d-111">0</span></span>                                          |
|    <span data-ttu-id="6351d-112">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6351d-112">Component</span></span>    |                                         <span data-ttu-id="6351d-113">0</span><span class="sxs-lookup"><span data-stu-id="6351d-113">0</span></span>                                          |
|  <span data-ttu-id="6351d-114">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6351d-114">Symbolic Name</span></span>  |                                         <span data-ttu-id="6351d-115">0</span><span class="sxs-lookup"><span data-stu-id="6351d-115">0</span></span>                                          |
|  <span data-ttu-id="6351d-116">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6351d-116">Message Text</span></span>   |                        <span data-ttu-id="6351d-117">WCF サービスのメタデータを使用中にエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="6351d-117">Error consuming WCF service metadata</span></span>                        |
  
### <a name="explanation"></a><span data-ttu-id="6351d-118">説明</span><span class="sxs-lookup"><span data-stu-id="6351d-118">Explanation</span></span>  
 <span data-ttu-id="6351d-119">このエラーは、サービスがないか、メタデータを示します使用できるか、無効です。</span><span class="sxs-lookup"><span data-stu-id="6351d-119">This error indicates the metadata for the service is either not available or is not valid.</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="6351d-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6351d-120">User Action</span></span>  
 <span data-ttu-id="6351d-121">サービス メタデータを修正し、(使用する WCF サービスを所有) 場合を使用しようとします。</span><span class="sxs-lookup"><span data-stu-id="6351d-121">Correct the service metadata and try to consume (if you own the WCF service you are trying to consume).</span></span> <span data-ttu-id="6351d-122">サービス構成エディターに移動 (**svcConfigEditor.exe**)、構成ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="6351d-122">Go to the Service Configuration Editor (**svcConfigEditor.exe**) and make changes to the configuration file.</span></span>  <span data-ttu-id="6351d-123">それ以外の場合、サービス プロバイダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="6351d-123">Otherwise, contact the service provider</span></span>

## <a name="failed-to-get-metadata"></a><span data-ttu-id="6351d-124">メタデータを取得できませんでした</span><span class="sxs-lookup"><span data-stu-id="6351d-124">Failed to get metadata</span></span>

|                 |                                   <span data-ttu-id="6351d-125">エラーの詳細</span><span class="sxs-lookup"><span data-stu-id="6351d-125">Error details</span></span>                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="6351d-126">製品名</span><span class="sxs-lookup"><span data-stu-id="6351d-126">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="6351d-127">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6351d-127">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="6351d-128">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6351d-128">Event ID</span></span>     |                                         <span data-ttu-id="6351d-129">0</span><span class="sxs-lookup"><span data-stu-id="6351d-129">0</span></span>                                          |
|  <span data-ttu-id="6351d-130">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6351d-130">Event Source</span></span>   |                                         <span data-ttu-id="6351d-131">0</span><span class="sxs-lookup"><span data-stu-id="6351d-131">0</span></span>                                          |
|    <span data-ttu-id="6351d-132">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6351d-132">Component</span></span>    |                                         <span data-ttu-id="6351d-133">0</span><span class="sxs-lookup"><span data-stu-id="6351d-133">0</span></span>                                          |
|  <span data-ttu-id="6351d-134">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6351d-134">Symbolic Name</span></span>  |                                         <span data-ttu-id="6351d-135">0</span><span class="sxs-lookup"><span data-stu-id="6351d-135">0</span></span>                                          |
|  <span data-ttu-id="6351d-136">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6351d-136">Message Text</span></span>   |                          <span data-ttu-id="6351d-137">メタデータを取得できませんでした"{0}</span><span class="sxs-lookup"><span data-stu-id="6351d-137">Failed to get metadata from "{0}</span></span>                          |
  
## <a name="explanation"></a><span data-ttu-id="6351d-138">説明</span><span class="sxs-lookup"><span data-stu-id="6351d-138">Explanation</span></span>  
 <span data-ttu-id="6351d-139">このエラーは、メタデータをそのサービスのご利用いただけませんを示します。</span><span class="sxs-lookup"><span data-stu-id="6351d-139">This error indicates the metadata is not available for that service.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6351d-140">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6351d-140">User Action</span></span>  
 <span data-ttu-id="6351d-141">サービスのメタデータを有効にして、(使用する WCF サービスを所有) 場合は、使用ウィザードを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="6351d-141">Enable metadata for the service and run the consuming wizard again (if you own the WCF service you are trying to consume).</span></span> <span data-ttu-id="6351d-142">それ以外の場合、サービス プロバイダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="6351d-142">Otherwise, contact the service provider.</span></span>
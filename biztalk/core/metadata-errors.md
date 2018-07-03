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
ms.openlocfilehash: 07167c2c0189c36f7b1a321d81bd0070398953e8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975123"
---
# <a name="metadata-errors"></a><span data-ttu-id="b86ab-102">メタデータ エラー</span><span class="sxs-lookup"><span data-stu-id="b86ab-102">Metadata Errors</span></span>
<span data-ttu-id="b86ab-103">診断と WCF メタデータのエラーの解決に関する情報。</span><span class="sxs-lookup"><span data-stu-id="b86ab-103">Information for diagnosing and resolving WCF Metadata errors.</span></span>  
  
## <a name="error-consuming-wcf-service-metadata"></a><span data-ttu-id="b86ab-104">WCF サービスのメタデータを使用中にエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="b86ab-104">Error consuming WCF service metadata</span></span>

|                 |                                   <span data-ttu-id="b86ab-105">エラーの詳細</span><span class="sxs-lookup"><span data-stu-id="b86ab-105">Error details</span></span>                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="b86ab-106">製品名</span><span class="sxs-lookup"><span data-stu-id="b86ab-106">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="b86ab-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b86ab-107">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="b86ab-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b86ab-108">Event ID</span></span>     |                                         <span data-ttu-id="b86ab-109">0</span><span class="sxs-lookup"><span data-stu-id="b86ab-109">0</span></span>                                          |
|  <span data-ttu-id="b86ab-110">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b86ab-110">Event Source</span></span>   |                                         <span data-ttu-id="b86ab-111">0</span><span class="sxs-lookup"><span data-stu-id="b86ab-111">0</span></span>                                          |
|    <span data-ttu-id="b86ab-112">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b86ab-112">Component</span></span>    |                                         <span data-ttu-id="b86ab-113">0</span><span class="sxs-lookup"><span data-stu-id="b86ab-113">0</span></span>                                          |
|  <span data-ttu-id="b86ab-114">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b86ab-114">Symbolic Name</span></span>  |                                         <span data-ttu-id="b86ab-115">0</span><span class="sxs-lookup"><span data-stu-id="b86ab-115">0</span></span>                                          |
|  <span data-ttu-id="b86ab-116">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b86ab-116">Message Text</span></span>   |                        <span data-ttu-id="b86ab-117">WCF サービスのメタデータを使用中にエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="b86ab-117">Error consuming WCF service metadata</span></span>                        |
  
### <a name="explanation"></a><span data-ttu-id="b86ab-118">説明</span><span class="sxs-lookup"><span data-stu-id="b86ab-118">Explanation</span></span>  
 <span data-ttu-id="b86ab-119">このエラーは、サービスのメタデータが使用できないか、有効ではないことを示します。</span><span class="sxs-lookup"><span data-stu-id="b86ab-119">This error indicates the metadata for the service is either not available or is not valid.</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="b86ab-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b86ab-120">User Action</span></span>  
 <span data-ttu-id="b86ab-121">サービスのメタデータを修正して使用します (使用する WCF サービスを所有している場合)。</span><span class="sxs-lookup"><span data-stu-id="b86ab-121">Correct the service metadata and try to consume (if you own the WCF service you are trying to consume).</span></span> <span data-ttu-id="b86ab-122">サービス構成エディターに移動 (**svcConfigEditor.exe**)、構成ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="b86ab-122">Go to the Service Configuration Editor (**svcConfigEditor.exe**) and make changes to the configuration file.</span></span>  <span data-ttu-id="b86ab-123">それ以外の場合、サービス プロバイダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="b86ab-123">Otherwise, contact the service provider</span></span>

## <a name="failed-to-get-metadata"></a><span data-ttu-id="b86ab-124">メタデータを取得できませんでした</span><span class="sxs-lookup"><span data-stu-id="b86ab-124">Failed to get metadata</span></span>

|                 |                                   <span data-ttu-id="b86ab-125">エラーの詳細</span><span class="sxs-lookup"><span data-stu-id="b86ab-125">Error details</span></span>                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="b86ab-126">製品名</span><span class="sxs-lookup"><span data-stu-id="b86ab-126">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="b86ab-127">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b86ab-127">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="b86ab-128">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b86ab-128">Event ID</span></span>     |                                         <span data-ttu-id="b86ab-129">0</span><span class="sxs-lookup"><span data-stu-id="b86ab-129">0</span></span>                                          |
|  <span data-ttu-id="b86ab-130">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b86ab-130">Event Source</span></span>   |                                         <span data-ttu-id="b86ab-131">0</span><span class="sxs-lookup"><span data-stu-id="b86ab-131">0</span></span>                                          |
|    <span data-ttu-id="b86ab-132">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b86ab-132">Component</span></span>    |                                         <span data-ttu-id="b86ab-133">0</span><span class="sxs-lookup"><span data-stu-id="b86ab-133">0</span></span>                                          |
|  <span data-ttu-id="b86ab-134">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b86ab-134">Symbolic Name</span></span>  |                                         <span data-ttu-id="b86ab-135">0</span><span class="sxs-lookup"><span data-stu-id="b86ab-135">0</span></span>                                          |
|  <span data-ttu-id="b86ab-136">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b86ab-136">Message Text</span></span>   |                          <span data-ttu-id="b86ab-137">メタデータを取得できませんでした"{0}</span><span class="sxs-lookup"><span data-stu-id="b86ab-137">Failed to get metadata from "{0}</span></span>                          |
  
## <a name="explanation"></a><span data-ttu-id="b86ab-138">説明</span><span class="sxs-lookup"><span data-stu-id="b86ab-138">Explanation</span></span>  
 <span data-ttu-id="b86ab-139">このエラーは、メタデータをそのサービスに使用できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="b86ab-139">This error indicates the metadata is not available for that service.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b86ab-140">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b86ab-140">User Action</span></span>  
 <span data-ttu-id="b86ab-141">サービスに対してメタデータを有効にし、カスタマイズ ウィザードをもう一度実行します (使用する WCF サービスを所有している場合)。</span><span class="sxs-lookup"><span data-stu-id="b86ab-141">Enable metadata for the service and run the consuming wizard again (if you own the WCF service you are trying to consume).</span></span> <span data-ttu-id="b86ab-142">それ以外の場合、サービス プロバイダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="b86ab-142">Otherwise, contact the service provider.</span></span>
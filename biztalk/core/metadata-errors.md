---
title: "メタデータ エラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ccb60c91-5905-4852-813b-586b82de4825
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4dce5fc9eb944eccbeed57073c2546f81825ec6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="metadata-errors"></a><span data-ttu-id="8b996-102">メタデータ エラー</span><span class="sxs-lookup"><span data-stu-id="8b996-102">Metadata Errors</span></span>
<span data-ttu-id="8b996-103">診断および WCF のメタデータ エラーを解決するための情報です。</span><span class="sxs-lookup"><span data-stu-id="8b996-103">Information for diagnosing and resolving WCF Metadata errors.</span></span>  
  
## <a name="error-consuming-wcf-service-metadata"></a><span data-ttu-id="8b996-104">WCF サービスのメタデータを使用中にエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="8b996-104">Error consuming WCF service metadata</span></span>

||<span data-ttu-id="8b996-105">エラーの詳細</span><span class="sxs-lookup"><span data-stu-id="8b996-105">Error details</span></span>|  
|-|-|  
|<span data-ttu-id="8b996-106">製品名</span><span class="sxs-lookup"><span data-stu-id="8b996-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="8b996-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="8b996-107">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="8b996-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="8b996-108">Event ID</span></span>|<span data-ttu-id="8b996-109">0</span><span class="sxs-lookup"><span data-stu-id="8b996-109">0</span></span>|  
|<span data-ttu-id="8b996-110">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="8b996-110">Event Source</span></span>|<span data-ttu-id="8b996-111">0</span><span class="sxs-lookup"><span data-stu-id="8b996-111">0</span></span>|  
|<span data-ttu-id="8b996-112">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8b996-112">Component</span></span>|<span data-ttu-id="8b996-113">0</span><span class="sxs-lookup"><span data-stu-id="8b996-113">0</span></span>|  
|<span data-ttu-id="8b996-114">シンボル名</span><span class="sxs-lookup"><span data-stu-id="8b996-114">Symbolic Name</span></span>|<span data-ttu-id="8b996-115">0</span><span class="sxs-lookup"><span data-stu-id="8b996-115">0</span></span>|  
|<span data-ttu-id="8b996-116">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="8b996-116">Message Text</span></span>|<span data-ttu-id="8b996-117">WCF サービスのメタデータを使用中にエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="8b996-117">Error consuming WCF service metadata</span></span>|  
  
### <a name="explanation"></a><span data-ttu-id="8b996-118">説明</span><span class="sxs-lookup"><span data-stu-id="8b996-118">Explanation</span></span>  
 <span data-ttu-id="8b996-119">このエラーは、サービスのメタデータが使用できないか、有効ではないことを示します。</span><span class="sxs-lookup"><span data-stu-id="8b996-119">This error indicates the metadata for the service is either not available or is not valid.</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="8b996-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="8b996-120">User Action</span></span>  
 <span data-ttu-id="8b996-121">サービスのメタデータを修正して使用します (使用する WCF サービスを所有している場合)。</span><span class="sxs-lookup"><span data-stu-id="8b996-121">Correct the service metadata and try to consume (if you own the WCF service you are trying to consume).</span></span> <span data-ttu-id="8b996-122">サービス構成エディターに移動 (**svcConfigEditor.exe**) して、構成ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="8b996-122">Go to the Service Configuration Editor (**svcConfigEditor.exe**) and make changes to the configuration file.</span></span>  <span data-ttu-id="8b996-123">それ以外の場合、サービス プロバイダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="8b996-123">Otherwise, contact the service provider</span></span>

## <a name="failed-to-get-metadata"></a><span data-ttu-id="8b996-124">メタデータを取得できませんでした</span><span class="sxs-lookup"><span data-stu-id="8b996-124">Failed to get metadata</span></span>

||<span data-ttu-id="8b996-125">エラーの詳細</span><span class="sxs-lookup"><span data-stu-id="8b996-125">Error details</span></span>|  
|-|-|  
|<span data-ttu-id="8b996-126">製品名</span><span class="sxs-lookup"><span data-stu-id="8b996-126">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="8b996-127">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="8b996-127">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="8b996-128">イベント ID</span><span class="sxs-lookup"><span data-stu-id="8b996-128">Event ID</span></span>|<span data-ttu-id="8b996-129">0</span><span class="sxs-lookup"><span data-stu-id="8b996-129">0</span></span>|  
|<span data-ttu-id="8b996-130">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="8b996-130">Event Source</span></span>|<span data-ttu-id="8b996-131">0</span><span class="sxs-lookup"><span data-stu-id="8b996-131">0</span></span>|  
|<span data-ttu-id="8b996-132">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8b996-132">Component</span></span>|<span data-ttu-id="8b996-133">0</span><span class="sxs-lookup"><span data-stu-id="8b996-133">0</span></span>|  
|<span data-ttu-id="8b996-134">シンボル名</span><span class="sxs-lookup"><span data-stu-id="8b996-134">Symbolic Name</span></span>|<span data-ttu-id="8b996-135">0</span><span class="sxs-lookup"><span data-stu-id="8b996-135">0</span></span>|  
|<span data-ttu-id="8b996-136">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="8b996-136">Message Text</span></span>|<span data-ttu-id="8b996-137">"{0}" からメタデータを取得できませんでした。</span><span class="sxs-lookup"><span data-stu-id="8b996-137">Failed to get metadata from "{0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8b996-138">説明</span><span class="sxs-lookup"><span data-stu-id="8b996-138">Explanation</span></span>  
 <span data-ttu-id="8b996-139">このエラーは、メタデータをそのサービスに使用できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="8b996-139">This error indicates the metadata is not available for that service.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8b996-140">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="8b996-140">User Action</span></span>  
 <span data-ttu-id="8b996-141">サービスに対してメタデータを有効にし、カスタマイズ ウィザードをもう一度実行します (使用する WCF サービスを所有している場合)。</span><span class="sxs-lookup"><span data-stu-id="8b996-141">Enable metadata for the service and run the consuming wizard again (if you own the WCF service you are trying to consume).</span></span> <span data-ttu-id="8b996-142">それ以外の場合、サービス プロバイダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="8b996-142">Otherwise, contact the service provider.</span></span>
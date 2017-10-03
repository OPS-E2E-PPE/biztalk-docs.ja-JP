---
title: "送信エラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3cf61c82-ad48-4555-af53-fb841fd0f503
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67741af0520d990be9a552685c8319aa6a5ae881
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="send-errors"></a><span data-ttu-id="2ad3d-102">送信エラー</span><span class="sxs-lookup"><span data-stu-id="2ad3d-102">Send Errors</span></span>
<span data-ttu-id="2ad3d-103">診断および WCF の送信エラーを解決するための情報です。</span><span class="sxs-lookup"><span data-stu-id="2ad3d-103">Information for diagnosing and resolving WCF Send errors.</span></span>  
  
## <a name="failed-to-generate-odx-file"></a><span data-ttu-id="2ad3d-104">ODX ファイルを生成できませんでした</span><span class="sxs-lookup"><span data-stu-id="2ad3d-104">Failed to generate ODX file</span></span>

||<span data-ttu-id="2ad3d-105">エラーの詳細</span><span class="sxs-lookup"><span data-stu-id="2ad3d-105">Error details</span></span>|  
|-|-|  
|<span data-ttu-id="2ad3d-106">製品名</span><span class="sxs-lookup"><span data-stu-id="2ad3d-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="2ad3d-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="2ad3d-107">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="2ad3d-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="2ad3d-108">Event ID</span></span>|<span data-ttu-id="2ad3d-109">0</span><span class="sxs-lookup"><span data-stu-id="2ad3d-109">0</span></span>|  
|<span data-ttu-id="2ad3d-110">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="2ad3d-110">Event Source</span></span>|<span data-ttu-id="2ad3d-111">0</span><span class="sxs-lookup"><span data-stu-id="2ad3d-111">0</span></span>|  
|<span data-ttu-id="2ad3d-112">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2ad3d-112">Component</span></span>|<span data-ttu-id="2ad3d-113">0</span><span class="sxs-lookup"><span data-stu-id="2ad3d-113">0</span></span>|  
|<span data-ttu-id="2ad3d-114">シンボル名</span><span class="sxs-lookup"><span data-stu-id="2ad3d-114">Symbolic Name</span></span>|<span data-ttu-id="2ad3d-115">0</span><span class="sxs-lookup"><span data-stu-id="2ad3d-115">0</span></span>|  
|<span data-ttu-id="2ad3d-116">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="2ad3d-116">Message Text</span></span>|<span data-ttu-id="2ad3d-117">ODX ファイルを生成できませんでした</span><span class="sxs-lookup"><span data-stu-id="2ad3d-117">Failed to generate ODX file</span></span>|  
  
### <a name="explanation"></a><span data-ttu-id="2ad3d-118">説明</span><span class="sxs-lookup"><span data-stu-id="2ad3d-118">Explanation</span></span>  
 <span data-ttu-id="2ad3d-119">このエラーは、サービスの使用時にエラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="2ad3d-119">This error indicates there was an error in consuming the service.</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="2ad3d-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="2ad3d-120">User Action</span></span>  
 <span data-ttu-id="2ad3d-121">サービスに有効な Web メソッドがあること、およびメタデータはホストされていることを確認します (WCF サービスを所有している場合)。</span><span class="sxs-lookup"><span data-stu-id="2ad3d-121">Check that the service has valid Web Method and that metadata is hosted (if you own the WCF services).</span></span> <span data-ttu-id="2ad3d-122">それ以外の場合、サービス プロバイダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="2ad3d-122">Otherwise, contact the service provider.</span></span>  
  
 <span data-ttu-id="2ad3d-123">WCF サービスの使用の詳細については、次を参照してください。[に関する考慮事項ときに使用して WCF サービスを WCF 送信アダプタ](../core/considerations-when-consuming-wcf-services-with-the-wcf-send-adapters.md)です。</span><span class="sxs-lookup"><span data-stu-id="2ad3d-123">For additional information on consuming WCF services, see [Considerations When Consuming WCF Services with the WCF Send Adapters](../core/considerations-when-consuming-wcf-services-with-the-wcf-send-adapters.md).</span></span>
 
## <a name="response-message-body-was-not-read"></a><span data-ttu-id="2ad3d-124">応答メッセージの本文を読み取れませんでした</span><span class="sxs-lookup"><span data-stu-id="2ad3d-124">Response message body was not read</span></span>
  
||<span data-ttu-id="2ad3d-125">エラーの詳細</span><span class="sxs-lookup"><span data-stu-id="2ad3d-125">Error details</span></span>|  
|-|-|  
|<span data-ttu-id="2ad3d-126">製品名</span><span class="sxs-lookup"><span data-stu-id="2ad3d-126">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="2ad3d-127">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="2ad3d-127">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="2ad3d-128">イベント ID</span><span class="sxs-lookup"><span data-stu-id="2ad3d-128">Event ID</span></span>|<span data-ttu-id="2ad3d-129">0</span><span class="sxs-lookup"><span data-stu-id="2ad3d-129">0</span></span>|  
|<span data-ttu-id="2ad3d-130">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="2ad3d-130">Event Source</span></span>|<span data-ttu-id="2ad3d-131">0</span><span class="sxs-lookup"><span data-stu-id="2ad3d-131">0</span></span>|  
|<span data-ttu-id="2ad3d-132">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2ad3d-132">Component</span></span>|<span data-ttu-id="2ad3d-133">0</span><span class="sxs-lookup"><span data-stu-id="2ad3d-133">0</span></span>|  
|<span data-ttu-id="2ad3d-134">シンボル名</span><span class="sxs-lookup"><span data-stu-id="2ad3d-134">Symbolic Name</span></span>|<span data-ttu-id="2ad3d-135">0</span><span class="sxs-lookup"><span data-stu-id="2ad3d-135">0</span></span>|  
|<span data-ttu-id="2ad3d-136">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="2ad3d-136">Message Text</span></span>|<span data-ttu-id="2ad3d-137">応答メッセージの本文を読み取れませんでした (接続が切断された可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="2ad3d-137">The response message body was not read  (This may indicate the connection has been closed.)</span></span>|  
  
### <a name="explanation"></a><span data-ttu-id="2ad3d-138">説明</span><span class="sxs-lookup"><span data-stu-id="2ad3d-138">Explanation</span></span>  
 <span data-ttu-id="2ad3d-139">応答メッセージが返信される前に、クライアントの接続が解除された可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2ad3d-139">The client may be disconnected before the response message is sent back.</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="2ad3d-140">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="2ad3d-140">User Action</span></span>  
 <span data-ttu-id="2ad3d-141">クライアントの接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="2ad3d-141">Check the client connectivity.</span></span> <span data-ttu-id="2ad3d-142">実行する手順と手順の範囲は、ポートの種類によって変わります。</span><span class="sxs-lookup"><span data-stu-id="2ad3d-142">The steps taken, and the extent of the action, will depend on the port type.</span></span>   
<span data-ttu-id="2ad3d-143">詳細については、次を参照してください。[トラブルシューティングに使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md)です。</span><span class="sxs-lookup"><span data-stu-id="2ad3d-143">For further information, see [Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md).</span></span>
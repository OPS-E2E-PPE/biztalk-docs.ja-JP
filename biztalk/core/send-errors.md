---
title: エラーを送信する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3cf61c82-ad48-4555-af53-fb841fd0f503
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76aa238227877ab70328e585d5d12b8c428e9061
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983325"
---
# <a name="send-errors"></a><span data-ttu-id="25336-102">送信エラー</span><span class="sxs-lookup"><span data-stu-id="25336-102">Send Errors</span></span>
<span data-ttu-id="25336-103">診断および WCF の送信エラーを解決するための情報です。</span><span class="sxs-lookup"><span data-stu-id="25336-103">Information for diagnosing and resolving WCF Send errors.</span></span>  
  
## <a name="failed-to-generate-odx-file"></a><span data-ttu-id="25336-104">ODX ファイルを生成できませんでした</span><span class="sxs-lookup"><span data-stu-id="25336-104">Failed to generate ODX file</span></span>

|                 |                                   <span data-ttu-id="25336-105">エラーの詳細</span><span class="sxs-lookup"><span data-stu-id="25336-105">Error details</span></span>                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="25336-106">製品名</span><span class="sxs-lookup"><span data-stu-id="25336-106">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="25336-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="25336-107">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="25336-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="25336-108">Event ID</span></span>     |                                         <span data-ttu-id="25336-109">0</span><span class="sxs-lookup"><span data-stu-id="25336-109">0</span></span>                                          |
|  <span data-ttu-id="25336-110">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="25336-110">Event Source</span></span>   |                                         <span data-ttu-id="25336-111">0</span><span class="sxs-lookup"><span data-stu-id="25336-111">0</span></span>                                          |
|    <span data-ttu-id="25336-112">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="25336-112">Component</span></span>    |                                         <span data-ttu-id="25336-113">0</span><span class="sxs-lookup"><span data-stu-id="25336-113">0</span></span>                                          |
|  <span data-ttu-id="25336-114">シンボル名</span><span class="sxs-lookup"><span data-stu-id="25336-114">Symbolic Name</span></span>  |                                         <span data-ttu-id="25336-115">0</span><span class="sxs-lookup"><span data-stu-id="25336-115">0</span></span>                                          |
|  <span data-ttu-id="25336-116">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="25336-116">Message Text</span></span>   |                            <span data-ttu-id="25336-117">ODX ファイルを生成できませんでした</span><span class="sxs-lookup"><span data-stu-id="25336-117">Failed to generate ODX file</span></span>                             |
  
### <a name="explanation"></a><span data-ttu-id="25336-118">説明</span><span class="sxs-lookup"><span data-stu-id="25336-118">Explanation</span></span>  
 <span data-ttu-id="25336-119">このエラーは、サービスの使用時にエラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="25336-119">This error indicates there was an error in consuming the service.</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="25336-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="25336-120">User Action</span></span>  
 <span data-ttu-id="25336-121">サービスに有効な Web メソッドがあること、およびメタデータはホストされていることを確認します (WCF サービスを所有している場合)。</span><span class="sxs-lookup"><span data-stu-id="25336-121">Check that the service has valid Web Method and that metadata is hosted (if you own the WCF services).</span></span> <span data-ttu-id="25336-122">それ以外の場合、サービス プロバイダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="25336-122">Otherwise, contact the service provider.</span></span>  
  
 <span data-ttu-id="25336-123">WCF サービスの使用の詳細については、[に関する考慮事項ときに使用して WCF サービスを WCF 送信アダプタ](../core/considerations-when-consuming-wcf-services-with-the-wcf-send-adapters.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25336-123">For additional information on consuming WCF services, see [Considerations When Consuming WCF Services with the WCF Send Adapters](../core/considerations-when-consuming-wcf-services-with-the-wcf-send-adapters.md).</span></span>
 
## <a name="response-message-body-was-not-read"></a><span data-ttu-id="25336-124">応答メッセージの本文を読み取れませんでした</span><span class="sxs-lookup"><span data-stu-id="25336-124">Response message body was not read</span></span>
  
|                 |                                        <span data-ttu-id="25336-125">エラーの詳細</span><span class="sxs-lookup"><span data-stu-id="25336-125">Error details</span></span>                                        |
|-----------------|---------------------------------------------------------------------------------------------|
|  <span data-ttu-id="25336-126">製品名</span><span class="sxs-lookup"><span data-stu-id="25336-126">Product Name</span></span>   |     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]      |
| <span data-ttu-id="25336-127">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="25336-127">Product Version</span></span> |                 [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                  |
|    <span data-ttu-id="25336-128">イベント ID</span><span class="sxs-lookup"><span data-stu-id="25336-128">Event ID</span></span>     |                                              <span data-ttu-id="25336-129">0</span><span class="sxs-lookup"><span data-stu-id="25336-129">0</span></span>                                              |
|  <span data-ttu-id="25336-130">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="25336-130">Event Source</span></span>   |                                              <span data-ttu-id="25336-131">0</span><span class="sxs-lookup"><span data-stu-id="25336-131">0</span></span>                                              |
|    <span data-ttu-id="25336-132">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="25336-132">Component</span></span>    |                                              <span data-ttu-id="25336-133">0</span><span class="sxs-lookup"><span data-stu-id="25336-133">0</span></span>                                              |
|  <span data-ttu-id="25336-134">シンボル名</span><span class="sxs-lookup"><span data-stu-id="25336-134">Symbolic Name</span></span>  |                                              <span data-ttu-id="25336-135">0</span><span class="sxs-lookup"><span data-stu-id="25336-135">0</span></span>                                              |
|  <span data-ttu-id="25336-136">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="25336-136">Message Text</span></span>   | <span data-ttu-id="25336-137">応答メッセージの本文を読み取れませんでした (接続が切断された可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="25336-137">The response message body was not read  (This may indicate the connection has been closed.)</span></span> |
  
### <a name="explanation"></a><span data-ttu-id="25336-138">説明</span><span class="sxs-lookup"><span data-stu-id="25336-138">Explanation</span></span>  
 <span data-ttu-id="25336-139">応答メッセージが返信される前に、クライアントの接続が解除された可能性があります。</span><span class="sxs-lookup"><span data-stu-id="25336-139">The client may be disconnected before the response message is sent back.</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="25336-140">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="25336-140">User Action</span></span>  
 <span data-ttu-id="25336-141">クライアントの接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="25336-141">Check the client connectivity.</span></span> <span data-ttu-id="25336-142">実行する手順と手順の範囲は、ポートの種類によって変わります。</span><span class="sxs-lookup"><span data-stu-id="25336-142">The steps taken, and the extent of the action, will depend on the port type.</span></span>   
<span data-ttu-id="25336-143">詳細については、[トラブルシューティングのために使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25336-143">For further information, see [Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md).</span></span>
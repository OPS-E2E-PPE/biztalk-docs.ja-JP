---
title: SAP アダプターのサンプル |Microsoft Docs
description: SAP 向け BizTalk Server、WCF サービス モデル、WCF チャネル モデル、およびデータ プロバイダーで使用できる mySAP WCF アダプタのサンプル
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4654c458-83be-417f-ae54-5c3a8f6ab81f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1926c9899d1c1198998c25845d5d6b4189884f0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012067"
---
# <a name="samples-for-the-sap-adapter"></a><span data-ttu-id="2dfd3-103">SAP アダプターのサンプル</span><span class="sxs-lookup"><span data-stu-id="2dfd3-103">Samples for the SAP adapter</span></span>
<span data-ttu-id="2dfd3-104">サンプルは[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]に分類されます。</span><span class="sxs-lookup"><span data-stu-id="2dfd3-104">Samples for [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] are categorized into:</span></span>  

- [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="2dfd3-105"> サンプル</span><span class="sxs-lookup"><span data-stu-id="2dfd3-105"> samples</span></span>  

- <span data-ttu-id="2dfd3-106">WCF サービス モデルのサンプル</span><span class="sxs-lookup"><span data-stu-id="2dfd3-106">WCF service model samples</span></span>  

- <span data-ttu-id="2dfd3-107">WCF チャネル モデルのサンプル</span><span class="sxs-lookup"><span data-stu-id="2dfd3-107">WCF channel model samples</span></span>  

- [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]<span data-ttu-id="2dfd3-108"> サンプル</span><span class="sxs-lookup"><span data-stu-id="2dfd3-108"> samples</span></span>  


 <span data-ttu-id="2dfd3-109">サンプルについては、「 [BizTalk Adapter Pack 2010: SAP アダプタ サンプル](https://www.microsoft.com/download/details.aspx?id=1314)します。</span><span class="sxs-lookup"><span data-stu-id="2dfd3-109">The samples are available at [BizTalk Adapter Pack 2010: SAP adapter samples](https://www.microsoft.com/download/details.aspx?id=1314).</span></span> 

> [!NOTE]
> [!INCLUDE[files-need-updated](../../includes/files-need-updated.md)]

 <span data-ttu-id="2dfd3-110">サンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="2dfd3-110">The following list describes the samples.</span></span>

## <a name="biztalk-server-samples"></a><span data-ttu-id="2dfd3-111">BizTalk Server のサンプル</span><span class="sxs-lookup"><span data-stu-id="2dfd3-111">BizTalk Server samples</span></span>  

|<span data-ttu-id="2dfd3-112">サンプルのディレクトリ名</span><span class="sxs-lookup"><span data-stu-id="2dfd3-112">Sample Directory Name</span></span>|<span data-ttu-id="2dfd3-113">説明</span><span class="sxs-lookup"><span data-stu-id="2dfd3-113">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="2dfd3-114">IDOCSend</span><span class="sxs-lookup"><span data-stu-id="2dfd3-114">IDOCSend</span></span>|<span data-ttu-id="2dfd3-115">IDOC を SAP システムに送信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2dfd3-115">Demonstrates how to send an IDOC to an SAP system.</span></span>|  
|<span data-ttu-id="2dfd3-116">ReceiveIDOC</span><span class="sxs-lookup"><span data-stu-id="2dfd3-116">ReceiveIDOC</span></span>|<span data-ttu-id="2dfd3-117">SAP システムから IDOC を受信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2dfd3-117">Demonstrates how to receive an IDOC from an SAP system.</span></span>|  
|<span data-ttu-id="2dfd3-118">ReceiveIDOC_SYSREL</span><span class="sxs-lookup"><span data-stu-id="2dfd3-118">ReceiveIDOC_SYSREL</span></span>|<span data-ttu-id="2dfd3-119">SAP システムから IDOC を受信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2dfd3-119">Demonstrates how to receive an IDOC from an SAP system.</span></span> <span data-ttu-id="2dfd3-120">IDOC を受信中は、SAP SYSREL より小さい、バージョン番号です。</span><span class="sxs-lookup"><span data-stu-id="2dfd3-120">The IDOC being received has the version number less than the SAP SYSREL.</span></span>|  
|<span data-ttu-id="2dfd3-121">RFCServer</span><span class="sxs-lookup"><span data-stu-id="2dfd3-121">RFCServer</span></span>|<span data-ttu-id="2dfd3-122">SAP システムから RFC サーバー呼び出しを受信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2dfd3-122">Demonstrates how to receive an RFC server call from the SAP system.</span></span>|  
|<span data-ttu-id="2dfd3-123">SAPTransaction</span><span class="sxs-lookup"><span data-stu-id="2dfd3-123">SAPTransaction</span></span>|<span data-ttu-id="2dfd3-124">使用して SAP システムでトランザクションを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2dfd3-124">Demonstrates how to perform transactions in an SAP system using.</span></span>|  
|<span data-ttu-id="2dfd3-125">tRFCClient</span><span class="sxs-lookup"><span data-stu-id="2dfd3-125">tRFCClient</span></span>|<span data-ttu-id="2dfd3-126">SAP システム上 tRFC クライアント呼び出しを行う方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2dfd3-126">Demonstrates how to make tRFC client calls on an SAP system.</span></span>|  

## <a name="wcf-service-model-samples"></a><span data-ttu-id="2dfd3-127">WCF サービス モデルのサンプル</span><span class="sxs-lookup"><span data-stu-id="2dfd3-127">WCF service model samples</span></span>   

|<span data-ttu-id="2dfd3-128">サンプルのディレクトリ名</span><span class="sxs-lookup"><span data-stu-id="2dfd3-128">Sample Directory Name</span></span>|<span data-ttu-id="2dfd3-129">説明</span><span class="sxs-lookup"><span data-stu-id="2dfd3-129">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="2dfd3-130">SapIdocStringClientSM</span><span class="sxs-lookup"><span data-stu-id="2dfd3-130">SapIdocStringClientSM</span></span>|<span data-ttu-id="2dfd3-131">SendIdoc 操作を呼び出すことによって、SAP システムに IDOC を送信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2dfd3-131">Demonstrates how to send an IDOC to an SAP system by invoking the SendIdoc operation.</span></span>|  
|<span data-ttu-id="2dfd3-132">SapRfcServerSM</span><span class="sxs-lookup"><span data-stu-id="2dfd3-132">SapRfcServerSM</span></span>|<span data-ttu-id="2dfd3-133">SAP システムから RFC サーバー呼び出しを受信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2dfd3-133">Demonstrates how to receive an RFC server call from an SAP system.</span></span>|  
|<span data-ttu-id="2dfd3-134">SapBapiTxClientSM</span><span class="sxs-lookup"><span data-stu-id="2dfd3-134">SapBapiTxClientSM</span></span>|<span data-ttu-id="2dfd3-135">SAP システムでのトランザクション内での Bapi を呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2dfd3-135">Demonstrates how to invoke BAPIs inside a transaction on an SAP system.</span></span>|  
|<span data-ttu-id="2dfd3-136">SapTrfcClientSM</span><span class="sxs-lookup"><span data-stu-id="2dfd3-136">SapTrfcClientSM</span></span>|<span data-ttu-id="2dfd3-137">SAP システムで tRFC クライアント呼び出しを起動する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2dfd3-137">Demonstrates how to invoke tRFC client calls on an SAP system.</span></span>|  

## <a name="wcf-channel-model-samples"></a><span data-ttu-id="2dfd3-138">WCF チャネル モデルのサンプル</span><span class="sxs-lookup"><span data-stu-id="2dfd3-138">WCF channel model samples</span></span>  

|<span data-ttu-id="2dfd3-139">サンプルのディレクトリ名</span><span class="sxs-lookup"><span data-stu-id="2dfd3-139">Sample Directory Name</span></span>|<span data-ttu-id="2dfd3-140">説明</span><span class="sxs-lookup"><span data-stu-id="2dfd3-140">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="2dfd3-141">SapIdocReceiveCM</span><span class="sxs-lookup"><span data-stu-id="2dfd3-141">SapIdocReceiveCM</span></span>|<span data-ttu-id="2dfd3-142">SAP システムから Idoc を受信する方法を示します</span><span class="sxs-lookup"><span data-stu-id="2dfd3-142">Demonstrates how to receive IDOCs from an SAP system</span></span>|  
|<span data-ttu-id="2dfd3-143">SapRfcServerCM</span><span class="sxs-lookup"><span data-stu-id="2dfd3-143">SapRfcServerCM</span></span>|<span data-ttu-id="2dfd3-144">SAP システムから RFC サーバー呼び出しを受信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2dfd3-144">Demonstrates how to receive an RFC server call from the SAP system.</span></span>|  

## <a name="data-provider-for-sap-samples"></a><span data-ttu-id="2dfd3-145">SAP のサンプルのデータ プロバイダー</span><span class="sxs-lookup"><span data-stu-id="2dfd3-145">Data Provider for SAP samples</span></span>  

| <span data-ttu-id="2dfd3-146">サンプルのディレクトリ名</span><span class="sxs-lookup"><span data-stu-id="2dfd3-146">Sample Directory Name</span></span> |                                             <span data-ttu-id="2dfd3-147">説明</span><span class="sxs-lookup"><span data-stu-id="2dfd3-147">Description</span></span>                                              |
|-----------------------|------------------------------------------------------------------------------------------------------|
|        <span data-ttu-id="2dfd3-148">sap の ado</span><span class="sxs-lookup"><span data-stu-id="2dfd3-148">sap ado</span></span>        | <span data-ttu-id="2dfd3-149">使用する方法を示します、[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="2dfd3-149">Demonstrates how to use the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span></span> |

## <a name="see-also"></a><span data-ttu-id="2dfd3-150">参照</span><span class="sxs-lookup"><span data-stu-id="2dfd3-150">See Also</span></span>  
[<span data-ttu-id="2dfd3-151">SAP アプリケーションを開発する</span><span class="sxs-lookup"><span data-stu-id="2dfd3-151">Develop your SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)
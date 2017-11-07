---
title: "SAP アダプタ サンプル |Microsoft ドキュメント"
description: "SAP 向け BizTalk Server、WCF サービスのモデル、WCF チャネル モデル、およびデータ プロバイダーで使用できる mySAP WCF アダプタ サンプル"
ms.custom: 
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4654c458-83be-417f-ae54-5c3a8f6ab81f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d163c573003f40b2049f7e921e5edc4997b4e115
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="samples-for-the-sap-adapter"></a><span data-ttu-id="94a1e-103">SAP アダプターのサンプル</span><span class="sxs-lookup"><span data-stu-id="94a1e-103">Samples for the SAP adapter</span></span>
<span data-ttu-id="94a1e-104">サンプルを[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]に分類されます。</span><span class="sxs-lookup"><span data-stu-id="94a1e-104">Samples for [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] are categorized into:</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="94a1e-105">サンプル</span><span class="sxs-lookup"><span data-stu-id="94a1e-105"> samples</span></span>  
  
-   <span data-ttu-id="94a1e-106">WCF サービス モデルのサンプル</span><span class="sxs-lookup"><span data-stu-id="94a1e-106">WCF service model samples</span></span>  
  
-   <span data-ttu-id="94a1e-107">WCF チャネル モデルのサンプル</span><span class="sxs-lookup"><span data-stu-id="94a1e-107">WCF channel model samples</span></span>  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]<span data-ttu-id="94a1e-108">サンプル</span><span class="sxs-lookup"><span data-stu-id="94a1e-108"> samples</span></span>  

  
 <span data-ttu-id="94a1e-109">サンプルはいただけます[BizTalk Adapter Pack 2010: SAP アダプタ サンプル](https://www.microsoft.com/download/details.aspx?id=1314)です。</span><span class="sxs-lookup"><span data-stu-id="94a1e-109">The samples are available at [BizTalk Adapter Pack 2010: SAP adapter samples](https://www.microsoft.com/download/details.aspx?id=1314).</span></span> 

> [!NOTE]
> [!INCLUDE[files-need-updated](../../includes/files-need-updated.md)]
  
 <span data-ttu-id="94a1e-110">サンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="94a1e-110">The following list describes the samples.</span></span>
  
## <a name="biztalk-server-samples"></a><span data-ttu-id="94a1e-111">BizTalk Server のサンプル</span><span class="sxs-lookup"><span data-stu-id="94a1e-111">BizTalk Server samples</span></span>  
  
|<span data-ttu-id="94a1e-112">サンプルのディレクトリ名</span><span class="sxs-lookup"><span data-stu-id="94a1e-112">Sample Directory Name</span></span>|<span data-ttu-id="94a1e-113">Description</span><span class="sxs-lookup"><span data-stu-id="94a1e-113">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="94a1e-114">IDOCSend</span><span class="sxs-lookup"><span data-stu-id="94a1e-114">IDOCSend</span></span>|<span data-ttu-id="94a1e-115">IDOC を SAP システムに送信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="94a1e-115">Demonstrates how to send an IDOC to an SAP system.</span></span>|  
|<span data-ttu-id="94a1e-116">ReceiveIDOC</span><span class="sxs-lookup"><span data-stu-id="94a1e-116">ReceiveIDOC</span></span>|<span data-ttu-id="94a1e-117">SAP システムから IDOC を受信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="94a1e-117">Demonstrates how to receive an IDOC from an SAP system.</span></span>|  
|<span data-ttu-id="94a1e-118">ReceiveIDOC_SYSREL</span><span class="sxs-lookup"><span data-stu-id="94a1e-118">ReceiveIDOC_SYSREL</span></span>|<span data-ttu-id="94a1e-119">SAP システムから IDOC を受信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="94a1e-119">Demonstrates how to receive an IDOC from an SAP system.</span></span> <span data-ttu-id="94a1e-120">IDOC の受信中には、SAP SYSREL 未満のバージョン番号があります。</span><span class="sxs-lookup"><span data-stu-id="94a1e-120">The IDOC being received has the version number less than the SAP SYSREL.</span></span>|  
|<span data-ttu-id="94a1e-121">RFCServer</span><span class="sxs-lookup"><span data-stu-id="94a1e-121">RFCServer</span></span>|<span data-ttu-id="94a1e-122">SAP システムから RFC サーバー呼び出しを受信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="94a1e-122">Demonstrates how to receive an RFC server call from the SAP system.</span></span>|  
|<span data-ttu-id="94a1e-123">SAPTransaction</span><span class="sxs-lookup"><span data-stu-id="94a1e-123">SAPTransaction</span></span>|<span data-ttu-id="94a1e-124">使用して SAP システムでトランザクションを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="94a1e-124">Demonstrates how to perform transactions in an SAP system using.</span></span>|  
|<span data-ttu-id="94a1e-125">tRFCClient</span><span class="sxs-lookup"><span data-stu-id="94a1e-125">tRFCClient</span></span>|<span data-ttu-id="94a1e-126">SAP システムで tRFC クライアント呼び出しを行う方法を示します。</span><span class="sxs-lookup"><span data-stu-id="94a1e-126">Demonstrates how to make tRFC client calls on an SAP system.</span></span>|  
  
## <a name="wcf-service-model-samples"></a><span data-ttu-id="94a1e-127">WCF サービス モデルのサンプル</span><span class="sxs-lookup"><span data-stu-id="94a1e-127">WCF service model samples</span></span>   
  
|<span data-ttu-id="94a1e-128">サンプルのディレクトリ名</span><span class="sxs-lookup"><span data-stu-id="94a1e-128">Sample Directory Name</span></span>|<span data-ttu-id="94a1e-129">Description</span><span class="sxs-lookup"><span data-stu-id="94a1e-129">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="94a1e-130">SapIdocStringClientSM</span><span class="sxs-lookup"><span data-stu-id="94a1e-130">SapIdocStringClientSM</span></span>|<span data-ttu-id="94a1e-131">SendIdoc 操作を呼び出すことによって、IDOC を SAP システムに送信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="94a1e-131">Demonstrates how to send an IDOC to an SAP system by invoking the SendIdoc operation.</span></span>|  
|<span data-ttu-id="94a1e-132">SapRfcServerSM</span><span class="sxs-lookup"><span data-stu-id="94a1e-132">SapRfcServerSM</span></span>|<span data-ttu-id="94a1e-133">SAP システムから RFC サーバー呼び出しを受信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="94a1e-133">Demonstrates how to receive an RFC server call from an SAP system.</span></span>|  
|<span data-ttu-id="94a1e-134">SapBapiTxClientSM</span><span class="sxs-lookup"><span data-stu-id="94a1e-134">SapBapiTxClientSM</span></span>|<span data-ttu-id="94a1e-135">SAP システムでトランザクション内の Bapi を呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="94a1e-135">Demonstrates how to invoke BAPIs inside a transaction on an SAP system.</span></span>|  
|<span data-ttu-id="94a1e-136">SapTrfcClientSM</span><span class="sxs-lookup"><span data-stu-id="94a1e-136">SapTrfcClientSM</span></span>|<span data-ttu-id="94a1e-137">SAP システムで tRFC クライアント呼び出しを起動する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="94a1e-137">Demonstrates how to invoke tRFC client calls on an SAP system.</span></span>|  
  
## <a name="wcf-channel-model-samples"></a><span data-ttu-id="94a1e-138">WCF チャネル モデルのサンプル</span><span class="sxs-lookup"><span data-stu-id="94a1e-138">WCF channel model samples</span></span>  
  
|<span data-ttu-id="94a1e-139">サンプルのディレクトリ名</span><span class="sxs-lookup"><span data-stu-id="94a1e-139">Sample Directory Name</span></span>|<span data-ttu-id="94a1e-140">Description</span><span class="sxs-lookup"><span data-stu-id="94a1e-140">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="94a1e-141">SapIdocReceiveCM</span><span class="sxs-lookup"><span data-stu-id="94a1e-141">SapIdocReceiveCM</span></span>|<span data-ttu-id="94a1e-142">SAP システムから Idoc を受信する方法を示します</span><span class="sxs-lookup"><span data-stu-id="94a1e-142">Demonstrates how to receive IDOCs from an SAP system</span></span>|  
|<span data-ttu-id="94a1e-143">SapRfcServerCM</span><span class="sxs-lookup"><span data-stu-id="94a1e-143">SapRfcServerCM</span></span>|<span data-ttu-id="94a1e-144">SAP システムから RFC サーバー呼び出しを受信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="94a1e-144">Demonstrates how to receive an RFC server call from the SAP system.</span></span>|  
  
## <a name="data-provider-for-sap-samples"></a><span data-ttu-id="94a1e-145">SAP のサンプルのデータ プロバイダー</span><span class="sxs-lookup"><span data-stu-id="94a1e-145">Data Provider for SAP samples</span></span>  
  
|<span data-ttu-id="94a1e-146">サンプルのディレクトリ名</span><span class="sxs-lookup"><span data-stu-id="94a1e-146">Sample Directory Name</span></span>|<span data-ttu-id="94a1e-147">Description</span><span class="sxs-lookup"><span data-stu-id="94a1e-147">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="94a1e-148">sap ado</span><span class="sxs-lookup"><span data-stu-id="94a1e-148">sap ado</span></span>|<span data-ttu-id="94a1e-149">使用する方法を示します、[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="94a1e-149">Demonstrates how to use the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span></span>|  
  
 
## <a name="see-also"></a><span data-ttu-id="94a1e-150">参照</span><span class="sxs-lookup"><span data-stu-id="94a1e-150">See Also</span></span>  
[<span data-ttu-id="94a1e-151">SAP アプリケーションを開発する</span><span class="sxs-lookup"><span data-stu-id="94a1e-151">Develop your SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)
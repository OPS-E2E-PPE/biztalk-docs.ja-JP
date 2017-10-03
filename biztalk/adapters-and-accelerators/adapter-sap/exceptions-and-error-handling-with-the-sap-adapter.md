---
title: "例外と、SAP アダプターのエラー処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exceptions and error handling
- error handling, troubleshooting
- troubleshooting, exceptions and error handling
ms.assetid: 598a25c5-6905-4c0c-835b-159d827b2269
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 043f76f7fc730430610b7598bbab208ca8b135a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="exceptions-and-error-handling-with-the-sap-adapter"></a><span data-ttu-id="2d769-102">例外とエラーは、SAP アダプターの処理</span><span class="sxs-lookup"><span data-stu-id="2d769-102">Exceptions and Error Handling with the SAP adapter</span></span>
<span data-ttu-id="2d769-103">例外の一覧を[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]をスローします。</span><span class="sxs-lookup"><span data-stu-id="2d769-103">Lists the exceptions that the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] throws.</span></span> <span data-ttu-id="2d769-104">これらを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="2d769-104">These can contain:</span></span>  
  
-   <span data-ttu-id="2d769-105">システム例外、.NET Framework をスローするは、内部例外</span><span class="sxs-lookup"><span data-stu-id="2d769-105">An inner exception, which is a system exception that the .NET Framework throws</span></span>  
  
-   <span data-ttu-id="2d769-106">LOB LOB クライアント ライブラリからスローされる例外。</span><span class="sxs-lookup"><span data-stu-id="2d769-106">An LOB exception that the LOB client library throws.</span></span>  
  
 <span data-ttu-id="2d769-107">詳細については、内部例外は、.NET Framework または SAP のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d769-107">For more information about the inner exception, see the .NET Framework or SAP documentation.</span></span> <span data-ttu-id="2d769-108">例外には、問題を解決する助けとなる詳細なエラー メッセージも含まれます。</span><span class="sxs-lookup"><span data-stu-id="2d769-108">Exceptions also contain a detailed error message that may help resolve the problem.</span></span>  

## <a name="exception-descriptions"></a><span data-ttu-id="2d769-109">例外の説明</span><span class="sxs-lookup"><span data-stu-id="2d769-109">Exception descriptions</span></span>  
|<span data-ttu-id="2d769-110">例外</span><span class="sxs-lookup"><span data-stu-id="2d769-110">Exception</span></span>|<span data-ttu-id="2d769-111">考えられる原因/説明</span><span class="sxs-lookup"><span data-stu-id="2d769-111">Possible Cause/Description</span></span>|  
|---------------|---------------------------------|  
|<span data-ttu-id="2d769-112">ObjectDisposedException</span><span class="sxs-lookup"><span data-stu-id="2d769-112">ObjectDisposedException</span></span>|<span data-ttu-id="2d769-113">アダプターは、アダプターのクライアントが、破棄された後、応答 XMLReader にアクセスしようとするときに、この例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="2d769-113">The adapter throws this exception when the adapter client is trying to access the response XMLReader after it has been disposed.</span></span>|  
|<span data-ttu-id="2d769-114">XmlReaderGenerationException</span><span class="sxs-lookup"><span data-stu-id="2d769-114">XmlReaderGenerationException</span></span>|<span data-ttu-id="2d769-115">アダプターは、出力メッセージから XmlReader を生成することがあるときに、この例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="2d769-115">The adapter throws this exception when it is unable to generate an XmlReader from the output message.</span></span> <span data-ttu-id="2d769-116">SAP システムから受信したデータをいくつかの問題のため可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="2d769-116">This could also be due to some problems with the data received from the SAP system.</span></span> <span data-ttu-id="2d769-117">内部例外と詳細については、エラー メッセージを探します。</span><span class="sxs-lookup"><span data-stu-id="2d769-117">Look for the inner exception and the error message for more information.</span></span>|  
|<span data-ttu-id="2d769-118">InvalidUriException</span><span class="sxs-lookup"><span data-stu-id="2d769-118">InvalidUriException</span></span>|<span data-ttu-id="2d769-119">接続 URI は、接続文字列に必要なコンポーネントを持っていない場合に、この例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="2d769-119">This exception is thrown when the connection URI does not have the required components for the connection string.</span></span>|  
|<span data-ttu-id="2d769-120">使用して ConnectionException</span><span class="sxs-lookup"><span data-stu-id="2d769-120">ConnectionException</span></span>|<span data-ttu-id="2d769-121">SAP システムへの接続に問題がある場合、または基になる接続が無効で、SAP システムでエラーのためか、ネットワークの問題になる場合は、この例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="2d769-121">This exception is thrown when there is a problem connecting to the SAP system or if an underlying connection becomes invalid, either due to an error on the SAP system or due to a network problem.</span></span>|  
|<span data-ttu-id="2d769-122">TimeoutException</span><span class="sxs-lookup"><span data-stu-id="2d769-122">TimeoutException</span></span>|<span data-ttu-id="2d769-123">操作の指定したタイムアウトがも過ぎている場合は、この例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="2d769-123">This exception is thrown when the timeout specified for an operation is lapsed.</span></span> <span data-ttu-id="2d769-124">内部例外には、指定されたタイムアウトだったための十分な理由の詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2d769-124">The inner exception contains the specifics of why the specified timeout was not sufficient.</span></span>|  
|<span data-ttu-id="2d769-125">XmlReaderParsingException</span><span class="sxs-lookup"><span data-stu-id="2d769-125">XmlReaderParsingException</span></span>|<span data-ttu-id="2d769-126">アダプターは、指定した型をサポートしていない場合、または種類の正しくない値が指定されている場合、この例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="2d769-126">The adapter throws this exception if it does not support the specified type, or if an incorrect value is specified for the type.</span></span> <span data-ttu-id="2d769-127">また、入力 XML が正しくない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d769-127">Also, the input XML could be incorrect.</span></span> <span data-ttu-id="2d769-128">正しくない値には、テキストまたは数字の最大の最大量を超えている場合が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2d769-128">An incorrect value includes cases where the maximum amount of text or maximum digits is exceeded.</span></span> <span data-ttu-id="2d769-129">入力 XML が操作名または名前空間が正しくない場合は、正しくない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d769-129">The input XML might be incorrect if the operation name or namespace is incorrect.</span></span>|  
|<span data-ttu-id="2d769-130">RFCException (AdapterException から派生)</span><span class="sxs-lookup"><span data-stu-id="2d769-130">RFCException (derived from AdapterException)</span></span>|<span data-ttu-id="2d769-131">アダプターは、SAP システムから受信したエラーがある場合、この例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="2d769-131">The adapter throws this exception if there is an error received from the SAP system.</span></span> <span data-ttu-id="2d769-132">SAP システムから受信した実際の例外は、内部例外です。</span><span class="sxs-lookup"><span data-stu-id="2d769-132">The inner exception is the actual exception received from the SAP system.</span></span>|  
|<span data-ttu-id="2d769-133">UnsupportedOperationException</span><span class="sxs-lookup"><span data-stu-id="2d769-133">UnsupportedOperationException</span></span>|<span data-ttu-id="2d769-134">アダプターは、アダプターのクライアントが無効なアクションを指定すると、この例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="2d769-134">The adapter throws this exception when the adapter client specifies an invalid action.</span></span>|  
|<span data-ttu-id="2d769-135">MetadataException</span><span class="sxs-lookup"><span data-stu-id="2d769-135">MetadataException</span></span>|<span data-ttu-id="2d769-136">アダプターは、メタデータの取得、参照、または検索中にエラーがある場合、この例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="2d769-136">The adapter throws this exception if there is an error during metadata retrieval, browse, or search.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2d769-137">参照</span><span class="sxs-lookup"><span data-stu-id="2d769-137">See Also</span></span>  
[<span data-ttu-id="2d769-138">SAP アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="2d769-138">Troubleshoot the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)
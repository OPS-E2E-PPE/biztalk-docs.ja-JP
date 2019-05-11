---
title: 例外と SAP アダプターを使用したエラーの処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exceptions and error handling
- error handling, troubleshooting
- troubleshooting, exceptions and error handling
ms.assetid: 598a25c5-6905-4c0c-835b-159d827b2269
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d609e456e835cc14288f239bb53b252eb58f7e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373449"
---
# <a name="exceptions-and-error-handling-with-the-sap-adapter"></a><span data-ttu-id="255d0-102">例外と SAP アダプターを使用したエラーの処理</span><span class="sxs-lookup"><span data-stu-id="255d0-102">Exceptions and Error Handling with the SAP adapter</span></span>
<span data-ttu-id="255d0-103">例外の一覧を表示する、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]をスローします。</span><span class="sxs-lookup"><span data-stu-id="255d0-103">Lists the exceptions that the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] throws.</span></span> <span data-ttu-id="255d0-104">これらを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="255d0-104">These can contain:</span></span>  

- <span data-ttu-id="255d0-105">内部例外、.NET Framework をスローする、システム例外</span><span class="sxs-lookup"><span data-stu-id="255d0-105">An inner exception, which is a system exception that the .NET Framework throws</span></span>  

- <span data-ttu-id="255d0-106">LOB クライアント ライブラリをスローする LOB 例外。</span><span class="sxs-lookup"><span data-stu-id="255d0-106">An LOB exception that the LOB client library throws.</span></span>  

  <span data-ttu-id="255d0-107">詳細については、内部例外は、.NET Framework または SAP のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="255d0-107">For more information about the inner exception, see the .NET Framework or SAP documentation.</span></span> <span data-ttu-id="255d0-108">例外には、問題の解決に役立つ可能性のある詳細なエラー メッセージも含まれます。</span><span class="sxs-lookup"><span data-stu-id="255d0-108">Exceptions also contain a detailed error message that may help resolve the problem.</span></span>  

## <a name="exception-descriptions"></a><span data-ttu-id="255d0-109">例外の説明</span><span class="sxs-lookup"><span data-stu-id="255d0-109">Exception descriptions</span></span>  

|<span data-ttu-id="255d0-110">例外</span><span class="sxs-lookup"><span data-stu-id="255d0-110">Exception</span></span>|<span data-ttu-id="255d0-111">考えられる原因の説明</span><span class="sxs-lookup"><span data-stu-id="255d0-111">Possible Cause/Description</span></span>|  
|---------------|---------------------------------|  
|<span data-ttu-id="255d0-112">ObjectDisposedException</span><span class="sxs-lookup"><span data-stu-id="255d0-112">ObjectDisposedException</span></span>|<span data-ttu-id="255d0-113">アダプターは、アダプターのクライアントが破棄された後、応答 XMLReader にアクセスしようとするときに、この例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="255d0-113">The adapter throws this exception when the adapter client is trying to access the response XMLReader after it has been disposed.</span></span>|  
|<span data-ttu-id="255d0-114">XmlReaderGenerationException</span><span class="sxs-lookup"><span data-stu-id="255d0-114">XmlReaderGenerationException</span></span>|<span data-ttu-id="255d0-115">アダプターは、出力メッセージから XmlReader を生成することができない場合、この例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="255d0-115">The adapter throws this exception when it is unable to generate an XmlReader from the output message.</span></span> <span data-ttu-id="255d0-116">SAP システムから受信したデータのいくつかの問題が原因可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="255d0-116">This could also be due to some problems with the data received from the SAP system.</span></span> <span data-ttu-id="255d0-117">内部例外と詳細については、エラー メッセージを探します。</span><span class="sxs-lookup"><span data-stu-id="255d0-117">Look for the inner exception and the error message for more information.</span></span>|  
|<span data-ttu-id="255d0-118">InvalidUriException</span><span class="sxs-lookup"><span data-stu-id="255d0-118">InvalidUriException</span></span>|<span data-ttu-id="255d0-119">接続 URI に接続文字列に必要なコンポーネントがあるない場合に、この例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="255d0-119">This exception is thrown when the connection URI does not have the required components for the connection string.</span></span>|  
|<span data-ttu-id="255d0-120">ConnectionException</span><span class="sxs-lookup"><span data-stu-id="255d0-120">ConnectionException</span></span>|<span data-ttu-id="255d0-121">SAP システムへの接続に問題がある場合、または、基になる接続が無効な SAP システムでエラーのため、またはネットワークの問題が原因になった場合、この例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="255d0-121">This exception is thrown when there is a problem connecting to the SAP system or if an underlying connection becomes invalid, either due to an error on the SAP system or due to a network problem.</span></span>|  
|<span data-ttu-id="255d0-122">TimeoutException</span><span class="sxs-lookup"><span data-stu-id="255d0-122">TimeoutException</span></span>|<span data-ttu-id="255d0-123">操作の指定したタイムアウトが過ぎているときは、この例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="255d0-123">This exception is thrown when the timeout specified for an operation is lapsed.</span></span> <span data-ttu-id="255d0-124">内部例外には、指定したタイムアウト時間は十分に理由の詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="255d0-124">The inner exception contains the specifics of why the specified timeout was not sufficient.</span></span>|  
|<span data-ttu-id="255d0-125">XmlReaderParsingException</span><span class="sxs-lookup"><span data-stu-id="255d0-125">XmlReaderParsingException</span></span>|<span data-ttu-id="255d0-126">アダプターは、指定した型をサポートしていない場合、または値が正しくありませんが、型指定されている場合、この例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="255d0-126">The adapter throws this exception if it does not support the specified type, or if an incorrect value is specified for the type.</span></span> <span data-ttu-id="255d0-127">また、入力 XML が正しくない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="255d0-127">Also, the input XML could be incorrect.</span></span> <span data-ttu-id="255d0-128">間違った値には、テキストまたは数字の最大の最大量を超える場合が含まれています。</span><span class="sxs-lookup"><span data-stu-id="255d0-128">An incorrect value includes cases where the maximum amount of text or maximum digits is exceeded.</span></span> <span data-ttu-id="255d0-129">入力 XML は、操作名または名前空間が正しくない場合は、適切でない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="255d0-129">The input XML might be incorrect if the operation name or namespace is incorrect.</span></span>|  
|<span data-ttu-id="255d0-130">RFCException (AdapterException から派生)</span><span class="sxs-lookup"><span data-stu-id="255d0-130">RFCException (derived from AdapterException)</span></span>|<span data-ttu-id="255d0-131">アダプターは、SAP システムから受信したエラーがある場合、この例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="255d0-131">The adapter throws this exception if there is an error received from the SAP system.</span></span> <span data-ttu-id="255d0-132">SAP システムから受信した実際の例外は、内部例外です。</span><span class="sxs-lookup"><span data-stu-id="255d0-132">The inner exception is the actual exception received from the SAP system.</span></span>|  
|<span data-ttu-id="255d0-133">UnsupportedOperationException</span><span class="sxs-lookup"><span data-stu-id="255d0-133">UnsupportedOperationException</span></span>|<span data-ttu-id="255d0-134">アダプターは、アダプターのクライアントが無効なアクションを指定すると、この例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="255d0-134">The adapter throws this exception when the adapter client specifies an invalid action.</span></span>|  
|<span data-ttu-id="255d0-135">MetadataException</span><span class="sxs-lookup"><span data-stu-id="255d0-135">MetadataException</span></span>|<span data-ttu-id="255d0-136">アダプターは、メタデータの取得、参照、または検索中にエラーがある場合、この例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="255d0-136">The adapter throws this exception if there is an error during metadata retrieval, browse, or search.</span></span>|  

## <a name="see-also"></a><span data-ttu-id="255d0-137">参照</span><span class="sxs-lookup"><span data-stu-id="255d0-137">See Also</span></span>  
[<span data-ttu-id="255d0-138">SAP アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="255d0-138">Troubleshoot the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)
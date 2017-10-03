---
title: "例外とエラーの Siebel アダプターの処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- error handling, troubleshooting
- exceptions, troubleshooting
- troubleshooting, exceptions and error handling
ms.assetid: d46e908f-0715-43e2-879b-f5d0beb9bc64
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 743e2a0f03e35282c24a506ff37e9d774f0b7505
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="exceptions-and-error-handling-with-the-siebel-adapter"></a><span data-ttu-id="06d7e-102">例外とエラーの Siebel アダプターの処理</span><span class="sxs-lookup"><span data-stu-id="06d7e-102">Exceptions and Error Handling with the Siebel adapter</span></span>
## <a name="exception-list"></a><span data-ttu-id="06d7e-103">例外の一覧</span><span class="sxs-lookup"><span data-stu-id="06d7e-103">Exception list</span></span>
<span data-ttu-id="06d7e-104">によってスローされた例外、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="06d7e-104">The exceptions thrown by the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].</span></span> <span data-ttu-id="06d7e-105">これらを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="06d7e-105">These can contain:</span></span>  
  
-   <span data-ttu-id="06d7e-106">システム例外、.NET Framework をスローするは、内部例外</span><span class="sxs-lookup"><span data-stu-id="06d7e-106">An inner exception, which is a system exception that the .NET Framework throws</span></span>  
  
-   <span data-ttu-id="06d7e-107">LOB LOB クライアント ライブラリからスローされる例外。</span><span class="sxs-lookup"><span data-stu-id="06d7e-107">An LOB exception that the LOB client library throws.</span></span>  
  
 <span data-ttu-id="06d7e-108">詳細については、内部例外は、それぞれの .NET Framework または Siebel のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="06d7e-108">For more information about the inner exception, refer to the respective .NET Framework or Siebel documentation.</span></span> <span data-ttu-id="06d7e-109">例外には、問題の解決に役立つ詳細なエラー メッセージも含まれています。</span><span class="sxs-lookup"><span data-stu-id="06d7e-109">The exception also contains a detailed error message that helps in resolving the problem.</span></span> <span data-ttu-id="06d7e-110">ここで説明した例外のリストが包括的ながないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="06d7e-110">Note that the list of exceptions mentioned here is not comprehensive.</span></span>  
  
|<span data-ttu-id="06d7e-111">例外</span><span class="sxs-lookup"><span data-stu-id="06d7e-111">Exception</span></span>|<span data-ttu-id="06d7e-112">考えられる原因/エラーの説明</span><span class="sxs-lookup"><span data-stu-id="06d7e-112">Possible Cause/Error Description</span></span>|  
|---------------|---------------------------------------|  
|<span data-ttu-id="06d7e-113">使用して ConnectionException</span><span class="sxs-lookup"><span data-stu-id="06d7e-113">ConnectionException</span></span>|<span data-ttu-id="06d7e-114">アダプターは、Siebel システムへの既存の接続を閉じたり、接続を確立することがない場合、この例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="06d7e-114">The adapter throws this exception if it is unable to establish a connection or close an existing connection to a Siebel system.</span></span>|  
|<span data-ttu-id="06d7e-115">CredentialsException</span><span class="sxs-lookup"><span data-stu-id="06d7e-115">CredentialsException</span></span>|<span data-ttu-id="06d7e-116">アダプターは、ユーザー名またはパスワード、Siebel システムへの接続にアダプタのクライアントが指定されていない場合、この例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="06d7e-116">The adapter throws this exception if the adapter client does not specify a user name or password to connect to a Siebel system.</span></span>|  
|<span data-ttu-id="06d7e-117">MetadataException</span><span class="sxs-lookup"><span data-stu-id="06d7e-117">MetadataException</span></span>|<span data-ttu-id="06d7e-118">アダプターは、Siebel の成果物のためのメタデータの取得に失敗した場合は、この例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="06d7e-118">The adapter throws this exception if it fails to retrieve metadata for Siebel artifacts.</span></span>|  
|<span data-ttu-id="06d7e-119">XmlReaderParsingException</span><span class="sxs-lookup"><span data-stu-id="06d7e-119">XmlReaderParsingException</span></span>|<span data-ttu-id="06d7e-120">アダプターは、Siebel システムでは操作を呼び出すをクライアント側アダプターによって提供される入力情報が不完全か、または正しくない場合、この例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="06d7e-120">The adapter throws this exception if the input information provided by the adapter clients to invoke an operation in the Siebel system, is either incomplete or incorrect.</span></span>|  
|<span data-ttu-id="06d7e-121">XmlReaderGenerationException</span><span class="sxs-lookup"><span data-stu-id="06d7e-121">XmlReaderGenerationException</span></span>|<span data-ttu-id="06d7e-122">アダプターは、Siebel システムで実行される操作の出力を生成することがない場合、この例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="06d7e-122">The adapter throws this exception if it is unable to generate output for an operation executed in a Siebel system.</span></span>|  
|<span data-ttu-id="06d7e-123">TargetSystemException</span><span class="sxs-lookup"><span data-stu-id="06d7e-123">TargetSystemException</span></span>|<span data-ttu-id="06d7e-124">場合、アダプターがこの例外をスローするアダプターを使用して、Siebel COM API で、例外をスロー、Siebel システムとのインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="06d7e-124">The adapter throws this exception if the Siebel COM API, which the adapter uses to interface with the Siebel system, throws an exception.</span></span> <span data-ttu-id="06d7e-125">内部例外には、Siebel COM API によってスローされる例外が含まれています。</span><span class="sxs-lookup"><span data-stu-id="06d7e-125">The inner exception contains the exception thrown by the Siebel COM API.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="06d7e-126">参照</span><span class="sxs-lookup"><span data-stu-id="06d7e-126">See Also</span></span>  
 <span data-ttu-id="06d7e-127">[Siebel eBusiness Applications の BizTalk アダプターを理解します。](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md) </span><span class="sxs-lookup"><span data-stu-id="06d7e-127">[Understand BizTalk Adapter for Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md) </span></span>  
[<span data-ttu-id="06d7e-128">Siebel アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="06d7e-128">Troubleshoot the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)
---
title: 例外とエラーの Siebel アダプターの処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- error handling, troubleshooting
- exceptions, troubleshooting
- troubleshooting, exceptions and error handling
ms.assetid: d46e908f-0715-43e2-879b-f5d0beb9bc64
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 149f69681e66a9be39a2586563d6d6a4df649f1d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371739"
---
# <a name="exceptions-and-error-handling-with-the-siebel-adapter"></a><span data-ttu-id="3bc10-102">例外とエラーの Siebel アダプターの処理</span><span class="sxs-lookup"><span data-stu-id="3bc10-102">Exceptions and Error Handling with the Siebel adapter</span></span>
## <a name="exception-list"></a><span data-ttu-id="3bc10-103">例外の一覧</span><span class="sxs-lookup"><span data-stu-id="3bc10-103">Exception list</span></span>
<span data-ttu-id="3bc10-104">によってスローされた例外、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3bc10-104">The exceptions thrown by the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].</span></span> <span data-ttu-id="3bc10-105">これらを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3bc10-105">These can contain:</span></span>  
  
- <span data-ttu-id="3bc10-106">内部例外、.NET Framework をスローする、システム例外</span><span class="sxs-lookup"><span data-stu-id="3bc10-106">An inner exception, which is a system exception that the .NET Framework throws</span></span>  
  
- <span data-ttu-id="3bc10-107">LOB クライアント ライブラリをスローする LOB 例外。</span><span class="sxs-lookup"><span data-stu-id="3bc10-107">An LOB exception that the LOB client library throws.</span></span>  
  
  <span data-ttu-id="3bc10-108">詳細については、内部例外は、それぞれの .NET Framework または Siebel のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3bc10-108">For more information about the inner exception, refer to the respective .NET Framework or Siebel documentation.</span></span> <span data-ttu-id="3bc10-109">例外には、問題の解決に役立つ詳細なエラー メッセージも含まれています。</span><span class="sxs-lookup"><span data-stu-id="3bc10-109">The exception also contains a detailed error message that helps in resolving the problem.</span></span> <span data-ttu-id="3bc10-110">ここで説明する例外の一覧は包括的なしないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3bc10-110">Note that the list of exceptions mentioned here is not comprehensive.</span></span>  
  
|<span data-ttu-id="3bc10-111">例外</span><span class="sxs-lookup"><span data-stu-id="3bc10-111">Exception</span></span>|<span data-ttu-id="3bc10-112">考えられる原因/エラーの説明</span><span class="sxs-lookup"><span data-stu-id="3bc10-112">Possible Cause/Error Description</span></span>|  
|---------------|---------------------------------------|  
|<span data-ttu-id="3bc10-113">ConnectionException</span><span class="sxs-lookup"><span data-stu-id="3bc10-113">ConnectionException</span></span>|<span data-ttu-id="3bc10-114">アダプターは、Siebel システムへの既存の接続を閉じたりする接続を確立できない場合、この例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="3bc10-114">The adapter throws this exception if it is unable to establish a connection or close an existing connection to a Siebel system.</span></span>|  
|<span data-ttu-id="3bc10-115">CredentialsException</span><span class="sxs-lookup"><span data-stu-id="3bc10-115">CredentialsException</span></span>|<span data-ttu-id="3bc10-116">アダプターは、アダプターのクライアントが、ユーザー名または Siebel システムに接続するためのパスワードを指定しない場合、この例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="3bc10-116">The adapter throws this exception if the adapter client does not specify a user name or password to connect to a Siebel system.</span></span>|  
|<span data-ttu-id="3bc10-117">MetadataException</span><span class="sxs-lookup"><span data-stu-id="3bc10-117">MetadataException</span></span>|<span data-ttu-id="3bc10-118">アダプターは、Siebel の成果物のメタデータの取得に失敗した場合、この例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="3bc10-118">The adapter throws this exception if it fails to retrieve metadata for Siebel artifacts.</span></span>|  
|<span data-ttu-id="3bc10-119">XmlReaderParsingException</span><span class="sxs-lookup"><span data-stu-id="3bc10-119">XmlReaderParsingException</span></span>|<span data-ttu-id="3bc10-120">アダプターは、操作を呼び出す、Siebel システムでアダプター クライアントによって提供される入力情報が不完全であるか、または正しくない場合、この例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="3bc10-120">The adapter throws this exception if the input information provided by the adapter clients to invoke an operation in the Siebel system, is either incomplete or incorrect.</span></span>|  
|<span data-ttu-id="3bc10-121">XmlReaderGenerationException</span><span class="sxs-lookup"><span data-stu-id="3bc10-121">XmlReaderGenerationException</span></span>|<span data-ttu-id="3bc10-122">アダプターは、Siebel システムで実行される操作の出力を生成できない場合、この例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="3bc10-122">The adapter throws this exception if it is unable to generate output for an operation executed in a Siebel system.</span></span>|  
|<span data-ttu-id="3bc10-123">TargetSystemException</span><span class="sxs-lookup"><span data-stu-id="3bc10-123">TargetSystemException</span></span>|<span data-ttu-id="3bc10-124">場合、アダプターはこの例外をスローします。 アダプターはを使用して、Siebel COM API で Siebel システム、例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="3bc10-124">The adapter throws this exception if the Siebel COM API, which the adapter uses to interface with the Siebel system, throws an exception.</span></span> <span data-ttu-id="3bc10-125">内部例外には、Siebel の COM API によってスローされる例外が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3bc10-125">The inner exception contains the exception thrown by the Siebel COM API.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3bc10-126">参照</span><span class="sxs-lookup"><span data-stu-id="3bc10-126">See Also</span></span>  
 <span data-ttu-id="3bc10-127">[BizTalk Adapter for Siebel eBusiness Applications についてください。](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md) </span><span class="sxs-lookup"><span data-stu-id="3bc10-127">[Understand BizTalk Adapter for Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md) </span></span>  
[<span data-ttu-id="3bc10-128">Siebel アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="3bc10-128">Troubleshoot the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)
---
title: Siebel アダプターによってどのような操作がサポートされている |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations, performing by using the adapter
ms.assetid: 800cf44b-357f-4850-8878-f49ceb549adf
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40bfb247ff0f3af2abeec584c5fd079f392cd18e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-operations-are-supported-by-the-siebel-adapter"></a><span data-ttu-id="44569-102">どのような操作、Siebel アダプターによってサポートされます。</span><span class="sxs-lookup"><span data-stu-id="44569-102">What operations are supported by the Siebel adapter</span></span>
<span data-ttu-id="44569-103">アダプターのクライアントは、いずれかで Siebel システムの操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="44569-103">Adapter clients can perform operations on the Siebel system by either:</span></span>  
  
-   <span data-ttu-id="44569-104">BizTalk プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="44569-104">Creating BizTalk projects.</span></span>  
  
-   <span data-ttu-id="44569-105">WCF チャネル モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="44569-105">Using the WCF channel model.</span></span>  
  
-   <span data-ttu-id="44569-106">WCF サービス モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="44569-106">Using the WCF service model.</span></span>  
  
 <span data-ttu-id="44569-107">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]アプリケーションがそれで呼び出すことができ、アプリケーションで呼び出すことができます、さらに、操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="44569-107">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="44569-108">これらの操作がチャネル経由で SOAP メッセージを送信することによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="44569-108">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="44569-109">応答が必要な場合、同じチャネル経由で SOAP メッセージで返されます。</span><span class="sxs-lookup"><span data-stu-id="44569-109">If a response is required, it is returned in a SOAP message over the same channel.</span></span> <span data-ttu-id="44569-110">メッセージの構造および各操作に関連付けられている SOAP アクションについては、次を参照してください。[メッセージと BizTalk Adapter for Siebel eBusiness Applications のメッセージ スキーマを](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)です。</span><span class="sxs-lookup"><span data-stu-id="44569-110">For information about the message structure and the SOAP action associated with each operation, see [Messages and Message Schemas for BizTalk Adapter for Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md).</span></span>  
  
 <span data-ttu-id="44569-111">このセクションでは、Siebel システムを使用して、サポートされる操作に関する情報を提供、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="44569-111">This section provides information about the operations supported on the Siebel system using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="44569-112">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel システムからの受信呼び出しの受信をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="44569-112">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] does not support receiving inbound calls from a Siebel system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="44569-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="44569-113">In This Section</span></span>  
  
-   [<span data-ttu-id="44569-114">Siebel ビジネス コンポーネントに対する操作</span><span class="sxs-lookup"><span data-stu-id="44569-114">Operations on Business Components in Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/operations-on-business-components-in-siebel.md)  
  
-   [<span data-ttu-id="44569-115">Siebel ビジネス サービスに対する操作</span><span class="sxs-lookup"><span data-stu-id="44569-115">Operations on Business Services in Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/operations-on-business-services-in-siebel.md)  
  
## <a name="see-also"></a><span data-ttu-id="44569-116">参照</span><span class="sxs-lookup"><span data-stu-id="44569-116">See Also</span></span>  
 [<span data-ttu-id="44569-117">BizTalk adapter 用 Siebel eBusiness Applications の概要</span><span class="sxs-lookup"><span data-stu-id="44569-117">Overview of BizTalk Adapter for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)
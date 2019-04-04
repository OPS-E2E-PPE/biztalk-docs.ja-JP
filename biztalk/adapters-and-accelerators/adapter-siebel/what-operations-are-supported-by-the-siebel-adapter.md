---
title: Siebel アダプターによってサポートされる操作 |Microsoft Docs
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
ms.openlocfilehash: f3f080cedb74210d02806681b6c9e20656d3d09e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004779"
---
# <a name="what-operations-are-supported-by-the-siebel-adapter"></a><span data-ttu-id="7bd18-102">Siebel アダプターによってサポートされる操作</span><span class="sxs-lookup"><span data-stu-id="7bd18-102">What operations are supported by the Siebel adapter</span></span>
<span data-ttu-id="7bd18-103">アダプターのクライアントは、いずれかで Siebel システムの操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="7bd18-103">Adapter clients can perform operations on the Siebel system by either:</span></span>  
  
- <span data-ttu-id="7bd18-104">BizTalk プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="7bd18-104">Creating BizTalk projects.</span></span>  
  
- <span data-ttu-id="7bd18-105">WCF チャネル モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="7bd18-105">Using the WCF channel model.</span></span>  
  
- <span data-ttu-id="7bd18-106">WCF サービス モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="7bd18-106">Using the WCF service model.</span></span>  
  
  <span data-ttu-id="7bd18-107">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]アプリケーションは、それを呼び出すことができ、アプリケーションで呼び出すことができます、さらに、操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="7bd18-107">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="7bd18-108">これらの操作は、チャネル経由で SOAP メッセージを送信することによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="7bd18-108">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="7bd18-109">応答が必要な場合、同じチャネル経由で SOAP メッセージで返されます。</span><span class="sxs-lookup"><span data-stu-id="7bd18-109">If a response is required, it is returned in a SOAP message over the same channel.</span></span> <span data-ttu-id="7bd18-110">メッセージの構造とそれぞれの操作に関連付けられている SOAP アクションについては、[メッセージと BizTalk adapter for Siebel eBusiness Applications のメッセージ スキーマ](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bd18-110">For information about the message structure and the SOAP action associated with each operation, see [Messages and Message Schemas for BizTalk Adapter for Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md).</span></span>  
  
  <span data-ttu-id="7bd18-111">このセクションで使用して Siebel システムでサポートされる操作に関する情報を提供する、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7bd18-111">This section provides information about the operations supported on the Siebel system using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7bd18-112">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel システムからの受信呼び出しの受信をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="7bd18-112">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] does not support receiving inbound calls from a Siebel system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7bd18-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7bd18-113">In This Section</span></span>  
  
-   [<span data-ttu-id="7bd18-114">Siebel ビジネス コンポーネントに対する操作</span><span class="sxs-lookup"><span data-stu-id="7bd18-114">Operations on Business Components in Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/operations-on-business-components-in-siebel.md)  
  
-   [<span data-ttu-id="7bd18-115">Siebel ビジネス サービスに対する操作</span><span class="sxs-lookup"><span data-stu-id="7bd18-115">Operations on Business Services in Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/operations-on-business-services-in-siebel.md)  
  
## <a name="see-also"></a><span data-ttu-id="7bd18-116">参照</span><span class="sxs-lookup"><span data-stu-id="7bd18-116">See Also</span></span>  
 [<span data-ttu-id="7bd18-117">BizTalk Adapter for Siebel eBusiness Applications の概要</span><span class="sxs-lookup"><span data-stu-id="7bd18-117">Overview of BizTalk Adapter for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)
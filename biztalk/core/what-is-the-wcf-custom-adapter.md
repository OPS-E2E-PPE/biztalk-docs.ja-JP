---
title: WCF-Custom アダプタについて | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-Custom adapters, about WCF-Custom adapters
ms.assetid: 7b2178dd-f737-4784-9bcb-e2b3979bfb0d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e090f82bc43d96dc14295af2fac2807cf1fd137
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-wcf-custom-adapter"></a><span data-ttu-id="b888a-103">WCF-Custom アダプタについて</span><span class="sxs-lookup"><span data-stu-id="b888a-103">What Is the WCF-Custom Adapter?</span></span>
<span data-ttu-id="b888a-104">WCF-Custom アダプタを使用すると、BizTalk Server で WCF 拡張機能コンポーネントを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b888a-104">The WCF-Custom adapter is used to enable the use of WCF extensibility components in BizTalk Server.</span></span> <span data-ttu-id="b888a-105">このアダプタによって、WCF フレームワークの完全な柔軟性が有効になります。</span><span class="sxs-lookup"><span data-stu-id="b888a-105">The adapter enables complete flexibility of the WCF framework.</span></span> <span data-ttu-id="b888a-106">これにより、ユーザーが、受信場所や送信ポートの WCF バインドを選択して構成できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b888a-106">It allows users to select and configure a WCF binding for the receive location and send port.</span></span> <span data-ttu-id="b888a-107">また、エンドポイント動作やセキュリティ設定を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="b888a-107">It also allows users to set the endpoint behaviors and security settings.</span></span>  
  
 <span data-ttu-id="b888a-108">WCF-Custom アダプタは、2 つのアダプタ (受信アダプタと送信アダプタ) で構成されます。</span><span class="sxs-lookup"><span data-stu-id="b888a-108">The WCF-Custom adapter consists of two adapters—a receive adapter and a send adapter.</span></span>  
  
 <span data-ttu-id="b888a-109">**Wcf-custom 受信アダプター**</span><span class="sxs-lookup"><span data-stu-id="b888a-109">**WCF-Custom Receive Adapter**</span></span>  
  
 <span data-ttu-id="b888a-110">この WCF-Custom 受信アダプタは、受信場所の [トランスポートのプロパティ] ダイアログ ボックスで選択および構成したバインド、サービス動作、エンドポイント動作、セキュリティ メカニズム、および受信メッセージ本文のソースを使用して WCF サービス要求を受信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b888a-110">You use the WCF-Custom receive adapter to receive WCF service requests through the bindings, service behavior, endpoint behavior, security mechanism, and the source of the inbound message body that you selected and configured in the transport properties dialog in the receive location.</span></span> <span data-ttu-id="b888a-111">WCF-Custom 受信アダプタを使用する受信場所は、一方向または要求 - 応答 (双方向) として構成できます。</span><span class="sxs-lookup"><span data-stu-id="b888a-111">A receive location that uses the WCF-Custom receive adapter can be configured as one-way or request-response (two-way).</span></span>  
  
 <span data-ttu-id="b888a-112">**Wcf-custom 送信アダプタ**</span><span class="sxs-lookup"><span data-stu-id="b888a-112">**WCF-Custom Send Adapter**</span></span>  
  
 <span data-ttu-id="b888a-113">この WCF-Custom 受信アダプタは、型宣言が不要なコントラクトと、選択および構成したバインド、サービス動作、エンドポイント動作、セキュリティ メカニズム、および送信メッセージ本文のソースを使用して WCF サービスを呼び出すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b888a-113">You use the WCF-Custom send adapter to call a WCF service through the typeless contract with the bindings, service behavior, endpoint behavior, security mechanism, and the source of the outbound message body that you selected and configured.</span></span>  
  
 <span data-ttu-id="b888a-114">WCF の詳細については、受信し送信アダプターを参照してください[WCF アダプタは何ですか?](../core/what-are-the-wcf-adapters.md)です。</span><span class="sxs-lookup"><span data-stu-id="b888a-114">For more information about WCF receive and send adapters, see [What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b888a-115">参照</span><span class="sxs-lookup"><span data-stu-id="b888a-115">See Also</span></span>  
 <span data-ttu-id="b888a-116">[WCF カスタム アダプターを構成します。](../core/configuring-the-wcf-custom-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="b888a-116">[Configuring the WCF-Custom Adapter](../core/configuring-the-wcf-custom-adapter.md) </span></span>  
 [<span data-ttu-id="b888a-117">WCF アダプタ</span><span class="sxs-lookup"><span data-stu-id="b888a-117">WCF Adapters</span></span>](../core/wcf-adapters.md)
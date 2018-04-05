---
title: Wcf-customisolated アダプターとは何ですか。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-CustomIsolated adapters, about WCF-CustomIsolated adapters
ms.assetid: 872fe97a-8a96-4b2a-8cc1-2db9b315c44f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fdf5a646f586030df6c9492fc6fb2999e49527a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-wcf-customisolated-adapter"></a><span data-ttu-id="33929-103">Wcf-customisolated アダプターとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="33929-103">What Is the WCF-CustomIsolated Adapter?</span></span>
<span data-ttu-id="33929-104">WCF-CustomIsolated アダプタは、分離ホストを使用して、BizTalk Server における WCF 拡張機能コンポーネントの使用を有効にするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="33929-104">The WCF-CustomIsolated adapter is used to enable the use of WCF extensibility components in BizTalk Server with an isolated host.</span></span> <span data-ttu-id="33929-105">このアダプタによって、WCF フレームワークの完全な柔軟性が有効になります。</span><span class="sxs-lookup"><span data-stu-id="33929-105">The adapter enables complete flexibility of the WCF framework.</span></span> <span data-ttu-id="33929-106">そのためユーザーは、受信場所の WCF バインドを選択して構成したり、エンドポイント動作やセキュリティ設定を指定したりできるようになります。</span><span class="sxs-lookup"><span data-stu-id="33929-106">It allows users to select and configure a WCF binding for the receive location, and to specify the endpoint behaviors and security settings.</span></span> <span data-ttu-id="33929-107">このアダプタを使用できるのは、インターネット インフォメーション サービス (IIS) でホストされているトランスポートのみです。</span><span class="sxs-lookup"><span data-stu-id="33929-107">This adapter can only be used by transports that are hosted in Internet Information Services (IIS).</span></span>  
  
 <span data-ttu-id="33929-108">WCF-CustomIsolated アダプタは、1 つの受信アダプタのみで構成されています。</span><span class="sxs-lookup"><span data-stu-id="33929-108">The WCF-CustomIsolated adapter consists of a receive adapter only.</span></span> <span data-ttu-id="33929-109">この WCF-CustomIsolated 受信アダプタは、分離ホストで実行されている受信場所に対して選択および構成した WCF バインド、サービス動作、エンドポイント動作、セキュリティ メカニズム、および受信メッセージ本文のソースを介して、WCF サービス要求を受信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="33929-109">You use the WCF-CustomIsolated receive adapter to receive WCF service requests through WCF bindings, service behavior, endpoint behavior, security mechanism, and the source of the inbound message body that you selected and configured for the receive location running in an isolated host.</span></span> <span data-ttu-id="33929-110">WCF-CustomIsolated 受信アダプタを使用する受信場所は、一方向または要求 - 応答 (双方向) として構成できます。</span><span class="sxs-lookup"><span data-stu-id="33929-110">A receive location that uses the WCF-CustomIsolated receive adapter can be configured as one-way or request-response (two-way).</span></span>  
  
 <span data-ttu-id="33929-111">受信アダプターの WCF の詳細についてを参照してください[WCF アダプターとは?](../core/what-are-the-wcf-adapters.md)です。</span><span class="sxs-lookup"><span data-stu-id="33929-111">For more information about WCF receive adapters, see [What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33929-112">参照</span><span class="sxs-lookup"><span data-stu-id="33929-112">See Also</span></span>  
 <span data-ttu-id="33929-113">[Wcf-customisolated アダプタを構成します。](../core/configuring-the-wcf-customisolated-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="33929-113">[Configuring the WCF-CustomIsolated Adapter](../core/configuring-the-wcf-customisolated-adapter.md) </span></span>  
 [<span data-ttu-id="33929-114">WCF アダプタ</span><span class="sxs-lookup"><span data-stu-id="33929-114">WCF Adapters</span></span>](../core/wcf-adapters.md)
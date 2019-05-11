---
title: Wcf-custom アダプターとは何ですか。 | Microsoft Docs
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
ms.openlocfilehash: eba1882957ed6974420d4827a43f90e1ef7ecba9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242760"
---
# <a name="what-is-the-wcf-custom-adapter"></a><span data-ttu-id="7706c-103">Wcf-custom アダプターとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="7706c-103">What Is the WCF-Custom Adapter?</span></span>
<span data-ttu-id="7706c-104">Wcf-custom アダプターは BizTalk Server で WCF 拡張機能コンポーネントの使用を有効にするために使用します。</span><span class="sxs-lookup"><span data-stu-id="7706c-104">The WCF-Custom adapter is used to enable the use of WCF extensibility components in BizTalk Server.</span></span> <span data-ttu-id="7706c-105">アダプターは、WCF フレームワークの完全な柔軟性を使用します。</span><span class="sxs-lookup"><span data-stu-id="7706c-105">The adapter enables complete flexibility of the WCF framework.</span></span> <span data-ttu-id="7706c-106">受信場所の WCF バインドを構成および送信ポートを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="7706c-106">It allows users to select and configure a WCF binding for the receive location and send port.</span></span> <span data-ttu-id="7706c-107">また、エンドポイント動作やセキュリティ設定を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="7706c-107">It also allows users to set the endpoint behaviors and security settings.</span></span>  
  
 <span data-ttu-id="7706c-108">Wcf-custom アダプターは、2 つのアダプターで構成されます-受信アダプタと送信アダプター。</span><span class="sxs-lookup"><span data-stu-id="7706c-108">The WCF-Custom adapter consists of two adapters—a receive adapter and a send adapter.</span></span>  
  
 <span data-ttu-id="7706c-109">**Wcf-custom 受信アダプター**</span><span class="sxs-lookup"><span data-stu-id="7706c-109">**WCF-Custom Receive Adapter**</span></span>  
  
 <span data-ttu-id="7706c-110">WCF カスタムを使用する受信アダプターは、バインド、サービス動作、エンドポイントの動作、セキュリティ メカニズムを介して WCF サービス要求を受信して、本文の受信メッセージのソースを選択して、トランスポート プロパティ ダイアログで構成します。受信場所。</span><span class="sxs-lookup"><span data-stu-id="7706c-110">You use the WCF-Custom receive adapter to receive WCF service requests through the bindings, service behavior, endpoint behavior, security mechanism, and the source of the inbound message body that you selected and configured in the transport properties dialog in the receive location.</span></span> <span data-ttu-id="7706c-111">Wcf-custom 受信アダプタを使用する受信場所は、一方向として構成できますまたは要求-応答 (双方向)。</span><span class="sxs-lookup"><span data-stu-id="7706c-111">A receive location that uses the WCF-Custom receive adapter can be configured as one-way or request-response (two-way).</span></span>  
  
 <span data-ttu-id="7706c-112">**Wcf-custom 送信アダプタ**</span><span class="sxs-lookup"><span data-stu-id="7706c-112">**WCF-Custom Send Adapter**</span></span>  
  
 <span data-ttu-id="7706c-113">Wcf-custom 送信アダプターを使用して、バインド、サービス動作、エンドポイントの動作、セキュリティ メカニズム、および選択および構成する送信メッセージの本文のソースを型宣言不要なコントラクトを介して WCF サービスを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="7706c-113">You use the WCF-Custom send adapter to call a WCF service through the typeless contract with the bindings, service behavior, endpoint behavior, security mechanism, and the source of the outbound message body that you selected and configured.</span></span>  
  
 <span data-ttu-id="7706c-114">WCF の詳細については、受信し送信アダプターを参照してください[WCF アダプタは何ですか?](../core/what-are-the-wcf-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="7706c-114">For more information about WCF receive and send adapters, see [What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7706c-115">参照</span><span class="sxs-lookup"><span data-stu-id="7706c-115">See Also</span></span>  
 <span data-ttu-id="7706c-116">[Wcf-custom アダプターを構成します。](../core/configuring-the-wcf-custom-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="7706c-116">[Configuring the WCF-Custom Adapter](../core/configuring-the-wcf-custom-adapter.md) </span></span>  
 [<span data-ttu-id="7706c-117">WCF アダプター</span><span class="sxs-lookup"><span data-stu-id="7706c-117">WCF Adapters</span></span>](../core/wcf-adapters.md)
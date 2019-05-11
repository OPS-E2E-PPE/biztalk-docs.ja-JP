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
ms.openlocfilehash: 1b60cc39092961703f45921c34a518f3da89691c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242793"
---
# <a name="what-is-the-wcf-customisolated-adapter"></a><span data-ttu-id="c3115-103">Wcf-customisolated アダプターとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="c3115-103">What Is the WCF-CustomIsolated Adapter?</span></span>
<span data-ttu-id="c3115-104">Wcf-customisolated アダプターは、分離ホストで BizTalk Server で WCF 拡張機能コンポーネントの使用できるように使用されます。</span><span class="sxs-lookup"><span data-stu-id="c3115-104">The WCF-CustomIsolated adapter is used to enable the use of WCF extensibility components in BizTalk Server with an isolated host.</span></span> <span data-ttu-id="c3115-105">アダプターは、WCF フレームワークの完全な柔軟性を使用します。</span><span class="sxs-lookup"><span data-stu-id="c3115-105">The adapter enables complete flexibility of the WCF framework.</span></span> <span data-ttu-id="c3115-106">ユーザーを選択し、受信場所の WCF バインドを構成し、エンドポイントの動作とセキュリティ設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c3115-106">It allows users to select and configure a WCF binding for the receive location, and to specify the endpoint behaviors and security settings.</span></span> <span data-ttu-id="c3115-107">このアダプターは、インターネット インフォメーション サービス (IIS) でホストされているトランスポートでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c3115-107">This adapter can only be used by transports that are hosted in Internet Information Services (IIS).</span></span>  
  
 <span data-ttu-id="c3115-108">Wcf-customisolated アダプタは、受信アダプタのみで構成されます。</span><span class="sxs-lookup"><span data-stu-id="c3115-108">The WCF-CustomIsolated adapter consists of a receive adapter only.</span></span> <span data-ttu-id="c3115-109">受信場所の WCF バインド、サービス動作、エンドポイントの動作、セキュリティ メカニズム、および選択および構成する受信メッセージ本文のソースから Wcf-customisolated 受信アダプターは WCF サービス要求の受信を使用します。分離ホストで実行されています。</span><span class="sxs-lookup"><span data-stu-id="c3115-109">You use the WCF-CustomIsolated receive adapter to receive WCF service requests through WCF bindings, service behavior, endpoint behavior, security mechanism, and the source of the inbound message body that you selected and configured for the receive location running in an isolated host.</span></span> <span data-ttu-id="c3115-110">Wcf-customisolated 受信アダプタを使用する受信場所は、一方向として構成できますまたは要求-応答 (双方向)。</span><span class="sxs-lookup"><span data-stu-id="c3115-110">A receive location that uses the WCF-CustomIsolated receive adapter can be configured as one-way or request-response (two-way).</span></span>  
  
 <span data-ttu-id="c3115-111">WCF の詳細については、受信アダプターを参照してください[WCF アダプタは何ですか?](../core/what-are-the-wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="c3115-111">For more information about WCF receive adapters, see [What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3115-112">参照</span><span class="sxs-lookup"><span data-stu-id="c3115-112">See Also</span></span>  
 <span data-ttu-id="c3115-113">[Wcf-customisolated アダプターを構成します。](../core/configuring-the-wcf-customisolated-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="c3115-113">[Configuring the WCF-CustomIsolated Adapter](../core/configuring-the-wcf-customisolated-adapter.md) </span></span>  
 [<span data-ttu-id="c3115-114">WCF アダプター</span><span class="sxs-lookup"><span data-stu-id="c3115-114">WCF Adapters</span></span>](../core/wcf-adapters.md)
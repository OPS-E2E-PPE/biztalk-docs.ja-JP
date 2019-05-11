---
title: WCF LOB Adapter SDK でサポートされているメッセージ交換パターンの表示 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b6662f17-b4f8-45fe-a22f-5d027dc9f2ff
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eca67c0f5ebbb3220ebd6d1a836cc37f271df9ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362649"
---
# <a name="view-the-supported-message-exchange-patterns-in-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="47a07-102">WCF LOB Adapter SDK でサポートされているメッセージ交換パターンを表示します。</span><span class="sxs-lookup"><span data-stu-id="47a07-102">View the supported message exchange patterns in the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="47a07-103">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] 、基になるでサポートされているメッセージング パターンのいくつかの操作をサポートしている[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]要求/応答、一方向の通信など。</span><span class="sxs-lookup"><span data-stu-id="47a07-103">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] supports several of the messaging patterns supported by the underlying [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] including request-reply, and one-way communication.</span></span> <span data-ttu-id="47a07-104">さまざまなトランスポートでは、異なるメッセージング パターンをサポートし、サポートされる対話の種類にも影響します。</span><span class="sxs-lookup"><span data-stu-id="47a07-104">Different transports support different messaging patterns, and thus affect the types of interactions that they support.</span></span>  
  
 <span data-ttu-id="47a07-105">次の表に示すパターンは、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="47a07-105">The patterns listed in the following table are handled by the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span>  
  
|<span data-ttu-id="47a07-106">パターン</span><span class="sxs-lookup"><span data-stu-id="47a07-106">Pattern</span></span>|<span data-ttu-id="47a07-107">説明</span><span class="sxs-lookup"><span data-stu-id="47a07-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="47a07-108">一方向受信</span><span class="sxs-lookup"><span data-stu-id="47a07-108">One-way inbound</span></span>|<span data-ttu-id="47a07-109">基幹業務システムから受信メッセージを受信するが、アダプターからの応答は発生しません。</span><span class="sxs-lookup"><span data-stu-id="47a07-109">Inbound messages are received from the line-of-business system but no response is expected from the adapter.</span></span>|  
|<span data-ttu-id="47a07-110">要求-応答受信</span><span class="sxs-lookup"><span data-stu-id="47a07-110">Request-response inbound</span></span>|<span data-ttu-id="47a07-111">アダプターから適切な応答が必要ですが、基幹業務システムからは、受信メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="47a07-111">Inbound messages are received from the line-of-business system which expects an appropriate response from the adapter.</span></span>|  
|<span data-ttu-id="47a07-112">一方向送信</span><span class="sxs-lookup"><span data-stu-id="47a07-112">One-way outbound</span></span>|<span data-ttu-id="47a07-113">送信メッセージは、基幹業務システムに送信されますが、アダプターからの応答は発生しません。</span><span class="sxs-lookup"><span data-stu-id="47a07-113">Outbound messages are sent to the line-of-business system but no response is expected from the adapter.</span></span>|  
|<span data-ttu-id="47a07-114">要求-応答の送信</span><span class="sxs-lookup"><span data-stu-id="47a07-114">Request-response outbound</span></span>|<span data-ttu-id="47a07-115">送信メッセージは、応答がアダプターから予測を含む、基幹業務システムに送信されます。</span><span class="sxs-lookup"><span data-stu-id="47a07-115">Outbound messages are sent to the line-of-business system with a response expected from the adapter.</span></span>|  
|<span data-ttu-id="47a07-116">セッションの多い受信</span><span class="sxs-lookup"><span data-stu-id="47a07-116">Sessionful inbound</span></span>|<span data-ttu-id="47a07-117">受信メッセージは、一意のセッション内で基幹業務システムから受信されます。</span><span class="sxs-lookup"><span data-stu-id="47a07-117">Inbound messages are received from the line-of-business system within a unique session.</span></span> <span data-ttu-id="47a07-118">アダプターから基幹業務システムでは、応答は発生しません。</span><span class="sxs-lookup"><span data-stu-id="47a07-118">No response is expected by the line-of-business system from the adapter.</span></span>|  
|<span data-ttu-id="47a07-119">送信セッションの多い</span><span class="sxs-lookup"><span data-stu-id="47a07-119">Sessionful outbound</span></span>|<span data-ttu-id="47a07-120">送信メッセージは、一意のセッション内で、基幹業務システムに送信されます。</span><span class="sxs-lookup"><span data-stu-id="47a07-120">Outbound messages are sent to the line-of-business system within a unique session.</span></span> <span data-ttu-id="47a07-121">アダプターによって、基幹業務システムからの応答は発生しません。</span><span class="sxs-lookup"><span data-stu-id="47a07-121">No response is expected from the line-of-business system by the adapter.</span></span>|  
  
 <span data-ttu-id="47a07-122">ターゲット アプリケーションの機能によってメッセージ パターンの選択をガイドします。</span><span class="sxs-lookup"><span data-stu-id="47a07-122">Your choice of message pattern will be guided by the functionality of the target application.</span></span>  
  
## <a name="planning-for-sessions"></a><span data-ttu-id="47a07-123">セッションの計画</span><span class="sxs-lookup"><span data-stu-id="47a07-123">Planning for Sessions</span></span>  
 <span data-ttu-id="47a07-124">メッセージング パターンでは、アダプターと基幹業務システム間で交換されるすべてのメッセージは、同じメッセージ交換の一部である必要があることを確認したいときにセッションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="47a07-124">A messaging pattern may use a session when it wants to ensure that all messages exchanged between the adapter and the line-of-business system must be part of the same conversation.</span></span> <span data-ttu-id="47a07-125">通常のセッションは、配信保証が必要ですが、メッセージ交換、アダプター開発者がいる可能性のあるその他の要件をサポートするためにも使用するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="47a07-125">Typically sessions are used when delivery guarantee is needed, but they can also be used to support other requirements that an adapter developer may have for message exchange.</span></span>  
  
 <span data-ttu-id="47a07-126">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]依存、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]のセッションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="47a07-126">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] relies on the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] for session support.</span></span> <span data-ttu-id="47a07-127">セッションの詳細については、次を参照してください。[セッション、インスタンス化、および同時実行](https://msdn.microsoft.com/library/ms731193.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="47a07-127">For more information about sessions, see [Sessions, Instancing, and Concurrency](https://msdn.microsoft.com/library/ms731193.aspx).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="47a07-128">参照</span><span class="sxs-lookup"><span data-stu-id="47a07-128">See Also</span></span>  
 [<span data-ttu-id="47a07-129">計画し、WCF LOB Adapter SDK を使用して、アダプターの設計</span><span class="sxs-lookup"><span data-stu-id="47a07-129">Plan and design an adapter using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)
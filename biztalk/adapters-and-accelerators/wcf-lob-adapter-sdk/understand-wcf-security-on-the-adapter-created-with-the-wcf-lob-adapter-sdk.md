---
title: "WCF LOB Adapter SDK で作成されたアダプターで WCF セキュリティについて理解 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1ee402b-ffda-42c1-8d85-d7cbe073a307
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baf0c62c3d0c37c1f69cb944112ff832dade5ec4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="understand-wcf-security-on-the-adapter-created-with-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="0ab16-102">WCF LOB Adapter SDK で作成されたアダプターで WCF のセキュリティを理解します。</span><span class="sxs-lookup"><span data-stu-id="0ab16-102">Understand WCF security on the adapter created with the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="0ab16-103">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]拡張、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]アーキテクチャのチャネルし、は、メッセージング インフラストラクチャとで提供される API を使用します。</span><span class="sxs-lookup"><span data-stu-id="0ab16-103">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] extends the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] channel architecture and relies on the messaging infrastructure and the API that it provides.</span></span>  <span data-ttu-id="0ab16-104">WCF LOB アダプターが、ターゲット システムに接続を確立する必要があるし、そのために認証とその他のセキュリティ情報がターゲット システムの接続を確立するために必要なアダプターを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ab16-104">A WCF LOB adapter needs to establish a connection to target systems, and hence it is necessary to configure the adapter with authentication and other security information required to make the target system connections.</span></span>  
  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]<span data-ttu-id="0ab16-105">分散プログラミングのプラットフォームは、SOAP メッセージを移動できる多数の異なるノード、SOAP 中継ぎ局、ファイアウォール、および可能性のあるインターネット送信者から基幹業務システムからアダプターにおよび、クライアントにログオンに基づいています。</span><span class="sxs-lookup"><span data-stu-id="0ab16-105"> is a distributed programming platform based on SOAP messages that can travel through many different nodes, SOAP intermediaries, firewalls, and potentially the Internet en-route from the line-of-business system to the adapter and on to the client.</span></span> <span data-ttu-id="0ab16-106">これは、アダプターと配置のシナリオに対するさまざまなセキュリティの脅威の数が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0ab16-106">This could present a number of different security threats to your adapter and deployment scenario.</span></span>  
  
 <span data-ttu-id="0ab16-107">セキュリティは、すべてのエンタープライズ アーキテクチャ ソリューションでの主要な役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="0ab16-107">Security plays a major part in any enterprise architecture solution.</span></span> <span data-ttu-id="0ab16-108">機密性、整合性、認証、およびセキュリティの脅威からアダプターを保護するために、WCF のセキュリティ モデルで提供される承認機能を活用することができます。</span><span class="sxs-lookup"><span data-stu-id="0ab16-108">You can leverage the confidentiality, integrity, authentication, and authorization features provided in the WCF security model to help secure the adapter from security threats.</span></span> <span data-ttu-id="0ab16-109">これら 2 つのエンティティ間の通信を保護するには、アダプターと、ターゲット システムの間のメッセージ レベルのセキュリティとトランスポートについても考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ab16-109">You must also consider the transport and message-level security between the adapter and the target system to protect the communication between these two entities.</span></span> <span data-ttu-id="0ab16-110">場合でも、WCF は、豊富な一連の ws-* 仕様、これらの実装の詳細セキュリティ標準では、アダプターは、基幹業務システムによって提供される機能に依存します。</span><span class="sxs-lookup"><span data-stu-id="0ab16-110">Even though WCF provides a rich set of WS-* specifications, implementation of these advanced security standards in your adapter will depend on the capabilities provided by the line-of-business system.</span></span>  
  
 <span data-ttu-id="0ab16-111">詳細については[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]、概要、概念、一般的なシナリオ、およびベスト プラクティスは、「」を参照を含むセキュリティ[Windows Communication Foundation セキュリティ](https://msdn.microsoft.com/library/ms732362.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="0ab16-111">For more information about [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] security including an overview, concepts, common scenarios, and best practices, see [Windows Communication Foundation Security](https://msdn.microsoft.com/library/ms732362.aspx).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0ab16-112">参照</span><span class="sxs-lookup"><span data-stu-id="0ab16-112">See Also</span></span>  
 [<span data-ttu-id="0ab16-113">計画し、WCF LOB Adapter SDK を使用して、アダプターの設計</span><span class="sxs-lookup"><span data-stu-id="0ab16-113">Plan and design an adapter using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)
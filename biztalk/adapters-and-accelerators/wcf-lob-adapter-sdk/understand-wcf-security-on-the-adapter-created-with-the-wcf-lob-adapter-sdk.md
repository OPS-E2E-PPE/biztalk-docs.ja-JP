---
title: WCF LOB Adapter SDK で作成されたアダプターで WCF セキュリティの概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1ee402b-ffda-42c1-8d85-d7cbe073a307
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b34be29b74b10d5b9768cff5bc40a26abe41dce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362721"
---
# <a name="understand-wcf-security-on-the-adapter-created-with-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="41dbe-102">WCF LOB Adapter SDK で作成されたアダプターで WCF セキュリティを概要します。</span><span class="sxs-lookup"><span data-stu-id="41dbe-102">Understand WCF security on the adapter created with the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="41dbe-103">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]拡張、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネルのアーキテクチャと、メッセージング インフラストラクチャとそれを提供する API に依存しています。</span><span class="sxs-lookup"><span data-stu-id="41dbe-103">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] extends the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] channel architecture and relies on the messaging infrastructure and the API that it provides.</span></span>  <span data-ttu-id="41dbe-104">WCF LOB アダプターを対象のシステムへの接続を確立する必要があるし、は認証とターゲット システムに接続するために必要なその他のセキュリティ情報と、アダプターを構成するために必要なためです。</span><span class="sxs-lookup"><span data-stu-id="41dbe-104">A WCF LOB adapter needs to establish a connection to target systems, and hence it is necessary to configure the adapter with authentication and other security information required to make the target system connections.</span></span>  
  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] <span data-ttu-id="41dbe-105">分散プログラミングのプラットフォームはアダプターに、クライアントへのログオンと基幹業務システムから多数の異なるノード、SOAP 中継ぎ局、ファイアウォール、および可能性のあるインターネットの途中で移動できる SOAP メッセージに基づいています。</span><span class="sxs-lookup"><span data-stu-id="41dbe-105">is a distributed programming platform based on SOAP messages that can travel through many different nodes, SOAP intermediaries, firewalls, and potentially the Internet en-route from the line-of-business system to the adapter and on to the client.</span></span> <span data-ttu-id="41dbe-106">これは、数、アダプターと展開シナリオに対するさまざまなセキュリティの脅威が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="41dbe-106">This could present a number of different security threats to your adapter and deployment scenario.</span></span>  
  
 <span data-ttu-id="41dbe-107">セキュリティは、すべてのエンタープライズ アーキテクチャ ソリューションでの主要な役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="41dbe-107">Security plays a major part in any enterprise architecture solution.</span></span> <span data-ttu-id="41dbe-108">機密性、整合性、認証、およびセキュリティの脅威からアダプターをセキュリティ保護するための WCF セキュリティ モデルで提供される承認機能を活用することができます。</span><span class="sxs-lookup"><span data-stu-id="41dbe-108">You can leverage the confidentiality, integrity, authentication, and authorization features provided in the WCF security model to help secure the adapter from security threats.</span></span> <span data-ttu-id="41dbe-109">トランスポートおよびこれら 2 つのエンティティ間の通信を保護するには、アダプターと、ターゲット システムの間のメッセージ レベルのセキュリティも考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41dbe-109">You must also consider the transport and message-level security between the adapter and the target system to protect the communication between these two entities.</span></span> <span data-ttu-id="41dbe-110">場合でも、WCF は ws-の豊富なセットを提供します \* の仕様、これらの実装の詳細セキュリティ標準では、アダプターは、基幹業務システムによって提供される機能に依存します。</span><span class="sxs-lookup"><span data-stu-id="41dbe-110">Even though WCF provides a rich set of WS-\* specifications, implementation of these advanced security standards in your adapter will depend on the capabilities provided by the line-of-business system.</span></span>  
  
 <span data-ttu-id="41dbe-111">詳細については[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]、概要、概念、一般的なシナリオ、およびベスト プラクティスは、参照を含むセキュリティ[Windows Communication Foundation セキュリティ](https://msdn.microsoft.com/library/ms732362.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="41dbe-111">For more information about [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] security including an overview, concepts, common scenarios, and best practices, see [Windows Communication Foundation Security](https://msdn.microsoft.com/library/ms732362.aspx).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="41dbe-112">参照</span><span class="sxs-lookup"><span data-stu-id="41dbe-112">See Also</span></span>  
 [<span data-ttu-id="41dbe-113">計画し、WCF LOB Adapter SDK を使用して、アダプターの設計</span><span class="sxs-lookup"><span data-stu-id="41dbe-113">Plan and design an adapter using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)
---
title: "オーケストレーションを開発するためのセキュリティに関する考慮事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, orchestrations
- messages, subscriptions
- orchestrations, security
- messages, security
ms.assetid: a29b2018-4a8f-49ad-a817-6f279db3f801
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e020759a8d389461978a4de4138bcc139d527539
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="security-considerations-for-developing-orchestrations"></a><span data-ttu-id="5a77c-102">オーケストレーションを開発するためのセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="5a77c-102">Security Considerations for Developing Orchestrations</span></span>
<span data-ttu-id="5a77c-103">オーケストレーションを設計する際は、潜在的なセキュリティの問題を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a77c-103">When designing your orchestrations, you should consider potential security issues.</span></span>  
  
## <a name="avoid-subscriptions-based-on-content-from-untrusted-messages"></a><span data-ttu-id="5a77c-104">信頼されないメッセージのコンテンツに基づくサブスクリプションを防ぐ</span><span class="sxs-lookup"><span data-stu-id="5a77c-104">Avoid subscriptions based on content from untrusted messages</span></span>  
 <span data-ttu-id="5a77c-105">メッセージのコンテンツやコンテキストに基づいてサブスクリプションを作成する可能性のあるオーケストレーション インスタンスが、権限レベルの低いメッセージによって開始されないようにするため、信頼されないメッセージのコンテンツやコンテキストに基づくメッセージのサブスクリプションが、オーケストレーションで作成されないようにすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5a77c-105">To ensure that a low-privilege message does not initiate an orchestration instance that could potentially create subscriptions based on the message content or context, it is highly recommended that your orchestrations do not create their message subscriptions based on the content or context of a message that is not trusted.</span></span>  
  
 <span data-ttu-id="5a77c-106">セキュリティの詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[BizTalk Server のセキュリティで保護する](../core/securing-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="5a77c-106">For information about security in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Securing BizTalk Server](../core/securing-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a77c-107">参照</span><span class="sxs-lookup"><span data-stu-id="5a77c-107">See Also</span></span>  
 <span data-ttu-id="5a77c-108">[オーケストレーションの作成](../core/creating-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="5a77c-108">[Creating Orchestrations](../core/creating-orchestrations.md) </span></span>  
 [<span data-ttu-id="5a77c-109">オーケストレーションについて</span><span class="sxs-lookup"><span data-stu-id="5a77c-109">About Orchestrations</span></span>](../core/about-orchestrations.md)
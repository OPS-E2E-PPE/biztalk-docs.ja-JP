---
title: オーケストレーションを開発するためのセキュリティに関する考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, orchestrations
- messages, subscriptions
- orchestrations, security
- messages, security
ms.assetid: a29b2018-4a8f-49ad-a817-6f279db3f801
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6d159a96052871796c102dc628dae2a06d85046
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280320"
---
# <a name="security-considerations-for-developing-orchestrations"></a><span data-ttu-id="a7f54-102">オーケストレーションを開発するためのセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="a7f54-102">Security Considerations for Developing Orchestrations</span></span>
<span data-ttu-id="a7f54-103">オーケストレーションを設計するときは、潜在的なセキュリティの問題を検討してください。</span><span class="sxs-lookup"><span data-stu-id="a7f54-103">When designing your orchestrations, you should consider potential security issues.</span></span>  
  
## <a name="avoid-subscriptions-based-on-content-from-untrusted-messages"></a><span data-ttu-id="a7f54-104">信頼されていないメッセージのコンテンツに基づいてサブスクリプションを回避します。</span><span class="sxs-lookup"><span data-stu-id="a7f54-104">Avoid subscriptions based on content from untrusted messages</span></span>  
 <span data-ttu-id="a7f54-105">特権の低いメッセージがメッセージのコンテンツやコンテキストに基づいてサブスクリプションを作成する可能性のあるオーケストレーション インスタンスを開始していないことを確認するを強くお勧め、オーケストレーションがメッセージのサブスクリプションを作成できません。コンテンツや信頼されていないメッセージのコンテキストに基づいています。</span><span class="sxs-lookup"><span data-stu-id="a7f54-105">To ensure that a low-privilege message does not initiate an orchestration instance that could potentially create subscriptions based on the message content or context, it is highly recommended that your orchestrations do not create their message subscriptions based on the content or context of a message that is not trusted.</span></span>  
  
 <span data-ttu-id="a7f54-106">セキュリティについて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[BizTalk Server のセキュリティで保護する](../core/securing-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="a7f54-106">For information about security in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Securing BizTalk Server](../core/securing-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7f54-107">参照</span><span class="sxs-lookup"><span data-stu-id="a7f54-107">See Also</span></span>  
 <span data-ttu-id="a7f54-108">[オーケストレーションの作成](../core/creating-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="a7f54-108">[Creating Orchestrations](../core/creating-orchestrations.md) </span></span>  
 [<span data-ttu-id="a7f54-109">オーケストレーションについて</span><span class="sxs-lookup"><span data-stu-id="a7f54-109">About Orchestrations</span></span>](../core/about-orchestrations.md)
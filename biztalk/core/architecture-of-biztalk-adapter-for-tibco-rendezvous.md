---
title: "BizTalk Adapter for TIBCO Rendezvous のアーキテクチャ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- passing messages
- architecture
- message passing
- messages, passing
ms.assetid: 174d6ceb-8e1d-4c93-827d-8155cfe47836
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 801f92453ffc85d83d57c1caa5c89ec618b96ed0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="architecture-of-biztalk-adapter-for-tibco-rendezvous"></a><span data-ttu-id="922b7-102">BizTalk Adapter for TIBCO Rendezvous のアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="922b7-102">Architecture of BizTalk Adapter for TIBCO Rendezvous</span></span>
<span data-ttu-id="922b7-103">Microsoft BizTalk Adapter for TIBCO Rendezvous は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と TIBCO Rendezvous 間に双方向の接続を提供します。</span><span class="sxs-lookup"><span data-stu-id="922b7-103">Microsoft BizTalk Adapter for TIBCO Rendezvous provides bi-directional connectivity between [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and TIBCO Rendezvous.</span></span> <span data-ttu-id="922b7-104">このアダプターは、TIBCO Rendezvous API と BizTalk Adapter Framework API の両方を使用して、緊密な統合を提供します。</span><span class="sxs-lookup"><span data-stu-id="922b7-104">This adapter uses both the TIBCO Rendezvous API and the BizTalk Adapter Framework API to provide tight integration.</span></span>  
  
 <span data-ttu-id="922b7-105">TIBCO Rendezvous は、エンタープライズ アプリケーション統合 (EAI) のメッセージ バスを提供するソフトウェア製品です。</span><span class="sxs-lookup"><span data-stu-id="922b7-105">TIBCO Rendezvous is a software product that provides a message bus for enterprise application integration (EAI).</span></span> <span data-ttu-id="922b7-106">TIBCO には、C、C++、Java、Visual Basic および Microsoft .NET Framework 用のメッセージング API が用意されており、Microsoft Office Excel ワークシートおよびその他の任意のアプリケーションでデータ フィードを受信できます。</span><span class="sxs-lookup"><span data-stu-id="922b7-106">TIBCO provides messaging APIs in C, C++, Java, Visual Basic and the Microsoft .NET Framework to receive data feeds on Microsoft Office Excel worksheets and other applications of choice.</span></span>  
  
## <a name="message-passing"></a><span data-ttu-id="922b7-107">メッセージ パッシング</span><span class="sxs-lookup"><span data-stu-id="922b7-107">Message Passing</span></span>  
 <span data-ttu-id="922b7-108">メッセージを渡す概念はとても簡単です。</span><span class="sxs-lookup"><span data-stu-id="922b7-108">The basic concept of message passing is fairly simple:</span></span>  
  
-   <span data-ttu-id="922b7-109">メッセージには、ピリオドで区切られた要素で構成される 1 つのサブジェクトがあります。</span><span class="sxs-lookup"><span data-stu-id="922b7-109">A message has a single subject composed of elements separated by periods.</span></span> <span data-ttu-id="922b7-110">メッセージは 1 つの Rendezous デーモンに送信されます (ただし、最終的に他の複数のデーモンに配信される場合があります)。</span><span class="sxs-lookup"><span data-stu-id="922b7-110">It is sent to a single Rendezvous daemon (though it might eventually be broadcast onto other daemons).</span></span>  
  
-   <span data-ttu-id="922b7-111">リスナーは、待機しているサブジェクトを (基本的なワイルドカード機能を使用して) デーモンに通知し、2 つのデーモンが相互に "接続" されている場合または実際には同一のデーモンである場合は、一致するサブジェクトを持つメッセージがリスナーに配信されます。</span><span class="sxs-lookup"><span data-stu-id="922b7-111">A listener announces its subjects of interest to a daemon (with a basic wildcard facility), and messages that have matching subjects are delivered to it if the two daemons are 'connected' to each other, or are indeed the same daemon.</span></span> <span data-ttu-id="922b7-112">詳細については、内のメッセージを参照してください。 [BizTalk Adapter for TIBCO Rendezvous のメッセージ](../core/messages-in-biztalk-adapter-for-tibco-rendezvous.md)です。</span><span class="sxs-lookup"><span data-stu-id="922b7-112">For more information, see Messages in [Messages in BizTalk Adapter for TIBCO Rendezvous](../core/messages-in-biztalk-adapter-for-tibco-rendezvous.md).</span></span>  
  
 <span data-ttu-id="922b7-113">次の図は、BizTalk Adapter for TIBCO Rendezvous のアーキテクチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="922b7-113">The following figure shows the architecture for BizTalk Adapter for TIBCO Rendezvous.</span></span>  
  
 ![](../core/media/tibcorend-arch.gif "TibcoRend_Arch")  
  
## <a name="see-also"></a><span data-ttu-id="922b7-114">参照</span><span class="sxs-lookup"><span data-stu-id="922b7-114">See Also</span></span>  
 <span data-ttu-id="922b7-115">[作業の開始](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="922b7-115">[Getting Started](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="922b7-116">計画とアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="922b7-116">Planning and Architecture</span></span>](../core/planning-and-architecture15.md)
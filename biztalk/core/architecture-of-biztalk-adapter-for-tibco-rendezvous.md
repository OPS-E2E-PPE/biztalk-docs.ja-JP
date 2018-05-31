---
title: TIBCO Rendezvous アダプターのアーキテクチャ |Microsoft ドキュメント
description: BizTalk Adapter for TIBCO Rendezvous しくみ、BizTalk Server でメッセージを渡すことの詳細します。
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 174d6ceb-8e1d-4c93-827d-8155cfe47836
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3bfee2b51df8781091ea30e512810bae21a5f2a
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013433"
---
# <a name="architecture-of-the-tibco-rendezvous-adapter"></a><span data-ttu-id="8f2e7-103">TIBCO Rendezvous アダプターのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="8f2e7-103">Architecture of the TIBCO Rendezvous adapter</span></span>

## <a name="overview"></a><span data-ttu-id="8f2e7-104">概要</span><span class="sxs-lookup"><span data-stu-id="8f2e7-104">Overview</span></span>
<span data-ttu-id="8f2e7-105">Microsoft BizTalk Adapter for TIBCO Rendezvous は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と TIBCO Rendezvous 間に双方向の接続を提供します。</span><span class="sxs-lookup"><span data-stu-id="8f2e7-105">Microsoft BizTalk Adapter for TIBCO Rendezvous provides bi-directional connectivity between [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and TIBCO Rendezvous.</span></span> <span data-ttu-id="8f2e7-106">このアダプターは、TIBCO Rendezvous API と BizTalk Adapter Framework API の両方を使用して、緊密な統合を提供します。</span><span class="sxs-lookup"><span data-stu-id="8f2e7-106">This adapter uses both the TIBCO Rendezvous API and the BizTalk Adapter Framework API to provide tight integration.</span></span>  
  
 <span data-ttu-id="8f2e7-107">TIBCO Rendezvous は、エンタープライズ アプリケーション統合 (EAI) のメッセージ バスを提供するソフトウェア製品です。</span><span class="sxs-lookup"><span data-stu-id="8f2e7-107">TIBCO Rendezvous is a software product that provides a message bus for enterprise application integration (EAI).</span></span> <span data-ttu-id="8f2e7-108">TIBCO には、C、C++、Java、Visual Basic および Microsoft .NET Framework 用のメッセージング API が用意されており、Microsoft Office Excel ワークシートおよびその他の任意のアプリケーションでデータ フィードを受信できます。</span><span class="sxs-lookup"><span data-stu-id="8f2e7-108">TIBCO provides messaging APIs in C, C++, Java, Visual Basic and the Microsoft .NET Framework to receive data feeds on Microsoft Office Excel worksheets and other applications of choice.</span></span>  
  
## <a name="message-passing"></a><span data-ttu-id="8f2e7-109">メッセージ パッシング</span><span class="sxs-lookup"><span data-stu-id="8f2e7-109">Message Passing</span></span>  
 <span data-ttu-id="8f2e7-110">メッセージを渡す概念はとても簡単です。</span><span class="sxs-lookup"><span data-stu-id="8f2e7-110">The basic concept of message passing is fairly simple:</span></span>  
  
-   <span data-ttu-id="8f2e7-111">メッセージには、ピリオドで区切られた要素で構成される 1 つのサブジェクトがあります。</span><span class="sxs-lookup"><span data-stu-id="8f2e7-111">A message has a single subject composed of elements separated by periods.</span></span> <span data-ttu-id="8f2e7-112">メッセージは 1 つの Rendezous デーモンに送信されます (ただし、最終的に他の複数のデーモンに配信される場合があります)。</span><span class="sxs-lookup"><span data-stu-id="8f2e7-112">It is sent to a single Rendezvous daemon (though it might eventually be broadcast onto other daemons).</span></span>  
  
-   <span data-ttu-id="8f2e7-113">リスナーは、待機しているサブジェクトを (基本的なワイルドカード機能を使用して) デーモンに通知し、2 つのデーモンが相互に "接続" されている場合または実際には同一のデーモンである場合は、一致するサブジェクトを持つメッセージがリスナーに配信されます。</span><span class="sxs-lookup"><span data-stu-id="8f2e7-113">A listener announces its subjects of interest to a daemon (with a basic wildcard facility), and messages that have matching subjects are delivered to it if the two daemons are 'connected' to each other, or are indeed the same daemon.</span></span> <span data-ttu-id="8f2e7-114">詳細については、内のメッセージを参照してください。 [BizTalk Adapter for TIBCO Rendezvous のメッセージ](../core/messages-in-biztalk-adapter-for-tibco-rendezvous.md)です。</span><span class="sxs-lookup"><span data-stu-id="8f2e7-114">For more information, see Messages in [Messages in BizTalk Adapter for TIBCO Rendezvous](../core/messages-in-biztalk-adapter-for-tibco-rendezvous.md).</span></span>  
  
 <span data-ttu-id="8f2e7-115">次の図は、BizTalk Adapter for TIBCO Rendezvous のアーキテクチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="8f2e7-115">The following figure shows the architecture for BizTalk Adapter for TIBCO Rendezvous.</span></span>  
  
 ![](../core/media/tibcorend-arch.gif "TibcoRend_Arch")  
  
## <a name="see-also"></a><span data-ttu-id="8f2e7-116">参照</span><span class="sxs-lookup"><span data-stu-id="8f2e7-116">See Also</span></span>  
 [<span data-ttu-id="8f2e7-117">作業の開始</span><span class="sxs-lookup"><span data-stu-id="8f2e7-117">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)  
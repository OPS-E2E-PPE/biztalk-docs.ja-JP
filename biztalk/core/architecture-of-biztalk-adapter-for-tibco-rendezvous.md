---
title: TIBCO Rendezvous アダプターのアーキテクチャ |Microsoft Docs
description: BizTalk Adapter for TIBCO Rendezvous は、BizTalk Server でメッセージを渡すなどについて説明します
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
ms.openlocfilehash: 2d368e27dd0652753d223fa15b7c82d8ddbbe8b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359012"
---
# <a name="architecture-of-the-tibco-rendezvous-adapter"></a><span data-ttu-id="1d152-103">TIBCO Rendezvous アダプターのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="1d152-103">Architecture of the TIBCO Rendezvous adapter</span></span>

## <a name="overview"></a><span data-ttu-id="1d152-104">概要</span><span class="sxs-lookup"><span data-stu-id="1d152-104">Overview</span></span>
<span data-ttu-id="1d152-105">Microsoft BizTalk Adapter for TIBCO Rendezvous 間の双方向接続を提供する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と TIBCO Rendezvous します。</span><span class="sxs-lookup"><span data-stu-id="1d152-105">Microsoft BizTalk Adapter for TIBCO Rendezvous provides bi-directional connectivity between [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and TIBCO Rendezvous.</span></span> <span data-ttu-id="1d152-106">このアダプターは、TIBCO Rendezvous API と BizTalk Adapter Framework API の両方を使用して、緊密な統合を提供します。</span><span class="sxs-lookup"><span data-stu-id="1d152-106">This adapter uses both the TIBCO Rendezvous API and the BizTalk Adapter Framework API to provide tight integration.</span></span>  
  
 <span data-ttu-id="1d152-107">TIBCO Rendezvous は、エンタープライズ アプリケーション統合 (EAI) のメッセージ バスを提供するソフトウェア製品です。</span><span class="sxs-lookup"><span data-stu-id="1d152-107">TIBCO Rendezvous is a software product that provides a message bus for enterprise application integration (EAI).</span></span> <span data-ttu-id="1d152-108">TIBCO には、C、C++、Java、Visual Basic および Microsoft .NET Framework を受信し、Microsoft Office Excel ワークシートにデータ フィードを任意の他のアプリケーションでのメッセージング Api が提供されます。</span><span class="sxs-lookup"><span data-stu-id="1d152-108">TIBCO provides messaging APIs in C, C++, Java, Visual Basic and the Microsoft .NET Framework to receive data feeds on Microsoft Office Excel worksheets and other applications of choice.</span></span>  
  
## <a name="message-passing"></a><span data-ttu-id="1d152-109">メッセージの受け渡し</span><span class="sxs-lookup"><span data-stu-id="1d152-109">Message Passing</span></span>  
 <span data-ttu-id="1d152-110">メッセージを渡す概念はとても簡単です。</span><span class="sxs-lookup"><span data-stu-id="1d152-110">The basic concept of message passing is fairly simple:</span></span>  
  
- <span data-ttu-id="1d152-111">メッセージには、ピリオドで区切られた要素で構成される 1 つのサブジェクトがあります。</span><span class="sxs-lookup"><span data-stu-id="1d152-111">A message has a single subject composed of elements separated by periods.</span></span> <span data-ttu-id="1d152-112">(ただし、最終的に他の複数のデーモンにブロードキャストする場合があります) は、1 つの Rendezvous デーモンに送信されます。</span><span class="sxs-lookup"><span data-stu-id="1d152-112">It is sent to a single Rendezvous daemon (though it might eventually be broadcast onto other daemons).</span></span>  
  
- <span data-ttu-id="1d152-113">リスナーを発表しているサブジェクトを (基本的なワイルドカード機能) デーモンに関心のあるとを一致するサブジェクトを持つメッセージは、2 つのデーモン、互いに '接続' または同一のデーモンでは実際に配信されます。</span><span class="sxs-lookup"><span data-stu-id="1d152-113">A listener announces its subjects of interest to a daemon (with a basic wildcard facility), and messages that have matching subjects are delivered to it if the two daemons are 'connected' to each other, or are indeed the same daemon.</span></span> <span data-ttu-id="1d152-114">詳細については、内のメッセージを参照してください。[で BizTalk Adapter for TIBCO Rendezvous メッセージ](../core/messages-in-biztalk-adapter-for-tibco-rendezvous.md)します。</span><span class="sxs-lookup"><span data-stu-id="1d152-114">For more information, see Messages in [Messages in BizTalk Adapter for TIBCO Rendezvous](../core/messages-in-biztalk-adapter-for-tibco-rendezvous.md).</span></span>  
  
  <span data-ttu-id="1d152-115">次の図は、BizTalk Adapter for TIBCO Rendezvous のアーキテクチャを示します。</span><span class="sxs-lookup"><span data-stu-id="1d152-115">The following figure shows the architecture for BizTalk Adapter for TIBCO Rendezvous.</span></span>  
  
  <span data-ttu-id="1d152-116">![](../core/media/tibcorend-arch.gif "TibcoRend_Arch")</span><span class="sxs-lookup"><span data-stu-id="1d152-116">![](../core/media/tibcorend-arch.gif "TibcoRend_Arch")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d152-117">参照</span><span class="sxs-lookup"><span data-stu-id="1d152-117">See Also</span></span>  
 [<span data-ttu-id="1d152-118">作業の開始</span><span class="sxs-lookup"><span data-stu-id="1d152-118">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)  
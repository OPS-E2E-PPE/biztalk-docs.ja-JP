---
title: "作成元の TIBCO Rendezvous 受信ハンドラーの |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: receive handlers
ms.assetid: 2d617a97-c165-46bb-b5a7-b66f0c1ff9f2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29146e407a65c16ed8becabf19361532a76bc9b5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-tibco-rendezvous-receive-handlers"></a><span data-ttu-id="857a8-102">TIBCO Rendezvous 受信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="857a8-102">Creating TIBCO Rendezvous Receive Handlers</span></span>
<span data-ttu-id="857a8-103">通知やイベントの作成は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] での他の呼び出しの作成と似ています。</span><span class="sxs-lookup"><span data-stu-id="857a8-103">Creating notifications or events is similar to creating other calls in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="857a8-104">ここでは、TIBCO Rendezvous メッセージを待機する受信場所を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="857a8-104">This section explains how to create a receive location to listen for TIBCO Rendezvous messages.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="857a8-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="857a8-105">In This Section</span></span>  
  
-   [<span data-ttu-id="857a8-106">TIBCO Rendezvous イベントと受信場所</span><span class="sxs-lookup"><span data-stu-id="857a8-106">TIBCO Rendezvous Events and Receive Locations</span></span>](../core/tibco-rendezvous-events-and-receive-locations.md)  
  
-   [<span data-ttu-id="857a8-107">作成する方法の受信ポート</span><span class="sxs-lookup"><span data-stu-id="857a8-107">How to Create Receive Ports</span></span>](../core/how-to-create-receive-ports.md)  
  
-   [<span data-ttu-id="857a8-108">設定の TIBCO Rendezvous 受信トランスポートのプロパティ</span><span class="sxs-lookup"><span data-stu-id="857a8-108">Setting TIBCO Rendezvous Receive Transport Properties</span></span>](../core/setting-tibco-rendezvous-receive-transport-properties.md)  
  
-   [<span data-ttu-id="857a8-109">設定する方法の TIBCO Rendezvous の受信パイプライン</span><span class="sxs-lookup"><span data-stu-id="857a8-109">How to Set Receive Pipelines for TIBCO Rendezvous</span></span>](../core/how-to-set-receive-pipelines-for-tibco-rendezvous.md)  
  
-   [<span data-ttu-id="857a8-110">使用して TIBCO Rendezvous から BizTalk Server のポートの受信</span><span class="sxs-lookup"><span data-stu-id="857a8-110">Using TIBCO Rendezvous Receive Ports from BizTalk Server</span></span>](../core/using-tibco-rendezvous-receive-ports-from-biztalk-server.md)  
  
-   [<span data-ttu-id="857a8-111">TIBCO Rendezvous から BizTalk Server を使用してメッセージを受信するには</span><span class="sxs-lookup"><span data-stu-id="857a8-111">Using BizTalk Server from TIBCO Rendezvous to Receive Messages</span></span>](../core/using-biztalk-server-from-tibco-rendezvous-to-receive-messages.md)  
  
-   [<span data-ttu-id="857a8-112">TIBCO Rendezvous のメッセージ マッピング</span><span class="sxs-lookup"><span data-stu-id="857a8-112">Message Mapping in TIBCO Rendezvous</span></span>](../core/message-mapping-in-tibco-rendezvous.md)  
  
-   [<span data-ttu-id="857a8-113">TIBCO Rendezvous でのデータ型マッピングの受信ハンドラー</span><span class="sxs-lookup"><span data-stu-id="857a8-113">Data Type Mapping for Receive Handlers in TIBCO Rendezvous</span></span>](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)  
  
-   [<span data-ttu-id="857a8-114">BizTalk Server のメッセージ コンテキスト プロパティが (受信ハンドラー)</span><span class="sxs-lookup"><span data-stu-id="857a8-114">BizTalk Server Message Context Properties (Receive Handlers)</span></span>](../core/biztalk-server-message-context-properties-receive-handlers.md)
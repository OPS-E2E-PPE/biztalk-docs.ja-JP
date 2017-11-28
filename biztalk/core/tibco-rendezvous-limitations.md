---
title: "TIBCO Rendezvous の制限事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: TIBCO Rendezvous, limitations
ms.assetid: 8e210457-2887-43f9-a249-be1daa6ee4eb
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 717188e42450d13dee92364cd9c673aaaf48eaf6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tibco-rendezvous-limitations"></a><span data-ttu-id="1e081-102">TIBCO Rendezvous の制限事項</span><span class="sxs-lookup"><span data-stu-id="1e081-102">TIBCO Rendezvous Limitations</span></span>
<span data-ttu-id="1e081-103">TIBCO Rendezvous では、フィールド名が一意であるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="1e081-103">In TIBCO Rendezvous, field name uniqueness is not guaranteed.</span></span> <span data-ttu-id="1e081-104">TIBCO Rendezvous メッセージに 2 つの同じフィールド名がある場合、生成される XML は無効になります。</span><span class="sxs-lookup"><span data-stu-id="1e081-104">If a TIBCO Rendezvous message contains two field names that are the same, the resulting XML is not valid.</span></span>  
  
 <span data-ttu-id="1e081-105">他にも次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="1e081-105">Other limitations include the following:</span></span>  
  
-   <span data-ttu-id="1e081-106">フィールドを並べ替えることはできません。</span><span class="sxs-lookup"><span data-stu-id="1e081-106">Field ordering/sorting is not provided.</span></span>  
  
-   <span data-ttu-id="1e081-107">TIBCO Rendezvous のドキュメントによると、サブジェクト名には印刷できない文字を使用できないことになっていますが、そのような文字を使用することはできます。</span><span class="sxs-lookup"><span data-stu-id="1e081-107">According to TIBCO Rendezvous documentation, non-printable characters are not used in subject names; however, it is still possible that such characters are used.</span></span> <span data-ttu-id="1e081-108">BizTalk Adapter for TIBCO Rendezvous では印刷できない文字が入ったサブジェクト名をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="1e081-108">BizTalk Adapter for TIBCO Rendezvous does not support subject names containing those characters.</span></span>  
  
-   <span data-ttu-id="1e081-109">デーモンへのセキュリティで保護された接続はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1e081-109">Secure connection to daemons is not supported.</span></span>  
  
-   <span data-ttu-id="1e081-110">カスタム データ型はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1e081-110">Custom data types are not supported.</span></span>  
  
-   <span data-ttu-id="1e081-111">認定メッセージングは送信側ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1e081-111">Certified Messaging is not supported on the transmit side.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e081-112">参照</span><span class="sxs-lookup"><span data-stu-id="1e081-112">See Also</span></span>  
 <span data-ttu-id="1e081-113">[TIBCO Rendezvous の概念](../core/tibco-rendezvous-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="1e081-113">[TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md) </span></span>  
 [<span data-ttu-id="1e081-114">作業の開始</span><span class="sxs-lookup"><span data-stu-id="1e081-114">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)
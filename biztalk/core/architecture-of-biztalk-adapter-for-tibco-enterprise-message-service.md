---
title: BizTalk Adapter for TIBCO Enterprise Message Service のアーキテクチャ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- transmit adapter
- one-way receive operations
- architecture
- one-way send operations
- receive adapter
ms.assetid: 304c7236-aacd-4761-8c33-e876b53e84ff
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88c7bc6420efb67085e4f3a05f6daf0c5dbd2feb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230282"
---
# <a name="architecture-of-biztalk-adapter-for-tibco-enterprise-message-service"></a><span data-ttu-id="9d6de-102">BizTalk Adapter for TIBCO Enterprise Message Service のアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="9d6de-102">Architecture of BizTalk Adapter for TIBCO Enterprise Message Service</span></span>
<span data-ttu-id="9d6de-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) は、TIBCO EMS システムと BizTalk Server との間でリアルタイムのビジネス データを交換する手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="9d6de-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) provides a means to exchange real-time business data between TIBCO EMS systems and BizTalk Server.</span></span> <span data-ttu-id="9d6de-104">このアダプターによって、XML アプリケーションと TIBCO EMS との対話処理が可能になります。</span><span class="sxs-lookup"><span data-stu-id="9d6de-104">The adapter enables interaction between an XML application and TIBCO EMS.</span></span>  
  
 <span data-ttu-id="9d6de-105">このアダプターは、次のいずれかを使用して、BizTalk アプリケーションが TIBCO EMS と通信できるようにする XML メッセージを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="9d6de-105">The adapter accepts XML messages that enable BizTalk applications to communicate with TIBCO EMS using one of the following:</span></span>  
  
-   <span data-ttu-id="9d6de-106">**送信アダプター**: 静的な一方向送信ポートを使用して TIBCO EMS にメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="9d6de-106">**Transmit Adapter**: Uses a static one-way send port to send a message to TIBCO EMS.</span></span>  
  
-   <span data-ttu-id="9d6de-107">**受信アダプター**: 使用して静的な一方向の受信ポートを TIBCO EMS からメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="9d6de-107">**Receive Adapter**: Uses a static one-way receive port to receive messages from TIBCO EMS.</span></span>  
  
## <a name="one-way-send-operation"></a><span data-ttu-id="9d6de-108">一方向の送信操作</span><span class="sxs-lookup"><span data-stu-id="9d6de-108">One-Way Send Operation</span></span>  
 <span data-ttu-id="9d6de-109">次の図は、BizTalk Adapter for TIBCO EMS を使用した一方向の送信操作のアーキテクチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="9d6de-109">The following figure shows the architecture of a one-way send operation using BizTalk Adapter for TIBCO EMS.</span></span>  
  
 ![](../core/media/tibcoems-architecture-send.gif "TIBCOEMS_architecture_send")  
  
## <a name="one-way-receive-operation"></a><span data-ttu-id="9d6de-110">一方向の受信操作</span><span class="sxs-lookup"><span data-stu-id="9d6de-110">One-Way Receive Operation</span></span>  
 <span data-ttu-id="9d6de-111">次の図は、BizTalk Adapter for TIBCO EMS を使用した一方向の受信操作のアーキテクチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="9d6de-111">The following figure shows the architecture for a one-way receive operation using BizTalk Adapter for TIBCO EMS.</span></span>  
  
 ![](../core/media/tibcoems-architecture-receive.gif "TIBCOEMS_architecture_receive")  
  
## <a name="see-also"></a><span data-ttu-id="9d6de-112">参照</span><span class="sxs-lookup"><span data-stu-id="9d6de-112">See Also</span></span>  
 <span data-ttu-id="9d6de-113">[アダプターの機能](../core/adapter-features.md) </span><span class="sxs-lookup"><span data-stu-id="9d6de-113">[Adapter Features](../core/adapter-features.md) </span></span>  
 [<span data-ttu-id="9d6de-114">計画とアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="9d6de-114">Planning and Architecture</span></span>](../core/planning-and-architecture16.md)
---
title: BizTalk Adapter for TIBCO Enterprise Message Service のアーキテクチャ |Microsoft Docs
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
ms.openlocfilehash: 8d1f6735ec5fee445fa5f2403f7ca48d32dfae2e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359021"
---
# <a name="architecture-of-biztalk-adapter-for-tibco-enterprise-message-service"></a><span data-ttu-id="41024-102">BizTalk Adapter for TIBCO Enterprise Message Service のアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="41024-102">Architecture of BizTalk Adapter for TIBCO Enterprise Message Service</span></span>
<span data-ttu-id="41024-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) は、TIBCO EMS システムと BizTalk Server の間のリアルタイムのビジネス データを交換する手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="41024-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) provides a means to exchange real-time business data between TIBCO EMS systems and BizTalk Server.</span></span> <span data-ttu-id="41024-104">アダプターでは、XML アプリケーションと TIBCO EMS 間操作ができます。</span><span class="sxs-lookup"><span data-stu-id="41024-104">The adapter enables interaction between an XML application and TIBCO EMS.</span></span>  
  
 <span data-ttu-id="41024-105">アダプターは、次のいずれかを使用して TIBCO EMS と通信する BizTalk アプリケーションを有効にする XML メッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="41024-105">The adapter accepts XML messages that enable BizTalk applications to communicate with TIBCO EMS using one of the following:</span></span>  
  
-   <span data-ttu-id="41024-106">**送信アダプター**:静的な一方向送信ポートを使用して、TIBCO EMS にメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="41024-106">**Transmit Adapter**: Uses a static one-way send port to send a message to TIBCO EMS.</span></span>  
  
-   <span data-ttu-id="41024-107">**受信アダプター**:TIBCO EMS からメッセージを受信ポートを受信する静的な一方向の使用されます。</span><span class="sxs-lookup"><span data-stu-id="41024-107">**Receive Adapter**: Uses a static one-way receive port to receive messages from TIBCO EMS.</span></span>  
  
## <a name="one-way-send-operation"></a><span data-ttu-id="41024-108">一方向の送信操作</span><span class="sxs-lookup"><span data-stu-id="41024-108">One-Way Send Operation</span></span>  
 <span data-ttu-id="41024-109">次の図は、BizTalk Adapter for TIBCO EMS の使用の一方向の送信操作のアーキテクチャを示します。</span><span class="sxs-lookup"><span data-stu-id="41024-109">The following figure shows the architecture of a one-way send operation using BizTalk Adapter for TIBCO EMS.</span></span>  
  
 <span data-ttu-id="41024-110">![](../core/media/tibcoems-architecture-send.gif "TIBCOEMS_architecture_send")</span><span class="sxs-lookup"><span data-stu-id="41024-110">![](../core/media/tibcoems-architecture-send.gif "TIBCOEMS_architecture_send")</span></span>  
  
## <a name="one-way-receive-operation"></a><span data-ttu-id="41024-111">一方向の受信操作</span><span class="sxs-lookup"><span data-stu-id="41024-111">One-Way Receive Operation</span></span>  
 <span data-ttu-id="41024-112">次の図は、一方向の受信操作が BizTalk Adapter for TIBCO EMS の使用のアーキテクチャを示します。</span><span class="sxs-lookup"><span data-stu-id="41024-112">The following figure shows the architecture for a one-way receive operation using BizTalk Adapter for TIBCO EMS.</span></span>  
  
 <span data-ttu-id="41024-113">![](../core/media/tibcoems-architecture-receive.gif "TIBCOEMS_architecture_receive")</span><span class="sxs-lookup"><span data-stu-id="41024-113">![](../core/media/tibcoems-architecture-receive.gif "TIBCOEMS_architecture_receive")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41024-114">参照</span><span class="sxs-lookup"><span data-stu-id="41024-114">See Also</span></span>  
 <span data-ttu-id="41024-115">[アダプターの機能](../core/adapter-features.md) </span><span class="sxs-lookup"><span data-stu-id="41024-115">[Adapter Features](../core/adapter-features.md) </span></span>  
 [<span data-ttu-id="41024-116">計画および設計</span><span class="sxs-lookup"><span data-stu-id="41024-116">Planning and Architecture</span></span>](../core/planning-and-architecture16.md)
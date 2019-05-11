---
title: MSMQ アダプターの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, configuring
- configuring [MSMQ adapters]
ms.assetid: 8f873ee1-4eaa-43d2-948d-aecc406a0bfb
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5615178f5eb5248f74b0991075e159df70c89a09
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355172"
---
# <a name="configuring-the-msmq-adapter"></a><span data-ttu-id="dd2c0-102">MSMQ アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="dd2c0-102">Configuring the MSMQ Adapter</span></span>
<span data-ttu-id="dd2c0-103">このセクションには、MSMQ アダプターの構成に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="dd2c0-103">This section includes information about configuring the MSMQ adapter.</span></span> <span data-ttu-id="dd2c0-104">受信場所と送信ポートの両方については、MSMQ アダプターを構成できます。</span><span class="sxs-lookup"><span data-stu-id="dd2c0-104">You can configure the MSMQ adapter for both receive locations and send ports.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd2c0-105">などのプロパティ シートで、特定のフィールドをクリアする**ユーザー名**と**パスワード**(値ではなく)、プロパティ名を右クリックし、クリックして**無効化**します。</span><span class="sxs-lookup"><span data-stu-id="dd2c0-105">To clear certain fields in the property sheet, such as **User Name** and **Password**, right-click the property name (not the value), and then click **Nullify**.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dd2c0-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="dd2c0-106">In This Section</span></span>  
  
-   [<span data-ttu-id="dd2c0-107">MSMQ 受信ハンドラーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="dd2c0-107">How to Configure an MSMQ Receive Handler</span></span>](../core/how-to-configure-an-msmq-receive-handler.md)  
  
-   [<span data-ttu-id="dd2c0-108">MSMQ 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="dd2c0-108">How to Configure an MSMQ Receive Location</span></span>](../core/how-to-configure-an-msmq-receive-location.md)  
  
-   [<span data-ttu-id="dd2c0-109">MSMQ 送信ハンドラーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="dd2c0-109">How to Configure an MSMQ Send Handler</span></span>](../core/how-to-configure-an-msmq-send-handler.md)  
  
-   [<span data-ttu-id="dd2c0-110">MSMQ 送信ポートを構成する方法</span><span class="sxs-lookup"><span data-stu-id="dd2c0-110">How to Configure an MSMQ Send Port</span></span>](../core/how-to-configure-an-msmq-send-port.md)  
  
-   [<span data-ttu-id="dd2c0-111">MSMQ 送信ポートを構成する方法</span><span class="sxs-lookup"><span data-stu-id="dd2c0-111">How to Configure an MSMQ Send Port</span></span>](../core/how-to-configure-an-msmq-send-port.md)  
  
-   [<span data-ttu-id="dd2c0-112">複数の MSMQ アダプターを使用して場所の受信を管理する方法</span><span class="sxs-lookup"><span data-stu-id="dd2c0-112">How to Manage Multiple Receive Locations Using the MSMQ Adapter</span></span>](../core/how-to-manage-multiple-receive-locations-using-the-msmq-adapter.md)  
  
-   [<span data-ttu-id="dd2c0-113">メッセージ キューのキュー</span><span class="sxs-lookup"><span data-stu-id="dd2c0-113">Message Queuing Queues</span></span>](../core/message-queuing-queues.md)  
  
-   [<span data-ttu-id="dd2c0-114">MSMQ アダプターのパフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="dd2c0-114">Optimizing Performance of the MSMQ Adapter</span></span>](../core/optimizing-performance-of-the-msmq-adapter.md)  
  
-   [<span data-ttu-id="dd2c0-115">MSMQ アダプターを使用したサイズの大きいメッセージの送受信</span><span class="sxs-lookup"><span data-stu-id="dd2c0-115">Sending and Receiving Large Messages Using the MSMQ Adapter</span></span>](../core/sending-and-receiving-large-messages-using-the-msmq-adapter.md)
---
title: MSMQ アダプターの構成 |Microsoft ドキュメント
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
ms.openlocfilehash: 74e2cac70171a22dad391addc81daa696e204fd6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232954"
---
# <a name="configuring-the-msmq-adapter"></a><span data-ttu-id="076c6-102">MSMQ アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="076c6-102">Configuring the MSMQ Adapter</span></span>
<span data-ttu-id="076c6-103">このセクションでは、MSMQ アダプタの構成情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="076c6-103">This section includes information about configuring the MSMQ adapter.</span></span> <span data-ttu-id="076c6-104">MSMQ アダプタは、受信場所と送信ポートの両方に構成できます。</span><span class="sxs-lookup"><span data-stu-id="076c6-104">You can configure the MSMQ adapter for both receive locations and send ports.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="076c6-105">などのプロパティ シートで、特定のフィールドをクリアする**ユーザー名**と**パスワード**(値) ではなくプロパティ名を右クリックし、クリックして**無効化**です。</span><span class="sxs-lookup"><span data-stu-id="076c6-105">To clear certain fields in the property sheet, such as **User Name** and **Password**, right-click the property name (not the value), and then click **Nullify**.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="076c6-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="076c6-106">In This Section</span></span>  
  
-   [<span data-ttu-id="076c6-107">MSMQ 受信ハンドラーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="076c6-107">How to Configure an MSMQ Receive Handler</span></span>](../core/how-to-configure-an-msmq-receive-handler.md)  
  
-   [<span data-ttu-id="076c6-108">MSMQ 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="076c6-108">How to Configure an MSMQ Receive Location</span></span>](../core/how-to-configure-an-msmq-receive-location.md)  
  
-   [<span data-ttu-id="076c6-109">MSMQ 送信ハンドラーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="076c6-109">How to Configure an MSMQ Send Handler</span></span>](../core/how-to-configure-an-msmq-send-handler.md)  
  
-   [<span data-ttu-id="076c6-110">MSMQ 送信ポートを構成する方法</span><span class="sxs-lookup"><span data-stu-id="076c6-110">How to Configure an MSMQ Send Port</span></span>](../core/how-to-configure-an-msmq-send-port.md)  
  
-   [<span data-ttu-id="076c6-111">MSMQ 送信ポートを構成する方法</span><span class="sxs-lookup"><span data-stu-id="076c6-111">How to Configure an MSMQ Send Port</span></span>](../core/how-to-configure-an-msmq-send-port.md)  
  
-   [<span data-ttu-id="076c6-112">複数の受信、MSMQ アダプタを使用して場所を管理する方法</span><span class="sxs-lookup"><span data-stu-id="076c6-112">How to Manage Multiple Receive Locations Using the MSMQ Adapter</span></span>](../core/how-to-manage-multiple-receive-locations-using-the-msmq-adapter.md)  
  
-   [<span data-ttu-id="076c6-113">メッセージ キューのキュー</span><span class="sxs-lookup"><span data-stu-id="076c6-113">Message Queuing Queues</span></span>](../core/message-queuing-queues.md)  
  
-   [<span data-ttu-id="076c6-114">MSMQ アダプターのパフォーマンスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="076c6-114">Optimizing Performance of the MSMQ Adapter</span></span>](../core/optimizing-performance-of-the-msmq-adapter.md)  
  
-   [<span data-ttu-id="076c6-115">MSMQ アダプターを使用してサイズの大きいメッセージを送受信します。</span><span class="sxs-lookup"><span data-stu-id="076c6-115">Sending and Receiving Large Messages Using the MSMQ Adapter</span></span>](../core/sending-and-receiving-large-messages-using-the-msmq-adapter.md)
---
title: SAP アダプターを物理ポートのバインドを手動で構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, sending messages to the SAP system
- physical port binding, manually configuring
- deploying, receiving messages from the SAP system
ms.assetid: c4f547aa-5514-4ca9-809b-d8d395de419c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3011bea808e59ec0ee80f3ac030937a9987d9233
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373247"
---
# <a name="manually-configure-a-physical-port-binding-to-the-sap-adapter"></a><span data-ttu-id="aa614-102">SAP アダプターを物理ポートのバインドを手動で構成します。</span><span class="sxs-lookup"><span data-stu-id="aa614-102">Manually configure a physical port binding to the SAP adapter</span></span>
<span data-ttu-id="aa614-103">構成、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]を使用して WCF カスタム バインドとして、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="aa614-103">Configure the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] as a WCF custom binding by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> 

## <a name="port-overview"></a><span data-ttu-id="aa614-104">ポートの概要</span><span class="sxs-lookup"><span data-stu-id="aa614-104">Port overview</span></span>
<span data-ttu-id="aa614-105">アダプタの展開後にすることを使用しての SAP システムからメッセージを送受信、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="aa614-105">After deploying the adapter, you will be able to send and receive messages from the SAP system by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="aa614-106">アダプターを展開する手順は、に応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="aa614-106">The steps for deploying the adapter vary depending on:</span></span>  
  
- <span data-ttu-id="aa614-107">間の通信の方向[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="aa614-107">The direction of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="aa614-108">送信、受信を構成することができます送信と受信、または受信送信ポート。</span><span class="sxs-lookup"><span data-stu-id="aa614-108">You may choose to configure a Send, Receive, Send-Receive, or a Receive-Send port.</span></span> <span data-ttu-id="aa614-109">選択項目は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="aa614-109">Your choices are summarized in the following table:</span></span>  
  
  |<span data-ttu-id="aa614-110">ポートの方向</span><span class="sxs-lookup"><span data-stu-id="aa614-110">Port direction</span></span>|<span data-ttu-id="aa614-111">通信方式</span><span class="sxs-lookup"><span data-stu-id="aa614-111">Communication pattern</span></span>|<span data-ttu-id="aa614-112">選択する通信の方向</span><span class="sxs-lookup"><span data-stu-id="aa614-112">Direction of communication to choose from</span></span>|  
  |---|---|---|  
  |<span data-ttu-id="aa614-113">Send</span><span class="sxs-lookup"><span data-stu-id="aa614-113">Send</span></span>|<span data-ttu-id="aa614-114">一方向</span><span class="sxs-lookup"><span data-stu-id="aa614-114">One-way</span></span>|<span data-ttu-id="aa614-115">常にこのポートでメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="aa614-115">I will always be sending messages on this port.</span></span>|  
  |<span data-ttu-id="aa614-116">Receive</span><span class="sxs-lookup"><span data-stu-id="aa614-116">Receive</span></span>|<span data-ttu-id="aa614-117">一方向</span><span class="sxs-lookup"><span data-stu-id="aa614-117">One-way</span></span>|<span data-ttu-id="aa614-118">常にこのポートでメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="aa614-118">I will always be receiving messages on this port.</span></span>|  
  |<span data-ttu-id="aa614-119">送信 - 受信</span><span class="sxs-lookup"><span data-stu-id="aa614-119">Send-Receive</span></span>|<span data-ttu-id="aa614-120">要求 - 応答</span><span class="sxs-lookup"><span data-stu-id="aa614-120">Request-response</span></span>|<span data-ttu-id="aa614-121">要求の送信と応答の受信をされます。</span><span class="sxs-lookup"><span data-stu-id="aa614-121">I will be sending a request and receiving a response.</span></span>|  
  |<span data-ttu-id="aa614-122">受信 - 送信</span><span class="sxs-lookup"><span data-stu-id="aa614-122">Receive-Send</span></span>|<span data-ttu-id="aa614-123">送信請求 - 応答送信アダプター</span><span class="sxs-lookup"><span data-stu-id="aa614-123">Solicit-response</span></span>|<span data-ttu-id="aa614-124">要求の受信と応答の送信を行います。</span><span class="sxs-lookup"><span data-stu-id="aa614-124">I will be receiving a request and sending a response.</span></span>|  
  
   <span data-ttu-id="aa614-125">詳細については、次を参照してください。[送信ポートを作成](../../core/how-to-create-a-send-port2.md)、または[受信ポートを作成](../../core/how-to-create-a-receive-port.md)です。</span><span class="sxs-lookup"><span data-stu-id="aa614-125">For more information, see [Create a Send Port](../../core/how-to-create-a-send-port2.md), or [Create a Receive Port](../../core/how-to-create-a-receive-port.md).</span></span>
  
- <span data-ttu-id="aa614-126">かどうか、アダプターは、SAP システムにメッセージを送信または SAP システムからメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="aa614-126">Whether the adapter sends messages to the SAP system or receives messages from the SAP system.</span></span> <span data-ttu-id="aa614-127">によって送信またはメッセージを受信するかどうかを作成、送信または受信ポートします。</span><span class="sxs-lookup"><span data-stu-id="aa614-127">Depending on whether you want to send or receive messages, you will create a send or receive port.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="aa614-128">構成、送信またはによって作成されるバインド構成ファイルをインポートしてポートを受信することができますも、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]メタデータの生成の一部として。</span><span class="sxs-lookup"><span data-stu-id="aa614-128">You can also configure the send or receive ports by importing a binding configuration file that is created by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] as part of metadata generation.</span></span> <span data-ttu-id="aa614-129">このバインド ファイルを使用してポートを構成する方法の詳細については、次を参照してください。 [sap ポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)します。</span><span class="sxs-lookup"><span data-stu-id="aa614-129">For instructions on configuring ports using this binding file, see [Configure a physical port binding using a port binding file to SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="aa614-130">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="aa614-130">In this section</span></span>  
  
-   [<span data-ttu-id="aa614-131">Wcf-custom アダプターと Oracle データベース アダプターを使用してポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="aa614-131">Configure a port using the WCF-custom adapter and Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/configure-a-port-using-the-wcf-custom-adapter-and-oracle-database-adapter.md)  
  
-   [<span data-ttu-id="aa614-132">WCF-SAP アダプターを使用してポートを構成する</span><span class="sxs-lookup"><span data-stu-id="aa614-132">Configure a port using the WCF-SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/configure-a-port-using-the-wcf-sap-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="aa614-133">参照</span><span class="sxs-lookup"><span data-stu-id="aa614-133">See Also</span></span>  
[<span data-ttu-id="aa614-134">SAP アプリケーションを作成するための構成要素</span><span class="sxs-lookup"><span data-stu-id="aa614-134">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)
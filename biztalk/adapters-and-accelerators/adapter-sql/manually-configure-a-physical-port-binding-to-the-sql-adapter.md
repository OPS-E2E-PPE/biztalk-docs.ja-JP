---
title: SQL アダプターを物理ポートのバインドを手動で構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d3f0bb78-c85f-4629-9e2d-cce180ff78ae
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7a9fb7a1390a59c564063f889a86096d2989d55
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979971"
---
# <a name="manually-configure-a-physical-port-binding-to-the-sql-adapter"></a><span data-ttu-id="2fbc0-102">SQL アダプターを物理ポートのバインドを手動で構成します。</span><span class="sxs-lookup"><span data-stu-id="2fbc0-102">Manually configure a physical port binding to the SQL adapter</span></span>
<span data-ttu-id="2fbc0-103">このセクションでは、構成に関する情報を提供、 [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] WCF カスタム バインドとして、またはを使用して WCF SQL ポートとして、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="2fbc0-103">This section provides information about configuring the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] as a WCF custom binding or as a WCF-SQL port by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="2fbc0-104">アダプタの展開後にすることを使用しての SQL Server からメッセージを送受信、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="2fbc0-104">After deploying the adapter, you will be able to send and receive messages from SQL Server by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="2fbc0-105">アダプターを展開する手順は、に応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="2fbc0-105">The steps for deploying the adapter vary depending on:</span></span>  
  
- <span data-ttu-id="2fbc0-106">間の通信の方向[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="2fbc0-106">The direction of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="2fbc0-107">受信、送信を構成することができます、または送信の受信ポート。</span><span class="sxs-lookup"><span data-stu-id="2fbc0-107">You may choose to configure a send, receive, or a send-receive port.</span></span> <span data-ttu-id="2fbc0-108">選択内容は、次の表にまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="2fbc0-108">Your choices are summarized in the following table.</span></span>  
  
  |<span data-ttu-id="2fbc0-109">ポートの方向</span><span class="sxs-lookup"><span data-stu-id="2fbc0-109">Port direction</span></span>|<span data-ttu-id="2fbc0-110">通信方式</span><span class="sxs-lookup"><span data-stu-id="2fbc0-110">Communication pattern</span></span>|<span data-ttu-id="2fbc0-111">選択する通信の方向</span><span class="sxs-lookup"><span data-stu-id="2fbc0-111">Direction of communication to choose from</span></span>|  
  |--------------------|---------------------------|-----------------------------------------------|  
  |<span data-ttu-id="2fbc0-112">Send</span><span class="sxs-lookup"><span data-stu-id="2fbc0-112">Send</span></span>|<span data-ttu-id="2fbc0-113">一方向</span><span class="sxs-lookup"><span data-stu-id="2fbc0-113">One-way</span></span>|<span data-ttu-id="2fbc0-114">常にこのポートでメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="2fbc0-114">I will always be sending messages on this port.</span></span>|  
  |<span data-ttu-id="2fbc0-115">Receive</span><span class="sxs-lookup"><span data-stu-id="2fbc0-115">Receive</span></span>|<span data-ttu-id="2fbc0-116">一方向</span><span class="sxs-lookup"><span data-stu-id="2fbc0-116">One-way</span></span>|<span data-ttu-id="2fbc0-117">常にこのポートでメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="2fbc0-117">I will always be receiving messages on this port.</span></span>|  
  |<span data-ttu-id="2fbc0-118">送受信</span><span class="sxs-lookup"><span data-stu-id="2fbc0-118">Send-receive</span></span>|<span data-ttu-id="2fbc0-119">要求 - 応答</span><span class="sxs-lookup"><span data-stu-id="2fbc0-119">Request-response</span></span>|<span data-ttu-id="2fbc0-120">要求の送信と応答の受信をされます。</span><span class="sxs-lookup"><span data-stu-id="2fbc0-120">I will be sending a request and receiving a response.</span></span>|  
  
  > [!NOTE]
  >  <span data-ttu-id="2fbc0-121">双方向受信ポートでサポートされていない、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="2fbc0-121">Two-way receive ports are not supported by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
   <span data-ttu-id="2fbc0-122">詳細については、次を参照してください。[送信ポートを作成する方法](../../core/how-to-create-a-send-port2.md)、または[受信ポートを作成する方法](../../core/how-to-create-a-receive-port.md)します。</span><span class="sxs-lookup"><span data-stu-id="2fbc0-122">For more information, see [How to Create a Send Port](../../core/how-to-create-a-send-port2.md), or [How to Create a Receive Port](../../core/how-to-create-a-receive-port.md).</span></span> 
  
- <span data-ttu-id="2fbc0-123">かどうか、アダプターでは、SQL Server (送信操作) にメッセージを送信または、(受信操作) の SQL Server からメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="2fbc0-123">Whether the adapter sends messages to the SQL Server (outbound operations) or receives messages from SQL Server (inbound operations).</span></span> <span data-ttu-id="2fbc0-124">によって送信またはメッセージを受信するかどうかを作成、送信または受信ポート、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="2fbc0-124">Depending on whether you want to send or receive messages, you will create a send or receive port, respectively.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="2fbc0-125">構成、送信またはによって作成されるバインド構成ファイルをインポートしてポートを受信することができますも、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]メタデータの生成の一部として。</span><span class="sxs-lookup"><span data-stu-id="2fbc0-125">You can also configure the send or receive ports by importing a binding configuration file that is created by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] as part of metadata generation.</span></span> <span data-ttu-id="2fbc0-126">このバインド ファイルを使用してポートを構成する方法の詳細については、次を参照してください。 [SQL アダプターを使用するポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="2fbc0-126">For instructions on configuring ports using this binding file, see [Configure a physical port binding using a port binding file to use the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="2fbc0-127">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2fbc0-127">In This Section</span></span>  
  
-   [<span data-ttu-id="2fbc0-128">Wcf-custom アダプタと SQL アダプタを使用してポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="2fbc0-128">Configure a port using the WCF-custom adapter and SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter.md)  
  
-   [<span data-ttu-id="2fbc0-129">WCF-SQL アダプターを使用してポートを構成する</span><span class="sxs-lookup"><span data-stu-id="2fbc0-129">Configure a port using the WCF-SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-sql-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="2fbc0-130">参照</span><span class="sxs-lookup"><span data-stu-id="2fbc0-130">See Also</span></span>  
[<span data-ttu-id="2fbc0-131">SQL アダプターを使用した BizTalk アプリケーションを開発する構成要素</span><span class="sxs-lookup"><span data-stu-id="2fbc0-131">Building blocks to develop BizTalk applications with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)
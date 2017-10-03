---
title: "SQL アダプターを物理ポートのバインドを手動で構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d3f0bb78-c85f-4629-9e2d-cce180ff78ae
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac72d914539eabc9b129985c2b9335270e561d18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="manually-configure-a-physical-port-binding-to-the-sql-adapter"></a><span data-ttu-id="623a4-102">SQL アダプターを物理ポートのバインドを手動で構成します。</span><span class="sxs-lookup"><span data-stu-id="623a4-102">Manually configure a physical port binding to the SQL adapter</span></span>
<span data-ttu-id="623a4-103">このセクションの構成に関する情報を提供する、 [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] WCF カスタム バインドとして、またはを使用して WCF SQL ポートとして、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="623a4-103">This section provides information about configuring the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] as a WCF custom binding or as a WCF-SQL port by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="623a4-104">アダプターを展開したらことができますを使用しての SQL Server からメッセージを送受信する、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="623a4-104">After deploying the adapter, you will be able to send and receive messages from SQL Server by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="623a4-105">アダプタの展開の手順が異なります。</span><span class="sxs-lookup"><span data-stu-id="623a4-105">The steps for deploying the adapter vary depending on:</span></span>  
  
-   <span data-ttu-id="623a4-106">間の通信の方向[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="623a4-106">The direction of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="623a4-107">[受信] の送信を構成することもできますまたは送受信ポートです。</span><span class="sxs-lookup"><span data-stu-id="623a4-107">You may choose to configure a send, receive, or a send-receive port.</span></span> <span data-ttu-id="623a4-108">選択した内容は、次の表にまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="623a4-108">Your choices are summarized in the following table.</span></span>  
  
    |<span data-ttu-id="623a4-109">ポートの方向</span><span class="sxs-lookup"><span data-stu-id="623a4-109">Port direction</span></span>|<span data-ttu-id="623a4-110">通信方式</span><span class="sxs-lookup"><span data-stu-id="623a4-110">Communication pattern</span></span>|<span data-ttu-id="623a4-111">選択への通信方向</span><span class="sxs-lookup"><span data-stu-id="623a4-111">Direction of communication to choose from</span></span>|  
    |--------------------|---------------------------|-----------------------------------------------|  
    |<span data-ttu-id="623a4-112">Send</span><span class="sxs-lookup"><span data-stu-id="623a4-112">Send</span></span>|<span data-ttu-id="623a4-113">一方向</span><span class="sxs-lookup"><span data-stu-id="623a4-113">One-way</span></span>|<span data-ttu-id="623a4-114">常にこのポートでメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="623a4-114">I will always be sending messages on this port.</span></span>|  
    |<span data-ttu-id="623a4-115">Receive</span><span class="sxs-lookup"><span data-stu-id="623a4-115">Receive</span></span>|<span data-ttu-id="623a4-116">一方向</span><span class="sxs-lookup"><span data-stu-id="623a4-116">One-way</span></span>|<span data-ttu-id="623a4-117">常にこのポートでメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="623a4-117">I will always be receiving messages on this port.</span></span>|  
    |<span data-ttu-id="623a4-118">送受信</span><span class="sxs-lookup"><span data-stu-id="623a4-118">Send-receive</span></span>|<span data-ttu-id="623a4-119">要求 - 応答</span><span class="sxs-lookup"><span data-stu-id="623a4-119">Request-response</span></span>|<span data-ttu-id="623a4-120">要求の送信と応答の受信をされます。</span><span class="sxs-lookup"><span data-stu-id="623a4-120">I will be sending a request and receiving a response.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="623a4-121">双方向受信ポートでサポートされていない、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="623a4-121">Two-way receive ports are not supported by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
     <span data-ttu-id="623a4-122">詳細については、次を参照してください。[送信ポートを作成する方法](../../core/how-to-create-a-send-port2.md)、または[受信ポートを作成する方法](../../core/how-to-create-a-receive-port.md)です。</span><span class="sxs-lookup"><span data-stu-id="623a4-122">For more information, see [How to Create a Send Port](../../core/how-to-create-a-send-port2.md), or [How to Create a Receive Port](../../core/how-to-create-a-receive-port.md).</span></span> 
  
-   <span data-ttu-id="623a4-123">かどうか、アダプターは、SQL Server (送信操作) にメッセージを送信または SQL Server (入力方向の操作) からメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="623a4-123">Whether the adapter sends messages to the SQL Server (outbound operations) or receives messages from SQL Server (inbound operations).</span></span> <span data-ttu-id="623a4-124">送信またはメッセージを受信するかどうかは、によってを作成、送信または受信ポートをそれぞれします。</span><span class="sxs-lookup"><span data-stu-id="623a4-124">Depending on whether you want to send or receive messages, you will create a send or receive port, respectively.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="623a4-125">また、送信構成またはによって作成されるバインディングの構成ファイルをインポートしてポートを受信する、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]メタデータの生成の一部として。</span><span class="sxs-lookup"><span data-stu-id="623a4-125">You can also configure the send or receive ports by importing a binding configuration file that is created by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] as part of metadata generation.</span></span> <span data-ttu-id="623a4-126">このバインド ファイルを使用するポートを構成する方法の詳細については、次を参照してください。 [SQL アダプターを使用するポートのバインド ファイルを使用する物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="623a4-126">For instructions on configuring ports using this binding file, see [Configure a physical port binding using a port binding file to use the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="623a4-127">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="623a4-127">In This Section</span></span>  
  
-   [<span data-ttu-id="623a4-128">Wcf-custom アダプタと SQL アダプタを使用してポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="623a4-128">Configure a port using the WCF-custom adapter and SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter.md)  
  
-   [<span data-ttu-id="623a4-129">WCF-SQL アダプターを使用してポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="623a4-129">Configure a port using the WCF-SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-sql-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="623a4-130">参照</span><span class="sxs-lookup"><span data-stu-id="623a4-130">See Also</span></span>  
[<span data-ttu-id="623a4-131">SQL アダプタを BizTalk アプリケーションを開発する構成要素</span><span class="sxs-lookup"><span data-stu-id="623a4-131">Building blocks to develop BizTalk applications with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)
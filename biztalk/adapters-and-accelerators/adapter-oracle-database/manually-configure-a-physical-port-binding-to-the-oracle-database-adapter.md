---
title: "Oracle データベース アダプターを物理ポートのバインドを手動で構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, sending to an Oracle database
- messages, receiving from an Oracle database
- physical port binding, manually configuring
ms.assetid: 6b118236-e9eb-494e-96b2-969c7064943d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2a64223485cf83fb214055cb1e11b44fb6bc7c4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="manually-configure-a-physical-port-binding-to-the-oracle-database-adapter"></a><span data-ttu-id="972e9-102">Oracle データベース アダプターを物理ポートのバインドを手動で構成します。</span><span class="sxs-lookup"><span data-stu-id="972e9-102">Manually configure a physical port binding to the Oracle Database Adapter</span></span>
<span data-ttu-id="972e9-103">このセクションの構成に関する情報を提供する、 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Wcf-oracledb バインディングを使用して、WCF カスタム バインドとして、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="972e9-103">This section provides information about configuring the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] as a WCF-Custom binding or WCF-OracleDB binding by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="972e9-104">アダプターを展開したらことができますを使用しての Oracle データベースからメッセージを送受信する、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="972e9-104">After deploying the adapter, you will be able to send and receive messages from the Oracle database by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="972e9-105">アダプタの展開の手順が異なります。</span><span class="sxs-lookup"><span data-stu-id="972e9-105">The steps for deploying the adapter vary depending on:</span></span>  
  
-   <span data-ttu-id="972e9-106">BizTalk Server の間の通信の方向と[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="972e9-106">The direction of communication between BizTalk Server and [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="972e9-107">送信、受信、送信と受信ポートまたは受信と送信ポートを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="972e9-107">You may choose to configure a send, receive, send-receive, or a receive-send port.</span></span> <span data-ttu-id="972e9-108">選択した内容は、次の表にまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="972e9-108">Your choices are summarized in the following table.</span></span>  
  
    |<span data-ttu-id="972e9-109">ポートの方向</span><span class="sxs-lookup"><span data-stu-id="972e9-109">Port direction</span></span>|<span data-ttu-id="972e9-110">通信方式</span><span class="sxs-lookup"><span data-stu-id="972e9-110">Communication pattern</span></span>|<span data-ttu-id="972e9-111">選択への通信方向</span><span class="sxs-lookup"><span data-stu-id="972e9-111">Direction of communication to choose from</span></span>|  
    |--------------------|---------------------------|-----------------------------------------------|  
    |<span data-ttu-id="972e9-112">Send</span><span class="sxs-lookup"><span data-stu-id="972e9-112">Send</span></span>|<span data-ttu-id="972e9-113">一方向</span><span class="sxs-lookup"><span data-stu-id="972e9-113">One-way</span></span>|<span data-ttu-id="972e9-114">常にこのポートでメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="972e9-114">I will always be sending messages on this port.</span></span>|  
    |<span data-ttu-id="972e9-115">Receive</span><span class="sxs-lookup"><span data-stu-id="972e9-115">Receive</span></span>|<span data-ttu-id="972e9-116">一方向</span><span class="sxs-lookup"><span data-stu-id="972e9-116">One-way</span></span>|<span data-ttu-id="972e9-117">常にこのポートでメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="972e9-117">I will always be receiving messages on this port.</span></span>|  
    |<span data-ttu-id="972e9-118">送受信</span><span class="sxs-lookup"><span data-stu-id="972e9-118">Send-receive</span></span>|<span data-ttu-id="972e9-119">要求 - 応答</span><span class="sxs-lookup"><span data-stu-id="972e9-119">Request-response</span></span>|<span data-ttu-id="972e9-120">要求の送信と応答の受信をされます。</span><span class="sxs-lookup"><span data-stu-id="972e9-120">I will be sending a request and receiving a response.</span></span>|  
    |<span data-ttu-id="972e9-121">受信送信</span><span class="sxs-lookup"><span data-stu-id="972e9-121">Receive-send</span></span>|<span data-ttu-id="972e9-122">送信請求 - 応答送信アダプター</span><span class="sxs-lookup"><span data-stu-id="972e9-122">Solicit-response</span></span>|<span data-ttu-id="972e9-123">要求の受信と応答の送信を行います。</span><span class="sxs-lookup"><span data-stu-id="972e9-123">I will be receiving a request and sending a response.</span></span>|  
  
     <span data-ttu-id="972e9-124">詳細については、次を参照してください。[送信ポートを作成](../../core/how-to-create-a-send-port2.md)、または[受信ポートを作成](../../core/how-to-create-a-receive-port.md)です。</span><span class="sxs-lookup"><span data-stu-id="972e9-124">For more information, see [Create a Send Port](../../core/how-to-create-a-send-port2.md), or [Create a Receive Port](../../core/how-to-create-a-receive-port.md).</span></span> 
  
-   <span data-ttu-id="972e9-125">かどうか、アダプターは、Oracle データベースにメッセージを送信または Oracle データベースからメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="972e9-125">Whether the adapter sends messages to the Oracle database or receives messages from the Oracle database.</span></span> <span data-ttu-id="972e9-126">送信またはメッセージを受信するかどうかは、によってを作成、送信または受信ポートをそれぞれします。</span><span class="sxs-lookup"><span data-stu-id="972e9-126">Depending on whether you want to send or receive messages, you will create a send or receive port, respectively.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="972e9-127">また、送信構成またはによって作成されるバインディングの構成ファイルをインポートしてポートを受信する、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]メタデータの生成の一部として。</span><span class="sxs-lookup"><span data-stu-id="972e9-127">You can also configure the send or receive ports by importing a binding configuration file that is created by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] as part of metadata generation.</span></span> <span data-ttu-id="972e9-128">このバインド ファイルを使用するポートを構成する方法の詳細については、次を参照してください。 [Oracle データベースへのポートのバインド ファイルを使用して物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)です。</span><span class="sxs-lookup"><span data-stu-id="972e9-128">For instructions on configuring ports using this binding file, see [Configure a physical port binding using a port binding file to Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md).</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="972e9-129">参照</span><span class="sxs-lookup"><span data-stu-id="972e9-129">See Also</span></span>  
[<span data-ttu-id="972e9-130">BizTalk アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="972e9-130">Develop your BizTalk applications</span></span>](../../core/develop-your-biztalk-applications.md)
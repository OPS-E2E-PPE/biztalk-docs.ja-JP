---
title: Oracle E-business アダプターを物理ポートのバインドを手動で構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 07369428-7b54-4d90-8c63-ba14e67fdbdd
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24ea54009ba97732cbcf6f248127b078c1c9ed05
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216418"
---
# <a name="manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter"></a><span data-ttu-id="d0eca-102">Oracle E-business アダプターを物理ポートのバインドを手動で構成します。</span><span class="sxs-lookup"><span data-stu-id="d0eca-102">Manually configure a physical port binding to the Oracle E-Business adapter</span></span>
<span data-ttu-id="d0eca-103">このセクションの構成に関する情報を提供する、 [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] WCF カスタム バインドとして、またはを使用して Wcf-oracleebs ポートとして、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="d0eca-103">This section provides information about configuring the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] as a WCF custom binding or as a WCF-OracleEBS port by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="d0eca-104">アダプターを展開したらことができますを使用しての Oracle E-business Suite からメッセージを送受信する、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="d0eca-104">After deploying the adapter, you will be able to send and receive messages from Oracle E-Business Suite by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="d0eca-105">アダプタの展開の手順が異なります。</span><span class="sxs-lookup"><span data-stu-id="d0eca-105">The steps for deploying the adapter vary depending on:</span></span>  
  
-   <span data-ttu-id="d0eca-106">間の通信の方向[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="d0eca-106">The direction of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="d0eca-107">送信、受信、送信と受信ポートまたは受信と送信ポートを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="d0eca-107">You may choose to configure a send, receive, send-receive, or a receive-send port.</span></span> <span data-ttu-id="d0eca-108">選択した内容は、次の表にまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="d0eca-108">Your choices are summarized in the following table.</span></span>  
  
    |<span data-ttu-id="d0eca-109">ポートの方向</span><span class="sxs-lookup"><span data-stu-id="d0eca-109">Port direction</span></span>|<span data-ttu-id="d0eca-110">通信方式</span><span class="sxs-lookup"><span data-stu-id="d0eca-110">Communication pattern</span></span>|<span data-ttu-id="d0eca-111">選択への通信方向</span><span class="sxs-lookup"><span data-stu-id="d0eca-111">Direction of communication to choose from</span></span>|  
    |--------------------|---------------------------|-----------------------------------------------|  
    |<span data-ttu-id="d0eca-112">Send</span><span class="sxs-lookup"><span data-stu-id="d0eca-112">Send</span></span>|<span data-ttu-id="d0eca-113">一方向</span><span class="sxs-lookup"><span data-stu-id="d0eca-113">One-way</span></span>|<span data-ttu-id="d0eca-114">常にこのポートでメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="d0eca-114">I will always be sending messages on this port.</span></span>|  
    |<span data-ttu-id="d0eca-115">Receive</span><span class="sxs-lookup"><span data-stu-id="d0eca-115">Receive</span></span>|<span data-ttu-id="d0eca-116">一方向</span><span class="sxs-lookup"><span data-stu-id="d0eca-116">One-way</span></span>|<span data-ttu-id="d0eca-117">常にこのポートでメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="d0eca-117">I will always be receiving messages on this port.</span></span>|  
    |<span data-ttu-id="d0eca-118">送受信</span><span class="sxs-lookup"><span data-stu-id="d0eca-118">Send-receive</span></span>|<span data-ttu-id="d0eca-119">要求 - 応答</span><span class="sxs-lookup"><span data-stu-id="d0eca-119">Request-response</span></span>|<span data-ttu-id="d0eca-120">要求の送信と応答の受信をされます。</span><span class="sxs-lookup"><span data-stu-id="d0eca-120">I will be sending a request and receiving a response.</span></span>|  
    |<span data-ttu-id="d0eca-121">受信送信</span><span class="sxs-lookup"><span data-stu-id="d0eca-121">Receive-send</span></span>|<span data-ttu-id="d0eca-122">送信請求 - 応答送信アダプター</span><span class="sxs-lookup"><span data-stu-id="d0eca-122">Solicit-response</span></span>|<span data-ttu-id="d0eca-123">要求の受信と応答の送信を行います。</span><span class="sxs-lookup"><span data-stu-id="d0eca-123">I will be receiving a request and sending a response.</span></span>|  
  
     <span data-ttu-id="d0eca-124">詳細については、次を参照してください。、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ヘルプ ドキュメントで[http://go.microsoft.com/fwlink/?LinkID=101130](http://go.microsoft.com/fwlink/?LinkID=101130)です。</span><span class="sxs-lookup"><span data-stu-id="d0eca-124">For more information, see the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Help documentation at [http://go.microsoft.com/fwlink/?LinkID=101130](http://go.microsoft.com/fwlink/?LinkID=101130).</span></span>  
  
-   <span data-ttu-id="d0eca-125">アダプターが送信するかどうかへのメッセージまたは Oracle E-business Suite からメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="d0eca-125">Whether the adapter sends messages to or receives messages from Oracle E-Business Suite.</span></span> <span data-ttu-id="d0eca-126">送信またはメッセージを受信するかどうかは、によってを作成、送信または受信ポートをそれぞれします。</span><span class="sxs-lookup"><span data-stu-id="d0eca-126">Depending on whether you want to send or receive messages, you will create a send or receive port, respectively.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d0eca-127">また、送信構成またはによって作成されるバインディングの構成ファイルをインポートしてポートを受信する、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]メタデータの生成の一部として。</span><span class="sxs-lookup"><span data-stu-id="d0eca-127">You can also configure the send or receive ports by importing a binding configuration file that is created by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] as part of metadata generation.</span></span> <span data-ttu-id="d0eca-128">このバインド ファイルを使用するポートを構成する方法の詳細については、次を参照してください。 [Oracle E-business Suite にポートのバインド ファイルを、物理ポートを使用してバインディングを構成](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)です。</span><span class="sxs-lookup"><span data-stu-id="d0eca-128">For instructions on configuring ports using this binding file, see [Configure a Physical Port Binding Using a Port Binding File to Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d0eca-129">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d0eca-129">In This Section</span></span>  
  
-   [<span data-ttu-id="d0eca-130">Wcf-custom アダプターおよび Oracle E-business Suite を使用してポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="d0eca-130">Configuring a Port Using the WCF-Custom Adapter and Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-port-using-the-wcf-custom-adapter-and-oracle-e-business-suite.md)  
  
-   [<span data-ttu-id="d0eca-131">Wcf-oracleebs アダプターを使用して、ポートの構成</span><span class="sxs-lookup"><span data-stu-id="d0eca-131">Configuring a Port Using the WCF-OracleEBS Adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-port-using-the-wcf-oracleebs-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="d0eca-132">参照</span><span class="sxs-lookup"><span data-stu-id="d0eca-132">See Also</span></span>  
 [<span data-ttu-id="d0eca-133">Oracle E-business Suite アプリケーションを作成する構成要素</span><span class="sxs-lookup"><span data-stu-id="d0eca-133">Building blocks to create Oracle E-Business Suite applications</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)
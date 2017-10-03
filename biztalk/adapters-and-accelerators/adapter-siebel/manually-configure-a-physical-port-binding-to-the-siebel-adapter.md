---
title: "Siebel アダプターを物理ポートのバインドを手動で構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- physical port binding, manually configuring
- how to, manually configure adapters for sending messages to a Siebel system
ms.assetid: a1445b8a-440f-45e8-96e9-a13142ca87c6
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed94ca9f6a44919684d36a1be931cbb33f746377
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="manually-configure-a-physical-port-binding-to-the-siebel-adapter"></a><span data-ttu-id="f523a-102">Siebel アダプターを物理ポートのバインドを手動で構成します。</span><span class="sxs-lookup"><span data-stu-id="f523a-102">Manually configure a physical port binding to the Siebel adapter</span></span>
<span data-ttu-id="f523a-103">このセクションの構成に関する情報を提供する、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]を使用して WCF カスタム バインドとして、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="f523a-103">This section provides information about configuring the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] as a WCF custom binding by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="f523a-104">アダプターを展開したらことができますを使用しての Siebel システムからメッセージを送受信する、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="f523a-104">After deploying the adapter, you will be able to send and receive messages from the Siebel system by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="f523a-105">アダプタの展開の手順の間の通信の方向によって異なる[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="f523a-105">The steps for deploying the adapter vary depending on the direction of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="f523a-106">送信ポートまたは送信受信ポートを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="f523a-106">You may choose to configure a Send or a Send-Receive port.</span></span> <span data-ttu-id="f523a-107">選択項目は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f523a-107">Your choices are summarized in the following table:</span></span>  
  
|<span data-ttu-id="f523a-108">ポートの方向</span><span class="sxs-lookup"><span data-stu-id="f523a-108">Port direction</span></span>|<span data-ttu-id="f523a-109">通信方式</span><span class="sxs-lookup"><span data-stu-id="f523a-109">Communication pattern</span></span>|<span data-ttu-id="f523a-110">選択への通信方向</span><span class="sxs-lookup"><span data-stu-id="f523a-110">Direction of communication to choose from</span></span>|  
|---|---|---|  
|<span data-ttu-id="f523a-111">Send</span><span class="sxs-lookup"><span data-stu-id="f523a-111">Send</span></span>|<span data-ttu-id="f523a-112">一方向</span><span class="sxs-lookup"><span data-stu-id="f523a-112">One-way</span></span>|<span data-ttu-id="f523a-113">常にこのポートでメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="f523a-113">I will always be sending messages on this port.</span></span>|  
|<span data-ttu-id="f523a-114">送信 - 受信</span><span class="sxs-lookup"><span data-stu-id="f523a-114">Send-Receive</span></span>|<span data-ttu-id="f523a-115">要求 - 応答</span><span class="sxs-lookup"><span data-stu-id="f523a-115">Request-response</span></span>|<span data-ttu-id="f523a-116">要求の送信と応答の受信をされます。</span><span class="sxs-lookup"><span data-stu-id="f523a-116">I will be sending a request and receiving a response.</span></span>|  
  
 <span data-ttu-id="f523a-117">詳細については、次を参照してください。[の作成および構成する送信ポート](../../core/creating-and-configuring-send-ports.md)です。</span><span class="sxs-lookup"><span data-stu-id="f523a-117">For more information, see [Creating and Configuring Send Ports](../../core/creating-and-configuring-send-ports.md).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="f523a-118">受信ポートがあるためにサポートされていません、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel システムの受信操作を有効にしません。</span><span class="sxs-lookup"><span data-stu-id="f523a-118">Receive ports are not supported because the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] does not enable inbound operations from the Siebel system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f523a-119">によって作成されるバインディングの構成ファイルをインポートして、Wcf-custom 送信ポートを構成することも、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]メタデータの生成の一部として。</span><span class="sxs-lookup"><span data-stu-id="f523a-119">You can also configure the WCF-Custom send ports by importing a binding configuration file that is created by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] as part of metadata generation.</span></span> <span data-ttu-id="f523a-120">このバインド ファイルを使用するポートを構成する方法の詳細については、次を参照してください。 [Siebel するポートのバインド ファイルを使用する物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md)です。</span><span class="sxs-lookup"><span data-stu-id="f523a-120">For instructions on configuring ports using this binding file, see [Configure a physical port binding using a port binding file to Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md).</span></span>
  
 
  
## <a name="see-also"></a><span data-ttu-id="f523a-121">参照</span><span class="sxs-lookup"><span data-stu-id="f523a-121">See Also</span></span>  
[<span data-ttu-id="f523a-122">Siebel アダプターと BizTalk アプリケーションを作成する構成要素</span><span class="sxs-lookup"><span data-stu-id="f523a-122">Building blocks to create BizTalk applications with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)
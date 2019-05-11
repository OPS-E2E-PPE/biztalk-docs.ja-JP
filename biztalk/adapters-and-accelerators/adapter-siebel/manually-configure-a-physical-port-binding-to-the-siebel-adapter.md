---
title: Siebel アダプターを物理ポートのバインドを手動で構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- physical port binding, manually configuring
- how to, manually configure adapters for sending messages to a Siebel system
ms.assetid: a1445b8a-440f-45e8-96e9-a13142ca87c6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 576188121d5dd33541440c8bb34d7b59fc97fb47
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371463"
---
# <a name="manually-configure-a-physical-port-binding-to-the-siebel-adapter"></a><span data-ttu-id="1dbea-102">Siebel アダプターを物理ポートのバインドを手動で構成します。</span><span class="sxs-lookup"><span data-stu-id="1dbea-102">Manually configure a physical port binding to the Siebel adapter</span></span>
<span data-ttu-id="1dbea-103">このセクションでは、構成に関する情報を提供、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]を使用して WCF カスタム バインドとして、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="1dbea-103">This section provides information about configuring the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] as a WCF custom binding by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="1dbea-104">アダプタの展開後にすることを使用しての Siebel システムからメッセージを送受信、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="1dbea-104">After deploying the adapter, you will be able to send and receive messages from the Siebel system by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="1dbea-105">アダプタの展開の手順の間の通信の方向によって異なります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1dbea-105">The steps for deploying the adapter vary depending on the direction of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="1dbea-106">送信または送受信ポートを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="1dbea-106">You may choose to configure a Send or a Send-Receive port.</span></span> <span data-ttu-id="1dbea-107">選択項目は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1dbea-107">Your choices are summarized in the following table:</span></span>  
  
|<span data-ttu-id="1dbea-108">ポートの方向</span><span class="sxs-lookup"><span data-stu-id="1dbea-108">Port direction</span></span>|<span data-ttu-id="1dbea-109">通信方式</span><span class="sxs-lookup"><span data-stu-id="1dbea-109">Communication pattern</span></span>|<span data-ttu-id="1dbea-110">選択する通信の方向</span><span class="sxs-lookup"><span data-stu-id="1dbea-110">Direction of communication to choose from</span></span>|  
|---|---|---|  
|<span data-ttu-id="1dbea-111">Send</span><span class="sxs-lookup"><span data-stu-id="1dbea-111">Send</span></span>|<span data-ttu-id="1dbea-112">一方向</span><span class="sxs-lookup"><span data-stu-id="1dbea-112">One-way</span></span>|<span data-ttu-id="1dbea-113">常にこのポートでメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="1dbea-113">I will always be sending messages on this port.</span></span>|  
|<span data-ttu-id="1dbea-114">送信 - 受信</span><span class="sxs-lookup"><span data-stu-id="1dbea-114">Send-Receive</span></span>|<span data-ttu-id="1dbea-115">要求 - 応答</span><span class="sxs-lookup"><span data-stu-id="1dbea-115">Request-response</span></span>|<span data-ttu-id="1dbea-116">要求の送信と応答の受信をされます。</span><span class="sxs-lookup"><span data-stu-id="1dbea-116">I will be sending a request and receiving a response.</span></span>|  
  
 <span data-ttu-id="1dbea-117">詳細については、次を参照してください。[構成する送信ポートの作成と](../../core/creating-and-configuring-send-ports.md)します。</span><span class="sxs-lookup"><span data-stu-id="1dbea-117">For more information, see [Creating and Configuring Send Ports](../../core/creating-and-configuring-send-ports.md).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="1dbea-118">受信ポートはため、サポートされていません、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel システムからの受信操作を有効にしません。</span><span class="sxs-lookup"><span data-stu-id="1dbea-118">Receive ports are not supported because the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] does not enable inbound operations from the Siebel system.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="1dbea-119">によって作成されるバインド構成ファイルをインポートすることで、Wcf-custom 送信ポートを構成することも、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]メタデータの生成の一部として。</span><span class="sxs-lookup"><span data-stu-id="1dbea-119">You can also configure the WCF-Custom send ports by importing a binding configuration file that is created by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] as part of metadata generation.</span></span> <span data-ttu-id="1dbea-120">このバインド ファイルを使用してポートを構成する方法の詳細については、次を参照してください。 [Siebel にポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md)します。</span><span class="sxs-lookup"><span data-stu-id="1dbea-120">For instructions on configuring ports using this binding file, see [Configure a physical port binding using a port binding file to Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md).</span></span>
  
 
  
## <a name="see-also"></a><span data-ttu-id="1dbea-121">参照</span><span class="sxs-lookup"><span data-stu-id="1dbea-121">See Also</span></span>  
[<span data-ttu-id="1dbea-122">Siebel アダプターを使用した BizTalk アプリケーションを作成する構成要素</span><span class="sxs-lookup"><span data-stu-id="1dbea-122">Building blocks to create BizTalk applications with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)
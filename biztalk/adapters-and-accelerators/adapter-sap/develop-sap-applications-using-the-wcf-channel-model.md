---
title: WCF チャネル モデルを使用して SAP アプリケーションの開発 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF channel model, developing applications by using
ms.assetid: 1ce70c8b-5eeb-4585-97af-b0a7b4398dac
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2bce6ad43b6efce111a2801ba7a5b44e73dce1a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013131"
---
# <a name="develop-sap-applications-using-the-wcf-channel-model"></a><span data-ttu-id="0bca6-102">WCF チャネル モデルを使用して SAP アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="0bca6-102">Develop SAP applications using the WCF Channel Model</span></span>
<span data-ttu-id="0bca6-103">使用することができます、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]チャネル モデルを使用する、 [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] SAP バインドで作成されたチャネル インスタンス経由で直接 XML メッセージを送信することです。</span><span class="sxs-lookup"><span data-stu-id="0bca6-103">You can use the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] channel model to consume the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] by sending XML messages directly over a channel instance created with the SAP Binding.</span></span>  
  
 <span data-ttu-id="0bca6-104">WCF チャネル モデルを使用して、厳密に型指定されたクラスと、WCF サービス モデルを公開するメソッドを使用する利点の 1 つは、チャネル モデルが SAP システムで実行する操作のきめの細かい制御を提供します。</span><span class="sxs-lookup"><span data-stu-id="0bca6-104">One advantage of using the WCF channel model over using the strongly-typed classes and methods that the WCF service model exposes is that the channel model provides more fine-grained control over the operations that you perform on the SAP system.</span></span> <span data-ttu-id="0bca6-105">なぜでしょうか。</span><span class="sxs-lookup"><span data-stu-id="0bca6-105">Why?</span></span> <span data-ttu-id="0bca6-106">WCF チャネル モデルでは、直接チャネル経由で送信するメッセージの内容を制御します。</span><span class="sxs-lookup"><span data-stu-id="0bca6-106">In the WCF channel model you directly control the contents of the messages that you send over the channel.</span></span>  
  
 <span data-ttu-id="0bca6-107">WCF チャネル モデルを使用する WCF サービスのモデルに対するもう 1 つの主な利点より包括的なデータのストリーミング サポートです。</span><span class="sxs-lookup"><span data-stu-id="0bca6-107">Another key advantage that the WCF channel model provides over the WCF service model is more comprehensive support for data streaming.</span></span> <span data-ttu-id="0bca6-108">WCF チャネル モデルを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="0bca6-108">By using the WCF channel model you can perform:</span></span>  
  
- <span data-ttu-id="0bca6-109">メッセージ ノードが、コードとアダプター間で交換されるすべてのメッセージをストリーミングします。</span><span class="sxs-lookup"><span data-stu-id="0bca6-109">Message node streaming on all messages exchanged between your code and the adapter.</span></span>  
  
- <span data-ttu-id="0bca6-110">ノード値の SendIdoc および ReceiveIdoc 操作にストリーミングをメッセージにします。</span><span class="sxs-lookup"><span data-stu-id="0bca6-110">Message node-value streaming on the SendIdoc and ReceiveIdoc operations.</span></span>  
  
  <span data-ttu-id="0bca6-111">これは、ため、WCF チャネル モデルで直接制御するアダプターに送信するメッセージをメッセージ本文が提供する方法と、アダプターから受信したメッセージのメッセージ本文を使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="0bca6-111">This is because in the WCF channel model you directly control how you provide the message body on messages that you send to the adapter and how you consume the message body on messages that you receive from the adapter.</span></span>  
  
  <span data-ttu-id="0bca6-112">これに対し、アダプターには、WCF サービス モデルでは、ストリーミングのサポートしますありません。</span><span class="sxs-lookup"><span data-stu-id="0bca6-112">In contrast, the adapter provides no support for streaming in the WCF service model.</span></span> <span data-ttu-id="0bca6-113">WCF サービス モデルでは、WCF ランタイムはシリアル化および XML とマネージ コード オブジェクトの表現の間でメッセージを逆シリアル化ため、アダプターと交換する各メッセージの完全なメモリ内コピーが行われます。</span><span class="sxs-lookup"><span data-stu-id="0bca6-113">Because, in the WCF service model, the WCF runtime serializes and deserializes messages between their XML and managed code object representations, a complete in-memory copy of each message that you exchange with the adapter is made.</span></span>  
  
  <span data-ttu-id="0bca6-114">このトピックのセクションでは、操作を実行する方法を説明します、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] WCF チャネル モデルを使用しています。</span><span class="sxs-lookup"><span data-stu-id="0bca6-114">The sections in this topic explain how to perform operations on the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] by using the WCF channel model.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0bca6-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0bca6-115">In This Section</span></span>  
  
-   [<span data-ttu-id="0bca6-116">SAP アダプターを使用した WCF チャネル モデルの概要</span><span class="sxs-lookup"><span data-stu-id="0bca6-116">Overview of the WCF Channel Model with the SAP Adapter</span></span>](../../adapters-and-accelerators/adapter-sap/overview-of-the-wcf-channel-model-with-the-sap-adapter.md)  
  
-   [<span data-ttu-id="0bca6-117">SAP を使用してチャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="0bca6-117">Create a channel using SAP</span></span>](../../adapters-and-accelerators/adapter-sap/create-a-channel-using-sap.md)  
  
-   [<span data-ttu-id="0bca6-118">WCF チャネル モデルを使用して SAP システムの操作を呼び出す</span><span class="sxs-lookup"><span data-stu-id="0bca6-118">Invoking Operations on the SAP System by Using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)  
  
-   [<span data-ttu-id="0bca6-119">WCF チャネル モデルを使用して SAP システムから受信操作の受信</span><span class="sxs-lookup"><span data-stu-id="0bca6-119">Receiving Inbound Operations from the SAP System by Using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md) 
  
-   [<span data-ttu-id="0bca6-120">WCF チャネル モデルを使用して SAP でのフラット ファイル Idoc のストリーミング</span><span class="sxs-lookup"><span data-stu-id="0bca6-120">Streaming Flat-File IDOCs in SAP using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md)
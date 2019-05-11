---
title: Siebel システムへの接続の作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connecting, to the Siebel system
ms.assetid: 5810eeb1-6e26-4620-a731-fb352eebea2e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57704a781776fb4e16689d454e367d38fd9da0ee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371762"
---
# <a name="create-a-connection-to-the-siebel-system"></a><span data-ttu-id="a0f6b-102">Siebel システムへの接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="a0f6b-102">Create a connection to the Siebel system</span></span>
<span data-ttu-id="a0f6b-103">[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。</span><span class="sxs-lookup"><span data-stu-id="a0f6b-103">The [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] is a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding.</span></span> <span data-ttu-id="a0f6b-104">そのため、WCF エンドポイントのアドレスで Siebel システムへの通信ができるようにします。</span><span class="sxs-lookup"><span data-stu-id="a0f6b-104">As such, it enables communication to a Siebel system through a WCF endpoint address.</span></span> <span data-ttu-id="a0f6b-105">WCF では、エンドポイント アドレスは、サービスのネットワークの場所を識別しする Uniform Resource Identifier (URI) としては通常表現します。</span><span class="sxs-lookup"><span data-stu-id="a0f6b-105">In WCF the endpoint address identifies the network location of a service and is typically expressed as a Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="a0f6b-106">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]接続プロパティを格納する、URI として、この場所を表します[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]Siebel システムへの接続を確立するために使用します。</span><span class="sxs-lookup"><span data-stu-id="a0f6b-106">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] expresses this location as a connection URI, which contains properties that the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] uses to establish a connection to the Siebel system.</span></span> <span data-ttu-id="a0f6b-107">接続 URI を指定する必要がありますとします。</span><span class="sxs-lookup"><span data-stu-id="a0f6b-107">You must specify a connection URI when you:</span></span>  
  
- <span data-ttu-id="a0f6b-108">チャネル ファクトリまたはを使用してチャネル リスナーを作成、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデル、またはを使用して WCF クライアントまたはサービス ホストを作成、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス モデル。</span><span class="sxs-lookup"><span data-stu-id="a0f6b-108">Create a channel factory or a channel listener using the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] channel model, or create a WCF client or service host using the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service model.</span></span>  
  
- <span data-ttu-id="a0f6b-109">物理ポートのバインドを作成、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューション。</span><span class="sxs-lookup"><span data-stu-id="a0f6b-109">Create a physical port binding in a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
- <span data-ttu-id="a0f6b-110">使用して、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] WCF クライアント クラス、または WCF サービス インターフェイスを生成する、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]モデル ソリューションのサービスです。</span><span class="sxs-lookup"><span data-stu-id="a0f6b-110">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate a WCF client class, or WCF service interface for a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service model solution.</span></span>  
  
- <span data-ttu-id="a0f6b-111">使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]からのメッセージ スキーマを取得する、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]の[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューション。</span><span class="sxs-lookup"><span data-stu-id="a0f6b-111">Use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to retrieve message schemas from the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] for a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
- <span data-ttu-id="a0f6b-112">WCF クライアント クラス、または WCF サービス モデル ソリューションの WCF サービスのインターフェイスを生成するには、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用します。</span><span class="sxs-lookup"><span data-stu-id="a0f6b-112">Use the ServiceModel Metadata Utility tool (svcutil.exe) to generate a WCF client class, or WCF service interface for a WCF service model solution.</span></span>  
  
  <span data-ttu-id="a0f6b-113">このセクションのトピックでは、間の接続を確立する方法をについて説明します、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]とを提供することで Siebel システム。</span><span class="sxs-lookup"><span data-stu-id="a0f6b-113">The topics in this section describe how to establish a connection between the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] and the Siebel system by providing you with:</span></span>  
  
- <span data-ttu-id="a0f6b-114">接続のプロパティ、および Siebel 接続 URI の構造について説明します。</span><span class="sxs-lookup"><span data-stu-id="a0f6b-114">Information about the connection properties and the structure of the Siebel connection URI.</span></span>  
  
- <span data-ttu-id="a0f6b-115">使用して接続を確立する方法を説明するトピックへのリンク、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a0f6b-115">Links to topics that show how to establish a connection by using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="a0f6b-116">参照</span><span class="sxs-lookup"><span data-stu-id="a0f6b-116">See Also</span></span>  
[<span data-ttu-id="a0f6b-117">Siebel アプリケーションの開発</span><span class="sxs-lookup"><span data-stu-id="a0f6b-117">Develop your Siebel applications</span></span>](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)
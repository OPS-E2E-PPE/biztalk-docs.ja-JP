---
title: "SAP システムへの接続を作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SAP system, connecting to
- connection URI
- URI
- Uniform Resource Identifier
ms.assetid: 25d1eaa7-d02a-4fd0-8adf-83505cdb1ab8
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9835047fd32556e6bd9f42adb768ce62f4536ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="create-a-connection-to-the-sap-system"></a><span data-ttu-id="54515-102">SAP システムへの接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="54515-102">Create a connection to the SAP system</span></span>
<span data-ttu-id="54515-103">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。</span><span class="sxs-lookup"><span data-stu-id="54515-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] is a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding.</span></span> <span data-ttu-id="54515-104">そのため、WCF エンドポイントのアドレスを使って、SAP システムへの通信を可能になります。</span><span class="sxs-lookup"><span data-stu-id="54515-104">As such, it enables communication to an SAP system through a WCF endpoint address.</span></span> <span data-ttu-id="54515-105">WCF では、エンドポイントのアドレスは、サービスのネットワークの場所を識別し、として、Uniform Resource Identifier () は通常表現します。</span><span class="sxs-lookup"><span data-stu-id="54515-105">In WCF the endpoint address identifies the network location of a service and is typically expressed as a Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="54515-106">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]接続プロパティが含まれて、URI とは、この場所の表現を[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]SAP システムへの接続を確立するために使用します。</span><span class="sxs-lookup"><span data-stu-id="54515-106">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expresses this location as a connection URI, which contains properties that the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses to establish a connection to the SAP system.</span></span> <span data-ttu-id="54515-107">接続 URI を指定する必要がありますとします。</span><span class="sxs-lookup"><span data-stu-id="54515-107">You must specify a connection URI when you:</span></span>  
  
-   <span data-ttu-id="54515-108">チャネル ファクトリまたはチャネルを使用してリスナーを作成する場合、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデルまたはを使用して WCF クライアントまたはサービス ホストを作成する場合、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス モデル。</span><span class="sxs-lookup"><span data-stu-id="54515-108">When you create a channel factory or a channel listener using the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] channel model or when you create a WCF client or service host using the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service model.</span></span>  
  
-   <span data-ttu-id="54515-109">物理ポートのバインドを作成、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="54515-109">Create a physical port binding in a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
-   <span data-ttu-id="54515-110">使用して、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] 、WCF クライアント クラスまたは WCF サービス インターフェイスを生成する、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]モデル ソリューションのサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="54515-110">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate a WCF client class or WCF service interface for a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service model solution.</span></span>  
  
-   <span data-ttu-id="54515-111">使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]からのメッセージ スキーマを取得する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]の[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="54515-111">Use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to retrieve message schemas from the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] for a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
-   <span data-ttu-id="54515-112">ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用して、WCF クライアント クラスまたは WCF サービスのモデル ソリューションの WCF サービスのインターフェイスを生成します。</span><span class="sxs-lookup"><span data-stu-id="54515-112">Use the ServiceModel Metadata Utility tool (svcutil.exe) to generate a WCF client class or WCF service interface for a WCF service model solution.</span></span>  
  
 <span data-ttu-id="54515-113">このセクションのトピックでは、間の接続を確立する方法を記述、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]とを提供することで、SAP システム。</span><span class="sxs-lookup"><span data-stu-id="54515-113">The topics in this section describe how to establish a connection between the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] and the SAP system by providing you with:</span></span>  
  
-   <span data-ttu-id="54515-114">接続のプロパティと、SAP 接続 URI の構造に関する情報。</span><span class="sxs-lookup"><span data-stu-id="54515-114">Information about the connection properties and the structure of the SAP connection URI.</span></span>  
  
-   <span data-ttu-id="54515-115">使用して接続を確立する方法を説明するトピックへのリンク、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="54515-115">Links to topics that show how to establish a connection by using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="54515-116">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="54515-116">In This Section</span></span>  
  
-   [<span data-ttu-id="54515-117">SAP システム接続 URI を作成します。</span><span class="sxs-lookup"><span data-stu-id="54515-117">Create the SAP system connection URI</span></span>](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)
---
title: "SQL Server への接続を作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 44a03b2c-55b5-49a0-92cc-6f017720d34a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3b87b4141c9e14c680d8100a7c505dda0a0093c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="create-a-connection-to-sql-server"></a><span data-ttu-id="084ed-102">SQL Server への接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="084ed-102">Create a connection to SQL Server</span></span>
<span data-ttu-id="084ed-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。</span><span class="sxs-lookup"><span data-stu-id="084ed-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] is a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding.</span></span> <span data-ttu-id="084ed-104">そのため、WCF エンドポイントのアドレスを使用して SQL Server データベースへの通信を可能になります。</span><span class="sxs-lookup"><span data-stu-id="084ed-104">As such, it enables communication to a SQL Server database through a WCF endpoint address.</span></span> <span data-ttu-id="084ed-105">WCF では、エンドポイントのアドレスはサービスのネットワークの場所を識別し、として、Uniform Resource Identifier ()、通常表現されます。</span><span class="sxs-lookup"><span data-stu-id="084ed-105">In WCF, the endpoint address identifies the network location of a service and is typically expressed as a Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="084ed-106">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接続プロパティが含まれて、URI とは、この場所の表現を[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]SQL Server データベースへの接続を確立するために使用します。</span><span class="sxs-lookup"><span data-stu-id="084ed-106">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] expresses this location as a connection URI, which contains properties that the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] uses to establish a connection to the SQL Server database.</span></span> <span data-ttu-id="084ed-107">接続 URI を指定する必要がありますとします。</span><span class="sxs-lookup"><span data-stu-id="084ed-107">You must specify a connection URI when you:</span></span>  
  
-   <span data-ttu-id="084ed-108">チャネル ファクトリまたは WCF チャネル モデルまたは WCF サービス モデルを使用して WCF クライアントまたはサービス ホストを作成する場合を使用してチャネル リスナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="084ed-108">Create a channel factory or a channel listener using the WCF channel model or when you create a WCF client or service host using the WCF service model.</span></span>  
  
-   <span data-ttu-id="084ed-109">物理ポートのバインドを作成、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="084ed-109">Create a physical port binding in a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
-   <span data-ttu-id="084ed-110">使用して、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] WCF クライアント クラスまたは WCF サービスのモデル ソリューションの WCF サービスのインターフェイスを生成します。</span><span class="sxs-lookup"><span data-stu-id="084ed-110">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate a WCF client class or WCF service interface for a WCF service model solution.</span></span>  
  
-   <span data-ttu-id="084ed-111">使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]からのメッセージ スキーマを取得する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]の BizTalk Server ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="084ed-111">Use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to retrieve message schemas from the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] for a BizTalk Server solution.</span></span>  
  
-   <span data-ttu-id="084ed-112">ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用して、WCF クライアント クラスまたは WCF サービスのモデル ソリューションの WCF サービスのインターフェイスを生成します。</span><span class="sxs-lookup"><span data-stu-id="084ed-112">Use the ServiceModel Metadata Utility tool (svcutil.exe) to generate a WCF client class or WCF service interface for a WCF service model solution.</span></span>  
  
 <span data-ttu-id="084ed-113">このセクションのトピック間の接続を確立する方法について説明、[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]および使用することによって、SQL Server データベース。</span><span class="sxs-lookup"><span data-stu-id="084ed-113">The topics in this section describe how to establish a connection between the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] and the SQL Server database by providing you with:</span></span>  
  
-   <span data-ttu-id="084ed-114">接続のプロパティと、SQL Server 接続 URI の構造に関する情報。</span><span class="sxs-lookup"><span data-stu-id="084ed-114">Information about the connection properties and the structure of the SQL Server connection URI.</span></span>  
  
-   <span data-ttu-id="084ed-115">使用して接続 URI を指定する方法を説明するトピックへのリンク、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="084ed-115">Links to topics that show how to specify a connection URI by using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
-   <span data-ttu-id="084ed-116">Windows 認証を使用して SQL Server への接続に関する情報。</span><span class="sxs-lookup"><span data-stu-id="084ed-116">Information about connecting to SQL Server using Windows Authentication.</span></span>  
  
  
  
## <a name="see-also"></a><span data-ttu-id="084ed-117">参照</span><span class="sxs-lookup"><span data-stu-id="084ed-117">See Also</span></span>  
[<span data-ttu-id="084ed-118">SQL アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="084ed-118">Develop your SQL applications</span></span>](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)
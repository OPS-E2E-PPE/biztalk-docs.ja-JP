---
title: WCF LOB Adapter SDK を使用する場合は、URI スキームとアドレス指定の形式を選択します |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bb4feee-3d39-43ca-82ac-aba38c13bc69
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fd645cbaf8b14fb66b5da3a506ac2258ba1d6be
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363363"
---
# <a name="select-a-uri-scheme-and-addressing-format-when-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="83837-102">WCF LOB Adapter SDK を使用する場合は、URI スキームとアドレス指定の形式を選択します</span><span class="sxs-lookup"><span data-stu-id="83837-102">Select a URI scheme and addressing format when using the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="83837-103">Web サービスのように、使用して開発されたアダプターの場合、リソースを一意に識別する Uniform Resource Identifier (URI)、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]を実行するアクションと同様に、システムに接続します。</span><span class="sxs-lookup"><span data-stu-id="83837-103">A Uniform Resource Identifier (URI) uniquely identifies resources like a Web service or, in the case of an adapter developed with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], the system to connect to as well as the action to perform.</span></span> <span data-ttu-id="83837-104">このセクションでは、エンドポイント アドレスとアダプターのアクションを記述する URI を作成する方法の推奨事項を提供します。</span><span class="sxs-lookup"><span data-stu-id="83837-104">This section provides a recommendation on how to construct a URI to uniquely describe the endpoint address and the action for your adapter.</span></span>  
  
## <a name="anatomy-of-a-uri"></a><span data-ttu-id="83837-105">URI の構造</span><span class="sxs-lookup"><span data-stu-id="83837-105">Anatomy of a URI</span></span>  
 <span data-ttu-id="83837-106">URI は、次の 3 つのコンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="83837-106">A URI consists of the following three components:</span></span>  
  
- <span data-ttu-id="83837-107">**スキーム名**URI 文字列の潜在顧客の一部であり、名前付け構造体の第 1 レベルの例には、http、urn、contoso がなどがあります。</span><span class="sxs-lookup"><span data-stu-id="83837-107">**Scheme name** is the lead part of the URI string and is the first level of the naming structure; examples include http, urn, and contoso.</span></span>  
  
- <span data-ttu-id="83837-108">**階層の一部**情報は通常、階層的で省略可能な機関、ホスト名、およびポート情報を含めることで構成されます。</span><span class="sxs-lookup"><span data-stu-id="83837-108">**Hierarchical part** consists of information that is usually hierarchical and can contain optional authority, hostname, and port information.</span></span> <span data-ttu-id="83837-109">例としては、 www.microsoft.com のユーザー名 =User@microsoft.com:4099します。</span><span class="sxs-lookup"><span data-stu-id="83837-109">Examples include www.microsoft.com and UserName=User@microsoft.com:4099.</span></span>  
  
- <span data-ttu-id="83837-110">**クエリ**疑問符 (?) でマークされ、通常はアンパサンドで区切られたキーと値のペアとしてグループ化のオプションの情報が含まれています (&)。</span><span class="sxs-lookup"><span data-stu-id="83837-110">**Query** contains optional information marked with a question mark (?) and typically grouped as key/value pairs separated by an ampersand (&).</span></span> <span data-ttu-id="83837-111">たとえば、contoso://microsoft.com/functions?name=Find します。</span><span class="sxs-lookup"><span data-stu-id="83837-111">For example, contoso://microsoft.com/functions?name=Find.</span></span>  
  
- <span data-ttu-id="83837-112">**フラグメント**アダプターで必要となる追加の識別情報を格納するために使用します。</span><span class="sxs-lookup"><span data-stu-id="83837-112">**Fragment** is used to store extra identifying information that may be needed by the adapter.</span></span> <span data-ttu-id="83837-113">ハッシュで区切られた、フラグメント (#)。たとえば、contoso://microsoft.com/functions?name=Find#public します。</span><span class="sxs-lookup"><span data-stu-id="83837-113">The fragment is separated by a hash (#); for example, contoso://microsoft.com/functions?name=Find#public.</span></span>  
  
  <span data-ttu-id="83837-114">すべての URI 構文によって提供される機能を使用する場合がありますできません。</span><span class="sxs-lookup"><span data-stu-id="83837-114">You might not use all of the features provided by the URI syntax.</span></span>  
  
## <a name="designing-the-uri"></a><span data-ttu-id="83837-115">URI の設計</span><span class="sxs-lookup"><span data-stu-id="83837-115">Designing the URI</span></span>  
 <span data-ttu-id="83837-116">アダプター開発者は、ターゲットの基幹業務システムの適切な URI を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83837-116">As an adapter developer, you will have to devise an appropriate URI for your target line-of-business system.</span></span> <span data-ttu-id="83837-117">実際の URI を設計するときは、一意でわかりやすいようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="83837-117">When designing your URI, it is important to make it unique and meaningful.</span></span>  
  
 <span data-ttu-id="83837-118">一意の URI とは、組織内およびその他の企業間の既存の Uri と、インターネットと競合しないです。</span><span class="sxs-lookup"><span data-stu-id="83837-118">A unique URI is one that does not conflict with existing URIs within an organization and across other businesses and the Internet.</span></span> <span data-ttu-id="83837-119">たとえば、"http"または現在認識されてしまう可能性や、既に非常に幅広く使用で考えられる原因接続または運用上の問題と、アダプターが別のシステムに要求をルーティングすることもあるため"afs"のようなスキーム名を選択します。</span><span class="sxs-lookup"><span data-stu-id="83837-119">For example, choosing a scheme name like "http" or "afs" that may be currently recognized or already in wide use could cause connection or operational problems because requests might be routed to a different system and not to your adapter.</span></span>  
  
 <span data-ttu-id="83837-120">URI の設計のもう 1 つの重要な側面ことが意味のあるユーザー、アダプターを利用する開発者向け。</span><span class="sxs-lookup"><span data-stu-id="83837-120">Another important aspect of URI design is making it meaningful to the developer audience who will be consuming your adapter.</span></span> <span data-ttu-id="83837-121">たとえばの信頼性情報処理システムを医療、アダプターを作成する場合は、会社名、システム名、およびシステムのバージョンを処理対象のクレームを含む URI スキームをデザインでした: northwind.contoso.cps.v1.0:// します。</span><span class="sxs-lookup"><span data-stu-id="83837-121">For example, if you are writing an adapter for a medical claims processing system, you could design a URI scheme that includes your company name, the target claims processing system name, and system version: northwind.contoso.cps.v1.0://.</span></span>  
  
## <a name="connecting-to-the-target-system"></a><span data-ttu-id="83837-122">ターゲット システムに接続します。</span><span class="sxs-lookup"><span data-stu-id="83837-122">Connecting to the Target System</span></span>  
 <span data-ttu-id="83837-123">接続文字列では、次の構文があります。</span><span class="sxs-lookup"><span data-stu-id="83837-123">Connection strings have the following syntax:</span></span>  
  
 <span data-ttu-id="83837-124">**\<スキーム\>://[userinfo"\@"]\<LOB 接続文字列\>**</span><span class="sxs-lookup"><span data-stu-id="83837-124">**\<scheme\>://[userinfo "\@"]\<LOB Connection String\>**</span></span>  
  
 <span data-ttu-id="83837-125">たとえば、注文システム (ビジネス アプリケーションのサンプル行)、contoso カタログに接続できます、次を使用します。</span><span class="sxs-lookup"><span data-stu-id="83837-125">For example, you could connect to the contoso catalog ordering system (a sample line of business application) using the following:</span></span>  
  
 <span data-ttu-id="83837-126">**northwind.contoso.v1.0://\<servername\>?Catalog=Contoso&Integrated Security=True**</span><span class="sxs-lookup"><span data-stu-id="83837-126">**northwind.contoso.v1.0://\<servername\>?Catalog=Contoso&Integrated Security=True**</span></span>  
  
 <span data-ttu-id="83837-127">ユーザー名とパスワード、およびその他の重要な資格情報を含む URI で省略可能な機関の情報を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="83837-127">You can also provide optional authority information in the URI including user name and password and other important credentials.</span></span> <span data-ttu-id="83837-128">ただし、このセキュリティ リスクを表示できます。</span><span class="sxs-lookup"><span data-stu-id="83837-128">However, this can present a security risk.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="83837-129">ユーザーの資格情報とその他の機密情報を URI に渡さないでください。</span><span class="sxs-lookup"><span data-stu-id="83837-129">Do not pass user credentials and other sensitive information in the URI.</span></span> <span data-ttu-id="83837-130">この情報を傍受され、承認されていないユーザーに表示可能性があります。</span><span class="sxs-lookup"><span data-stu-id="83837-130">This information could be intercepted and viewed by unauthorized users.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83837-131">参照</span><span class="sxs-lookup"><span data-stu-id="83837-131">See Also</span></span>  
 [<span data-ttu-id="83837-132">計画し、WCF LOB Adapter SDK を使用して、アダプターの設計</span><span class="sxs-lookup"><span data-stu-id="83837-132">Plan and design an adapter using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)
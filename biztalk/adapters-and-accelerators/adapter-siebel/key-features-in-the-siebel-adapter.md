---
title: "Siebel アダプターの機能のキー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- features, performance-related
- adapter features, new
- features, technology-related
- features, metadata-related
- adapter features, operations-related
- adapter features, performance-related
- features, new
- features, operations-related
- adapter features, metadata-related
ms.assetid: 4612c9ab-810e-4c69-9168-a25c58682e71
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 295ff8b13358109a5d4737fb5f9325b3c9caa0f8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="key-features-in-the-siebel-adapter"></a><span data-ttu-id="e86cf-102">Siebel アダプターの主要な機能</span><span class="sxs-lookup"><span data-stu-id="e86cf-102">Key features in the Siebel Adapter</span></span>
<span data-ttu-id="e86cf-103">このセクションでは、の新機能を示します[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e86cf-103">This section lists the new features in [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e86cf-104">このトピックの内容が以前のバージョンから使用された[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="e86cf-104">This topic has been used from the previous version of [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] Help.</span></span>  
  
## <a name="new-features-in-the-siebel-adapter"></a><span data-ttu-id="e86cf-105">Siebel アダプターの新機能</span><span class="sxs-lookup"><span data-stu-id="e86cf-105">New Features in the Siebel Adapter</span></span>  
 <span data-ttu-id="e86cf-106">このリリースで導入された新機能は、次のとおり、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e86cf-106">The following are the new features introduced in this release of the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
### <a name="technology-related-features"></a><span data-ttu-id="e86cf-107">テクノロジに関連する機能</span><span class="sxs-lookup"><span data-stu-id="e86cf-107">Technology-Related Features</span></span>  
  
|<span data-ttu-id="e86cf-108">機能</span><span class="sxs-lookup"><span data-stu-id="e86cf-108">Feature</span></span>|<span data-ttu-id="e86cf-109">解説</span><span class="sxs-lookup"><span data-stu-id="e86cf-109">Comment</span></span>|  
|-------------|-------------|  
|<span data-ttu-id="e86cf-110">使用するためのサポート、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]と Microsoft Office SharePoint Server (MOSS)</span><span class="sxs-lookup"><span data-stu-id="e86cf-110">Support for using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] with Microsoft Office SharePoint Server (MOSS)</span></span>|<span data-ttu-id="e86cf-111">アダプターを使用すると、MOSS ポータルに Siebel システムからデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="e86cf-111">You can use the adapters to present data from the Siebel system onto a MOSS portal.</span></span> <span data-ttu-id="e86cf-112">詳細については、次を参照してください。[の Microsoft Office SharePoint Server と Siebel アダプターを使用して](https://msdn.microsoft.com/library/dd788017.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="e86cf-112">For more information, see [Using the Siebel Adapter with Microsoft Office SharePoint Server](https://msdn.microsoft.com/library/dd788017.aspx).</span></span>|  
  
### <a name="operations-related-features"></a><span data-ttu-id="e86cf-113">操作に関連する機能</span><span class="sxs-lookup"><span data-stu-id="e86cf-113">Operations-Related Features</span></span>  
  
|<span data-ttu-id="e86cf-114">機能</span><span class="sxs-lookup"><span data-stu-id="e86cf-114">Feature</span></span>|<span data-ttu-id="e86cf-115">解説</span><span class="sxs-lookup"><span data-stu-id="e86cf-115">Comment</span></span>|  
|-------------|-------------|  
|<span data-ttu-id="e86cf-116">ビジネス コンポーネントに関連付ける操作のサポート</span><span class="sxs-lookup"><span data-stu-id="e86cf-116">Support for ASSOCIATE operation on business components</span></span>|<span data-ttu-id="e86cf-117">アダプターのクライアントには、親の検索式を指定することによってレコードと子レコードを関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="e86cf-117">Adapter clients can associate records by specifying search expressions for parent and child records.</span></span> <span data-ttu-id="e86cf-118">これは、複数値を持つグループ (MVG) フィールドでビジネス コンポーネントに対してのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="e86cf-118">This is applicable only for business components with multivalued group (MVG) fields.</span></span> <span data-ttu-id="e86cf-119">検索式が親と子の両方のビジネス コンポーネントの 1 つのレコードをフィルターする必要がありますに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e86cf-119">Note that the search expressions should filter exactly one record for both the parent and child business components.</span></span>|  
|<span data-ttu-id="e86cf-120">ビジネス コンポーネントに関連付け解除操作のサポート</span><span class="sxs-lookup"><span data-stu-id="e86cf-120">Support for DISASSOCIATE operation on business components</span></span>|<span data-ttu-id="e86cf-121">アダプターのクライアントには、親の検索式を指定することによってレコードと子レコードを切り離すこともできます。</span><span class="sxs-lookup"><span data-stu-id="e86cf-121">Adapter clients can dissociate records by specifying search expressions for parent and child records.</span></span> <span data-ttu-id="e86cf-122">これは、複数値を持つグループ (MVG) フィールドでビジネス コンポーネントに対してのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="e86cf-122">This is applicable only for business components with multivalued group (MVG) fields.</span></span> <span data-ttu-id="e86cf-123">検索式が親と子の両方のビジネス コンポーネントの 1 つのレコードをフィルターする必要がありますに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e86cf-123">Note that the search expressions must filter exactly one record for both the parent and child business components.</span></span>|  
|<span data-ttu-id="e86cf-124">複数値リンク クエリのサポート</span><span class="sxs-lookup"><span data-stu-id="e86cf-124">Support for multivalue link queries</span></span>|<span data-ttu-id="e86cf-125">アダプターのクライアントは、親レコードとフィールドに複数の名前を指定して、親レコードに関連付けられている子レコードを照会できます。</span><span class="sxs-lookup"><span data-stu-id="e86cf-125">Adapter clients can query the child records associated with a parent record by specifying the parent record and the multivalued field name.</span></span> <span data-ttu-id="e86cf-126">これは、複数値を持つグループ (MVG) フィールドでビジネス コンポーネントに対してのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="e86cf-126">This is applicable only for business components with multivalued group (MVG) fields.</span></span>|  
  
### <a name="other-features"></a><span data-ttu-id="e86cf-127">その他の機能</span><span class="sxs-lookup"><span data-stu-id="e86cf-127">Other Features</span></span>  
  
|<span data-ttu-id="e86cf-128">機能</span><span class="sxs-lookup"><span data-stu-id="e86cf-128">Feature</span></span>|<span data-ttu-id="e86cf-129">解説</span><span class="sxs-lookup"><span data-stu-id="e86cf-129">Comment</span></span>|  
|-------------|-------------|  
|<span data-ttu-id="e86cf-130">アダプターを使用する新しい方法[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e86cf-130">New way of using the adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]</span></span>|<span data-ttu-id="e86cf-131">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]で BizTalk WCF カスタム ポートまたは Wcf-siebel ポートとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="e86cf-131">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] can be used in BizTalk either as a WCF-Custom port or a WCF-Siebel port.</span></span> <span data-ttu-id="e86cf-132">使用する場合、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] WCF カスタム ポートを経由は WCF カスタム ポートを追加する必要はありません、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールに、WCF カスタム ポートが追加されるため、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]既定では管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="e86cf-132">If you want to use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] through a WCF-Custom port, you do not need to add the WCF-Custom port to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console because the WCF-Custom port is added to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by default.</span></span> <span data-ttu-id="e86cf-133">ただし、使用する場合、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Wcf-siebel ポートを介して、Wcf-siebel アダプターを追加する必要があります最初、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="e86cf-133">However, if you want to use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] through a WCF-Siebel port, you must first add the WCF-Siebel adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="e86cf-134">詳細については、次を参照してください。 [Siebel アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)です。</span><span class="sxs-lookup"><span data-stu-id="e86cf-134">For more information, see [Add the Siebel Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e86cf-135">参照</span><span class="sxs-lookup"><span data-stu-id="e86cf-135">See Also</span></span>  
 [<span data-ttu-id="e86cf-136">Siebel eBusiness Applications の BizTalk アダプターを理解します。</span><span class="sxs-lookup"><span data-stu-id="e86cf-136">Understand BizTalk Adapter for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)
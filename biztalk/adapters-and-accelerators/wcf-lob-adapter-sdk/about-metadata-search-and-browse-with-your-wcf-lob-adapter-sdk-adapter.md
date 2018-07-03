---
title: メタデータの検索と、WCF LOB Adapter SDK のアダプターを使用した参照に関する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1dc529ba-86ce-4f83-a4f8-73f5765308e2
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 215199bec64562a302c9550bc5526a8758e4843a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983435"
---
# <a name="about-metadata-search-and-browse-with-your-wcf-lob-adapter-sdk-adapter"></a><span data-ttu-id="c64bc-102">メタデータの検索と、WCF LOB Adapter SDK のアダプターを使用した参照について</span><span class="sxs-lookup"><span data-stu-id="c64bc-102">About metadata search and browse with your WCF LOB Adapter SDK adapter</span></span>
<span data-ttu-id="c64bc-103">使用して構築された静的なサービスとは異なり、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]を使用してビルドされたアダプターは、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]型と基幹業務システムで使用できる操作に関する動的な情報を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="c64bc-103">Unlike a static service built using the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], adapters built using the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] can provide dynamic information about the types and operations available in a line-of-business system.</span></span> <span data-ttu-id="c64bc-104">開発者は、次の操作をサポートできます。</span><span class="sxs-lookup"><span data-stu-id="c64bc-104">Developers can support the following operations:</span></span>  
  
- <span data-ttu-id="c64bc-105">**メタデータ参照**、すべての操作の一覧を確認するユーザーを有効にして、基幹業務システムで使用できる型します。</span><span class="sxs-lookup"><span data-stu-id="c64bc-105">**Metadata Browse**, enabling the user to review a list of all operations and types available in the line-of-business system.</span></span>  
  
- <span data-ttu-id="c64bc-106">**メタデータの検索**、基幹業務システムに基づく多くの場合、別の条件を使用して操作を検索するユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c64bc-106">**Metadata Search**, enabling the user to search for operations using different criteria often based on the line of business system.</span></span> <span data-ttu-id="c64bc-107">たとえば、ユーザーがで検索できます"* CUST\*"を名前に「顧客」を任意の場所があるすべての操作を取得します。</span><span class="sxs-lookup"><span data-stu-id="c64bc-107">For example, the user could search on "*CUST\*" to retrieve all operations that have "CUST" anywhere in their name.</span></span>  
  
- <span data-ttu-id="c64bc-108">**メタデータの取得**、サポートされる操作やデータ型の特定のリストに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c64bc-108">**Metadata Retrieval**, which supplies information about a specific list of supported operations or data types.</span></span>  
  
  <span data-ttu-id="c64bc-109">基幹業務システムに数百または数千回の操作が含まれる場合は、特定の操作を検索または特定のグループの情報を参照する機能を提供すると、ユーザー エクスペリエンスを強化できます。</span><span class="sxs-lookup"><span data-stu-id="c64bc-109">If the line of business system contains hundreds or thousands of operations, providing the ability to search for specific operations or browse certain groups of information can enhance the user experience.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c64bc-110">参照</span><span class="sxs-lookup"><span data-stu-id="c64bc-110">See Also</span></span>  
 [<span data-ttu-id="c64bc-111">計画し、WCF LOB Adapter SDK を使用して、アダプターの設計 </span><span class="sxs-lookup"><span data-stu-id="c64bc-111">Plan and Design your Adapter using the WCF LOB Adapter SDK </span></span>](plan-and-design-your-adapter-using-the-wcf-lob-adapter-sdk.md)
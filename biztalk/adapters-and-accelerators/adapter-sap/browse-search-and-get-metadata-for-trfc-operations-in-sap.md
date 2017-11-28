---
title: "参照、検索、および SAP の tRFC 操作のメタデータを取得 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tRFC operations
- tRFC operations, browsing
- searching, tRFC operations
- tRFC operations, searching
- browsing, tRFC operations
ms.assetid: cf4a16d1-7bbf-4dea-b54d-b5315fbcd552
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5124eb4b3a56df70ec55d157ee80a394d6bff83d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="browse-search-and-get-metadata-for-trfc-operations-in-sap"></a><span data-ttu-id="832e5-102">参照、検索、および SAP の tRFC 操作のメタデータを取得</span><span class="sxs-lookup"><span data-stu-id="832e5-102">Browse, search, and get metadata for tRFC operations in SAP</span></span>
<span data-ttu-id="832e5-103">tRFCs は、SAP システムで、個別の成果物ではありません。</span><span class="sxs-lookup"><span data-stu-id="832e5-103">tRFCs are not a separate artifact in an SAP system.</span></span> <span data-ttu-id="832e5-104">これらは、分類によって別のノードの下、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]の特性にメタデータが Rfc のものと異なるためです。</span><span class="sxs-lookup"><span data-stu-id="832e5-104">These are categorized under a separate node by the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] because their metadata characteristics are different from that of RFCs.</span></span> <span data-ttu-id="832e5-105">ただし、プログラムの参照、検索、および tRFCs のメタデータの取得は、Rfc のものと同じです。</span><span class="sxs-lookup"><span data-stu-id="832e5-105">However, the experience of browsing, searching, and retrieving metadata for tRFCs is identical to that of the RFCs.</span></span> <span data-ttu-id="832e5-106">参照してください[参照、検索、および get 操作のメタデータの RFC に SAP](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md)使用については、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を参照するには、検索、および SAP システムから tRFCs のメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="832e5-106">Refer to [Browse, search, and get metadata for RFC operations in SAP](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md) for information about using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to browse, search, and retrieve metadata for tRFCs from an SAP system.</span></span>  
  
 <span data-ttu-id="832e5-107">なお、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サーフェスの特別な操作**RfcConfirmTransID**下にある、 **TRFC**ノード。</span><span class="sxs-lookup"><span data-stu-id="832e5-107">Note that the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces a special operation **RfcConfirmTransID** under the **TRFC** node.</span></span> <span data-ttu-id="832e5-108">SAP アダプターでは、この操作を使用して、SAP サーバーに tRFC の呼び出しをコミットします。</span><span class="sxs-lookup"><span data-stu-id="832e5-108">The SAP adapter uses this operation to commit tRFC calls made to the SAP server.</span></span> <span data-ttu-id="832e5-109">この操作の詳細については、次を参照してください。 [SAP で tRFCs に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)です。</span><span class="sxs-lookup"><span data-stu-id="832e5-109">For more information about this operation, see [Operations on tRFCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="832e5-110">参照</span><span class="sxs-lookup"><span data-stu-id="832e5-110">See Also</span></span>  
 [<span data-ttu-id="832e5-111">Visual Studio での SAP 操作のメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="832e5-111">Get Metadata for SAP Operations in Visual Studio</span></span>](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)
---
title: "ドキュメント参照 URL ノード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Document Reference URL nodes [Tracking Profile Editor]
- Tracking Profile Editor, node descriptions
- definition files [BAM], related documents
ms.assetid: 38c8ae50-ed56-451c-9549-db852d4770e5
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7939a7e74483b8df192530fd9da2deafeda0681
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="document-reference-url-nodes"></a><span data-ttu-id="4378b-102">ドキュメント参照 URL ノード</span><span class="sxs-lookup"><span data-stu-id="4378b-102">Document Reference URL Nodes</span></span>
<span data-ttu-id="4378b-103">ドキュメント参照 URL ノードは、ナレッジ ワーカーが作成した監視モデルから開発者がインポートする、アクティビティ定義ファイル内に存在します。</span><span class="sxs-lookup"><span data-stu-id="4378b-103">Document Reference URL nodes exist in the activity definition file that the developer imports from the knowledge worker created observation model.</span></span> <span data-ttu-id="4378b-104">ドキュメント参照 URL ノードには、このアクティビティに関連するドキュメントが格納されている場所への参照が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4378b-104">Document Reference URL nodes contain references to a location that contains a document that is related to this activity.</span></span> <span data-ttu-id="4378b-105">たとえば注文書の承認ワーク フローを表すアクティビティなど、すべての種類のドキュメントが対象になります。ドキュメント参照 URL は、基になる注文書を指すこともあります。</span><span class="sxs-lookup"><span data-stu-id="4378b-105">This can be any type of document, for example an activity that represents a purchase order approval work flow, the Document Reference URL might point to the underlying purchase order document.</span></span>  
  
## <a name="working-with-document-reference-url-nodes"></a><span data-ttu-id="4378b-106">ドキュメント参照 URL ノードの操作</span><span class="sxs-lookup"><span data-stu-id="4378b-106">Working with Document Reference URL nodes</span></span>  
 <span data-ttu-id="4378b-107">ドキュメント参照 URL のデータ ソースは、通常、 **MessageRefURL** BizTalk Server システムのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="4378b-107">The data source for the Document Reference URL is typically the **MessageRefURL** BizTalk Server system property.</span></span> <span data-ttu-id="4378b-108">URL を保存するカスタム スキーマを使用して、カスタム スキーマからドキュメント参照 URL にプロパティをマップすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4378b-108">You can also use custom schemas that store URLs and map the property to the Document Reference URL from the custom schema.</span></span>  
  
 <span data-ttu-id="4378b-109">ドキュメント参照 URL に関する注意事項を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4378b-109">Items to note about Document Reference URLs:</span></span>  
  
-   <span data-ttu-id="4378b-110">1 つ以上のドキュメント参照 URL を追加できますが、各ノードの名前はアクティビティ内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4378b-110">You can add one or more Document Reference URLs, but each node must have unique name within the activity.</span></span>  
  
-   <span data-ttu-id="4378b-111">**MessageRefURL**ドキュメント参照 URL ノードを設定するために必要なプロパティは、値は、WSS、FILE および FTP のトランスポート アダプターの場合のみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="4378b-111">The **MessageRefURL** property needed to populate a Document Reference URL node is only populated with a value in the case of WSS, FILE, and FTP transport adapters.</span></span>  
  
-   <span data-ttu-id="4378b-112">ビジネス エンドユーザーは、BAM ポータルでこの参照を表示できますが、参照 URL の主な目的はカスタム ユーザー インターフェイスの開発者にアクセスするために使用できるように関連するドキュメントの情報をエンドユーザーに提示するようにします。</span><span class="sxs-lookup"><span data-stu-id="4378b-112">While business end-users can view this reference in the BAM portal, the primary purpose of the reference URL is to allow custom user interface developers to gain access to associated document information so that they can present it to the end user.</span></span>  <span data-ttu-id="4378b-113">BAM ポータルでドキュメントの参照を表示する方法の詳細については、次を参照してください。[関連ドキュメント](../core/related-documents.md)です。</span><span class="sxs-lookup"><span data-stu-id="4378b-113">For more information on viewing the document reference in the BAM portal, see [Related Documents](../core/related-documents.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4378b-114">参照</span><span class="sxs-lookup"><span data-stu-id="4378b-114">See Also</span></span>  
 [<span data-ttu-id="4378b-115">TPE アクティビティ ビューのノード</span><span class="sxs-lookup"><span data-stu-id="4378b-115">TPE Activity View Nodes</span></span>](../core/tpe-activity-view-nodes.md)
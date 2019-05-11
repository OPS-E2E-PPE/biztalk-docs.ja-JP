---
title: ドキュメント参照 URL ノード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Document Reference URL nodes [Tracking Profile Editor]
- Tracking Profile Editor, node descriptions
- definition files [BAM], related documents
ms.assetid: 38c8ae50-ed56-451c-9549-db852d4770e5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c9cbc37b48ad6592215723695b54edc17e834b8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350962"
---
# <a name="document-reference-url-nodes"></a><span data-ttu-id="daa05-102">ドキュメント参照 URL ノード</span><span class="sxs-lookup"><span data-stu-id="daa05-102">Document Reference URL Nodes</span></span>
<span data-ttu-id="daa05-103">ドキュメント参照 URL ノードは、ナレッジ ワーカーが作成した監視モデルから開発者がインポートするアクティビティ定義ファイルに存在します。</span><span class="sxs-lookup"><span data-stu-id="daa05-103">Document Reference URL nodes exist in the activity definition file that the developer imports from the knowledge worker created observation model.</span></span> <span data-ttu-id="daa05-104">ドキュメント参照 URL ノードには、このアクティビティに関連するドキュメントを格納している場所への参照が含まれます。</span><span class="sxs-lookup"><span data-stu-id="daa05-104">Document Reference URL nodes contain references to a location that contains a document that is related to this activity.</span></span> <span data-ttu-id="daa05-105">ドキュメント、購買発注書ドキュメントをポイントして、基になる可能性があります、購買注文の承認ワークフロー ドキュメント参照 URL を表すアクティビティなどの任意の型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="daa05-105">This can be any type of document, for example an activity that represents a purchase order approval work flow, the Document Reference URL might point to the underlying purchase order document.</span></span>  
  
## <a name="working-with-document-reference-url-nodes"></a><span data-ttu-id="daa05-106">ドキュメント参照 URL ノードの操作</span><span class="sxs-lookup"><span data-stu-id="daa05-106">Working with Document Reference URL nodes</span></span>  
 <span data-ttu-id="daa05-107">ドキュメント参照 URL のデータ ソースは、通常、 **MessageRefURL** BizTalk Server システムのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="daa05-107">The data source for the Document Reference URL is typically the **MessageRefURL** BizTalk Server system property.</span></span> <span data-ttu-id="daa05-108">Url を保存し、カスタム スキーマからドキュメント参照 URL プロパティをマップするカスタム スキーマを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="daa05-108">You can also use custom schemas that store URLs and map the property to the Document Reference URL from the custom schema.</span></span>  
  
 <span data-ttu-id="daa05-109">ドキュメント参照 Url に関する注意事項:</span><span class="sxs-lookup"><span data-stu-id="daa05-109">Items to note about Document Reference URLs:</span></span>  
  
-   <span data-ttu-id="daa05-110">1 つまたは複数のドキュメント参照 Url を追加できますが、各ノードは、アクティビティ内で一意の名前をいる必要があります。</span><span class="sxs-lookup"><span data-stu-id="daa05-110">You can add one or more Document Reference URLs, but each node must have unique name within the activity.</span></span>  
  
-   <span data-ttu-id="daa05-111">**MessageRefURL**ドキュメント参照 URL ノードを設定するために必要なプロパティは、値は、WSS、FILE および FTP のトランスポート アダプターの場合のみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="daa05-111">The **MessageRefURL** property needed to populate a Document Reference URL node is only populated with a value in the case of WSS, FILE, and FTP transport adapters.</span></span>  
  
-   <span data-ttu-id="daa05-112">ビジネス エンドユーザーは、BAM ポータルで、この参照を表示できますが、参照 URL の主な目的は、エンドユーザーに提供できるようにカスタム ユーザー インターフェイス開発者へのアクセスを許可するドキュメントの情報を関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="daa05-112">While business end-users can view this reference in the BAM portal, the primary purpose of the reference URL is to allow custom user interface developers to gain access to associated document information so that they can present it to the end user.</span></span>  <span data-ttu-id="daa05-113">BAM ポータルでドキュメントの参照を表示する方法の詳細については、次を参照してください。[関連ドキュメント](../core/related-documents.md)します。</span><span class="sxs-lookup"><span data-stu-id="daa05-113">For more information on viewing the document reference in the BAM portal, see [Related Documents](../core/related-documents.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daa05-114">参照</span><span class="sxs-lookup"><span data-stu-id="daa05-114">See Also</span></span>  
 [<span data-ttu-id="daa05-115">TPE アクティビティ ビューのノード</span><span class="sxs-lookup"><span data-stu-id="daa05-115">TPE Activity View Nodes</span></span>](../core/tpe-activity-view-nodes.md)
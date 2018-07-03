---
title: 関連ドキュメント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- queries [BAM], document references
- definition files [BAM], related documents
- Query Builder [BAM portal], viewing details
- document references [BAM]
- Query Builder [BAM portal], document references
- queries [BAM], viewing details
ms.assetid: 9c5f2175-fe7c-40ec-910d-1ac5c8142045
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56338d268bac6568f8e175b6e70da202715fd7a8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006735"
---
# <a name="related-documents"></a><span data-ttu-id="44f05-102">関連ドキュメント</span><span class="sxs-lookup"><span data-stu-id="44f05-102">Related Documents</span></span>
<span data-ttu-id="44f05-103">クエリ結果の詳細に表示される [関連ドキュメント] 領域には、アクティビティに関連する参考用ドキュメントが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="44f05-103">The Related Documents area of the query results detail displays a list of documents that are reference documents that relate to the activity.</span></span> <span data-ttu-id="44f05-104">表示されるドキュメントの種類は、CAD 画像、.WAV ファイル、注文書などさまざまです。</span><span class="sxs-lookup"><span data-stu-id="44f05-104">The documents can be of any type, including a CAD image, a .WAV file, or a purchase order.</span></span> <span data-ttu-id="44f05-105">たとえば、発注アクティビティでは、通常、基本のドキュメントの種類として注文書が使用されます。</span><span class="sxs-lookup"><span data-stu-id="44f05-105">For example, a Purchase Order activity will typically have a Purchase Order as a base document type.</span></span> <span data-ttu-id="44f05-106">表示される一覧には、注文書へのリンクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="44f05-106">The list will contain a link to the purchase order.</span></span>  
  
## <a name="adding-document-references"></a><span data-ttu-id="44f05-107">ドキュメント参照の追加</span><span class="sxs-lookup"><span data-stu-id="44f05-107">Adding document references</span></span>  
 <span data-ttu-id="44f05-108">関連ドキュメントの一覧は、次のいずれかの方法で生成します。</span><span class="sxs-lookup"><span data-stu-id="44f05-108">The list of related documents is generated in one of two ways:</span></span>  
  
- <span data-ttu-id="44f05-109">追跡プロファイルの作成時にアクティビティ ツリーの Document Reference URL ノードを含め、物理的なドキュメントへの参照ポインターを含んだソースからその Document Reference URL ノードを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="44f05-109">When you develop your tracking profile you include a Document Reference URL node in the activity tree and then map it from a source containing a reference pointer to the physical document.</span></span>  
  
- <span data-ttu-id="44f05-110">統合アプリケーション開発者が、カスタム アプリケーションを呼び出すことにより、プログラムを使用してこの一覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="44f05-110">Your integration developer programmatically populates the list by calling your custom application.</span></span>  
  
  <span data-ttu-id="44f05-111">これらのメソッドのいずれかを使用してドキュメント参照の定義内の行を追加します、 \<activityname\>_References テーブルにドキュメントの場所。</span><span class="sxs-lookup"><span data-stu-id="44f05-111">Defining the document reference using either of these methods adds a row in the \<activityname\>_References table with the document location.</span></span>  
  
  <span data-ttu-id="44f05-112">これらのタスクのどちらが実行された場合、**関連ドキュメント**領域は空白です。</span><span class="sxs-lookup"><span data-stu-id="44f05-112">If neither of these tasks has been performed, the **Related Document** area is blank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44f05-113">参照</span><span class="sxs-lookup"><span data-stu-id="44f05-113">See Also</span></span>  
 [<span data-ttu-id="44f05-114">Xml-data Reduced を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44f05-114">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)
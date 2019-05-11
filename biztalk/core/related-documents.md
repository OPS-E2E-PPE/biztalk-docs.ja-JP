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
ms.openlocfilehash: 3cb8259a6c8975673308a0aebb5e9c0336920715
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397974"
---
# <a name="related-documents"></a><span data-ttu-id="9b36e-102">関連ドキュメント</span><span class="sxs-lookup"><span data-stu-id="9b36e-102">Related Documents</span></span>
<span data-ttu-id="9b36e-103">クエリ結果の詳細の関連するドキュメント領域には、ドキュメントに、アクティビティに関連する参考用ドキュメントの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b36e-103">The Related Documents area of the query results detail displays a list of documents that are reference documents that relate to the activity.</span></span> <span data-ttu-id="9b36e-104">表示される、CAD 画像を含む、あらゆる種類のドキュメントをします。WAV ファイル、または注文書。</span><span class="sxs-lookup"><span data-stu-id="9b36e-104">The documents can be of any type, including a CAD image, a .WAV file, or a purchase order.</span></span> <span data-ttu-id="9b36e-105">たとえば、発注アクティビティでは、ベースのドキュメントの種類として注文書が必要が通常あります。</span><span class="sxs-lookup"><span data-stu-id="9b36e-105">For example, a Purchase Order activity will typically have a Purchase Order as a base document type.</span></span> <span data-ttu-id="9b36e-106">注文書へのリンクの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b36e-106">The list will contain a link to the purchase order.</span></span>  
  
## <a name="adding-document-references"></a><span data-ttu-id="9b36e-107">ドキュメント参照の追加</span><span class="sxs-lookup"><span data-stu-id="9b36e-107">Adding document references</span></span>  
 <span data-ttu-id="9b36e-108">2 つの方法のいずれかでは、関連ドキュメントの一覧が生成されます。</span><span class="sxs-lookup"><span data-stu-id="9b36e-108">The list of related documents is generated in one of two ways:</span></span>  
  
- <span data-ttu-id="9b36e-109">追跡プロファイルを開発する際に、ドキュメント参照 URL ノードをアクティビティ ツリーに追加し、物理的なドキュメントへの参照ポインターを格納しているソースからマップします。</span><span class="sxs-lookup"><span data-stu-id="9b36e-109">When you develop your tracking profile you include a Document Reference URL node in the activity tree and then map it from a source containing a reference pointer to the physical document.</span></span>  
  
- <span data-ttu-id="9b36e-110">統合開発者プログラムでは、カスタム アプリケーションを呼び出すことによってリストを設定します。</span><span class="sxs-lookup"><span data-stu-id="9b36e-110">Your integration developer programmatically populates the list by calling your custom application.</span></span>  
  
  <span data-ttu-id="9b36e-111">これらのメソッドのいずれかを使用してドキュメント参照の定義内の行を追加します、 \<activityname\>_References テーブルにドキュメントの場所。</span><span class="sxs-lookup"><span data-stu-id="9b36e-111">Defining the document reference using either of these methods adds a row in the \<activityname\>_References table with the document location.</span></span>  
  
  <span data-ttu-id="9b36e-112">これらのタスクのどちらが実行された場合、**関連ドキュメント**領域は空白です。</span><span class="sxs-lookup"><span data-stu-id="9b36e-112">If neither of these tasks has been performed, the **Related Document** area is blank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b36e-113">参照</span><span class="sxs-lookup"><span data-stu-id="9b36e-113">See Also</span></span>  
 [<span data-ttu-id="9b36e-114">追跡プロファイル エディター</span><span class="sxs-lookup"><span data-stu-id="9b36e-114">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)
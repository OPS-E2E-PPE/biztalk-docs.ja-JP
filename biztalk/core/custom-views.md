---
title: カスタム ビュー |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9084cc07-be98-4c57-afea-4fa369a38bad
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 184f49330374126f4afc0bd4bb376ea31a5ca681
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238170"
---
# <a name="custom-views"></a><span data-ttu-id="6c1ca-102">カスタム ビュー</span><span class="sxs-lookup"><span data-stu-id="6c1ca-102">Custom Views</span></span>
<span data-ttu-id="6c1ca-103">カスタム ビューは、読み取り専用のウィンドウ コントロール オブジェクトでは通常 (から派生した**System.Windows.Forms.Control**)、ファイルまたはサポートされているファイルの種類のカスタマイズされた表示形式でスキーマを表すための拡張機能によって提供されますで、BizTalk エディター拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="6c1ca-103">A custom view is typically a read-only window control object (derived from **System.Windows.Forms.Control**), and is provided by an extension to represent the schema in a display format customized for the type of file or files supported by the BizTalk Editor extension.</span></span> <span data-ttu-id="6c1ca-104">拡張機能を使用して、複数のカスタム ビューを実装できます。ただし、カスタム ビューがなくても問題はありません。</span><span class="sxs-lookup"><span data-stu-id="6c1ca-104">An extension can implement multiple custom views, though it need not have any custom view.</span></span>  
  
 <span data-ttu-id="6c1ca-105">カスタム ビューは、ビューの下部にあるタブを使用してアクセスできる XSD ビューと同様に、BizTalk エディター ペインの追加ビューとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c1ca-105">A custom view is displayed as an additional view in the same BizTalk Editor pane as the XSD view, accessible by using tabs at the bottom of the views.</span></span> <span data-ttu-id="6c1ca-106">たとえば、フラット ファイル拡張子は、"フラット ファイル" というタブの付いた新しいビューを追加します。</span><span class="sxs-lookup"><span data-stu-id="6c1ca-106">For example, the Flat File Extension adds a new view with a tab labeled Flat File.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c1ca-107">参照</span><span class="sxs-lookup"><span data-stu-id="6c1ca-107">See Also</span></span>  
 [<span data-ttu-id="6c1ca-108">BizTalk エディターの拡張</span><span class="sxs-lookup"><span data-stu-id="6c1ca-108">Extending BizTalk Editor</span></span>](../core/extending-biztalk-editor.md)
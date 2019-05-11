---
title: カスタム ビュー |Microsoft Docs
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
ms.openlocfilehash: 60433668a62c1a7b7483aca3af82ecd8c5d7f8c7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353321"
---
# <a name="custom-views"></a><span data-ttu-id="47f52-102">カスタム ビュー</span><span class="sxs-lookup"><span data-stu-id="47f52-102">Custom Views</span></span>
<span data-ttu-id="47f52-103">カスタム ビューは読み取り専用のウィンドウ コントロール オブジェクトは通常 (から派生した**System.Windows.Forms.Control**)、またはサポートされている複数のファイルの種類用にカスタマイズされた表示形式でスキーマを表す拡張機能によって提供されるとで、BizTalk エディター拡張機能。</span><span class="sxs-lookup"><span data-stu-id="47f52-103">A custom view is typically a read-only window control object (derived from **System.Windows.Forms.Control**), and is provided by an extension to represent the schema in a display format customized for the type of file or files supported by the BizTalk Editor extension.</span></span> <span data-ttu-id="47f52-104">拡張機能は、任意のカスタム ビューは必要ありませんが、複数のカスタム ビューを実装できます。</span><span class="sxs-lookup"><span data-stu-id="47f52-104">An extension can implement multiple custom views, though it need not have any custom view.</span></span>  
  
 <span data-ttu-id="47f52-105">カスタム ビューは、ビューの下部にあるタブを使用してアクセスできる XSD ビューと同じ BizTalk エディター ペインに追加のビューとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="47f52-105">A custom view is displayed as an additional view in the same BizTalk Editor pane as the XSD view, accessible by using tabs at the bottom of the views.</span></span> <span data-ttu-id="47f52-106">たとえば、フラット ファイル拡張子は、タブの付いたフラット ファイル新しいビューを追加します。</span><span class="sxs-lookup"><span data-stu-id="47f52-106">For example, the Flat File Extension adds a new view with a tab labeled Flat File.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47f52-107">参照</span><span class="sxs-lookup"><span data-stu-id="47f52-107">See Also</span></span>  
 [<span data-ttu-id="47f52-108">BizTalk エディターの拡張</span><span class="sxs-lookup"><span data-stu-id="47f52-108">Extending BizTalk Editor</span></span>](../core/extending-biztalk-editor.md)
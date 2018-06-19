---
title: 大きなスキーマの操作 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8348036d-6edb-46a3-badd-0223cfe0a92f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5c5ef679070009b5dfb5fdd403d238cfe243cb2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289714"
---
# <a name="working-with-large-schemas"></a><span data-ttu-id="3ae8c-102">大きなスキーマの操作</span><span class="sxs-lookup"><span data-stu-id="3ae8c-102">Working with Large Schemas</span></span>
<span data-ttu-id="3ae8c-103">スキーマが非常に大きくなると、XSD ビューの更新に時間がかかり、ユーザー インターフェイスの応答にも影響することがあります。</span><span class="sxs-lookup"><span data-stu-id="3ae8c-103">When your schemas become very large, you may find that refreshing the XSD view is increasingly slow and that the response of other aspects of the user interface can be impacted as well.</span></span> <span data-ttu-id="3ae8c-104">この問題を解決するには自動更新機能をオフにして、代わりに、手動**更新**を定期的に更新する XSD ビューと XSD ビューにリンクします。</span><span class="sxs-lookup"><span data-stu-id="3ae8c-104">The solution to this issue is to turn off the auto-refresh feature and instead use the manual **Refresh** link in the XSD view to periodically refresh the XSD view.</span></span> <span data-ttu-id="3ae8c-105">手順については有効にするため、自動更新機能をオフを参照してくださいで XSD ビューの自動更新のオンとオフ"するには」の手順で[XSD ビューの管理](../core/how-to-manage-the-xsd-view.md)です。</span><span class="sxs-lookup"><span data-stu-id="3ae8c-105">For step-by-step instructions about how turn the auto-refresh feature on an off, see the procedure "To turn automatic refresh of the XSD view on and off" in [Managing the XSD View](../core/how-to-manage-the-xsd-view.md).</span></span>  
  
 <span data-ttu-id="3ae8c-106">パフォーマンスが低下することもサイズの大きいスキーマでにアタッチされている複数のルートを持つ、**スキーマ**ノード。</span><span class="sxs-lookup"><span data-stu-id="3ae8c-106">Performance may also be slow in large schemas with multiple roots attached to the **schema** node.</span></span> <span data-ttu-id="3ae8c-107">設定、**ルート参照**プロパティは、ユーザー インターフェイスのパフォーマンスを向上させることがあります。</span><span class="sxs-lookup"><span data-stu-id="3ae8c-107">Setting the **Root Reference** property may increase performance in the user interface.</span></span> <span data-ttu-id="3ae8c-108">設定**ルート参照**コンパイラがすべてのルート スキーマに対して、c# のクラスを作成するためのパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="3ae8c-108">Setting **Root Reference** improves performance because the compiler creates C# classes for all root schemas.</span></span> <span data-ttu-id="3ae8c-109">単一のルートは、少数のクラスの作成を意味します。</span><span class="sxs-lookup"><span data-stu-id="3ae8c-109">A single root means the creation of fewer classes.</span></span>  
  
 <span data-ttu-id="3ae8c-110">**インスタンスの検証**が表示されるインスタンスを検証する前に、スキーマで検証が常に行われるため、ユーザー インターフェイスの速度の遅い。</span><span class="sxs-lookup"><span data-stu-id="3ae8c-110">**Validate Instance** may appear slow in the user interface because a validation is always done on the schema before validating the instance.</span></span> <span data-ttu-id="3ae8c-111">スキーマの検証は、ユーザー インターフェイスでのみ行われます。</span><span class="sxs-lookup"><span data-stu-id="3ae8c-111">Schema validation occurs only in the user interface.</span></span> <span data-ttu-id="3ae8c-112">設定、**ルート参照**プロパティ ユーザー インターフェイスのパフォーマンスも向上ここでします。</span><span class="sxs-lookup"><span data-stu-id="3ae8c-112">Setting the **Root Reference** property also improves user interface performance in this case.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ae8c-113">参照</span><span class="sxs-lookup"><span data-stu-id="3ae8c-113">See Also</span></span>  
 [<span data-ttu-id="3ae8c-114">BizTalk エディターの使用</span><span class="sxs-lookup"><span data-stu-id="3ae8c-114">Using BizTalk Editor</span></span>](../core/using-biztalk-editor.md)
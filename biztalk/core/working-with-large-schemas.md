---
title: 大規模なスキーマの使用 |Microsoft Docs
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
ms.openlocfilehash: f122d56c5a5632a3d6edcb785968c51f487f0b8b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295372"
---
# <a name="working-with-large-schemas"></a><span data-ttu-id="11cc6-102">大規模なスキーマの使用</span><span class="sxs-lookup"><span data-stu-id="11cc6-102">Working with Large Schemas</span></span>
<span data-ttu-id="11cc6-103">スキーマが非常に大きいになると、XSD ビューの更新がかかり、他のユーザー インターフェイスの応答にも影響できることがあります。</span><span class="sxs-lookup"><span data-stu-id="11cc6-103">When your schemas become very large, you may find that refreshing the XSD view is increasingly slow and that the response of other aspects of the user interface can be impacted as well.</span></span> <span data-ttu-id="11cc6-104">この問題を解決するには自動更新機能をオフにし、代わりに、手動**更新**XSD ビューを定期的に更新する XSD ビューでリンクします。</span><span class="sxs-lookup"><span data-stu-id="11cc6-104">The solution to this issue is to turn off the auto-refresh feature and instead use the manual **Refresh** link in the XSD view to periodically refresh the XSD view.</span></span> <span data-ttu-id="11cc6-105">詳細な手順について有効にするため、自動更新機能をオフの場合、上で XSD ビューの自動更新のオンとオフ"するには」の手順で[XSD ビューの管理](../core/how-to-manage-the-xsd-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="11cc6-105">For step-by-step instructions about how turn the auto-refresh feature on an off, see the procedure "To turn automatic refresh of the XSD view on and off" in [Managing the XSD View](../core/how-to-manage-the-xsd-view.md).</span></span>  
  
 <span data-ttu-id="11cc6-106">パフォーマンスも低下するサイズの大きいスキーマで複数のルートにアタッチされている、**スキーマ**ノード。</span><span class="sxs-lookup"><span data-stu-id="11cc6-106">Performance may also be slow in large schemas with multiple roots attached to the **schema** node.</span></span> <span data-ttu-id="11cc6-107">設定、**ルート参照**プロパティは、ユーザー インターフェイスでのパフォーマンスを向上させることがあります。</span><span class="sxs-lookup"><span data-stu-id="11cc6-107">Setting the **Root Reference** property may increase performance in the user interface.</span></span> <span data-ttu-id="11cc6-108">設定**ルート参照**コンパイラを作成するためのパフォーマンスが向上C#クラスのすべてのスキーマのルートに対して。</span><span class="sxs-lookup"><span data-stu-id="11cc6-108">Setting **Root Reference** improves performance because the compiler creates C# classes for all root schemas.</span></span> <span data-ttu-id="11cc6-109">単一のルートでは、少数のクラスの作成を意味します。</span><span class="sxs-lookup"><span data-stu-id="11cc6-109">A single root means the creation of fewer classes.</span></span>  
  
 <span data-ttu-id="11cc6-110">**インスタンスの検証**が表示されるユーザー インターフェイスのインスタンスを検証する前に、スキーマの検証が常に行われるため、速度の遅い。</span><span class="sxs-lookup"><span data-stu-id="11cc6-110">**Validate Instance** may appear slow in the user interface because a validation is always done on the schema before validating the instance.</span></span> <span data-ttu-id="11cc6-111">スキーマの検証は、ユーザー インターフェイスでのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="11cc6-111">Schema validation occurs only in the user interface.</span></span> <span data-ttu-id="11cc6-112">設定、**ルート参照**プロパティ ユーザー インターフェイスのパフォーマンスも向上ここでします。</span><span class="sxs-lookup"><span data-stu-id="11cc6-112">Setting the **Root Reference** property also improves user interface performance in this case.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11cc6-113">参照</span><span class="sxs-lookup"><span data-stu-id="11cc6-113">See Also</span></span>  
 [<span data-ttu-id="11cc6-114">BizTalk エディターを使用してください。</span><span class="sxs-lookup"><span data-stu-id="11cc6-114">Using BizTalk Editor</span></span>](../core/using-biztalk-editor.md)
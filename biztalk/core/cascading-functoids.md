---
title: カスケード Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functoid types, Cascading
- Cascading functoids
ms.assetid: 03c46e7b-be1c-475e-b68b-f9d1d7732fce
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 020ff5eeb4bed7e5f1c6a09b1757300f2db525e4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357607"
---
# <a name="cascading-functoids"></a><span data-ttu-id="ec577-102">カスケード Functoid</span><span class="sxs-lookup"><span data-stu-id="ec577-102">Cascading Functoids</span></span>
<span data-ttu-id="ec577-103">送信先スキーマのレコードまたはフィールドにリンクする前に、ある Functoid が別の Functoid にリンクしている場合、Functoid が連鎖しているといいます。</span><span class="sxs-lookup"><span data-stu-id="ec577-103">Functoids are said to be cascaded when one functoid is linked to another functoid before it is linked to a record or field in the destination schema.</span></span> <span data-ttu-id="ec577-104">たとえば、2 つの文字列を連結して別の文字列を生成し、送信先スキーマのフィールドに入力する場合に、Functoid の連鎖を作成します。</span><span class="sxs-lookup"><span data-stu-id="ec577-104">For example, you can create cascading functoids in which two concatenated strings produce a third string fed into a field in the destination schema.</span></span>  
  
 <span data-ttu-id="ec577-105">Functoid を連鎖させる場合、グリッド ページに複数の連続する変換を作成できます。</span><span class="sxs-lookup"><span data-stu-id="ec577-105">When you cascade functoids, you can create multiple, consecutive transformations in the grid page.</span></span> <span data-ttu-id="ec577-106">1 ページ内で連鎖する Functoid の数に制限はありませんが、連鎖は効率的に使用してください。</span><span class="sxs-lookup"><span data-stu-id="ec577-106">While there is no limit to the number of functoids that you can cascade in a page, use cascading wisely.</span></span> <span data-ttu-id="ec577-107">複雑な連鎖を使用すると、入力インスタンス メッセージから出力インスタンス メッセージへの変換にかかる時間が長くなり、実行時のパフォーマンスが大幅に低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ec577-107">Complex cascading can increase the time to transform an input instance message into an output instance message, significantly reducing run time performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec577-108">参照</span><span class="sxs-lookup"><span data-stu-id="ec577-108">See Also</span></span>  
 <span data-ttu-id="ec577-109">[マップの Functoid](../core/functoids-in-maps.md) </span><span class="sxs-lookup"><span data-stu-id="ec577-109">[Functoids in Maps](../core/functoids-in-maps.md) </span></span>  
 [<span data-ttu-id="ec577-110">Functoid を使用した複雑なマッピングの作成</span><span class="sxs-lookup"><span data-stu-id="ec577-110">Using Functoids to Create More Complex Mappings</span></span>](../core/using-functoids-to-create-more-complex-mappings.md)
---
title: "エラー - インデックス Functoid にインデックスがありません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.indexFunctoidHasNoIndex
ms.assetid: a523705e-6134-4d98-8ea6-dbfc7b43dae5
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0159d308c9befc90590d281351409ba571921a53
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="error---index-functoid-has-no-index"></a><span data-ttu-id="b6849-102">エラー - インデックス Functoid にインデックスがありません。</span><span class="sxs-lookup"><span data-stu-id="b6849-102">Error - Index Functoid Has No Index</span></span>
<span data-ttu-id="b6849-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="b6849-103">**Error Code**</span></span>  
  
 <span data-ttu-id="b6849-104">btm1014</span><span class="sxs-lookup"><span data-stu-id="b6849-104">btm1014</span></span>  
  
 <span data-ttu-id="b6849-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="b6849-105">**Explanation**</span></span>  
  
 <span data-ttu-id="b6849-106">インデックス値が指定されていない対象**インデックス**functoid です。</span><span class="sxs-lookup"><span data-stu-id="b6849-106">No index value(s) have been provided for the indicated **Index** functoid.</span></span>  
  
 <span data-ttu-id="b6849-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="b6849-107">**User Action**</span></span>  
  
 <span data-ttu-id="b6849-108">対象の適切な数のインデックス入力パラメーターを提供**インデックス**functoid は、適切な数は、ループの数によって決定されます、**レコード**を内のノード、 **フィールド**送信元スキーマ内のノードで入れ子になっています。</span><span class="sxs-lookup"><span data-stu-id="b6849-108">Provide an appropriate number of index input parameters for the indicated **Index** functoid, where the appropriate number is determined by the number of looping **Record** nodes within which the **Field** node in the source schema is nested.</span></span> <span data-ttu-id="b6849-109">インデックス入力パラメーターを作成するには、対象の functoid を選択して、省略記号ボタンをクリックして (**.**) に関連付けられたボタン、**入力パラメーター**プロパティで、Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウで、次を使用して、 ![ ] (../core/media/bts-tls-paraminsert.gif "bts_tls_paraminsert")ボタンを**構成\<Functoid\> Functoid**最初の 1 つが直接の親にインデックスを表す 1 つまたは複数の定数入力パラメーターを追加するダイアログ ボックスループ**レコード**ノード、および後続のインデックス入力パラメーターがますますリモートの祖先のループを表す**レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="b6849-109">To created index input parameters, select the indicated functoid, click the ellipsis (**...**) button associated with the **Input Parameters** property in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, and then use the  ![](../core/media/bts-tls-paraminsert.gif "bts_tls_paraminsert") button within the **Configure \<Functoid\> Functoid** dialog box to add one or more constant input parameters, where the first one represents an index into the immediate parent looping **Record** node, and subsequent index input parameters represent increasingly remote ancestor looping **Record** nodes.</span></span>
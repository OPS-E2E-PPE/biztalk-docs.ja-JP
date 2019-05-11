---
title: エラー - インデックス Functoid にインデックスがありません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.indexFunctoidHasNoIndex
ms.assetid: a523705e-6134-4d98-8ea6-dbfc7b43dae5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74355e4593d542d394cf5408842ed22f37da099f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388815"
---
# <a name="error---index-functoid-has-no-index"></a><span data-ttu-id="921aa-102">エラー - インデックス Functoid にインデックスがありません。</span><span class="sxs-lookup"><span data-stu-id="921aa-102">Error - Index Functoid Has No Index</span></span>
<span data-ttu-id="921aa-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="921aa-103">**Error Code**</span></span>  
  
 <span data-ttu-id="921aa-104">btm1014</span><span class="sxs-lookup"><span data-stu-id="921aa-104">btm1014</span></span>  
  
 <span data-ttu-id="921aa-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="921aa-105">**Explanation**</span></span>  
  
 <span data-ttu-id="921aa-106">インデックス値が指定されていない対象**インデックス**functoid。</span><span class="sxs-lookup"><span data-stu-id="921aa-106">No index value(s) have been provided for the indicated **Index** functoid.</span></span>  
  
 <span data-ttu-id="921aa-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="921aa-107">**User Action**</span></span>  
  
 <span data-ttu-id="921aa-108">対象の適切な数のインデックス入力パラメーターを提供**インデックス**functoid は、ループの数によって、適切な数の決まり**レコード**を内のノード、 **フィールド**送信元スキーマ内のノードが入れ子になった。</span><span class="sxs-lookup"><span data-stu-id="921aa-108">Provide an appropriate number of index input parameters for the indicated **Index** functoid, where the appropriate number is determined by the number of looping **Record** nodes within which the **Field** node in the source schema is nested.</span></span> <span data-ttu-id="921aa-109">インデックス入力パラメーターを作成するには、対象の functoid を選択して、省略記号をクリックします (**.**) ボタンに関連付けられている、**入力パラメーター**プロパティで、Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウ、およびしを使用して、 ![](../core/media/bts-tls-paraminsert.gif "bts_tls_paraminsert")内でボタン、**構成\<Functoid\> Functoid**が 1 つ目は直接の親にインデックスを表す 1 つまたは複数の定数入力パラメーターを追加する ダイアログ ボックスループ**レコード**ノード、および後続のインデックス入力パラメーターがますますリモートの祖先のループを表す**レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="921aa-109">To created index input parameters, select the indicated functoid, click the ellipsis (**...**) button associated with the **Input Parameters** property in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, and then use the  ![](../core/media/bts-tls-paraminsert.gif "bts_tls_paraminsert") button within the **Configure \<Functoid\> Functoid** dialog box to add one or more constant input parameters, where the first one represents an index into the immediate parent looping **Record** node, and subsequent index input parameters represent increasingly remote ancestor looping **Record** nodes.</span></span>
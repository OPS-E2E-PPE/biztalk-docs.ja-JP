---
title: "エラー - インデックス Functoid にインデックスが多すぎる |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.indexFunctoidHasTooManyIndices
ms.assetid: 5dd2d5b4-3f7a-45be-b6f4-708b0a76805a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a22b49a921b957c0fb36f9e6b6925c991cc3cf6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="error---index-functoid-has-too-many-indexes"></a><span data-ttu-id="756b9-102">エラー - インデックス Functoid にインデックスが多すぎます</span><span class="sxs-lookup"><span data-stu-id="756b9-102">Error - Index Functoid Has Too Many Indexes</span></span>
<span data-ttu-id="756b9-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="756b9-103">**Error Code**</span></span>  
  
 <span data-ttu-id="756b9-104">btm1016</span><span class="sxs-lookup"><span data-stu-id="756b9-104">btm1016</span></span>  
  
 <span data-ttu-id="756b9-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="756b9-105">**Explanation**</span></span>  
  
 <span data-ttu-id="756b9-106">指定された**インデックス**functoid が多すぎますインデックス入力パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="756b9-106">The indicated **Index** functoid has too many index input parameters specified.</span></span> <span data-ttu-id="756b9-107">インデックス入力パラメーターの数が、祖先のループの数を超えない**レコード**を内のノード、**フィールド**最初の入力パラメーターが入れ子になったとして指定されたノード。</span><span class="sxs-lookup"><span data-stu-id="756b9-107">The number of index input parameters must not exceed the number of ancestor looping **Record** nodes within which the **Field** node specified as the first input parameter is nested.</span></span>  
  
 <span data-ttu-id="756b9-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="756b9-108">**User Action**</span></span>  
  
 <span data-ttu-id="756b9-109">選択し**インデックス**functoid は、省略記号ボタン (**.**) に関連付けられたボタン、**入力パラメーター**プロパティで、Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウにし、**構成\<Functoid\>Functoid**ダイアログ ボックスで、削除を選択しをクリックすると、余分なインデックス入力パラメーター、 ![ ] (../core/media/bts-tls-paramdelete.gif "bts_tls_paramdelete")それぞれのボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="756b9-109">Select the indicated **Index** functoid, click the ellipsis (**...**) button associated with the **Input Parameters** property in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, and then in the **Configure \<Functoid\> Functoid** dialog box, delete the excess index input parameters by selecting and clicking the  ![](../core/media/bts-tls-paramdelete.gif "bts_tls_paramdelete") button for each of them.</span></span>
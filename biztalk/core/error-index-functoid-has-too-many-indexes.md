---
title: エラー - インデックス Functoid のインデックスが多すぎますが |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.indexFunctoidHasTooManyIndices
ms.assetid: 5dd2d5b4-3f7a-45be-b6f4-708b0a76805a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 800d8ca920dac64ee2d9c603bfcb949188824764
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348137"
---
# <a name="error---index-functoid-has-too-many-indexes"></a><span data-ttu-id="39b1e-102">エラー - インデックス Functoid にインデックスが多すぎます</span><span class="sxs-lookup"><span data-stu-id="39b1e-102">Error - Index Functoid Has Too Many Indexes</span></span>
<span data-ttu-id="39b1e-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="39b1e-103">**Error Code**</span></span>  
  
 <span data-ttu-id="39b1e-104">btm1016</span><span class="sxs-lookup"><span data-stu-id="39b1e-104">btm1016</span></span>  
  
 <span data-ttu-id="39b1e-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="39b1e-105">**Explanation**</span></span>  
  
 <span data-ttu-id="39b1e-106">指定された**インデックス**functoid が多すぎるインデックス入力パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="39b1e-106">The indicated **Index** functoid has too many index input parameters specified.</span></span> <span data-ttu-id="39b1e-107">インデックス入力パラメーターの数が、祖先のループの数を超えない**レコード**を内のノード、**フィールド**最初の入力パラメーターが入れ子になったように指定されたノード。</span><span class="sxs-lookup"><span data-stu-id="39b1e-107">The number of index input parameters must not exceed the number of ancestor looping **Record** nodes within which the **Field** node specified as the first input parameter is nested.</span></span>  
  
 <span data-ttu-id="39b1e-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="39b1e-108">**User Action**</span></span>  
  
 <span data-ttu-id="39b1e-109">選択**インデックス**functoid は、省略記号をクリックします (**.**) ボタンに関連付けられている、**入力パラメーター**プロパティで、Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウで、し、**構成\<Functoid\>Functoid**ダイアログ ボックスで、余分なインデックス入力パラメーターを選択してクリックすると削除、 ![](../core/media/bts-tls-paramdelete.gif "bts_tls_paramdelete")それぞれのボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="39b1e-109">Select the indicated **Index** functoid, click the ellipsis (**...**) button associated with the **Input Parameters** property in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, and then in the **Configure \<Functoid\> Functoid** dialog box, delete the excess index input parameters by selecting and clicking the  ![](../core/media/bts-tls-paramdelete.gif "bts_tls_paramdelete") button for each of them.</span></span>
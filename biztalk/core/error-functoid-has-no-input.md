---
title: "エラー - Functoid に入力がありません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.functiodHasNoInput
ms.assetid: ea59b902-953d-4a5f-aa28-dbaa0a017dca
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: edf8f6b74fb6aa69c0b822b07e8f712ea9a5007b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="error---functoid-has-no-input"></a><span data-ttu-id="bfc0c-102">エラー - Functoid に入力がありません。</span><span class="sxs-lookup"><span data-stu-id="bfc0c-102">Error - Functoid Has No Input</span></span>
<span data-ttu-id="bfc0c-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="bfc0c-103">**Error Code**</span></span>  
  
 <span data-ttu-id="bfc0c-104">btm1012</span><span class="sxs-lookup"><span data-stu-id="bfc0c-104">btm1012</span></span>  
  
 <span data-ttu-id="bfc0c-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="bfc0c-105">**Explanation**</span></span>  
  
 <span data-ttu-id="bfc0c-106">Functoid には少なくとも 1 つの入力パラメーターが必要ですが、入力パラメーターが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="bfc0c-106">The indicated functoid requires at least one input parameter, but no input parameters have been specified.</span></span>  
  
 <span data-ttu-id="bfc0c-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="bfc0c-107">**User Action**</span></span>  
  
 <span data-ttu-id="bfc0c-108">次のうちの 1 つまたは両方の方法を使用して、Functoid に適切な数の入力パラメーターを指定します。その際、想定されている入力パラメーターの順序に特に注意してください。</span><span class="sxs-lookup"><span data-stu-id="bfc0c-108">Use one or both of the following methods to provide the appropriate number of input parameters to the indicated functoid, paying particular attention to the expected order of input parameters:</span></span>  
  
-   <span data-ttu-id="bfc0c-109">送信元スキーマまたは他の Functoid の出力のいずれかのノードと対象の Functoid の間でドラッグしてリンクを作成します。他の Functoid とは、マップ グリッド ページで対象の Functoid の左側に表示されている Functoid を指します。</span><span class="sxs-lookup"><span data-stu-id="bfc0c-109">Drag to create links between the indicated functoid and either nodes in the source schema or the output of other functoids that are located to the left of the indicated functoid in a map grid page.</span></span>  
  
-   <span data-ttu-id="bfc0c-110">対象の functoid を選択し、省略記号ボタン (**.**) に関連付けられたボタン、**入力パラメーター**プロパティで、Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウを構成してで、入力パラメーターの順序を変更、**構成\<Functoid\> Functoid**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="bfc0c-110">Select the indicated functoid, click the ellipsis (**...**) button associated with the **Input Parameters** property in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, and then configure and rearrange the order of the input parameters in the **Configure \<Functoid\> Functoid** dialog box.</span></span> <span data-ttu-id="bfc0c-111">このダイアログ ボックスでは、定数入力パラメーターを作成して値を設定し、他の入力パラメーターを考慮したうえで適切な順序に配置できます。</span><span class="sxs-lookup"><span data-stu-id="bfc0c-111">Constant input parameters can be created, given values, and put in the proper order relative to the other input parameters in this dialog box.</span></span>
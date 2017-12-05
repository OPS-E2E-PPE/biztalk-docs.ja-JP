---
title: "エラー - 累積 Functoid の無効を 2 番目の入力 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.secondInputToCumulativeNotValid
ms.assetid: e41a58a7-e0a2-4284-bd19-279578a8915d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0228beda57b961d515471e42760abe3ab92db54
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="error---second-input-to-cumulative-functoid-not-valid"></a><span data-ttu-id="0c71e-102">エラー - 累積 Functoid の無効を 2 番目の入力</span><span class="sxs-lookup"><span data-stu-id="0c71e-102">Error - Second Input to Cumulative Functoid Not Valid</span></span>
<span data-ttu-id="0c71e-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="0c71e-103">**Error Code**</span></span>  
  
 <span data-ttu-id="0c71e-104">btm1031</span><span class="sxs-lookup"><span data-stu-id="0c71e-104">btm1031</span></span>  
  
 <span data-ttu-id="0c71e-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="0c71e-105">**Explanation**</span></span>  
  
 <span data-ttu-id="0c71e-106">指定された**累積**functoid が、2 番目の入力パラメーターが無効です。</span><span class="sxs-lookup"><span data-stu-id="0c71e-106">The indicated **Cumulative** functoid has a second input parameter that is not valid.</span></span> <span data-ttu-id="0c71e-107">累積 Functoid への 2 番目の入力パラメーターは、送信元スキーマ内の累積の実行対象の範囲を示す正の整数である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c71e-107">The second input parameter to cumulative functoids must be a positive integer that indicates the range within the source schema over which the accumulation will be performed.</span></span>  
  
 <span data-ttu-id="0c71e-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="0c71e-108">**User Action**</span></span>  
  
 <span data-ttu-id="0c71e-109">選択し**累積的な**functoid は、省略記号ボタン (**.**) に関連付けられたボタン、 **Functoid 入力の順序**プロパティで、Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウにし、**構成\<Functoid\>Functoid**  ダイアログ ボックスを確実に 2 番目の入力パラメーター、存在する場合、正の整数。</span><span class="sxs-lookup"><span data-stu-id="0c71e-109">Select the indicated **Cumulative** functoid, click the ellipsis (**...**) button associated with the **Order Functoid Inputs** property in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, and then in the **Configure \<Functoid\> Functoid** dialog box, ensure that the second input parameter, if any, is a positive integer.</span></span>
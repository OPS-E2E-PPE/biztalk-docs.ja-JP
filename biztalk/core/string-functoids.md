---
title: 文字列 Functoid |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d73be02-9c93-481f-81e4-39b60bcfa2df
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06bcb1d42a5e72a57765d17c18a48b6f4808d412
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278530"
---
# <a name="string-functoids"></a><span data-ttu-id="6435d-102">文字列 Functoid</span><span class="sxs-lookup"><span data-stu-id="6435d-102">String Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="6435d-103">概要</span><span class="sxs-lookup"><span data-stu-id="6435d-103">Overview</span></span>
<span data-ttu-id="6435d-104">**文字列**functoid はすべて大文字または小文字ではすべて、文字列の連結、文字列の長さ、トリミング、空白文字への変換などの標準的な方法で文字列を操作するために使用します。</span><span class="sxs-lookup"><span data-stu-id="6435d-104">**String** functoids are used to manipulate strings in standard ways such as conversions to all uppercase or all lowercase, string concatenation, determination of string length, white space trimming, and so on.</span></span>  
  
 <span data-ttu-id="6435d-105">Functoid**大文字**、**小文字**、**サイズ**、**文字列右スペース削除**、および**文字列左スペース削除**1 つしか入力パラメーターを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="6435d-105">The functoids **Uppercase**, **Lowercase**, **Size**, **String Right Trim**, and **String Left Trim** accept only one input parameter.</span></span> <span data-ttu-id="6435d-106">Functoid**文字列位置検出**、**左文字列抽出**、および**右文字列抽出**2 つの入力パラメーターを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="6435d-106">The functoids **String Find**, **String Left**, and **String Right** accept two input parameters.</span></span> <span data-ttu-id="6435d-107">**文字列抽出**functoid は 3 つの入力を受け取りませんが、**文字列連結**functoid は 1 ~ 100 の範囲の入力パラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="6435d-107">The **String Extract** functoid accepts three inputs, whereas the **String Concatenate** functoid accepts input parameters between 1 and 100.</span></span>  
  
 <span data-ttu-id="6435d-108">2 つ**文字列**functoid は、文字列の文字の数値の位置を参照してください:**文字列抽出**と**文字列位置検出**です。</span><span class="sxs-lookup"><span data-stu-id="6435d-108">Two **String** functoids refer to the numeric position of a character in a string: **String Extract** and **String Find**.</span></span> <span data-ttu-id="6435d-109">これらの Functoid は、文字位置を 1 (0 ではない) からカウントします。</span><span class="sxs-lookup"><span data-stu-id="6435d-109">These functoids begin counting character positions at 1, not 0.</span></span>  
  
 <span data-ttu-id="6435d-110">2 つ文字列を切り捨てる functoid、**文字列左スペース削除**と**文字列右スペース削除**、すべての空白文字 (スペース、タブ、およびなど) から削除左または右 (場合もあります)、指定した文字列の。</span><span class="sxs-lookup"><span data-stu-id="6435d-110">The two string trimming functoids, **String Left Trim** and **String Right Trim**, remove all white space characters (spaces, tabs, and so on) from the left  or right (as the case may be) of the specified string.</span></span>  

## <a name="available-functoids"></a><span data-ttu-id="6435d-111">使用可能な functoid</span><span class="sxs-lookup"><span data-stu-id="6435d-111">Available functoids</span></span> 
 <span data-ttu-id="6435d-112">**文字列**functoid には。</span><span class="sxs-lookup"><span data-stu-id="6435d-112">The **String** functoids are:</span></span> 

* <span data-ttu-id="6435d-113">小文字</span><span class="sxs-lookup"><span data-stu-id="6435d-113">Lowercase</span></span>
* <span data-ttu-id="6435d-114">サイズ</span><span class="sxs-lookup"><span data-stu-id="6435d-114">Size</span></span>
* <span data-ttu-id="6435d-115">文字列連結します。</span><span class="sxs-lookup"><span data-stu-id="6435d-115">String Concatenate</span></span>
* <span data-ttu-id="6435d-116">文字列抽出</span><span class="sxs-lookup"><span data-stu-id="6435d-116">String Extract</span></span>
* <span data-ttu-id="6435d-117">文字列位置検出</span><span class="sxs-lookup"><span data-stu-id="6435d-117">String Find</span></span>
* <span data-ttu-id="6435d-118">左文字列抽出</span><span class="sxs-lookup"><span data-stu-id="6435d-118">String Left</span></span>
* <span data-ttu-id="6435d-119">文字列左スペース削除</span><span class="sxs-lookup"><span data-stu-id="6435d-119">String Left Trim</span></span>
* <span data-ttu-id="6435d-120">右文字列抽出</span><span class="sxs-lookup"><span data-stu-id="6435d-120">String Right</span></span>
* <span data-ttu-id="6435d-121">文字列右スペース削除</span><span class="sxs-lookup"><span data-stu-id="6435d-121">String Right Trim</span></span>
* <span data-ttu-id="6435d-122">大文字</span><span class="sxs-lookup"><span data-stu-id="6435d-122">Uppercase</span></span>

<span data-ttu-id="6435d-123">これらの functoid の詳細について[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="6435d-123">More details on these functoids [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6435d-124">参照</span><span class="sxs-lookup"><span data-stu-id="6435d-124">See Also</span></span>  
-  [<span data-ttu-id="6435d-125">マップに基本 Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="6435d-125">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)   
-  <span data-ttu-id="6435d-126">**文字列 Functoid のリファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="6435d-126">**String Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
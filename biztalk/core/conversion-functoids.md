---
title: "変換 Functoid |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0cd7abcf-f524-4e85-b8d5-d6123767490f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 192db4b03f80674f2eb90be2255a8682454bde2b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="conversion-functoids"></a><span data-ttu-id="f57cc-102">変換 Functoid</span><span class="sxs-lookup"><span data-stu-id="f57cc-102">Conversion Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="f57cc-103">概要</span><span class="sxs-lookup"><span data-stu-id="f57cc-103">Overview</span></span>
<span data-ttu-id="f57cc-104">**変換**functoid を使用して番号と、ASCII の同等の間で変換して、基数 8 ベースの 10 個の番号に変換および 16 進の基本します。</span><span class="sxs-lookup"><span data-stu-id="f57cc-104">**Conversion** functoids are used to convert between numbers and their ASCII equivalents, and to convert base 10 numbers to their base 8 and base 16 equivalents.</span></span>  
  
 <span data-ttu-id="f57cc-105">すべての変換 Functoid は単一の入力パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f57cc-105">All of the conversion functoids take a single input parameter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f57cc-106">基になる型システムでの変更により、**変換**このバージョンの BizTalk マッパーの functoid は、以前のバージョンで作成されるものよりも若干異なる結果を生成します。</span><span class="sxs-lookup"><span data-stu-id="f57cc-106">Due to changes in the underlying type system, the **Conversion** functoids in this version of BizTalk Mapper produce slightly different results than those produced in previous versions.</span></span> <span data-ttu-id="f57cc-107">たとえば、以前のバージョンの BizTalk マッパー、入力値-20 を**16 進**0xFFEC の出力に functoid が発生しました。</span><span class="sxs-lookup"><span data-stu-id="f57cc-107">For example, in previous versions of BizTalk Mapper an input value of -20 to the **Hexadecimal** functoid resulted in an output of 0xFFEC.</span></span> <span data-ttu-id="f57cc-108">今回のバージョンでは、同じ入力値 -20 で 0xFFFFFFEC という出力になります。</span><span class="sxs-lookup"><span data-stu-id="f57cc-108">In this version, the same input value of -20 will result in an output of 0xFFFFFFEC.</span></span>  

## <a name="available-functoids"></a><span data-ttu-id="f57cc-109">使用可能な functoid</span><span class="sxs-lookup"><span data-stu-id="f57cc-109">Available functoids</span></span>  
 <span data-ttu-id="f57cc-110">**変換**functoid には。</span><span class="sxs-lookup"><span data-stu-id="f57cc-110">The **Conversion** functoids are:</span></span> 

* <span data-ttu-id="f57cc-111">値の ASCII 文字化</span><span class="sxs-lookup"><span data-stu-id="f57cc-111">ASCII to Character</span></span>
* <span data-ttu-id="f57cc-112">文字の ASCII 値算出</span><span class="sxs-lookup"><span data-stu-id="f57cc-112">Character to ASCII</span></span>
* <span data-ttu-id="f57cc-113">16 進数</span><span class="sxs-lookup"><span data-stu-id="f57cc-113">Hexadecimal</span></span>
* <span data-ttu-id="f57cc-114">8 進変換</span><span class="sxs-lookup"><span data-stu-id="f57cc-114">Octal</span></span>

<span data-ttu-id="f57cc-115">これらの functoid が説明されている[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="f57cc-115">These functoids are described [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 

## <a name="see-also"></a><span data-ttu-id="f57cc-116">参照</span><span class="sxs-lookup"><span data-stu-id="f57cc-116">See Also</span></span>  
 [<span data-ttu-id="f57cc-117">マップに基本 Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="f57cc-117">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)   

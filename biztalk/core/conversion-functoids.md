---
title: 変換 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0cd7abcf-f524-4e85-b8d5-d6123767490f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b042428f3a67227db6fb53966149458bc279926
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390247"
---
# <a name="conversion-functoids"></a><span data-ttu-id="54ea1-102">変換 Functoid</span><span class="sxs-lookup"><span data-stu-id="54ea1-102">Conversion Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="54ea1-103">概要</span><span class="sxs-lookup"><span data-stu-id="54ea1-103">Overview</span></span>
<span data-ttu-id="54ea1-104">**変換**番号と、ASCII 値の間で変換して、基数 8 を 10 進数に変換し、16 進の基本 functoid を使用します。</span><span class="sxs-lookup"><span data-stu-id="54ea1-104">**Conversion** functoids are used to convert between numbers and their ASCII equivalents, and to convert base 10 numbers to their base 8 and base 16 equivalents.</span></span>  
  
 <span data-ttu-id="54ea1-105">すべての変換 functoid は、1 つの入力パラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="54ea1-105">All of the conversion functoids take a single input parameter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54ea1-106">基になる型システムでの変更により、**変換**このバージョンの BizTalk マッパーの functoid は、以前のバージョンで生成されたものよりもわずかに異なる結果を生成します。</span><span class="sxs-lookup"><span data-stu-id="54ea1-106">Due to changes in the underlying type system, the **Conversion** functoids in this version of BizTalk Mapper produce slightly different results than those produced in previous versions.</span></span> <span data-ttu-id="54ea1-107">たとえば、以前のバージョンの BizTalk マッパーの入力値-20 でに、 **16 進数**functoid 0xFFEC の出力が発生しました。</span><span class="sxs-lookup"><span data-stu-id="54ea1-107">For example, in previous versions of BizTalk Mapper an input value of -20 to the **Hexadecimal** functoid resulted in an output of 0xFFEC.</span></span> <span data-ttu-id="54ea1-108">このバージョンでは、同じ入力値-20 0xFFFFFFEC の出力になります。</span><span class="sxs-lookup"><span data-stu-id="54ea1-108">In this version, the same input value of -20 will result in an output of 0xFFFFFFEC.</span></span>  

## <a name="available-functoids"></a><span data-ttu-id="54ea1-109">使用可能な functoid</span><span class="sxs-lookup"><span data-stu-id="54ea1-109">Available functoids</span></span>  
 <span data-ttu-id="54ea1-110">**変換**functoid には。</span><span class="sxs-lookup"><span data-stu-id="54ea1-110">The **Conversion** functoids are:</span></span> 

* <span data-ttu-id="54ea1-111">値の ASCII 文字</span><span class="sxs-lookup"><span data-stu-id="54ea1-111">ASCII to Character</span></span>
* <span data-ttu-id="54ea1-112">ASCII 文字</span><span class="sxs-lookup"><span data-stu-id="54ea1-112">Character to ASCII</span></span>
* <span data-ttu-id="54ea1-113">16 進数</span><span class="sxs-lookup"><span data-stu-id="54ea1-113">Hexadecimal</span></span>
* <span data-ttu-id="54ea1-114">8 進数</span><span class="sxs-lookup"><span data-stu-id="54ea1-114">Octal</span></span>

<span data-ttu-id="54ea1-115">これらの functoid が説明されている[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="54ea1-115">These functoids are described [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 

## <a name="see-also"></a><span data-ttu-id="54ea1-116">参照</span><span class="sxs-lookup"><span data-stu-id="54ea1-116">See Also</span></span>  
 [<span data-ttu-id="54ea1-117">マップに基本 Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="54ea1-117">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)   

---
title: 日付と時刻 Functoid |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2e2d49f5-1aaf-4e4d-8da1-e8605304dccb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ec31607ecefb417fef597b5ba700e6461c71a2f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238522"
---
# <a name="date-and-time-functoids"></a><span data-ttu-id="a44fa-102">日付と時刻 Functoid</span><span class="sxs-lookup"><span data-stu-id="a44fa-102">Date and Time Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="a44fa-103">概要</span><span class="sxs-lookup"><span data-stu-id="a44fa-103">Overview</span></span>
<span data-ttu-id="a44fa-104">**日付/時刻**functoid は 2 つのカテゴリに分けることができます。</span><span class="sxs-lookup"><span data-stu-id="a44fa-104">**Date / Time** functoids can be divided into two categories.</span></span> <span data-ttu-id="a44fa-105">最初のカテゴリには、1 つの functoid が含まれています。**日数加算**、を使用して、指定した日付と時刻の値を指定した日数を追加します。</span><span class="sxs-lookup"><span data-stu-id="a44fa-105">The first category contains a single functoid, **Add Days**, which is used to add a specified number of days to a specified date and time value.</span></span> <span data-ttu-id="a44fa-106">これは、出力インスタンス メッセージのフィールドが将来の日時の推定値を含む場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a44fa-106">This can be useful when a field in the output instance message is supposed to include a date and time estimate in the future.</span></span> <span data-ttu-id="a44fa-107">たとえば、**日数加算**見積もりを生成する functoid を使用することができます、注文を受け取った日付からの固定の差分に基づいて出荷日。</span><span class="sxs-lookup"><span data-stu-id="a44fa-107">For example, the **Add Days** functoid can be used to generate an estimated shipping date based a fixed delta from the date that an order was received.</span></span>  
  
 <span data-ttu-id="a44fa-108">2 番目のカテゴリには、すべての残りの functoid が含まれています、**日付と時刻**カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="a44fa-108">The second category includes all of the remaining functoids in the **Date and Time** category.</span></span> <span data-ttu-id="a44fa-109">これらの Functoid を使用して実行時にタイムスタンプを提供することで、メッセージ変換が行われる日時を出力インスタンス メッセージに格納できます。</span><span class="sxs-lookup"><span data-stu-id="a44fa-109">They are used to provide a timestamp at run time, so that the date and time at which message transformation is being performed can be included in the output instance message.</span></span>  
  
 <span data-ttu-id="a44fa-110">**日数加算**functoid が、2 つの入力パラメーターを受け入れる、**日付**、**日付と時刻**、および**時間**functoid に入力いるなしパラメーター。</span><span class="sxs-lookup"><span data-stu-id="a44fa-110">The **Add Days** functoid accepts two input parameters, whereas the **Date**, **Date and Time**, and **Time** functoids have no input parameters.</span></span>  

## <a name="available-functoids"></a><span data-ttu-id="a44fa-111">使用可能な functoid</span><span class="sxs-lookup"><span data-stu-id="a44fa-111">Available functoids</span></span>  
 <span data-ttu-id="a44fa-112">**日付/時刻**functoid には。</span><span class="sxs-lookup"><span data-stu-id="a44fa-112">The **Date / Time** functoids are:</span></span> 

* <span data-ttu-id="a44fa-113">日数加算</span><span class="sxs-lookup"><span data-stu-id="a44fa-113">Add Days</span></span>
* <span data-ttu-id="a44fa-114">日付</span><span class="sxs-lookup"><span data-stu-id="a44fa-114">Date</span></span>
* <span data-ttu-id="a44fa-115">日時</span><span class="sxs-lookup"><span data-stu-id="a44fa-115">Date and Time</span></span>
* <span data-ttu-id="a44fa-116">[時刻]</span><span class="sxs-lookup"><span data-stu-id="a44fa-116">Time</span></span>

<span data-ttu-id="a44fa-117">これらの functoid の詳細については、使用可能な**Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="a44fa-117">More details on these functoids are available **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a44fa-118">参照</span><span class="sxs-lookup"><span data-stu-id="a44fa-118">See Also</span></span>  
-  [<span data-ttu-id="a44fa-119">マップに基本 Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="a44fa-119">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)   
-  <span data-ttu-id="a44fa-120">**日時 Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="a44fa-120">**Date and Time Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
---
title: 退避の計算のサンプル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4da41d0d-10ee-4f64-97d1-3cfa9da153f7
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77701083272da9e09c21cb05daf3c4e9764b604c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993043"
---
# <a name="sample-dehydration-calculation"></a><span data-ttu-id="8dab2-102">退避の計算のサンプル</span><span class="sxs-lookup"><span data-stu-id="8dab2-102">Sample Dehydration Calculation</span></span>
<span data-ttu-id="8dab2-103">次に示す例は、BizTalk が退避するかどうかをプライベート バイトを使用して計算するサンプルです。</span><span class="sxs-lookup"><span data-stu-id="8dab2-103">Here is an example of a sample calculation, using private bytes, to determine if BizTalk will dehydrate or not.</span></span> <span data-ttu-id="8dab2-104">ここでは、既定の構成値と、いくつかの実行時値の例を使用します。</span><span class="sxs-lookup"><span data-stu-id="8dab2-104">It uses the default configured values, and some example run-time values.</span></span>  
  
 <span data-ttu-id="8dab2-105">退避プロパティとしては次の値を想定します。</span><span class="sxs-lookup"><span data-stu-id="8dab2-105">Assume the following values for the dehydration properties:</span></span>  
  
- <span data-ttu-id="8dab2-106">**TimeBlocked** = 60 (秒単位でブロック時間の例である場合)</span><span class="sxs-lookup"><span data-stu-id="8dab2-106">**TimeBlocked** = 60 (example time blocked in seconds)</span></span>  
  
- <span data-ttu-id="8dab2-107">**WaitingHistory** = 90 (秒単位で待機している履歴を例)</span><span class="sxs-lookup"><span data-stu-id="8dab2-107">**WaitingHistory** = 90 (example waiting history in seconds)</span></span>  
  
- <span data-ttu-id="8dab2-108">**ActualPrivateBytes** = 250 (プライベート バイトの値の例)</span><span class="sxs-lookup"><span data-stu-id="8dab2-108">**ActualPrivateBytes** = 250 (example value for private bytes)</span></span>  
  
- <span data-ttu-id="8dab2-109">**OptimalUsage** = 50 (既定の構成値)</span><span class="sxs-lookup"><span data-stu-id="8dab2-109">**OptimalUsage** = 50 (default configuration value)</span></span>  
  
- <span data-ttu-id="8dab2-110">**MaximalUsage** = 350 (既定の構成値)</span><span class="sxs-lookup"><span data-stu-id="8dab2-110">**MaximalUsage** = 350 (default configuration value)</span></span>  
  
  <span data-ttu-id="8dab2-111">以降、 **ActualPrivateBytes**間**OptimalUsage**と**MaximalUsage**アルファとして計算されます。</span><span class="sxs-lookup"><span data-stu-id="8dab2-111">Since the **ActualPrivateBytes** are between **OptimalUsage** and **MaximalUsage**, alpha is calculated as:</span></span>  
  
```  
alpha(private) = (350 – 250) / 350 – 50)  
alpha(private) = 100 / 300  
alpha(private) = 0.33  
```  
  
 <span data-ttu-id="8dab2-112">計算し、 **TestThreshold**次のようにします。</span><span class="sxs-lookup"><span data-stu-id="8dab2-112">Then you calculate the **TestThreshold** as follows:</span></span>  
  
```  
TestThreshold = 1 + (0.33 * (1800 – 1))  
TestThreshold = 1 + 599.66  
TestThreshold = 600.66  
```  
  
 <span data-ttu-id="8dab2-113">最後に、退避するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="8dab2-113">And finally, make the decision to dehydrate or not:</span></span>  
  
```  
Dehydrate = (90 == -1 OR 90 > 600 OR 60 > (2 * 600))  
Dehydrate = false  
```  
  
 <span data-ttu-id="8dab2-114">この例を使用すると、オーケストレーションはこの時点では退避されないと判断できます。</span><span class="sxs-lookup"><span data-stu-id="8dab2-114">Using this example, you can determine that the orchestration will not be dehydrated at this time.</span></span>
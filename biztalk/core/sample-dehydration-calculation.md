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
ms.openlocfilehash: 025d83e8a7bd6c5a3c324bd5dae8354ac43321ed
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393906"
---
# <a name="sample-dehydration-calculation"></a><span data-ttu-id="d7bca-102">退避の計算のサンプル</span><span class="sxs-lookup"><span data-stu-id="d7bca-102">Sample Dehydration Calculation</span></span>
<span data-ttu-id="d7bca-103">プライベート (バイト単位) を使用していない、または BizTalk が退避を決定する、サンプルの計算の例を示します。</span><span class="sxs-lookup"><span data-stu-id="d7bca-103">Here is an example of a sample calculation, using private bytes, to determine if BizTalk will dehydrate or not.</span></span> <span data-ttu-id="d7bca-104">既定の構成値、およびいくつかの例の実行時値を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7bca-104">It uses the default configured values, and some example run-time values.</span></span>  
  
 <span data-ttu-id="d7bca-105">次の退避プロパティの値があるとします。</span><span class="sxs-lookup"><span data-stu-id="d7bca-105">Assume the following values for the dehydration properties:</span></span>  
  
- <span data-ttu-id="d7bca-106">**TimeBlocked** = 60 (秒単位でブロック時間の例である場合)</span><span class="sxs-lookup"><span data-stu-id="d7bca-106">**TimeBlocked** = 60 (example time blocked in seconds)</span></span>  
  
- <span data-ttu-id="d7bca-107">**WaitingHistory** = 90 (秒単位で待機している履歴を例)</span><span class="sxs-lookup"><span data-stu-id="d7bca-107">**WaitingHistory** = 90 (example waiting history in seconds)</span></span>  
  
- <span data-ttu-id="d7bca-108">**ActualPrivateBytes** = 250 (プライベート バイトの値の例)</span><span class="sxs-lookup"><span data-stu-id="d7bca-108">**ActualPrivateBytes** = 250 (example value for private bytes)</span></span>  
  
- <span data-ttu-id="d7bca-109">**OptimalUsage** = 50 (既定の構成値)</span><span class="sxs-lookup"><span data-stu-id="d7bca-109">**OptimalUsage** = 50 (default configuration value)</span></span>  
  
- <span data-ttu-id="d7bca-110">**MaximalUsage** = 350 (既定の構成値)</span><span class="sxs-lookup"><span data-stu-id="d7bca-110">**MaximalUsage** = 350 (default configuration value)</span></span>  
  
  <span data-ttu-id="d7bca-111">以降、 **ActualPrivateBytes**間**OptimalUsage**と**MaximalUsage**アルファとして計算されます。</span><span class="sxs-lookup"><span data-stu-id="d7bca-111">Since the **ActualPrivateBytes** are between **OptimalUsage** and **MaximalUsage**, alpha is calculated as:</span></span>  
  
```  
alpha(private) = (350 – 250) / 350 – 50)  
alpha(private) = 100 / 300  
alpha(private) = 0.33  
```  
  
 <span data-ttu-id="d7bca-112">計算し、 **TestThreshold**次のようにします。</span><span class="sxs-lookup"><span data-stu-id="d7bca-112">Then you calculate the **TestThreshold** as follows:</span></span>  
  
```  
TestThreshold = 1 + (0.33 * (1800 – 1))  
TestThreshold = 1 + 599.66  
TestThreshold = 600.66  
```  
  
 <span data-ttu-id="d7bca-113">最後に、かどうかを退避するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d7bca-113">And finally, make the decision to dehydrate or not:</span></span>  
  
```  
Dehydrate = (90 == -1 OR 90 > 600 OR 60 > (2 * 600))  
Dehydrate = false  
```  
  
 <span data-ttu-id="d7bca-114">この例を使用して、オーケストレーションができないこと退避この時点で確認できます。</span><span class="sxs-lookup"><span data-stu-id="d7bca-114">Using this example, you can determine that the orchestration will not be dehydrated at this time.</span></span>
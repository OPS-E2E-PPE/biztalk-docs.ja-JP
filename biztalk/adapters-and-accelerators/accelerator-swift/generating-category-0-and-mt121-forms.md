---
title: カテゴリ 0 と MT121 フォームの生成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1470b8e1-0008-4f15-8958-ba4c7ecbffd8
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15f79784a227833695068681e1738d901f263680
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377626"
---
# <a name="generating-category-0-and-mt121-forms"></a><span data-ttu-id="f509f-102">カテゴリ 0 と MT121 フォームを生成します。</span><span class="sxs-lookup"><span data-stu-id="f509f-102">Generating Category 0 and MT121 Forms</span></span>
<span data-ttu-id="f509f-103">カテゴリ 0 と MT121 InfoPath フォームの生成 別のテンプレート ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="f509f-103">Category 0 and MT121 InfoPath forms generation require different template files.</span></span> <span data-ttu-id="f509f-104">カテゴリ 0 フォームは、5 つのカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="f509f-104">Category 0 forms are divided into 5 categories.</span></span> <span data-ttu-id="f509f-105">MT のカテゴリの残りの部分と同じ方法での一般的なカテゴリのメッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="f509f-105">General categories messages are generated in the same way as do the rest of the MT categories.</span></span> <span data-ttu-id="f509f-106">そのメッセージの名前を持つその他の 4 つのカテゴリの例を示しましょう。</span><span class="sxs-lookup"><span data-stu-id="f509f-106">Examples of other 4 categories with their message names are given below:</span></span>  
  
-   <span data-ttu-id="f509f-107">**カテゴリ 0 GAHeader フォーム (MT036、MT042、MT047、MT072、MT077、および MT085) を生成します。**</span><span class="sxs-lookup"><span data-stu-id="f509f-107">**To generate category 0 GAHeader forms (MT036, MT042, MT047, MT072, MT077, and MT085):**</span></span>  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\GAHeader” " C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas -f GAHeaderForms.txt\`  
  
-   <span data-ttu-id="f509f-108">**カテゴリ 0 NoTextBlocks フォーム (MT035、MT043、MT048、および MT049) を生成します。**</span><span class="sxs-lookup"><span data-stu-id="f509f-108">**To generate category 0 NoTextBlocks forms (MT035, MT043, MT048, and MT049):**</span></span>  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\NoTextBlocks” " C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas –f NoTextBlocksForms.txt`  
  
-   <span data-ttu-id="f509f-109">**カテゴリ 0 NoTrailer フォーム (MT021) を生成します。**</span><span class="sxs-lookup"><span data-stu-id="f509f-109">**To generate category 0 NoTrailer forms (MT021):**</span></span>  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\NoTrailer” " C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas –f NoTrailerForms.txt`  
  
-   <span data-ttu-id="f509f-110">**カテゴリ 0 NoTrailerTextBlocks フォーム (MT082) を生成します。**</span><span class="sxs-lookup"><span data-stu-id="f509f-110">**To generate category 0 NoTrailerTextBlocks forms (MT082):**</span></span>  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\NoTrailerTextBlocks” " C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas –f NoTrailerTextBlocks.txt`  
  
-   <span data-ttu-id="f509f-111">**カテゴリ 1 NoHeaderTextBlock フォーム (MT121) を生成します。**</span><span class="sxs-lookup"><span data-stu-id="f509f-111">**To generate category 1 NoHeaderTextBlock forms (MT121):**</span></span>  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\ NoHeaderTextBlock” " C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas -f NoHeaderTextBlockForms.txt`
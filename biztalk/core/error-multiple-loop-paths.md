---
title: エラー - 複数のループ パスが |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.multipleLoopPaths
ms.assetid: 3f7c0c1c-5aaa-4da9-99ab-78bac536b8dd
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02461c4e9fb86bb0c2c902be394b08840172c4d1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388616"
---
# <a name="error---multiple-loop-paths"></a><span data-ttu-id="be7b3-102">エラー - 複数のループ パス</span><span class="sxs-lookup"><span data-stu-id="be7b3-102">Error - Multiple Loop Paths</span></span>
<span data-ttu-id="be7b3-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="be7b3-103">**Error Code**</span></span>  
  
 <span data-ttu-id="be7b3-104">btm1030</span><span class="sxs-lookup"><span data-stu-id="be7b3-104">btm1030</span></span>  
  
 <span data-ttu-id="be7b3-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="be7b3-105">**Explanation**</span></span>  
  
 <span data-ttu-id="be7b3-106">送信先スキーマで指定されたノードには、複数の送信元ループ パスがあります。</span><span class="sxs-lookup"><span data-stu-id="be7b3-106">The indicated node in the destination schema has multiple source loop paths.</span></span>  
  
 <span data-ttu-id="be7b3-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="be7b3-107">**User Action**</span></span>  
  
 <span data-ttu-id="be7b3-108">使用して、**ループ**functoid をループの実行、送信元スキーマ ノードを明示的に指定します。</span><span class="sxs-lookup"><span data-stu-id="be7b3-108">Use a **Looping** functoid to explicitly specify the node in the source schema over which the looping will be performed.</span></span>
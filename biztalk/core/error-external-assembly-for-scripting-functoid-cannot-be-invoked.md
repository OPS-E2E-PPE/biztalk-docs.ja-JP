---
title: エラー - スクリプト Functoid の外部アセンブリを呼び出すことができません |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.cannotInvokeExternalAssembly
ms.assetid: 30d97b05-2cbf-44a5-b219-3a5ae17fc597
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37f6df36a955f2f40da35368fd72fd2d1fcbb7b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---external-assembly-for-scripting-functoid-cannot-be-invoked"></a><span data-ttu-id="b6650-102">エラー - スクリプト Functoid の外部アセンブリを呼び出すことができません。</span><span class="sxs-lookup"><span data-stu-id="b6650-102">Error - External Assembly for Scripting Functoid Cannot Be Invoked</span></span>
<span data-ttu-id="b6650-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="b6650-103">**Error Code**</span></span>  
  
 <span data-ttu-id="b6650-104">btm1067</span><span class="sxs-lookup"><span data-stu-id="b6650-104">btm1067</span></span>  
  
 <span data-ttu-id="b6650-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="b6650-105">**Explanation**</span></span>  
  
 <span data-ttu-id="b6650-106">関連するに関連付けられている外部アセンブリ メソッド**スクリプト**functoid を呼び出すことができません。</span><span class="sxs-lookup"><span data-stu-id="b6650-106">The external assembly method that is associated with the relevant **Scripting** functoid cannot be invoked.</span></span> <span data-ttu-id="b6650-107">このような外部アセンブリは、マップのコンパイルには必要ありませんが、マップのテストの操作では、グローバル アセンブリ キャッシュ (GAC) に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6650-107">Although not required for map compilation, the Test Map operation requires that such external assemblies be present in the global assembly cache (GAC).</span></span> <span data-ttu-id="b6650-108">通常、ランタイム操作でも、外部アセンブリが GAC に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6650-108">Normal, run time operation also requires that external assemblies be present in the GAC.</span></span>  
  
 <span data-ttu-id="b6650-109">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="b6650-109">**User Action**</span></span>  
  
 <span data-ttu-id="b6650-110">関連するによって参照される外部アセンブリを確認してください**スクリプト**functoid が GAC にします。</span><span class="sxs-lookup"><span data-stu-id="b6650-110">Ensure that the external assembly referenced by the relevant **Scripting** functoid is in the GAC.</span></span>
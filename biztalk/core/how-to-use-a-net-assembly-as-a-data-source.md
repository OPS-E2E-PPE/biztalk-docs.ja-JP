---
title: データ ソースとして、.NET アセンブリを使用する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rule Composer, data sources
ms.assetid: 14dbec48-acc9-4c3c-bd7f-737dabf29543
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fa56370cf894d0d18a36320ca97c4d028fee487
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256634"
---
# <a name="how-to-use-a-net-assembly-as-a-data-source"></a><span data-ttu-id="bc9ea-102">.NET アセンブリをデータ ソースとして使用する方法</span><span class="sxs-lookup"><span data-stu-id="bc9ea-102">How to Use a .NET Assembly as a Data Source</span></span>
<span data-ttu-id="bc9ea-103">.NET アセンブリをデータ ソースとして指定できます。</span><span class="sxs-lookup"><span data-stu-id="bc9ea-103">You can specify a .NET assembly as a data source.</span></span> <span data-ttu-id="bc9ea-104">アセンブリからクラスまたはクラス メンバーを続けて選択して、ボキャブラリの定義やルール上にドラッグできます。</span><span class="sxs-lookup"><span data-stu-id="bc9ea-104">You can subsequently select a class or class member from the assembly, and drag it onto a vocabulary definition or rule.</span></span>  
  
### <a name="to-specify-a-net-assembly-as-a-data-source"></a><span data-ttu-id="bc9ea-105">.NET アセンブリをデータ ソースとして指定するには</span><span class="sxs-lookup"><span data-stu-id="bc9ea-105">To specify a .NET assembly as a data source</span></span>  
  
1.  <span data-ttu-id="bc9ea-106">[ファクト エクスプ ローラー] ウィンドウ、 **.NET クラス**タブです。</span><span class="sxs-lookup"><span data-stu-id="bc9ea-106">In the Facts Explorer window, click the **.NET Classes** tab.</span></span>  
  
2.  <span data-ttu-id="bc9ea-107">右クリックし、**モジュール**ノード。</span><span class="sxs-lookup"><span data-stu-id="bc9ea-107">Right-click the **Modules** node.</span></span>  
  
3.  <span data-ttu-id="bc9ea-108">使用できるアセンブリから、.NET アセンブリを選択します。</span><span class="sxs-lookup"><span data-stu-id="bc9ea-108">From the available assemblies, select a .NET assembly.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bc9ea-109">アセンブリは、グローバル アセンブリ キャッシュ (GAC) 内に格納されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc9ea-109">The assemblies have to be in the global assembly cache (GAC).</span></span> <span data-ttu-id="bc9ea-110">ビジネス ルール作成ツールは、.NET アセンブリで参照するときに .NET アセンブリを読み込みます、**ファクト エクスプ ローラー**ウィンドウまたは、 **.NET クラスまたはクラス メンバーの定義**のページ、**ボキャブラリ定義**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="bc9ea-110">The business rule composer loads a .NET assembly when you browse for the .NET assembly in the **Facts Explorer** window or in the **.NET Class or Class Member Definition** page of the **Vocabulary Definition** window.</span></span>  <span data-ttu-id="bc9ea-111">GAC でアセンブリを更新した場合は、ビジネス ルール作成ツールを終了してから再起動し、更新した .NET アセンブリを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="bc9ea-111">If you update the assembly in the GAC, close the business rule composer and restart it to load the updated .NET assembly.</span></span> <span data-ttu-id="bc9ea-112">ビジネス ルール作成ツールでは、アセンブリが自動更新されません。</span><span class="sxs-lookup"><span data-stu-id="bc9ea-112">The business rule composer does not refresh the assembly automatically.</span></span>  
  
     <span data-ttu-id="bc9ea-113">![ファクトと定義ツリー ブラウザーのスクリーン ショット。](../core/media/ebiz-netbrowse.gif "ebiz_netbrowse")</span><span class="sxs-lookup"><span data-stu-id="bc9ea-113">![Screenshot of facts and definition tree browser.](../core/media/ebiz-netbrowse.gif "ebiz_netbrowse")</span></span>
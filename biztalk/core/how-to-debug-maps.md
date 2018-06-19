---
title: マップをデバッグする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1ee1e26-fced-4126-b48a-71007043424d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e40964b267ad0788308a92490a106f940a6cb33e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249034"
---
# <a name="how-to-debug-maps"></a><span data-ttu-id="cffe4-102">マップをデバッグする方法</span><span class="sxs-lookup"><span data-stu-id="cffe4-102">How to Debug Maps</span></span>
<span data-ttu-id="cffe4-103">**マップのデバッグ**の識別と複雑なマッピングの問題を修正する便利な機能です。</span><span class="sxs-lookup"><span data-stu-id="cffe4-103">The **Debug Map** feature is useful in identifying and fixing complex mapping issues.</span></span> <span data-ttu-id="cffe4-104">このトピックでは、インライン XSLT デバッガーを使用したマップのデバッグ手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="cffe4-104">This topic provides step-by-step instructions for debugging maps using the inline XSLT debugger.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cffe4-105">マップをデバッグするときに、**マップのデバッグ**機能は、マップ ファイルのプロパティを使用して**TestMap の入力インスタンス**と**TestMap 出力インスタンス**です。</span><span class="sxs-lookup"><span data-stu-id="cffe4-105">When debugging the map, the **Debug Map** feature uses the map file properties **TestMap Input Instance** and **TestMap Output Instance**.</span></span> <span data-ttu-id="cffe4-106">そのため、マップをデバッグする前に、入力を構成して、マップ ファイルのインスタンスのプロパティを出力することを勧めします。</span><span class="sxs-lookup"><span data-stu-id="cffe4-106">Therefore, before you debug the map, we recommend that you configure the input and output instance properties in the map file.</span></span>  
  
### <a name="to-debug-a-biztalk-map"></a><span data-ttu-id="cffe4-107">BizTalk マップをデバッグするには</span><span class="sxs-lookup"><span data-stu-id="cffe4-107">To debug a BizTalk map</span></span>  
  
1.  <span data-ttu-id="cffe4-108">ソリューション エクスプ ローラーで、テスト、およびをクリックする地図を右クリックして**マップのデバッグ**です。</span><span class="sxs-lookup"><span data-stu-id="cffe4-108">In Solution Explorer, right-click the map you want to test, and then click **Debug Map**.</span></span> [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]<span data-ttu-id="cffe4-109"> のエディターにマップが XSLT 形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="cffe4-109"> displays the map in XSLT format in its editor.</span></span>  
  
2.  <span data-ttu-id="cffe4-110">F10 キーまたは F11 キーを押して XSL コードをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="cffe4-110">Press F10 or F11 to debug the XSL code.</span></span> <span data-ttu-id="cffe4-111">Functoid の呼び出しで F11 キーを押すと、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] により Functoid の C# コードがステップ実行されます。</span><span class="sxs-lookup"><span data-stu-id="cffe4-111">When you press F11 on a functoid call, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] steps into the C# code for the functoid.</span></span> <span data-ttu-id="cffe4-112">Functoid のソース コードで使用されている変数の値を、ローカルの Windows デバッガーで確認できます。</span><span class="sxs-lookup"><span data-stu-id="cffe4-112">You can view the values of variables used in the functoid source code in the Local Windows Debugger.</span></span>
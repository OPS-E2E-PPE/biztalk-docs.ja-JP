---
title: マップをデバッグする方法 |Microsoft Docs
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
ms.openlocfilehash: 9459cc2d2d51347e508ac989a9aeb54b9ac1059d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338888"
---
# <a name="how-to-debug-maps"></a><span data-ttu-id="474a5-102">マップをデバッグする方法</span><span class="sxs-lookup"><span data-stu-id="474a5-102">How to Debug Maps</span></span>
<span data-ttu-id="474a5-103">**マップのデバッグ**識別および複雑なマッピングの問題を修正する便利な機能です。</span><span class="sxs-lookup"><span data-stu-id="474a5-103">The **Debug Map** feature is useful in identifying and fixing complex mapping issues.</span></span> <span data-ttu-id="474a5-104">このトピックでは、インライン XSLT デバッガーを使用してマップをデバッグするための詳細な手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="474a5-104">This topic provides step-by-step instructions for debugging maps using the inline XSLT debugger.</span></span>  

> [!NOTE]
>  <span data-ttu-id="474a5-105">マップをデバッグするときに、**マップのデバッグ**機能は、マップ ファイルのプロパティを使用して**TestMap の入力インスタンス**と**TestMap 出力インスタンス**します。</span><span class="sxs-lookup"><span data-stu-id="474a5-105">When debugging the map, the **Debug Map** feature uses the map file properties **TestMap Input Instance** and **TestMap Output Instance**.</span></span> <span data-ttu-id="474a5-106">そのため、マップをデバッグする前に、入力を構成し、マップ ファイルにインスタンスのプロパティを出力することを勧めします。</span><span class="sxs-lookup"><span data-stu-id="474a5-106">Therefore, before you debug the map, we recommend that you configure the input and output instance properties in the map file.</span></span>  

### <a name="to-debug-a-biztalk-map"></a><span data-ttu-id="474a5-107">BizTalk マップをデバッグするには</span><span class="sxs-lookup"><span data-stu-id="474a5-107">To debug a BizTalk map</span></span>  

1. <span data-ttu-id="474a5-108">ソリューション エクスプ ローラーで、テスト、およびクリックするマップを右クリックして**マップのデバッグ**します。</span><span class="sxs-lookup"><span data-stu-id="474a5-108">In Solution Explorer, right-click the map you want to test, and then click **Debug Map**.</span></span> [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] <span data-ttu-id="474a5-109">エディターで XSLT 形式で、マップを表示します。</span><span class="sxs-lookup"><span data-stu-id="474a5-109">displays the map in XSLT format in its editor.</span></span>  

2. <span data-ttu-id="474a5-110">XSL コードをデバッグするには、f10 キーまたは F11 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="474a5-110">Press F10 or F11 to debug the XSL code.</span></span> <span data-ttu-id="474a5-111">Functoid の呼び出しで f11 キーを押す[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]にステップ イン、 C# 、functoid のコード。</span><span class="sxs-lookup"><span data-stu-id="474a5-111">When you press F11 on a functoid call, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] steps into the C# code for the functoid.</span></span> <span data-ttu-id="474a5-112">ローカル Windows デバッガーで functoid のソース コードで使用される変数の値を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="474a5-112">You can view the values of variables used in the functoid source code in the Local Windows Debugger.</span></span>

---
title: コンパイラ リンクを非表示にしたりする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66bfd9de-c4d2-46ee-854f-cf7c7cd07368
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3c006f5de761837ec1ed0d6f983d380a76a50a5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010051"
---
# <a name="how-to-show-and-hide-compiler-links"></a><span data-ttu-id="7ecaf-102">コンパイラ リンクを表示する/非表示にする方法</span><span class="sxs-lookup"><span data-stu-id="7ecaf-102">How to Show and Hide Compiler Links</span></span>
<span data-ttu-id="7ecaf-103">マップをコンパイルすると、BizTalk マッパーにより、マップで必要となるすべてのリンクを示す追加のリンク (コンパイラ リンク) が作成されます。</span><span class="sxs-lookup"><span data-stu-id="7ecaf-103">When you compile a map, BizTalk Mapper creates additional links, known as compiler links to account for all linking needed in the map.</span></span> <span data-ttu-id="7ecaf-104">これらのリンクのいくつかは、作成したリンクによって暗黙的に指定されます。</span><span class="sxs-lookup"><span data-stu-id="7ecaf-104">Some of these links are only implied by the links you created.</span></span> <span data-ttu-id="7ecaf-105">マップをコンパイルまたはテストする際、追加されたコンパイラ リンクをメイン ウィンドウに表示するかどうかを、Visual Studio の出力ウィンドウの最終行で選択できます。</span><span class="sxs-lookup"><span data-stu-id="7ecaf-105">When you compile, or test, a map, the final line in the Visual Studio Output window allows you to show or hide these additional compiler links in the main window.</span></span> <span data-ttu-id="7ecaf-106">既定では、コンパイラ リンクは赤色の波線で表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ecaf-106">By default, the compiler links appear as red dashed lines.</span></span>  
  
### <a name="to-show-or-hide-compiler-links"></a><span data-ttu-id="7ecaf-107">コンパイラ リンクの表示と非表示を切り替えるには</span><span class="sxs-lookup"><span data-stu-id="7ecaf-107">To show or hide compiler links</span></span>  
  
1. <span data-ttu-id="7ecaf-108">ソリューション エクスプ ローラーでマップを表示する をクリックするコンパイラ リンクを右クリックして**マップのテスト**します。</span><span class="sxs-lookup"><span data-stu-id="7ecaf-108">In Solution Explorer, right-click the map whose complier links you want to view, and then click **Test Map**.</span></span>  
  
2. <span data-ttu-id="7ecaf-109">Visual Studio のエラー一覧 ウィンドウで最後にスクロールし、という行をダブルクリックします**ここをダブルクリックすると、コンパイラ リンクの表示/非表示に**します。</span><span class="sxs-lookup"><span data-stu-id="7ecaf-109">In the Visual Studio Error List window, scroll to the end and double-click the line that says **Double-click here to show/Hide compiler links**.</span></span>  
  
    <span data-ttu-id="7ecaf-110">この行をもう一度クリックすると、コンパイラ リンクの表示と非表示が切り替わります。</span><span class="sxs-lookup"><span data-stu-id="7ecaf-110">To change the display state of compiler links from shown to hidden, or from hidden to shown, just double-click that line again.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="7ecaf-111">場合を構築または再構築、BizTalk プロジェクトまたはソリューションの 1 つまたは複数のマップ、メッセージを格納している**ここをダブルクリックすると、コンパイラ リンクの表示/非表示に**に表示される、**エラー一覧**の Visual Studio のウィンドウプロジェクトまたはソリューションのすべてのマップ。</span><span class="sxs-lookup"><span data-stu-id="7ecaf-111">When you build/rebuild a BizTalk project or solution containing one or more maps, the message **Double-click here to show/Hide compiler links** is displayed in the **Error List** window of Visual Studio for all the maps in the project or solution.</span></span>  
  
   <span data-ttu-id="7ecaf-112">マップをテストするには、入力インスタンスおよび出力インスタンスのプロパティを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ecaf-112">To test a map, you must configure the properties for the input and output instances.</span></span> <span data-ttu-id="7ecaf-113">これらのプロパティを構成する方法の詳細については、[マップの検証の構成とテストのパラメーターは、方法](../core/how-to-configure-map-validation-and-test-parameters.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ecaf-113">For more information about how to configure these properties, see [How to Configure Map Validation and Test Parameters](../core/how-to-configure-map-validation-and-test-parameters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ecaf-114">参照</span><span class="sxs-lookup"><span data-stu-id="7ecaf-114">See Also</span></span>  
 [<span data-ttu-id="7ecaf-115">リンクを使用してレコードとフィールド マッピングを指定する</span><span class="sxs-lookup"><span data-stu-id="7ecaf-115">Using Links to Specify Record and Field Mappings</span></span>](../core/using-links-to-specify-record-and-field-mappings.md)
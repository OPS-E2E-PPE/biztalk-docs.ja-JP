---
title: Functoid 入力パラメーター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cca24f93-74a8-460c-b9ab-9aa2c767fe2f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a4a93d827a5f58401bb9b8fcdf9727c2a61767e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008099"
---
# <a name="functoid-input-parameters"></a><span data-ttu-id="c30e5-102">Functoid 入力パラメーター</span><span class="sxs-lookup"><span data-stu-id="c30e5-102">Functoid Input Parameters</span></span>
<span data-ttu-id="c30e5-103">Functoid をマップで使用する場合の重要な点は、Functoid に対する入力パラメーターを適切に構成することです。</span><span class="sxs-lookup"><span data-stu-id="c30e5-103">A critical aspect of using functoids in your maps is properly configuring the input parameters to the functoid.</span></span> <span data-ttu-id="c30e5-104">入力パラメーターの順序はすべての functoid にとって重要ではありません (など、**加算**functoid は、同じ表示がまた 1 つが要求するプロパティを関連付ける)、多くの functoid の入力パラメーターが必要正しい順序で指定します。</span><span class="sxs-lookup"><span data-stu-id="c30e5-104">While the order of input parameters is not critical for all functoids (such as the **Addition** functoid, which displays the same associate properties that one expects from addition), many functoids must have their input parameters specified in the correct order.</span></span>  
  
## <a name="create-input-paramaters"></a><span data-ttu-id="c30e5-105">入力パラメーターを作成します。</span><span class="sxs-lookup"><span data-stu-id="c30e5-105">Create input paramaters</span></span>
 <span data-ttu-id="c30e5-106">Functoid の入力パラメーターを作成する 2 つの方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c30e5-106">There are two ways that input parameters to a functoid can be created:</span></span>  
  
- <span data-ttu-id="c30e5-107">表示されたグリッド ページで、Functoid の左側からのリンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="c30e5-107">By creating links into the left side of a functoid in the displayed grid page.</span></span> <span data-ttu-id="c30e5-108">リンクを作成する順序は、関連付けられた入力パラメーターが Functoid に渡される順序です。</span><span class="sxs-lookup"><span data-stu-id="c30e5-108">The order in which you create the links is the order in which the associated input parameters are passed to the functoid.</span></span>  
  
- <span data-ttu-id="c30e5-109">開き、**構成\<Functoid\> Functoid**入力パラメーター ダイアログ ボックスを新規に追加します。</span><span class="sxs-lookup"><span data-stu-id="c30e5-109">By opening the **Configure \<Functoid\> Functoid** dialog box and adding new input parameters.</span></span> <span data-ttu-id="c30e5-110">このダイアログ ボックスも重要です。ここでは、Functoid の入力パラメーターの順序を入れ替えて適切な順序にすることができるからです。</span><span class="sxs-lookup"><span data-stu-id="c30e5-110">This dialog box is also important because it allows you to reorder the input parameters to a functoid so that they are in the correct order.</span></span> <span data-ttu-id="c30e5-111">たとえば、Functoid へのリンクを間違った順序で作成した場合に、このダイアログ ボックスを開いて必要な修正を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c30e5-111">For example, if you create links to the functoid in the incorrect order, you can go to this dialog box and make the necessary corrections.</span></span> <span data-ttu-id="c30e5-112">Functoid の入力パラメーターの構成の詳しい手順については、「 [Functoid の入力パラメーターを構成する方法](../core/how-to-configure-functoid-input-parameters.md)します。</span><span class="sxs-lookup"><span data-stu-id="c30e5-112">For step-by-step instructions on configuring the input parameters for a functoid, see [How to Configure Functoid Input Parameters](../core/how-to-configure-functoid-input-parameters.md).</span></span>  
  
  <span data-ttu-id="c30e5-113">使用する必要があります、**構成\<Functoid\> Functoid**ダイアログ ボックスの定数入力パラメーターを作成します。</span><span class="sxs-lookup"><span data-stu-id="c30e5-113">You must use the **Configure \<Functoid\> Functoid** dialog box to create input parameters that are constants.</span></span>  
  
  <span data-ttu-id="c30e5-114">リンクまたは functoid を使用して、ラベルを指定すると、**ラベル**プロパティ リンクまたは functoid が選択されている場合は、プロパティ ウィンドウで、そのラベルに表示されます、**構成\<Functoid\>Functoid**  ダイアログ ボックスではなく、スキーマ ノードの対応する XPath や入力パラメーターとして使用される functoid の名前。</span><span class="sxs-lookup"><span data-stu-id="c30e5-114">When you provide a label for a link or functoid using the **Label** property in the Properties window when the link or functoid is selected, that label will be shown in the **Configure \<Functoid\> Functoid** dialog box rather than the corresponding XPath of a schema node, or the name of a functoid being used as an input parameter.</span></span> <span data-ttu-id="c30e5-115">ラベルを使用すると、各パラメーターの識別や、適切な順序での配置を容易に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c30e5-115">With labels, it will be much easier to tell which parameter is which, and to get them into the correct order.</span></span>  
  
  <span data-ttu-id="c30e5-116">Functoid の入力パラメーターの適切な順序の詳細については、次を参照してください。、 **Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c30e5-116">For definitive information about the correct order of functoid input parameters, see the **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c30e5-117">参照</span><span class="sxs-lookup"><span data-stu-id="c30e5-117">See Also</span></span>  
 <span data-ttu-id="c30e5-118">[Functoid 入力パラメーターを構成します。](../core/how-to-configure-functoid-input-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="c30e5-118">[Configure Functoid Input Parameters](../core/how-to-configure-functoid-input-parameters.md) </span></span>  
 <span data-ttu-id="c30e5-119">[スクリプト Functoid を構成します。](../core/how-to-configure-the-scripting-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="c30e5-119">[Configure the Scripting Functoid](../core/how-to-configure-the-scripting-functoid.md) </span></span>  
 [<span data-ttu-id="c30e5-120">テーブル ループ Functoid およびテーブル抽出 Functoid の構成</span><span class="sxs-lookup"><span data-stu-id="c30e5-120">Configure the Table Looping and Table Extractor Functoids</span></span>](../core/how-to-configure-the-table-looping-and-table-extractor-functoids.md)
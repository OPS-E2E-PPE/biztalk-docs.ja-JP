---
title: "Functoid 入力パラメーター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cca24f93-74a8-460c-b9ab-9aa2c767fe2f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97919e3afcb6277f33aa65e6e8e6370aecb23844
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="functoid-input-parameters"></a><span data-ttu-id="f9a62-102">Functoid 入力パラメーター</span><span class="sxs-lookup"><span data-stu-id="f9a62-102">Functoid Input Parameters</span></span>
<span data-ttu-id="f9a62-103">Functoid をマップで使用する場合の重要な点は、Functoid に対する入力パラメーターを適切に構成することです。</span><span class="sxs-lookup"><span data-stu-id="f9a62-103">A critical aspect of using functoids in your maps is properly configuring the input parameters to the functoid.</span></span> <span data-ttu-id="f9a62-104">入力パラメーターの順序はすべての functoid にとって重要ではありません (など、**加算**functoid は、表示されて、同じ加算から予想される 1 つのプロパティに関連付ける)、多くの functoid の入力パラメーターを持つ必要があります正しい順序で指定します。</span><span class="sxs-lookup"><span data-stu-id="f9a62-104">While the order of input parameters is not critical for all functoids (such as the **Addition** functoid, which displays the same associate properties that one expects from addition), many functoids must have their input parameters specified in the correct order.</span></span>  
  
## <a name="create-input-paramaters"></a><span data-ttu-id="f9a62-105">入力パラメーターを作成します。</span><span class="sxs-lookup"><span data-stu-id="f9a62-105">Create input paramaters</span></span>
 <span data-ttu-id="f9a62-106">Functoid の入力パラメーターを作成する 2 つの方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f9a62-106">There are two ways that input parameters to a functoid can be created:</span></span>  
  
-   <span data-ttu-id="f9a62-107">表示されたグリッド ページで、Functoid の左側からのリンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="f9a62-107">By creating links into the left side of a functoid in the displayed grid page.</span></span> <span data-ttu-id="f9a62-108">リンクを作成する順序は、関連付けられた入力パラメーターが Functoid に渡される順序です。</span><span class="sxs-lookup"><span data-stu-id="f9a62-108">The order in which you create the links is the order in which the associated input parameters are passed to the functoid.</span></span>  
  
-   <span data-ttu-id="f9a62-109">開き、**構成\<Functoid > Functoid**入力パラメーター ダイアログ ボックスを新規に追加します。</span><span class="sxs-lookup"><span data-stu-id="f9a62-109">By opening the **Configure \<Functoid> Functoid** dialog box and adding new input parameters.</span></span> <span data-ttu-id="f9a62-110">このダイアログ ボックスも重要です。ここでは、Functoid の入力パラメーターの順序を入れ替えて適切な順序にすることができるからです。</span><span class="sxs-lookup"><span data-stu-id="f9a62-110">This dialog box is also important because it allows you to reorder the input parameters to a functoid so that they are in the correct order.</span></span> <span data-ttu-id="f9a62-111">たとえば、Functoid へのリンクを間違った順序で作成した場合に、このダイアログ ボックスを開いて必要な修正を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f9a62-111">For example, if you create links to the functoid in the incorrect order, you can go to this dialog box and make the necessary corrections.</span></span> <span data-ttu-id="f9a62-112">Functoid の入力パラメーターの構成の詳しい手順については、「 [Functoid の入力パラメーターを構成する方法](../core/how-to-configure-functoid-input-parameters.md)です。</span><span class="sxs-lookup"><span data-stu-id="f9a62-112">For step-by-step instructions on configuring the input parameters for a functoid, see [How to Configure Functoid Input Parameters](../core/how-to-configure-functoid-input-parameters.md).</span></span>  
  
 <span data-ttu-id="f9a62-113">使用する必要があります、**構成\<Functoid > Functoid**定数入力パラメーターを作成する ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="f9a62-113">You must use the **Configure \<Functoid> Functoid** dialog box to create input parameters that are constants.</span></span>  
  
 <span data-ttu-id="f9a62-114">使用して、リンクまたは functoid のラベルを指定すると、**ラベル**リンクまたは functoid が選択されている場合は、プロパティ ウィンドウでプロパティ、そのラベルに表示される、**構成\<Functoid > Functoid**  ダイアログ ボックスではなく、対応するスキーマ ノードの XPath や入力パラメーターとして使用される functoid の名前。</span><span class="sxs-lookup"><span data-stu-id="f9a62-114">When you provide a label for a link or functoid using the **Label** property in the Properties window when the link or functoid is selected, that label will be shown in the **Configure \<Functoid> Functoid** dialog box rather than the corresponding XPath of a schema node, or the name of a functoid being used as an input parameter.</span></span> <span data-ttu-id="f9a62-115">ラベルを使用すると、各パラメーターの識別や、適切な順序での配置を容易に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f9a62-115">With labels, it will be much easier to tell which parameter is which, and to get them into the correct order.</span></span>  
  
 <span data-ttu-id="f9a62-116">Functoid の入力パラメーターの正しい順序に関する明確な情報は、次を参照してください。、 **Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="f9a62-116">For definitive information about the correct order of functoid input parameters, see the **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f9a62-117">参照</span><span class="sxs-lookup"><span data-stu-id="f9a62-117">See Also</span></span>  
 <span data-ttu-id="f9a62-118">[Functoid 入力パラメーターを構成します。](../core/how-to-configure-functoid-input-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="f9a62-118">[Configure Functoid Input Parameters](../core/how-to-configure-functoid-input-parameters.md) </span></span>  
 <span data-ttu-id="f9a62-119">[スクリプト Functoid を構成します。](../core/how-to-configure-the-scripting-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="f9a62-119">[Configure the Scripting Functoid](../core/how-to-configure-the-scripting-functoid.md) </span></span>  
 [<span data-ttu-id="f9a62-120">テーブル ループを構成し、テーブル抽出 Functoid</span><span class="sxs-lookup"><span data-stu-id="f9a62-120">Configure the Table Looping and Table Extractor Functoids</span></span>](../core/how-to-configure-the-table-looping-and-table-extractor-functoids.md)
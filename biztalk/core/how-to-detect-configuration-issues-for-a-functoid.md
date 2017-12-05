---
title: "Functoid の構成の問題を検出する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 32afc333-934c-4ffb-b1b5-61af07157200
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8561156091c992e9329ef7d9627589eff9e0ed6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-detect-configuration-issues-for-a-functoid"></a><span data-ttu-id="3ad2f-102">Functoid の構成に関する問題を検出する方法</span><span class="sxs-lookup"><span data-stu-id="3ad2f-102">How to Detect Configuration Issues for a Functoid</span></span>
<span data-ttu-id="3ad2f-103">マップを操作しているときに、Functoid やリンクの構成に関する問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3ad2f-103">While working with maps, you might encounter issues with configuration of a functoid and/or link.</span></span> <span data-ttu-id="3ad2f-104">BizTalk マッパーでは、ビジュアル化機構を使用して、functoid の構成に関連する問題をすばやく識別できます。</span><span class="sxs-lookup"><span data-stu-id="3ad2f-104">The BizTalk Mapper uses a visualization mechanism to help quickly identify problems associated with a functoid configuration.</span></span> <span data-ttu-id="3ad2f-105">この視覚的で、functoid アイコンで警告の注釈として表示されます (の例: ![Functoid IntelliSense](../core/media/mapper-functoidintellisense.gif "Mapper_FunctoidIntelliSense"))、リレーションシップ ビューでします。</span><span class="sxs-lookup"><span data-stu-id="3ad2f-105">This visual indication renders as a warning annotation on the functoid icon (for e.g. ![Functoid IntelliSense](../core/media/mapper-functoidintellisense.gif "Mapper_FunctoidIntelliSense")) in the relationship view.</span></span> <span data-ttu-id="3ad2f-106">このトピックでは、Functoid の構成の問題を検出する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3ad2f-106">This topic provides information about how to detect the configuration issues for a functoid.</span></span>  
  
 <span data-ttu-id="3ad2f-107">警告状態アイコンは、Functoid が適切に構成されていないことをマッパーが検出した場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ad2f-107">The warning status icon appears when the Mapper detects that a functoid is not properly configured.</span></span> <span data-ttu-id="3ad2f-108">Functoid 上にマウスを移動すると、マッパーによって検出された問題の簡単な説明が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ad2f-108">Moving the mouse over the functoid also displays brief information of the issue identified by the Mapper.</span></span> <span data-ttu-id="3ad2f-109">たとえば、Functoid に最小数の有効な入力がない場合、Functoid のツールヒントに必要な入力パラメーターの数が示されます。</span><span class="sxs-lookup"><span data-stu-id="3ad2f-109">For example, if a functoid does not have minimum number of valid inputs, the tooltip for the functoid mentions the number of input parameters required.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3ad2f-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="3ad2f-110">Prerequisites</span></span>  
 <span data-ttu-id="3ad2f-111">この操作では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ad2f-111">This operation requires that BizTalk Mapper is running.</span></span>  
  
### <a name="to-detect-configuration-issues-for-a-functoid"></a><span data-ttu-id="3ad2f-112">Functoid の構成の問題を検出するには</span><span class="sxs-lookup"><span data-stu-id="3ad2f-112">To detect configuration issues for a functoid</span></span>  
  
1.  <span data-ttu-id="3ad2f-113">必要な Functoid をツールボックスからグリッド ページにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="3ad2f-113">Drag the required functoid from the toolbox onto the grid page.</span></span> <span data-ttu-id="3ad2f-114">Functoid に警告アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ad2f-114">You see the functoid with a warning icon.</span></span>  
  
2.  <span data-ttu-id="3ad2f-115">次のいずれかの操作が可能です。</span><span class="sxs-lookup"><span data-stu-id="3ad2f-115">You can do one of the following:</span></span>  
  
    -   <span data-ttu-id="3ad2f-116">マウス ポインターを Functoid 上に移動します。</span><span class="sxs-lookup"><span data-stu-id="3ad2f-116">Move the mouse pointer on the functoid.</span></span> <span data-ttu-id="3ad2f-117">ツールヒントに、エラーと対処方法に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ad2f-117">The tooltip displays information about the error and what you need to do.</span></span>  
  
         <span data-ttu-id="3ad2f-118">次の図は、Functoid "Addition" の構成時のエラー情報が表示されたツールヒントです。</span><span class="sxs-lookup"><span data-stu-id="3ad2f-118">The following figure displays a tooltip with error information while configuring the functoid “Addition.”</span></span>  
  
         <span data-ttu-id="3ad2f-119">![Functoid の構成のエラー検出](../core/media/errordetectionfunctoid.gif "ErrorDetectionFunctoid")</span><span class="sxs-lookup"><span data-stu-id="3ad2f-119">![Error detection in functoid configuration](../core/media/errordetectionfunctoid.gif "ErrorDetectionFunctoid")</span></span>  
  
    -   <span data-ttu-id="3ad2f-120">Functoid をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="3ad2f-120">Double-click the functoid.</span></span> <span data-ttu-id="3ad2f-121">**構成\<Functoid\> Functoid**  ダイアログ ボックスには、入力パラメーターの警告アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ad2f-121">The **Configure \<Functoid\> Functoid** dialog box displays warning icons against the input parameters.</span></span> <span data-ttu-id="3ad2f-122">これは、選択した Functoid の入力パラメーターが構成されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="3ad2f-122">This indicates that the input parameters of the selected functoid are not configured.</span></span>  
  
         <span data-ttu-id="3ad2f-123">次の図は、"Addition" Functoid の入力パラメーターに関するエラー情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="3ad2f-123">The following figure displays error information about input parameters for the “Addition” functoid.</span></span>  
  
         <span data-ttu-id="3ad2f-124">![Functoid が構成されていないときに表示される警告](../core/media/configure-input-parameters-warningicon.gif "Configure_input_parameters_WarningIcon")</span><span class="sxs-lookup"><span data-stu-id="3ad2f-124">![Warning displayed when functoid is not configured](../core/media/configure-input-parameters-warningicon.gif "Configure_input_parameters_WarningIcon")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ad2f-125">参照</span><span class="sxs-lookup"><span data-stu-id="3ad2f-125">See Also</span></span>  
 [<span data-ttu-id="3ad2f-126">BizTalk マッパーの強化された機能の使用</span><span class="sxs-lookup"><span data-stu-id="3ad2f-126">Using Enhanced Features in BizTalk Mapper</span></span>](../core/using-enhanced-features-in-biztalk-mapper.md)
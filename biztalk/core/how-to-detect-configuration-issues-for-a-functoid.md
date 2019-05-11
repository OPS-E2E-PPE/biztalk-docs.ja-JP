---
title: Functoid の構成の問題を検出する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 32afc333-934c-4ffb-b1b5-61af07157200
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da91fbeb9afc3d6f93a319e82e7e83d396ad4e16
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385233"
---
# <a name="how-to-detect-configuration-issues-for-a-functoid"></a><span data-ttu-id="01a26-102">Functoid の構成に関する問題を検出する方法</span><span class="sxs-lookup"><span data-stu-id="01a26-102">How to Detect Configuration Issues for a Functoid</span></span>
<span data-ttu-id="01a26-103">マップを操作しているときに、functoid やリンクの構成に関する問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="01a26-103">While working with maps, you might encounter issues with configuration of a functoid and/or link.</span></span> <span data-ttu-id="01a26-104">BizTalk マッパーでは、視覚化メカニズムを使用して、functoid の構成に関連する問題をすばやく識別できます。</span><span class="sxs-lookup"><span data-stu-id="01a26-104">The BizTalk Mapper uses a visualization mechanism to help quickly identify problems associated with a functoid configuration.</span></span> <span data-ttu-id="01a26-105">この視覚的で、functoid アイコンで警告の注釈として表示されます (の例: ![Functoid IntelliSense](../core/media/mapper-functoidintellisense.gif "Mapper_FunctoidIntelliSense"))、リレーションシップ ビューで。</span><span class="sxs-lookup"><span data-stu-id="01a26-105">This visual indication renders as a warning annotation on the functoid icon (for e.g. ![Functoid IntelliSense](../core/media/mapper-functoidintellisense.gif "Mapper_FunctoidIntelliSense")) in the relationship view.</span></span> <span data-ttu-id="01a26-106">このトピックでは、functoid の構成の問題を検出する方法についての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="01a26-106">This topic provides information about how to detect the configuration issues for a functoid.</span></span>  
  
 <span data-ttu-id="01a26-107">マッパー functoid が正しく構成されていないことを検出すると、警告状態アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="01a26-107">The warning status icon appears when the Mapper detects that a functoid is not properly configured.</span></span> <span data-ttu-id="01a26-108">Functoid 上にマウスを動かすと、マッパーによって特定された問題の簡単な情報も表示されます。</span><span class="sxs-lookup"><span data-stu-id="01a26-108">Moving the mouse over the functoid also displays brief information of the issue identified by the Mapper.</span></span> <span data-ttu-id="01a26-109">たとえば、functoid が有効な入力値の最小数を持たない場合、functoid のツールヒントは、必要な入力パラメーターの数を示しています。</span><span class="sxs-lookup"><span data-stu-id="01a26-109">For example, if a functoid does not have minimum number of valid inputs, the tooltip for the functoid mentions the number of input parameters required.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="01a26-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="01a26-110">Prerequisites</span></span>  
 <span data-ttu-id="01a26-111">この操作では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="01a26-111">This operation requires that BizTalk Mapper is running.</span></span>  
  
### <a name="to-detect-configuration-issues-for-a-functoid"></a><span data-ttu-id="01a26-112">Functoid の構成の問題を検出するには</span><span class="sxs-lookup"><span data-stu-id="01a26-112">To detect configuration issues for a functoid</span></span>  
  
1.  <span data-ttu-id="01a26-113">ツールボックスからグリッド ページに必要な functoid をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="01a26-113">Drag the required functoid from the toolbox onto the grid page.</span></span> <span data-ttu-id="01a26-114">警告アイコンが functoid が表示されます。</span><span class="sxs-lookup"><span data-stu-id="01a26-114">You see the functoid with a warning icon.</span></span>  
  
2.  <span data-ttu-id="01a26-115">次のいずれかの操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="01a26-115">You can do one of the following:</span></span>  
  
    -   <span data-ttu-id="01a26-116">Functoid には、マウス ポインターを移動します。</span><span class="sxs-lookup"><span data-stu-id="01a26-116">Move the mouse pointer on the functoid.</span></span> <span data-ttu-id="01a26-117">ツールヒントには、行う必要があるとエラーに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="01a26-117">The tooltip displays information about the error and what you need to do.</span></span>  
  
         <span data-ttu-id="01a26-118">次の図は、functoid"Addition。"を構成するときにエラー情報を含むヒントを表示します。</span><span class="sxs-lookup"><span data-stu-id="01a26-118">The following figure displays a tooltip with error information while configuring the functoid “Addition.”</span></span>  
  
         <span data-ttu-id="01a26-119">![Functoid の構成でのエラー検出](../core/media/errordetectionfunctoid.gif "ErrorDetectionFunctoid")</span><span class="sxs-lookup"><span data-stu-id="01a26-119">![Error detection in functoid configuration](../core/media/errordetectionfunctoid.gif "ErrorDetectionFunctoid")</span></span>  
  
    -   <span data-ttu-id="01a26-120">Functoid をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="01a26-120">Double-click the functoid.</span></span> <span data-ttu-id="01a26-121">**構成\<Functoid\> Functoid**  ダイアログ ボックスに入力パラメーターの警告アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="01a26-121">The **Configure \<Functoid\> Functoid** dialog box displays warning icons against the input parameters.</span></span> <span data-ttu-id="01a26-122">これは、選択した functoid の入力パラメーターが構成されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="01a26-122">This indicates that the input parameters of the selected functoid are not configured.</span></span>  
  
         <span data-ttu-id="01a26-123">次の図は、"Addition"functoid の入力パラメーターに関するエラー情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="01a26-123">The following figure displays error information about input parameters for the “Addition” functoid.</span></span>  
  
         <span data-ttu-id="01a26-124">![Functoid が構成されていないときに表示される警告](../core/media/configure-input-parameters-warningicon.gif "Configure_input_parameters_WarningIcon")</span><span class="sxs-lookup"><span data-stu-id="01a26-124">![Warning displayed when functoid is not configured](../core/media/configure-input-parameters-warningicon.gif "Configure_input_parameters_WarningIcon")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01a26-125">参照</span><span class="sxs-lookup"><span data-stu-id="01a26-125">See Also</span></span>  
 [<span data-ttu-id="01a26-126">BizTalk マッパーの強化された機能の使用</span><span class="sxs-lookup"><span data-stu-id="01a26-126">Using Enhanced Features in BizTalk Mapper</span></span>](../core/using-enhanced-features-in-biztalk-mapper.md)
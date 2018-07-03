---
title: オーケストレーションにパラメーターを追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, parameters
ms.assetid: 35c731ed-6327-4de7-8d2e-4d14024bda77
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 220b0fbcb9970beae10e4c76b9386c65d7fb4fca
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988843"
---
# <a name="how-to-add-parameters-to-orchestrations"></a><span data-ttu-id="7edbb-102">オーケストレーションにパラメーターを追加する方法</span><span class="sxs-lookup"><span data-stu-id="7edbb-102">How to Add Parameters to Orchestrations</span></span>
<span data-ttu-id="7edbb-103">[オーケストレーションの種類] ウィンドウでは、オーケストレーションが受け取るパラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7edbb-103">You can specify what parameters your orchestration should take in the Orchestration View window.</span></span> <span data-ttu-id="7edbb-104">オーケストレーションは、次の項目をパラメーターとして受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="7edbb-104">An orchestration can take the following items as parameters:</span></span>  
  
- <span data-ttu-id="7edbb-105">メッセージ</span><span class="sxs-lookup"><span data-stu-id="7edbb-105">Messages</span></span>  
  
- <span data-ttu-id="7edbb-106">変数 (オブジェクトを含む)</span><span class="sxs-lookup"><span data-stu-id="7edbb-106">Variables (including objects)</span></span>  
  
- <span data-ttu-id="7edbb-107">関連付けセット</span><span class="sxs-lookup"><span data-stu-id="7edbb-107">Correlation sets</span></span>  
  
- <span data-ttu-id="7edbb-108">ロール リンク</span><span class="sxs-lookup"><span data-stu-id="7edbb-108">Role links</span></span>  
  
- <span data-ttu-id="7edbb-109">[ポート]</span><span class="sxs-lookup"><span data-stu-id="7edbb-109">Ports</span></span>  
  
  <span data-ttu-id="7edbb-110">パラメーターは、入力パラメーターまたは出力パラメーターとしてオーケストレーション間で渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="7edbb-110">Parameters can be passed between orchestrations as in parameters or out parameters.</span></span> <span data-ttu-id="7edbb-111">入力パラメーターは値渡しまたは参照渡しできます。</span><span class="sxs-lookup"><span data-stu-id="7edbb-111">In parameters can be passed by value or by reference.</span></span> <span data-ttu-id="7edbb-112">出力パラメーターは参照渡しのみが可能です。</span><span class="sxs-lookup"><span data-stu-id="7edbb-112">Out parameters can only be passed by reference.</span></span> <span data-ttu-id="7edbb-113">パラメーターには、変数、メッセージ、関連付けセット、ロール リンク、およびポートを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="7edbb-113">Parameters can include variables, messages, correlation sets, role links, and ports.</span></span>  
  
### <a name="to-set-orchestration-parameters"></a><span data-ttu-id="7edbb-114">オーケストレーションのパラメーターを設定するには</span><span class="sxs-lookup"><span data-stu-id="7edbb-114">To set orchestration parameters</span></span>  
  
1.  <span data-ttu-id="7edbb-115">オーケストレーションの種類 ウィンドウで実行して、**オーケストレーション パラメーター**変数、メッセージ、およびポートを追加するフォルダー。</span><span class="sxs-lookup"><span data-stu-id="7edbb-115">In the Orchestration View window, use the **Orchestration Parameters** folder to add variables, messages, and ports.</span></span>  
  
2.  <span data-ttu-id="7edbb-116">追加された各項目に対して、**オーケストレーション パラメーター**フォルダー、[プロパティ] ウィンドウを使用して、**方向**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="7edbb-116">For each item added to the **Orchestration Parameters** folder, use the Properties window to specify the **Direction** property:</span></span>  
  
    -   <span data-ttu-id="7edbb-117">入力 - 値で渡される入力パラメーター。</span><span class="sxs-lookup"><span data-stu-id="7edbb-117">In—A parameter passed in by value.</span></span>  
  
    -   <span data-ttu-id="7edbb-118">参照 - 参照で渡される入力パラメーター。</span><span class="sxs-lookup"><span data-stu-id="7edbb-118">Ref—A parameter passed in by reference.</span></span>  
  
    -   <span data-ttu-id="7edbb-119">出力 - 参照で渡される出力パラメーター。</span><span class="sxs-lookup"><span data-stu-id="7edbb-119">Out—A parameter passed out by reference.</span></span>  
  
### <a name="to-add-a-parameter-to-an-orchestration"></a><span data-ttu-id="7edbb-120">オーケストレーションにパラメーターを追加するには</span><span class="sxs-lookup"><span data-stu-id="7edbb-120">To add a parameter to an orchestration</span></span>  
  
1. <span data-ttu-id="7edbb-121">オーケストレーションの種類 ウィンドウで右クリックし、**オーケストレーション パラメーター**フォルダーを目的のパラメーターの種類をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7edbb-121">In the Orchestration View window, right-click the **Orchestration Parameters** folder and then click the kind of parameter you want.</span></span>  
  
2. <span data-ttu-id="7edbb-122">構成済みのポートおよびロール リンクの場合は、ウィザードを使用してパラメーターを構成します。</span><span class="sxs-lookup"><span data-stu-id="7edbb-122">For configured ports and role links, use the wizard to configure the parameter.</span></span>  
  
    <span data-ttu-id="7edbb-123">- または -</span><span class="sxs-lookup"><span data-stu-id="7edbb-123">—Or—</span></span>  
  
    <span data-ttu-id="7edbb-124">その他のパラメーターの種類については、プロパティ ページを使用してパラメーターを構成します。</span><span class="sxs-lookup"><span data-stu-id="7edbb-124">For other parameter types, use the properties page to configure the parameter.</span></span>  
  
   <span data-ttu-id="7edbb-125">**パラメーターの型**</span><span class="sxs-lookup"><span data-stu-id="7edbb-125">**Parameter types**</span></span>  
  
   <span data-ttu-id="7edbb-126">パラメーターは、参照パラメーターおよび出力パラメーターとして、値で渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="7edbb-126">Parameters can be passed by value, as reference parameters, and as out parameters.</span></span> <span data-ttu-id="7edbb-127">パラメーターを値でオーケストレーションに渡すと、データのコピーが作成され、オーケストレーションによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="7edbb-127">When a parameter is passed by value to an orchestration, a copy of the data is made and used by the orchestration.</span></span>  
  
   <span data-ttu-id="7edbb-128">参照パラメーターを使用する場合、コピーは作成されません。</span><span class="sxs-lookup"><span data-stu-id="7edbb-128">When you use a reference parameter, no copy is made.</span></span> <span data-ttu-id="7edbb-129">データが格納されているメモリ位置は、呼び出し元のプログラムとオーケストレーションによって共有されます。また、オーケストレーションは、このメモリ位置の内容を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="7edbb-129">The memory location that contains the data is shared between the calling program and the orchestration, and the contents of this memory location can be modified by the orchestration.</span></span> <span data-ttu-id="7edbb-130">このような変更は、パラメーターの値がオーケストレーション内だけでなく、呼び出し元のプログラム内でも変更されるということを意味します。</span><span class="sxs-lookup"><span data-stu-id="7edbb-130">Such a modification means that the value of the parameter is changed not only in the orchestration, but also in the calling program.</span></span>  
  
   <span data-ttu-id="7edbb-131">出力パラメーターは参照パラメーターに似ています。ただし、オーケストレーションは、出力パラメーターを渡されたときに、そのパラメーターに有効なデータが格納されていると想定することができません。代わりに、呼び出し元のプログラムは、オーケストレーションがこのパラメーターに値を割り当てると想定します。</span><span class="sxs-lookup"><span data-stu-id="7edbb-131">An out parameter is similar to a reference parameter, but the orchestration cannot assume that it contains valid data when passed in; rather, the calling program expects the orchestration to assign a value to this parameter.</span></span>  
  
   <span data-ttu-id="7edbb-132">**オーケストレーション パラメーターのルール**</span><span class="sxs-lookup"><span data-stu-id="7edbb-132">**Rules for orchestration parameters**</span></span>  
  
-   <span data-ttu-id="7edbb-133">出力パラメーターまたは参照パラメーターとして渡すことができるのはメッセージと変数 (オブジェクトを含む) だけです。</span><span class="sxs-lookup"><span data-stu-id="7edbb-133">You can pass only messages and variables (including objects) as out or reference parameters.</span></span>  
  
-   <span data-ttu-id="7edbb-134">を渡すまたはオーケストレーションにパラメーターを参照することはできません、**オーケストレーションの開始**図形。</span><span class="sxs-lookup"><span data-stu-id="7edbb-134">You cannot pass out or reference parameters to an orchestration in a **Start Orchestration** shape.</span></span>  
  
-   <span data-ttu-id="7edbb-135">ロール リンクや動的ポートなどの入力パラメーターは、オーケストレーションに渡す前に明示的に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7edbb-135">In parameters, including any role links and dynamic ports, must be definitely assigned before being passed to an orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7edbb-136">参照</span><span class="sxs-lookup"><span data-stu-id="7edbb-136">See Also</span></span>  
 <span data-ttu-id="7edbb-137">[オーケストレーション図形](../core/orchestration-shapes.md) </span><span class="sxs-lookup"><span data-stu-id="7edbb-137">[Orchestration Shapes](../core/orchestration-shapes.md) </span></span>  
 <span data-ttu-id="7edbb-138">[オーケストレーションに図形を追加する方法](../core/how-to-add-shapes-to-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="7edbb-138">[How to Add Shapes to Orchestrations](../core/how-to-add-shapes-to-orchestrations.md) </span></span>  
 <span data-ttu-id="7edbb-139">[[成果物の種類] ダイアログ ボックスを使用する方法](../core/how-to-use-the-select-artifact-type-dialog-box.md)</span><span class="sxs-lookup"><span data-stu-id="7edbb-139">[How to Use the Select Artifact Type Dialog Box](../core/how-to-use-the-select-artifact-type-dialog-box.md)</span></span>
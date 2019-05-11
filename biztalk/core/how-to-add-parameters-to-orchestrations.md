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
ms.openlocfilehash: d68fc3491f8bdb55ad8e41a43144b0cb2f8f8cf8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387283"
---
# <a name="how-to-add-parameters-to-orchestrations"></a><span data-ttu-id="8c59b-102">オーケストレーションにパラメーターを追加する方法</span><span class="sxs-lookup"><span data-stu-id="8c59b-102">How to Add Parameters to Orchestrations</span></span>
<span data-ttu-id="8c59b-103">オーケストレーションの種類 ウィンドウで、オーケストレーションが受け取るパラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8c59b-103">You can specify what parameters your orchestration should take in the Orchestration View window.</span></span> <span data-ttu-id="8c59b-104">オーケストレーションは、パラメーターとして、次の項目を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="8c59b-104">An orchestration can take the following items as parameters:</span></span>  
  
- <span data-ttu-id="8c59b-105">メッセージ</span><span class="sxs-lookup"><span data-stu-id="8c59b-105">Messages</span></span>  
  
- <span data-ttu-id="8c59b-106">変数 (オブジェクトを含む)</span><span class="sxs-lookup"><span data-stu-id="8c59b-106">Variables (including objects)</span></span>  
  
- <span data-ttu-id="8c59b-107">関連付けセット</span><span class="sxs-lookup"><span data-stu-id="8c59b-107">Correlation sets</span></span>  
  
- <span data-ttu-id="8c59b-108">ロール リンク</span><span class="sxs-lookup"><span data-stu-id="8c59b-108">Role links</span></span>  
  
- <span data-ttu-id="8c59b-109">ポート</span><span class="sxs-lookup"><span data-stu-id="8c59b-109">Ports</span></span>  
  
  <span data-ttu-id="8c59b-110">オーケストレーション パラメーターや out パラメーターの間でパラメーターを渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="8c59b-110">Parameters can be passed between orchestrations as in parameters or out parameters.</span></span> <span data-ttu-id="8c59b-111">パラメーターに渡すことができます値渡しまたは参照します。</span><span class="sxs-lookup"><span data-stu-id="8c59b-111">In parameters can be passed by value or by reference.</span></span> <span data-ttu-id="8c59b-112">Out パラメーターできますのみ参照を渡しされます。</span><span class="sxs-lookup"><span data-stu-id="8c59b-112">Out parameters can only be passed by reference.</span></span> <span data-ttu-id="8c59b-113">パラメーターには、変数、メッセージ、関連付けセット、ロール リンク、およびポートを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="8c59b-113">Parameters can include variables, messages, correlation sets, role links, and ports.</span></span>  
  
### <a name="to-set-orchestration-parameters"></a><span data-ttu-id="8c59b-114">オーケストレーション パラメーターを設定するには</span><span class="sxs-lookup"><span data-stu-id="8c59b-114">To set orchestration parameters</span></span>  
  
1.  <span data-ttu-id="8c59b-115">オーケストレーションの種類 ウィンドウで実行して、**オーケストレーション パラメーター**変数、メッセージ、およびポートを追加するフォルダー。</span><span class="sxs-lookup"><span data-stu-id="8c59b-115">In the Orchestration View window, use the **Orchestration Parameters** folder to add variables, messages, and ports.</span></span>  
  
2.  <span data-ttu-id="8c59b-116">追加された各項目に対して、**オーケストレーション パラメーター**フォルダー、[プロパティ] ウィンドウを使用して、**方向**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="8c59b-116">For each item added to the **Orchestration Parameters** folder, use the Properties window to specify the **Direction** property:</span></span>  
  
    -   <span data-ttu-id="8c59b-117">値渡しで渡されるパラメーター。</span><span class="sxs-lookup"><span data-stu-id="8c59b-117">In—A parameter passed in by value.</span></span>  
  
    -   <span data-ttu-id="8c59b-118">Ref、参照渡しで渡されるパラメーター。</span><span class="sxs-lookup"><span data-stu-id="8c59b-118">Ref—A parameter passed in by reference.</span></span>  
  
    -   <span data-ttu-id="8c59b-119">参照によって渡されるパラメーター。</span><span class="sxs-lookup"><span data-stu-id="8c59b-119">Out—A parameter passed out by reference.</span></span>  
  
### <a name="to-add-a-parameter-to-an-orchestration"></a><span data-ttu-id="8c59b-120">オーケストレーションにパラメーターを追加するには</span><span class="sxs-lookup"><span data-stu-id="8c59b-120">To add a parameter to an orchestration</span></span>  
  
1. <span data-ttu-id="8c59b-121">オーケストレーションの種類 ウィンドウで右クリックし、**オーケストレーション パラメーター**フォルダーを目的のパラメーターの種類をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c59b-121">In the Orchestration View window, right-click the **Orchestration Parameters** folder and then click the kind of parameter you want.</span></span>  
  
2. <span data-ttu-id="8c59b-122">構成されたポートおよびロール リンクでは、ウィザードを使用して、パラメーターを構成します。</span><span class="sxs-lookup"><span data-stu-id="8c59b-122">For configured ports and role links, use the wizard to configure the parameter.</span></span>  
  
    <span data-ttu-id="8c59b-123">- または -</span><span class="sxs-lookup"><span data-stu-id="8c59b-123">—Or—</span></span>  
  
    <span data-ttu-id="8c59b-124">その他のパラメーターの型のプロパティ ページを使用して、パラメーターを構成します。</span><span class="sxs-lookup"><span data-stu-id="8c59b-124">For other parameter types, use the properties page to configure the parameter.</span></span>  
  
   <span data-ttu-id="8c59b-125">**パラメーターの型**</span><span class="sxs-lookup"><span data-stu-id="8c59b-125">**Parameter types**</span></span>  
  
   <span data-ttu-id="8c59b-126">参照のパラメーターとして値渡しのパラメーターを渡すことが呼び出し力パラメーターとして。</span><span class="sxs-lookup"><span data-stu-id="8c59b-126">Parameters can be passed by value, as reference parameters, and as out parameters.</span></span> <span data-ttu-id="8c59b-127">オーケストレーションにパラメーターが値によって渡されると、データのコピーが行われ、オーケストレーションによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="8c59b-127">When a parameter is passed by value to an orchestration, a copy of the data is made and used by the orchestration.</span></span>  
  
   <span data-ttu-id="8c59b-128">参照パラメーターを使用する場合、コピーは作成されません。</span><span class="sxs-lookup"><span data-stu-id="8c59b-128">When you use a reference parameter, no copy is made.</span></span> <span data-ttu-id="8c59b-129">呼び出し元のプログラムと、オーケストレーション間、データが含まれるメモリ位置で共有し、オーケストレーションによって、このメモリ位置の内容を変更できます。</span><span class="sxs-lookup"><span data-stu-id="8c59b-129">The memory location that contains the data is shared between the calling program and the orchestration, and the contents of this memory location can be modified by the orchestration.</span></span> <span data-ttu-id="8c59b-130">このような変更は、オーケストレーション内だけでなく、呼び出し元のプログラムでも、パラメーターの値が変更されたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="8c59b-130">Such a modification means that the value of the parameter is changed not only in the orchestration, but also in the calling program.</span></span>  
  
   <span data-ttu-id="8c59b-131">出力パラメーターは、参照パラメーターに似ていますが、オーケストレーションはことはできません。 渡されたときに有効なデータが含まれている前提としています。代わりに、呼び出し元のプログラムには、このパラメーターに値を代入するオーケストレーションが期待しています。</span><span class="sxs-lookup"><span data-stu-id="8c59b-131">An out parameter is similar to a reference parameter, but the orchestration cannot assume that it contains valid data when passed in; rather, the calling program expects the orchestration to assign a value to this parameter.</span></span>  
  
   <span data-ttu-id="8c59b-132">**オーケストレーション パラメーターのルール**</span><span class="sxs-lookup"><span data-stu-id="8c59b-132">**Rules for orchestration parameters**</span></span>  
  
-   <span data-ttu-id="8c59b-133">のみのメッセージや変数 (オブジェクトを含む) 時 out を渡すか、パラメーターを参照できます。</span><span class="sxs-lookup"><span data-stu-id="8c59b-133">You can pass only messages and variables (including objects) as out or reference parameters.</span></span>  
  
-   <span data-ttu-id="8c59b-134">を渡すまたはオーケストレーションにパラメーターを参照することはできません、**オーケストレーションの開始**図形。</span><span class="sxs-lookup"><span data-stu-id="8c59b-134">You cannot pass out or reference parameters to an orchestration in a **Start Orchestration** shape.</span></span>  
  
-   <span data-ttu-id="8c59b-135">ロール リンクや動的ポートを含むパラメーターにする必要があります明示的に代入するオーケストレーションに渡される前にします。</span><span class="sxs-lookup"><span data-stu-id="8c59b-135">In parameters, including any role links and dynamic ports, must be definitely assigned before being passed to an orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c59b-136">参照</span><span class="sxs-lookup"><span data-stu-id="8c59b-136">See Also</span></span>  
 <span data-ttu-id="8c59b-137">[オーケストレーション図形](../core/orchestration-shapes.md) </span><span class="sxs-lookup"><span data-stu-id="8c59b-137">[Orchestration Shapes](../core/orchestration-shapes.md) </span></span>  
 <span data-ttu-id="8c59b-138">[オーケストレーションに図形を追加する方法](../core/how-to-add-shapes-to-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="8c59b-138">[How to Add Shapes to Orchestrations](../core/how-to-add-shapes-to-orchestrations.md) </span></span>  
 <span data-ttu-id="8c59b-139">[[成果物の種類] ダイアログ ボックスを使用する方法](../core/how-to-use-the-select-artifact-type-dialog-box.md)</span><span class="sxs-lookup"><span data-stu-id="8c59b-139">[How to Use the Select Artifact Type Dialog Box](../core/how-to-use-the-select-artifact-type-dialog-box.md)</span></span>
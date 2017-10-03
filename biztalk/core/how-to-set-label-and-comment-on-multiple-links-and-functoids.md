---
title: "複数のリンクおよび Functoid のラベルとコメントを設定する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2b554a19-2bd4-4dbc-b5cb-567b98c07024
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65bcb25fae52da46bbea1679e3b4e215720782d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-label-and-comment-on-multiple-links-and-functoids"></a><span data-ttu-id="0bb68-102">複数のリンクおよび Functoid にラベルおよびコメントを設定する方法</span><span class="sxs-lookup"><span data-stu-id="0bb68-102">How to Set Label and Comment on Multiple Links and Functoids</span></span>
<span data-ttu-id="0bb68-103">複数の Functoid やリンクに共通のラベルやコメントを設定できます。</span><span class="sxs-lookup"><span data-stu-id="0bb68-103">You can set a common label and/or a comment for multiple functoids and/or links.</span></span> <span data-ttu-id="0bb68-104">このトピックでは、次の操作を実行する方法の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="0bb68-104">This topic provides details about how to perform this operation.</span></span>  
  
 <span data-ttu-id="0bb68-105">複数の functoid およびリンクを選択する方法については、次を参照してください。[および Functoid を複数のリンクを選択する方法](../core/how-to-select-multiple-links-and-functoids.md)です。</span><span class="sxs-lookup"><span data-stu-id="0bb68-105">For information about how to select multiple functoid(s) and/or link(s), see [How to Select Multiple Links and Functoids](../core/how-to-select-multiple-links-and-functoids.md).</span></span>  
  
 <span data-ttu-id="0bb68-106">複数の Functoid およびリンクを選択した後は、以下のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0bb68-106">After selecting multiple functoid(s) and/or link(s), you can do any of the following:</span></span>  
  
-   <span data-ttu-id="0bb68-107">選択したリンクに共通のラベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="0bb68-107">Set a common label for selected links.</span></span>  
  
-   <span data-ttu-id="0bb68-108">選択した Functoid に共通のラベルやコメントを設定します。</span><span class="sxs-lookup"><span data-stu-id="0bb68-108">Set a common label and/or comment for the selected functoids.</span></span>  
  
-   <span data-ttu-id="0bb68-109">選択した Functoid とリンクに共通のラベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="0bb68-109">Set a common label for the selected functoids and links.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0bb68-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="0bb68-110">Prerequisites</span></span>  
 <span data-ttu-id="0bb68-111">これらの手順では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bb68-111">These instructions require that BizTalk Mapper is running.</span></span>  
  
## <a name="to-set-a-common-label-for-selected-links"></a><span data-ttu-id="0bb68-112">選択したリンクに共通のラベルを設定するには</span><span class="sxs-lookup"><span data-stu-id="0bb68-112">To set a common label for selected links</span></span>  
 <span data-ttu-id="0bb68-113">複数のリンクに対する共通ラベルの設定は、1 つのアトミック操作です。</span><span class="sxs-lookup"><span data-stu-id="0bb68-113">Setting a common label on multiple links is one atomic operation.</span></span> <span data-ttu-id="0bb68-114">この操作は元に戻したり、やり直したりできます。</span><span class="sxs-lookup"><span data-stu-id="0bb68-114">You can undo or redo this operation.</span></span>  
  
 <span data-ttu-id="0bb68-115">選択したリンクに共通のラベルを設定するには:</span><span class="sxs-lookup"><span data-stu-id="0bb68-115">To set a common label for the selected links:</span></span>  
  
1.  <span data-ttu-id="0bb68-116">マッパー グリッド ページで、対象のリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="0bb68-116">On the Mapper grid page, select the desired links.</span></span>  
  
2.  <span data-ttu-id="0bb68-117">**プロパティ** ウィンドウで適切なラベルを入力、**ラベル**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="0bb68-117">In the **Properties** window, enter a suitable label in the **Label** property.</span></span>  
  
## <a name="to-set-a-common-label-andor-comment-for-selected-functoids"></a><span data-ttu-id="0bb68-118">選択した Functoid に共通のラベルやコメントを設定するには</span><span class="sxs-lookup"><span data-stu-id="0bb68-118">To set a common label and/or comment for selected functoids</span></span>  
 <span data-ttu-id="0bb68-119">選択した Functoid に対する共通のラベルの設定および共通のコメントの設定は、2 つの異なるアトミック操作です。</span><span class="sxs-lookup"><span data-stu-id="0bb68-119">Setting a common label and setting a common comment for the selected functoids are two different atomic operations.</span></span> <span data-ttu-id="0bb68-120">これらの操作は元に戻したり、やり直したりできます。</span><span class="sxs-lookup"><span data-stu-id="0bb68-120">You can undo or redo these operations.</span></span>  
  
 <span data-ttu-id="0bb68-121">選択した Functoid に共通のラベルやコメントを設定するには:</span><span class="sxs-lookup"><span data-stu-id="0bb68-121">To set a common label/comment for the selected functoids:</span></span>  
  
1.  <span data-ttu-id="0bb68-122">マッパー グリッド ページで、対象の Functoid を選択します。</span><span class="sxs-lookup"><span data-stu-id="0bb68-122">On the Mapper grid page, select the desired functoids.</span></span>  
  
2.  <span data-ttu-id="0bb68-123">**プロパティ**ウィンドウで、入力に適切なラベルやコメントを**ラベル**と**コメント**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="0bb68-123">In the **Properties** window, enter a suitable label and/or comment in the **Label** and **Comments** properties.</span></span>  
  
## <a name="to-set-a-common-label-for-selected-functoids-and-links"></a><span data-ttu-id="0bb68-124">選択した Functoid およびリンクに共通のラベルを設定するには</span><span class="sxs-lookup"><span data-stu-id="0bb68-124">To set a common label for selected functoids and links</span></span>  
 <span data-ttu-id="0bb68-125">選択した Functoid とリンクに共通のラベルを設定できます。</span><span class="sxs-lookup"><span data-stu-id="0bb68-125">You can set a common label for the selected functoids and links.</span></span> <span data-ttu-id="0bb68-126">**ラベル**のみプロパティは、functoid およびリンクの両方に共通です。</span><span class="sxs-lookup"><span data-stu-id="0bb68-126">**Label** is the only property which is common to both functoids and links.</span></span> <span data-ttu-id="0bb68-127">この操作は元に戻したり、やり直したりできます。</span><span class="sxs-lookup"><span data-stu-id="0bb68-127">You can undo or redo this operation.</span></span>  
  
 <span data-ttu-id="0bb68-128">選択した Functoid およびリンクに共通のラベルを設定するには: </span><span class="sxs-lookup"><span data-stu-id="0bb68-128">To set a common label for the selected functoids and links:</span></span>  
  
1.  <span data-ttu-id="0bb68-129">マッパー グリッド ページで、対象の Functoid およびリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="0bb68-129">On the Mapper grid page, select the desired functoids and links.</span></span>  
  
2.  <span data-ttu-id="0bb68-130">**プロパティ** ウィンドウで適切なラベルを入力、**ラベル**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="0bb68-130">In the **Properties** window, enter a suitable label in the **Label** property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bb68-131">参照</span><span class="sxs-lookup"><span data-stu-id="0bb68-131">See Also</span></span>  
 [<span data-ttu-id="0bb68-132">リンクを使用してレコードを指定してフィールドのマッピング</span><span class="sxs-lookup"><span data-stu-id="0bb68-132">Using Links to Specify Record and Field Mappings</span></span>](../core/using-links-to-specify-record-and-field-mappings.md)
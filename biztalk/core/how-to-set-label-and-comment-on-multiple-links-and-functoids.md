---
title: 複数のリンクおよび Functoid のラベルとコメントを設定する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b554a19-2bd4-4dbc-b5cb-567b98c07024
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9353a8d612d5aac43f380e1410809f61fa19f708
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334385"
---
# <a name="how-to-set-label-and-comment-on-multiple-links-and-functoids"></a><span data-ttu-id="a7b0f-102">複数のリンクおよび Functoid にラベルおよびコメントを設定する方法</span><span class="sxs-lookup"><span data-stu-id="a7b0f-102">How to Set Label and Comment on Multiple Links and Functoids</span></span>
<span data-ttu-id="a7b0f-103">共通のラベルや複数の functoid やリンクのコメントを設定できます。</span><span class="sxs-lookup"><span data-stu-id="a7b0f-103">You can set a common label and/or a comment for multiple functoids and/or links.</span></span> <span data-ttu-id="a7b0f-104">このトピックでは、この操作を実行する方法について詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="a7b0f-104">This topic provides details about how to perform this operation.</span></span>  
  
 <span data-ttu-id="a7b0f-105">複数の functoid およびリンクを選択する方法については、次を参照してください。[および Functoid を複数のリンクを選択する方法](../core/how-to-select-multiple-links-and-functoids.md)します。</span><span class="sxs-lookup"><span data-stu-id="a7b0f-105">For information about how to select multiple functoid(s) and/or link(s), see [How to Select Multiple Links and Functoids](../core/how-to-select-multiple-links-and-functoids.md).</span></span>  
  
 <span data-ttu-id="a7b0f-106">複数の functoid およびリンクを選択した後、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a7b0f-106">After selecting multiple functoid(s) and/or link(s), you can do any of the following:</span></span>  
  
-   <span data-ttu-id="a7b0f-107">選択したリンクに共通のラベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="a7b0f-107">Set a common label for selected links.</span></span>  
  
-   <span data-ttu-id="a7b0f-108">共通のラベルや選択した functoid のコメントを設定します。</span><span class="sxs-lookup"><span data-stu-id="a7b0f-108">Set a common label and/or comment for the selected functoids.</span></span>  
  
-   <span data-ttu-id="a7b0f-109">選択した functoid およびリンクに共通のラベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="a7b0f-109">Set a common label for the selected functoids and links.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a7b0f-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="a7b0f-110">Prerequisites</span></span>  
 <span data-ttu-id="a7b0f-111">これらの手順では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7b0f-111">These instructions require that BizTalk Mapper is running.</span></span>  
  
## <a name="to-set-a-common-label-for-selected-links"></a><span data-ttu-id="a7b0f-112">選択したリンクに共通のラベルを設定するには</span><span class="sxs-lookup"><span data-stu-id="a7b0f-112">To set a common label for selected links</span></span>  
 <span data-ttu-id="a7b0f-113">1 つのアトミック操作は、複数のリンクに共通のラベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="a7b0f-113">Setting a common label on multiple links is one atomic operation.</span></span> <span data-ttu-id="a7b0f-114">元に戻すまたはこの操作をやり直すことができます。</span><span class="sxs-lookup"><span data-stu-id="a7b0f-114">You can undo or redo this operation.</span></span>  
  
 <span data-ttu-id="a7b0f-115">選択したリンクに共通のラベルを設定するには。</span><span class="sxs-lookup"><span data-stu-id="a7b0f-115">To set a common label for the selected links:</span></span>  
  
1.  <span data-ttu-id="a7b0f-116">マッパー グリッド ページで、対象のリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="a7b0f-116">On the Mapper grid page, select the desired links.</span></span>  
  
2.  <span data-ttu-id="a7b0f-117">**プロパティ** ウィンドウで適切なラベルを入力、**ラベル**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a7b0f-117">In the **Properties** window, enter a suitable label in the **Label** property.</span></span>  
  
## <a name="to-set-a-common-label-andor-comment-for-selected-functoids"></a><span data-ttu-id="a7b0f-118">共通のラベルや選択した functoid のコメントを設定するには</span><span class="sxs-lookup"><span data-stu-id="a7b0f-118">To set a common label and/or comment for selected functoids</span></span>  
 <span data-ttu-id="a7b0f-119">共通のラベルを設定し、選択した functoid の一般的なコメントを設定は、2 つの異なるアトミック操作です。</span><span class="sxs-lookup"><span data-stu-id="a7b0f-119">Setting a common label and setting a common comment for the selected functoids are two different atomic operations.</span></span> <span data-ttu-id="a7b0f-120">元に戻すまたはこれらの操作をやり直すことができます。</span><span class="sxs-lookup"><span data-stu-id="a7b0f-120">You can undo or redo these operations.</span></span>  
  
 <span data-ttu-id="a7b0f-121">選択した functoid に共通のラベルやコメントを設定します。</span><span class="sxs-lookup"><span data-stu-id="a7b0f-121">To set a common label/comment for the selected functoids:</span></span>  
  
1.  <span data-ttu-id="a7b0f-122">マッパー グリッド ページで、対象の functoid を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7b0f-122">On the Mapper grid page, select the desired functoids.</span></span>  
  
2.  <span data-ttu-id="a7b0f-123">**プロパティ**ウィンドウで、入力に適切なラベルやコメントを**ラベル**と**コメント**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a7b0f-123">In the **Properties** window, enter a suitable label and/or comment in the **Label** and **Comments** properties.</span></span>  
  
## <a name="to-set-a-common-label-for-selected-functoids-and-links"></a><span data-ttu-id="a7b0f-124">選択した functoid およびリンクに共通のラベルを設定するには</span><span class="sxs-lookup"><span data-stu-id="a7b0f-124">To set a common label for selected functoids and links</span></span>  
 <span data-ttu-id="a7b0f-125">選択した functoid およびリンクに共通のラベルを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="a7b0f-125">You can set a common label for the selected functoids and links.</span></span> <span data-ttu-id="a7b0f-126">**ラベル**functoid とリンクの両方に共通である専用のプロパティします。</span><span class="sxs-lookup"><span data-stu-id="a7b0f-126">**Label** is the only property which is common to both functoids and links.</span></span> <span data-ttu-id="a7b0f-127">元に戻すまたはこの操作をやり直すことができます。</span><span class="sxs-lookup"><span data-stu-id="a7b0f-127">You can undo or redo this operation.</span></span>  
  
 <span data-ttu-id="a7b0f-128">選択した functoid およびリンクに共通のラベルを設定するには。</span><span class="sxs-lookup"><span data-stu-id="a7b0f-128">To set a common label for the selected functoids and links:</span></span>  
  
1.  <span data-ttu-id="a7b0f-129">マッパー グリッド ページで、目的の functoid およびリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="a7b0f-129">On the Mapper grid page, select the desired functoids and links.</span></span>  
  
2.  <span data-ttu-id="a7b0f-130">**プロパティ** ウィンドウで適切なラベルを入力、**ラベル**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a7b0f-130">In the **Properties** window, enter a suitable label in the **Label** property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7b0f-131">参照</span><span class="sxs-lookup"><span data-stu-id="a7b0f-131">See Also</span></span>  
 [<span data-ttu-id="a7b0f-132">リンクを使用してレコードとフィールド マッピングを指定する</span><span class="sxs-lookup"><span data-stu-id="a7b0f-132">Using Links to Specify Record and Field Mappings</span></span>](../core/using-links-to-specify-record-and-field-mappings.md)
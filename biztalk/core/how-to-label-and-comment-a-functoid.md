---
title: ラベルを付けるし、Functoid のコメントを指定する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.functiod.general
ms.assetid: 58ff3a07-cbb6-4817-b301-d2b434ed2ad9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5720402e548992044eda26366c8b7b50bb95746a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-label-and-comment-a-functoid"></a><span data-ttu-id="1f518-102">Functoid にラベル付けする方法とコメントを追加する方法</span><span class="sxs-lookup"><span data-stu-id="1f518-102">How to Label and Comment a Functoid</span></span>
<span data-ttu-id="1f518-103">ラベルとコメントは、マップの Functoid またはリンクの目的を文書化するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1f518-103">Labels and comments are helpful to document the purpose of a functoid or a link in a map.</span></span> <span data-ttu-id="1f518-104">使用することができます、**ラベル**functoid の名前を指定するプロパティです。</span><span class="sxs-lookup"><span data-stu-id="1f518-104">You can use the **Label** property to provide a name for a functoid.</span></span> <span data-ttu-id="1f518-105">**コメント**プロパティでは、によって実行される操作についての関連する通常、functoid に関する追加情報を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="1f518-105">The **Comments** property enables you to provide additional information about the functoid, typically relevant information about the operation being performed by it.</span></span>  
  
 <span data-ttu-id="1f518-106">次の図では、Functoid のラベルとコメントを示します。</span><span class="sxs-lookup"><span data-stu-id="1f518-106">The following figure shows the label and comments for a functoid.</span></span> <span data-ttu-id="1f518-107">この Functoid は、送信元スキーマからの 2 つの入力 (Field1 と Field3) を追加し、ターゲット スキーマの Field4 に結果を出力します。</span><span class="sxs-lookup"><span data-stu-id="1f518-107">The functoid adds two inputs (Field1 and Field3) from the source schema and outputs the result to Field4 in the target schema.</span></span> <span data-ttu-id="1f518-108">この例では、Functoid のラベルは "Add Field1 and Field3" で、コメントは "The addition is an output to Field4" です。</span><span class="sxs-lookup"><span data-stu-id="1f518-108">In this example, the functoid label is “Add Field1 and Field3” and the comment is “The addition is an output to Field4”.</span></span>  
  
 <span data-ttu-id="1f518-109">![Functoid のラベルとコメントを挿入する](../core/media/label.gif "Label_")</span><span class="sxs-lookup"><span data-stu-id="1f518-109">![Inserting functoid labels and comments](../core/media/label.gif "Label_")</span></span>  
  
 <span data-ttu-id="1f518-110">Functoid は非常に複雑なマッピングの一部である場合があるので、適切なラベルを付け、関連するコメントも指定することが重要です。</span><span class="sxs-lookup"><span data-stu-id="1f518-110">Because a functoid can be a part of very complex mapping, it is important to label it properly and also to provide relevant comments.</span></span> <span data-ttu-id="1f518-111">Functoid とリンクの両方にラベルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="1f518-111">You can label both functoids and links.</span></span> <span data-ttu-id="1f518-112">リンクのラベルを付ける方法については、次を参照してください。[リンクのラベルを付ける方法](../core/how-to-label-a-link.md)です。</span><span class="sxs-lookup"><span data-stu-id="1f518-112">For information on how to label a link, see [How to Label a Link](../core/how-to-label-a-link.md).</span></span>  
  
 <span data-ttu-id="1f518-113">Functoid のラベルとコメントは次の方法で指定できます。</span><span class="sxs-lookup"><span data-stu-id="1f518-113">You can label and comment a functoid in the following ways:</span></span>  
  
-   <span data-ttu-id="1f518-114">使用して、**構成\<Functoid\> Functoid**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="1f518-114">By using the **Configure \<Functoid\> Functoid** dialog box.</span></span>  
  
-   <span data-ttu-id="1f518-115">使用して、**プロパティ**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="1f518-115">By using the **Properties** window.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1f518-116">前提条件</span><span class="sxs-lookup"><span data-stu-id="1f518-116">Prerequisites</span></span>  
 <span data-ttu-id="1f518-117">これらの手順では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f518-117">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-label-and-comment-a-functoid-from-configure-dialog-box"></a><span data-ttu-id="1f518-118">構成ダイアログ ボックスで Functoid のラベルとコメントを指定するには</span><span class="sxs-lookup"><span data-stu-id="1f518-118">To label and comment a functoid from Configure dialog box</span></span>  
  
1.  <span data-ttu-id="1f518-119">Functoid のラベルとコメント、して、をクリックを右クリックして**Functoid 入力の構成**です。</span><span class="sxs-lookup"><span data-stu-id="1f518-119">Right-click the functoid you want to label and comment, and then click **Configure Functoid Inputs**.</span></span>  
  
2.  <span data-ttu-id="1f518-120">**構成\<Functoid\> Functoid**ダイアログ ボックスで、をクリックして、**ラベルとコメント**タブです。</span><span class="sxs-lookup"><span data-stu-id="1f518-120">In the **Configure \<Functoid\> Functoid** dialog box, click the **Label and Comments** tab.</span></span>  
  
3.  <span data-ttu-id="1f518-121">次の情報を入力し、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="1f518-121">Enter the following information, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="1f518-122">**ラベル –**新しい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="1f518-122">**Label –** Enter the new name.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="1f518-123">使用できる文字の最大数は 256 です。</span><span class="sxs-lookup"><span data-stu-id="1f518-123">The maximum number of characters allowed is 256.</span></span> <span data-ttu-id="1f518-124">数は 256 文字の文字列が指定されている場合は、最初の 256 文字が受け入れられ、残りの部分は破棄されます。</span><span class="sxs-lookup"><span data-stu-id="1f518-124">If a string with more than 256 characters is specified, the first 256 characters are accepted and the rest are discarded.</span></span>  
  
    -   <span data-ttu-id="1f518-125">**コメント –** functoid のコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="1f518-125">**Comments –** Enter the comments for the functoid.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="1f518-126">使用できる文字の最大数は 1024 です。</span><span class="sxs-lookup"><span data-stu-id="1f518-126">The maximum number of characters allowed is 1024.</span></span> <span data-ttu-id="1f518-127">1024 を超える文字の文字列が指定されている場合は、最初の 1024 文字が受け入れられ、残りの部分は破棄されます。</span><span class="sxs-lookup"><span data-stu-id="1f518-127">If a string with more than 1024 characters is specified, the first 1024 characters are accepted and the rest are discarded.</span></span>  
  
### <a name="to-label-and-comment-a-functoid-from-properties-window"></a><span data-ttu-id="1f518-128">[プロパティ] ウィンドウで Functoid のラベルとコメントを指定するには</span><span class="sxs-lookup"><span data-stu-id="1f518-128">To label and comment a functoid from Properties window</span></span>  
  
1.  <span data-ttu-id="1f518-129">ラベルとコメントを指定する Functoid を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f518-129">Select the functoid you want to label and comment.</span></span>  
  
2.  <span data-ttu-id="1f518-130">**プロパティ**ウィンドウが、次の情報を入力し、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="1f518-130">In the **Properties** window, enter the following information, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="1f518-131">**ラベル –**新しい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="1f518-131">**Label –** Enter the new name.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="1f518-132">使用できる文字の最大数は 256 です。</span><span class="sxs-lookup"><span data-stu-id="1f518-132">The maximum number of characters allowed is 256.</span></span> <span data-ttu-id="1f518-133">数は 256 文字の文字列が指定されている場合は、最初の 256 文字が受け入れられ、残りの部分は破棄されます。</span><span class="sxs-lookup"><span data-stu-id="1f518-133">If a string with more than 256 characters is specified, the first 256 characters are accepted and the rest are discarded.</span></span>  
  
    -   <span data-ttu-id="1f518-134">**コメント –** functoid のコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="1f518-134">**Comments –** Enter the comments for the functoid.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="1f518-135">使用できる文字の最大数は 1024 です。</span><span class="sxs-lookup"><span data-stu-id="1f518-135">The maximum number of characters allowed is 1024.</span></span> <span data-ttu-id="1f518-136">1024 を超える文字の文字列が指定されている場合は、最初の 1024 文字が受け入れられ、残りの部分は破棄されます。</span><span class="sxs-lookup"><span data-stu-id="1f518-136">If a string with more than 1024 characters is specified, the first 1024 characters are accepted and the rest are discarded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f518-137">参照</span><span class="sxs-lookup"><span data-stu-id="1f518-137">See Also</span></span>  
 [<span data-ttu-id="1f518-138">Functoid のプロパティおよび入力パラメーターの編集</span><span class="sxs-lookup"><span data-stu-id="1f518-138">Editing Functoid Properties and Input Parameters</span></span>](../core/editing-functoid-properties-and-input-parameters.md)
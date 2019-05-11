---
title: Functoid、ラベルし、コメントする方法 |Microsoft Docs
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
ms.openlocfilehash: db30ca1b7bee06c633245e05808ad521b27e51d2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384863"
---
# <a name="how-to-label-and-comment-a-functoid"></a><span data-ttu-id="989c5-102">Functoid、ラベルし、コメントする方法</span><span class="sxs-lookup"><span data-stu-id="989c5-102">How to Label and Comment a Functoid</span></span>
<span data-ttu-id="989c5-103">ラベルとコメントは、functoid またはマップ内のリンクの目的を文書化に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="989c5-103">Labels and comments are helpful to document the purpose of a functoid or a link in a map.</span></span> <span data-ttu-id="989c5-104">使用することができます、**ラベル**functoid の名前を指定するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="989c5-104">You can use the **Label** property to provide a name for a functoid.</span></span> <span data-ttu-id="989c5-105">**コメント**プロパティでは、通常に関連することによって実行される操作について、functoid に関する追加情報を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="989c5-105">The **Comments** property enables you to provide additional information about the functoid, typically relevant information about the operation being performed by it.</span></span>  
  
 <span data-ttu-id="989c5-106">次の図は、ラベルと、functoid のコメントを示します。</span><span class="sxs-lookup"><span data-stu-id="989c5-106">The following figure shows the label and comments for a functoid.</span></span> <span data-ttu-id="989c5-107">Functoid は、送信元スキーマから 2 つの入力 (Field1 と Field3) を追加し、ターゲット スキーマの Field4 に結果を出力します。</span><span class="sxs-lookup"><span data-stu-id="989c5-107">The functoid adds two inputs (Field1 and Field3) from the source schema and outputs the result to Field4 in the target schema.</span></span> <span data-ttu-id="989c5-108">この例では、functoid のラベルは"Add Field1 and Field3"とコメントが"The addition is an output to Field4"。</span><span class="sxs-lookup"><span data-stu-id="989c5-108">In this example, the functoid label is “Add Field1 and Field3” and the comment is “The addition is an output to Field4”.</span></span>  
  
 <span data-ttu-id="989c5-109">![Functoid のラベルとコメントを挿入する](../core/media/label.gif "Label_")</span><span class="sxs-lookup"><span data-stu-id="989c5-109">![Inserting functoid labels and comments](../core/media/label.gif "Label_")</span></span>  
  
 <span data-ttu-id="989c5-110">非常に複雑なマッピングの一部の functoid を使用できる、ので、適切にラベルと関連するコメントを提供する重要なは。</span><span class="sxs-lookup"><span data-stu-id="989c5-110">Because a functoid can be a part of very complex mapping, it is important to label it properly and also to provide relevant comments.</span></span> <span data-ttu-id="989c5-111">ラベルの functoid およびリンクの両方を指定できます。</span><span class="sxs-lookup"><span data-stu-id="989c5-111">You can label both functoids and links.</span></span> <span data-ttu-id="989c5-112">リンクのラベル付けする方法については、次を参照してください。[リンクにラベルを付ける方法](../core/how-to-label-a-link.md)します。</span><span class="sxs-lookup"><span data-stu-id="989c5-112">For information on how to label a link, see [How to Label a Link](../core/how-to-label-a-link.md).</span></span>  
  
 <span data-ttu-id="989c5-113">ラベルおよび functoid のコメントを次のようにできます。</span><span class="sxs-lookup"><span data-stu-id="989c5-113">You can label and comment a functoid in the following ways:</span></span>  
  
-   <span data-ttu-id="989c5-114">使用して、**構成\<Functoid\> Functoid**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="989c5-114">By using the **Configure \<Functoid\> Functoid** dialog box.</span></span>  
  
-   <span data-ttu-id="989c5-115">使用して、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="989c5-115">By using the **Properties** window.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="989c5-116">前提条件</span><span class="sxs-lookup"><span data-stu-id="989c5-116">Prerequisites</span></span>  
 <span data-ttu-id="989c5-117">これらの手順では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="989c5-117">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-label-and-comment-a-functoid-from-configure-dialog-box"></a><span data-ttu-id="989c5-118">ラベルとコメントの構成 ダイアログ ボックスから functoid を</span><span class="sxs-lookup"><span data-stu-id="989c5-118">To label and comment a functoid from Configure dialog box</span></span>  
  
1.  <span data-ttu-id="989c5-119">Functoid のラベルとコメントをクリックしたを右クリックして**Functoid 入力の構成**します。</span><span class="sxs-lookup"><span data-stu-id="989c5-119">Right-click the functoid you want to label and comment, and then click **Configure Functoid Inputs**.</span></span>  
  
2.  <span data-ttu-id="989c5-120">**構成\<Functoid\> Functoid**ダイアログ ボックスで、をクリックして、**ラベルとコメント**タブ。</span><span class="sxs-lookup"><span data-stu-id="989c5-120">In the **Configure \<Functoid\> Functoid** dialog box, click the **Label and Comments** tab.</span></span>  
  
3.  <span data-ttu-id="989c5-121">次の情報を入力し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="989c5-121">Enter the following information, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="989c5-122">**ラベル –** 新しい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="989c5-122">**Label –** Enter the new name.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="989c5-123">許可される文字の最大数には 256 です。</span><span class="sxs-lookup"><span data-stu-id="989c5-123">The maximum number of characters allowed is 256.</span></span> <span data-ttu-id="989c5-124">数は 256 文字の文字列が指定されている場合は、最初の 256 文字が受け入れられ、残りは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="989c5-124">If a string with more than 256 characters is specified, the first 256 characters are accepted and the rest are discarded.</span></span>  
  
    -   <span data-ttu-id="989c5-125">**コメント –** functoid のコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="989c5-125">**Comments –** Enter the comments for the functoid.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="989c5-126">許可される文字の最大数は、1024 です。</span><span class="sxs-lookup"><span data-stu-id="989c5-126">The maximum number of characters allowed is 1024.</span></span> <span data-ttu-id="989c5-127">1,024 個を超える文字の文字列が指定されている場合は、最初の 1024 文字が受け入れられ、残りは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="989c5-127">If a string with more than 1024 characters is specified, the first 1024 characters are accepted and the rest are discarded.</span></span>  
  
### <a name="to-label-and-comment-a-functoid-from-properties-window"></a><span data-ttu-id="989c5-128">ラベルとコメント プロパティ ウィンドウから functoid を</span><span class="sxs-lookup"><span data-stu-id="989c5-128">To label and comment a functoid from Properties window</span></span>  
  
1.  <span data-ttu-id="989c5-129">ラベルとコメント functoid を選択します。</span><span class="sxs-lookup"><span data-stu-id="989c5-129">Select the functoid you want to label and comment.</span></span>  
  
2.  <span data-ttu-id="989c5-130">**プロパティ**ウィンドウが、次の情報を入力し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="989c5-130">In the **Properties** window, enter the following information, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="989c5-131">**ラベル –** 新しい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="989c5-131">**Label –** Enter the new name.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="989c5-132">許可される文字の最大数には 256 です。</span><span class="sxs-lookup"><span data-stu-id="989c5-132">The maximum number of characters allowed is 256.</span></span> <span data-ttu-id="989c5-133">数は 256 文字の文字列が指定されている場合は、最初の 256 文字が受け入れられ、残りは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="989c5-133">If a string with more than 256 characters is specified, the first 256 characters are accepted and the rest are discarded.</span></span>  
  
    -   <span data-ttu-id="989c5-134">**コメント –** functoid のコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="989c5-134">**Comments –** Enter the comments for the functoid.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="989c5-135">許可される文字の最大数は、1024 です。</span><span class="sxs-lookup"><span data-stu-id="989c5-135">The maximum number of characters allowed is 1024.</span></span> <span data-ttu-id="989c5-136">1,024 個を超える文字の文字列が指定されている場合は、最初の 1024 文字が受け入れられ、残りは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="989c5-136">If a string with more than 1024 characters is specified, the first 1024 characters are accepted and the rest are discarded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="989c5-137">参照</span><span class="sxs-lookup"><span data-stu-id="989c5-137">See Also</span></span>  
 [<span data-ttu-id="989c5-138">Functoid のプロパティおよび入力パラメーターの編集</span><span class="sxs-lookup"><span data-stu-id="989c5-138">Editing Functoid Properties and Input Parameters</span></span>](../core/editing-functoid-properties-and-input-parameters.md)
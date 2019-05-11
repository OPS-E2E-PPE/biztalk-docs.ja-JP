---
title: リンクのラベル付けする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5fb81763-8b50-4334-88a8-efad1c5d82d9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba6bbe74c77cba09ba5098810d8782cde592e55f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336937"
---
# <a name="how-to-label-a-link"></a><span data-ttu-id="3f3fa-102">リンクにラベル付けする方法</span><span class="sxs-lookup"><span data-stu-id="3f3fa-102">How to Label a Link</span></span>
<span data-ttu-id="3f3fa-103">ラベルは、functoid またはマップ内のリンクの目的を文書化すると便利です。</span><span class="sxs-lookup"><span data-stu-id="3f3fa-103">Labels are helpful to document the purpose of a functoid or a link in a map.</span></span> <span data-ttu-id="3f3fa-104">使用することができます、**ラベル**リンクに名前を付けるプロパティ。</span><span class="sxs-lookup"><span data-stu-id="3f3fa-104">You can use the **Label** property to name a link.</span></span> <span data-ttu-id="3f3fa-105">これは、機能は、マップに大きいスキーマ構造が含まれていて、入力と出力へのリンク、functoid を識別するが難しくなるときに便利です。</span><span class="sxs-lookup"><span data-stu-id="3f3fa-105">This is useful when your map contains big schema structures and identifying the inputs and output links to a functoid becomes difficult.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f3fa-106">Functoid のラベルとコメントする方法については、次を参照してください。[方法、Functoid ラベルとコメント](../core/how-to-label-and-comment-a-functoid.md)します。</span><span class="sxs-lookup"><span data-stu-id="3f3fa-106">For information on how to label and comment functoids, see [How to Label and Comment a Functoid](../core/how-to-label-and-comment-a-functoid.md).</span></span>  
  
 <span data-ttu-id="3f3fa-107">次の図は、リンクのラベルを示します。</span><span class="sxs-lookup"><span data-stu-id="3f3fa-107">The following figure shows a link label.</span></span>  
  
 <span data-ttu-id="3f3fa-108">![リンクのラベル付け](../core/media/new-labelling-link.gif "New_Labelling_link")</span><span class="sxs-lookup"><span data-stu-id="3f3fa-108">![Labelling a link](../core/media/new-labelling-link.gif "New_Labelling_link")</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3f3fa-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="3f3fa-109">Prerequisites</span></span>  
 <span data-ttu-id="3f3fa-110">これらの手順では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f3fa-110">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-add-a-label-to-a-link"></a><span data-ttu-id="3f3fa-111">リンクにラベルを追加するには</span><span class="sxs-lookup"><span data-stu-id="3f3fa-111">To add a label to a link</span></span>  
  
1.  <span data-ttu-id="3f3fa-112">ラベルを付けるリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="3f3fa-112">Select the link you want to label.</span></span>  
  
2.  <span data-ttu-id="3f3fa-113">**プロパティ** ウィンドウで新しい名前を指定、**ラベル**フィールド。</span><span class="sxs-lookup"><span data-stu-id="3f3fa-113">In the **Properties** window, provide the new name in the **Label** field.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="3f3fa-114">許可される文字の最大数には 256 です。</span><span class="sxs-lookup"><span data-stu-id="3f3fa-114">The maximum number of characters allowed is 256.</span></span> <span data-ttu-id="3f3fa-115">数は 256 文字の文字列が指定されている場合は、最初の 256 文字が受け入れられ、残りは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="3f3fa-115">If a string with more than 256 characters is specified, the first 256 characters are accepted and the rest are discarded.</span></span>  
  
     <span data-ttu-id="3f3fa-116">![ラベルのプロパティをリンク](../core/media/new-to-label-link.gif "New_To_Label_Link")</span><span class="sxs-lookup"><span data-stu-id="3f3fa-116">![Link label properties](../core/media/new-to-label-link.gif "New_To_Label_Link")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f3fa-117">参照</span><span class="sxs-lookup"><span data-stu-id="3f3fa-117">See Also</span></span>  
 [<span data-ttu-id="3f3fa-118">リンクを使用してレコードとフィールド マッピングを指定する</span><span class="sxs-lookup"><span data-stu-id="3f3fa-118">Using Links to Specify Record and Field Mappings</span></span>](../core/using-links-to-specify-record-and-field-mappings.md)
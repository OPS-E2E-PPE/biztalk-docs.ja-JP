---
title: リンクのラベルを付ける方法 |Microsoft ドキュメント
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
ms.openlocfilehash: c0e47a776fdbc8eccbc1037b3c73b069d810eee0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253794"
---
# <a name="how-to-label-a-link"></a><span data-ttu-id="6205f-102">リンクにラベル付けする方法</span><span class="sxs-lookup"><span data-stu-id="6205f-102">How to Label a Link</span></span>
<span data-ttu-id="6205f-103">ラベルは、マップの Functoid またはリンクの目的を文書化するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6205f-103">Labels are helpful to document the purpose of a functoid or a link in a map.</span></span> <span data-ttu-id="6205f-104">使用することができます、**ラベル**プロパティをリンクの名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="6205f-104">You can use the **Label** property to name a link.</span></span> <span data-ttu-id="6205f-105">これは、マップに大きいスキーマ構造が含まれ、Functoid への入力リンクと出力リンクの識別が困難な場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="6205f-105">This is useful when your map contains big schema structures and identifying the inputs and output links to a functoid becomes difficult.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6205f-106">Functoid のラベルとコメントをする方法については、次を参照してください。[方法、Functoid ラベルとコメント](../core/how-to-label-and-comment-a-functoid.md)です。</span><span class="sxs-lookup"><span data-stu-id="6205f-106">For information on how to label and comment functoids, see [How to Label and Comment a Functoid](../core/how-to-label-and-comment-a-functoid.md).</span></span>  
  
 <span data-ttu-id="6205f-107">次の図ではリンク ラベルを示します。</span><span class="sxs-lookup"><span data-stu-id="6205f-107">The following figure shows a link label.</span></span>  
  
 <span data-ttu-id="6205f-108">![リンクのラベル付け](../core/media/new-labelling-link.gif "New_Labelling_link")</span><span class="sxs-lookup"><span data-stu-id="6205f-108">![Labelling a link](../core/media/new-labelling-link.gif "New_Labelling_link")</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6205f-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="6205f-109">Prerequisites</span></span>  
 <span data-ttu-id="6205f-110">これらの手順では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6205f-110">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-add-a-label-to-a-link"></a><span data-ttu-id="6205f-111">ラベルをリンクに追加するには</span><span class="sxs-lookup"><span data-stu-id="6205f-111">To add a label to a link</span></span>  
  
1.  <span data-ttu-id="6205f-112">ラベルを指定するリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="6205f-112">Select the link you want to label.</span></span>  
  
2.  <span data-ttu-id="6205f-113">**プロパティ** ウィンドウで新しい名前を指定、**ラベル**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="6205f-113">In the **Properties** window, provide the new name in the **Label** field.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="6205f-114">使用できる文字の最大数は 256 です。</span><span class="sxs-lookup"><span data-stu-id="6205f-114">The maximum number of characters allowed is 256.</span></span> <span data-ttu-id="6205f-115">数は 256 文字の文字列が指定されている場合は、最初の 256 文字が受け入れられ、残りの部分は破棄されます。</span><span class="sxs-lookup"><span data-stu-id="6205f-115">If a string with more than 256 characters is specified, the first 256 characters are accepted and the rest are discarded.</span></span>  
  
     <span data-ttu-id="6205f-116">![ラベルのプロパティをリンク](../core/media/new-to-label-link.gif "New_To_Label_Link")</span><span class="sxs-lookup"><span data-stu-id="6205f-116">![Link label properties](../core/media/new-to-label-link.gif "New_To_Label_Link")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6205f-117">参照</span><span class="sxs-lookup"><span data-stu-id="6205f-117">See Also</span></span>  
 [<span data-ttu-id="6205f-118">リンクを使用してレコードを指定してフィールドのマッピング</span><span class="sxs-lookup"><span data-stu-id="6205f-118">Using Links to Specify Record and Field Mappings</span></span>](../core/using-links-to-specify-record-and-field-mappings.md)
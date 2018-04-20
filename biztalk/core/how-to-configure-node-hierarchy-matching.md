---
title: 一致するノードの階層を構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5302e194-cbc7-4d26-b25b-eb4e38abfe23
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d29a794db6f34d7e8251c32bbf428b3a336601fe
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="how-to-configure-node-hierarchy-matching"></a><span data-ttu-id="d6886-102">ノード階層の照合を構成する方法</span><span class="sxs-lookup"><span data-stu-id="d6886-102">How to Configure Node Hierarchy Matching</span></span>
<span data-ttu-id="d6886-103">マップにリンクを作成すると、BizTalk マッパーが自動的にコンパイラ リンクを作成して、描画されたリンクが実装されます。</span><span class="sxs-lookup"><span data-stu-id="d6886-103">When you create a link in a map, the BizTalk Mapper automatically creates compiler links to implement the link you have drawn.</span></span> <span data-ttu-id="d6886-104">**ターゲット リンク** リンクのプロパティは、BizTalk マッパーによるコンパイラ リンクの描画を制御します。</span><span class="sxs-lookup"><span data-stu-id="d6886-104">The **Target Links** property of a link controls how the BizTalk Mapper draws the compiler links.</span></span> <span data-ttu-id="d6886-105">ここでは、ターゲット リンクを設定する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="d6886-105">This topic provides information about how to set the target links.</span></span>  
  
 <span data-ttu-id="d6886-106">**送信元のリンク** プロパティは、値が送信元ノードから取得され、送信先ノードに適用する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6886-106">The **Source Links** property specifies how a value is retrieved from the source node and applied to the destination node.</span></span> <span data-ttu-id="d6886-107">送信元のリンクを設定する方法については、次を参照してください。[ソースへのリンクのコンパイラ値を設定する方法](../core/how-to-set-the-source-links-compiler-value.md)です。</span><span class="sxs-lookup"><span data-stu-id="d6886-107">For information about how to set source links, see [How to Set the Source Links Compiler Value](../core/how-to-set-the-source-links-compiler-value.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6886-108">この操作では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6886-108">This operation requires that BizTalk Mapper is running.</span></span>  
  
### <a name="to-set-the-target-links-property"></a><span data-ttu-id="d6886-109">送信先のリンク プロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="d6886-109">To set the Target Links property</span></span>  
  
1.  <span data-ttu-id="d6886-110">マップ グリッド ページで、送信先リンク プロパティを設定するリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6886-110">On the map grid page, click a link to which you want to set the target links property.</span></span>  
  
2.  <span data-ttu-id="d6886-111">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]**プロパティ**ウィンドウで、設定、**ターゲット リンク**プロパティに、次のいずれか。</span><span class="sxs-lookup"><span data-stu-id="d6886-111">In the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]**Properties** window, set the **Target Links** property to one of the following choices:</span></span>  
  
    -   <span data-ttu-id="d6886-112">**リンクをフラット化します。**</span><span class="sxs-lookup"><span data-stu-id="d6886-112">**Flatten Links.**</span></span> <span data-ttu-id="d6886-113">送信元レコード ノードの階層がフラット化されて、送信先スキーマのリンク先レコード ノードと照合されます。</span><span class="sxs-lookup"><span data-stu-id="d6886-113">The hierarchy in the source record node is flattened to the linked-to-record node in the destination schema.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="d6886-114">既定では、BizTalk マッパーの設定、 **ターゲット リンク** プロパティを **Flatten**します。</span><span class="sxs-lookup"><span data-stu-id="d6886-114">By default, the BizTalk Mapper sets the **Target Links** property to **Flatten**.</span></span>  
  
    -   <span data-ttu-id="d6886-115">**リンクを上から順に一致します。**</span><span class="sxs-lookup"><span data-stu-id="d6886-115">**Match Links Top Down.**</span></span> <span data-ttu-id="d6886-116">ノードは、上のレベルから下のレベルへと順に照合されます。</span><span class="sxs-lookup"><span data-stu-id="d6886-116">Node matching is performed level-to-level from the top down.</span></span>  
  
    -   <span data-ttu-id="d6886-117">**リンクを下から一致します。**</span><span class="sxs-lookup"><span data-stu-id="d6886-117">**Match Links Bottom Up.**</span></span> <span data-ttu-id="d6886-118">ノードは、下のレベルから上のレベルへと順に照合されます。</span><span class="sxs-lookup"><span data-stu-id="d6886-118">Node matching is performed level-to-level from the bottom up.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6886-119">参照</span><span class="sxs-lookup"><span data-stu-id="d6886-119">See Also</span></span>  
 <span data-ttu-id="d6886-120">[ノード階層レベルの照合](../core/node-hierarchy-level-matching.md) </span><span class="sxs-lookup"><span data-stu-id="d6886-120">[Node-Hierarchy Level Matching](../core/node-hierarchy-level-matching.md) </span></span>  
 <span data-ttu-id="d6886-121">[コンパイラ ディレクティブおよびリンク](../core/compiler-directives-and-links.md) </span><span class="sxs-lookup"><span data-stu-id="d6886-121">[Compiler Directives and Links](../core/compiler-directives-and-links.md) </span></span>  
 [<span data-ttu-id="d6886-122">リンクを使用してレコードを指定して、フィールド マッピング</span><span class="sxs-lookup"><span data-stu-id="d6886-122">Using Links to Specify Record and Field Mappings</span></span>](../core/using-links-to-specify-record-and-field-mappings.md)
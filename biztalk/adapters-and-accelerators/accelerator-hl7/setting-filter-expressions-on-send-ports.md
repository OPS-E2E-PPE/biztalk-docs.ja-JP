---
title: "送信ポートのフィルター式を設定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send ports, context properties
- filtering, send ports
- send ports, filtering
- context properties, send ports
- context properties, filtering
- filtering, context properties
ms.assetid: 48c7c83b-9464-4ed9-bd8d-cf5b75e16702
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b94497f4e1412f81c36df3195994aafa32ecc451
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="setting-filter-expressions-on-send-ports"></a><span data-ttu-id="c2aa2-102">送信ポートのフィルター式を設定</span><span class="sxs-lookup"><span data-stu-id="c2aa2-102">Setting Filter Expressions on Send Ports</span></span>
<span data-ttu-id="c2aa2-103">ポートの送信を制御する送信ポートにフィルター式のコンテキスト プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="c2aa2-103">You set context properties in filter expressions on the send port to control what the port sends.</span></span> <span data-ttu-id="c2aa2-104">プロパティのフィルター処理する方法の柔軟性を提供する演算子の数が、フィルター式を設定することができます (より大きいより優れたまたは同じか、少ないよりと小さい、等しいかどうか、存在よりまたは等しい)。</span><span class="sxs-lookup"><span data-stu-id="c2aa2-104">You can set the filter expressions with a number of operators that offer you flexibility in how you filter the property (equality or inequality, exists, greater than, great than or equal to, less than, and less than or equal to).</span></span>  
  
### <a name="to-set-the-filter-expression-on-a-send-port"></a><span data-ttu-id="c2aa2-105">送信ポートにフィルター式を設定するには</span><span class="sxs-lookup"><span data-stu-id="c2aa2-105">To set the filter expression on a send port</span></span>  
  
1.  <span data-ttu-id="c2aa2-106">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、 **BizTalk グループ**、**アプリケーション**、および**BizTalk アプリケーション1** (または別のアプリケーション)。</span><span class="sxs-lookup"><span data-stu-id="c2aa2-106">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and **BizTalk Application 1** (or another application).</span></span> <span data-ttu-id="c2aa2-107">をクリックして**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="c2aa2-107">Click **Send Ports**.</span></span>  
  
2.  <span data-ttu-id="c2aa2-108">では、フィルター式を設定し、をクリックする送信ポートを右クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="c2aa2-108">Right-click the send port that you want to set the filter expression for, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="c2aa2-109">送信ポートのプロパティ ダイアログ ボックスのコンソール ツリーで、クリックして**フィルター**です。</span><span class="sxs-lookup"><span data-stu-id="c2aa2-109">In the console tree of the Send Port Properties dialog box, click **Filters**.</span></span>  
  
4.  <span data-ttu-id="c2aa2-110">内のテキスト ボックスをクリックして、**プロパティ**列からコンテキスト プロパティを選択し、**プロパティ**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="c2aa2-110">Click the text box in the **Property** column, and then select the context property from the **Property** drop-down list.</span></span>  
  
5.  <span data-ttu-id="c2aa2-111">クリックして、**演算子** ボックスに、プロパティの行と、プロパティの演算子をドロップダウン リストから選択します。</span><span class="sxs-lookup"><span data-stu-id="c2aa2-111">Click the **Operator** box in the row for the property, and select the operator for the property from the drop-down list.</span></span>  
  
6.  <span data-ttu-id="c2aa2-112">クリックして、**値** ボックスに、プロパティの行と値の式を入力します。</span><span class="sxs-lookup"><span data-stu-id="c2aa2-112">Click the **Value** box in the row for the property, and type a value expression.</span></span>  
  
7.  <span data-ttu-id="c2aa2-113">フィルター式に対して別の句を追加する必要がある場合にクリックして、 **Group By**  ボックスに、プロパティの行と選択**と**または**または**の関係を判断する、句。</span><span class="sxs-lookup"><span data-stu-id="c2aa2-113">If you need to add another  clause for the filter expression, click the **Group By** box in the row for the property, and select **And** or **Or** to determine the relationship of the clauses.</span></span>  
  
8.  <span data-ttu-id="c2aa2-114">手順 4 ~ 6 を別のフィルター句を追加します。</span><span class="sxs-lookup"><span data-stu-id="c2aa2-114">Repeat steps 4 through 6 to add another filter clause.</span></span>  
  
9. <span data-ttu-id="c2aa2-115">フィルター式でが正しいこと、ウィンドウの下部にあることを確認、**フィルター**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="c2aa2-115">Verify that the filter expression is correct in the pane at the bottom of the **Filters** pane.</span></span>  
  
10. <span data-ttu-id="c2aa2-116">すべてのフィルター句を追加したら、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="c2aa2-116">When you have added all filter clauses, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2aa2-117">参照</span><span class="sxs-lookup"><span data-stu-id="c2aa2-117">See Also</span></span>  
 <span data-ttu-id="c2aa2-118">[HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="c2aa2-118">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 [<span data-ttu-id="c2aa2-119">コンテキスト プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="c2aa2-119">Using Context Properties</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-context-properties.md)
---
title: 送信ポートでのフィルター式の設定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, context properties
- filtering, send ports
- send ports, filtering
- context properties, send ports
- context properties, filtering
- filtering, context properties
ms.assetid: 48c7c83b-9464-4ed9-bd8d-cf5b75e16702
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab5fcc0e4245599dfffb29f6f5690707df325c04
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291569"
---
# <a name="setting-filter-expressions-on-send-ports"></a><span data-ttu-id="d6c05-102">送信ポートのフィルター式の設定</span><span class="sxs-lookup"><span data-stu-id="d6c05-102">Setting Filter Expressions on Send Ports</span></span>
<span data-ttu-id="d6c05-103">ポートの送信を制御する送信ポートでフィルター式のコンテキスト プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="d6c05-103">You set context properties in filter expressions on the send port to control what the port sends.</span></span> <span data-ttu-id="d6c05-104">フィルター式を設定するにはさまざまなプロパティをフィルター処理する方法の柔軟性を提供する演算子 (等値演算子または非等値、存在するより大きいより大きいまたは等しい、未満よりと小さい以上)。</span><span class="sxs-lookup"><span data-stu-id="d6c05-104">You can set the filter expressions with a number of operators that offer you flexibility in how you filter the property (equality or inequality, exists, greater than, great than or equal to, less than, and less than or equal to).</span></span>  
  
### <a name="to-set-the-filter-expression-on-a-send-port"></a><span data-ttu-id="d6c05-105">送信ポートでフィルター式を設定するには</span><span class="sxs-lookup"><span data-stu-id="d6c05-105">To set the filter expression on a send port</span></span>  
  
1.  <span data-ttu-id="d6c05-106">BizTalk Server 管理コンソールで  **BizTalk Server 管理**、 **BizTalk グループ**、**アプリケーション**、および**BizTalk アプリケーション1** (または別のアプリケーション)。</span><span class="sxs-lookup"><span data-stu-id="d6c05-106">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and **BizTalk Application 1** (or another application).</span></span> <span data-ttu-id="d6c05-107">クリックして**送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="d6c05-107">Click **Send Ports**.</span></span>  
  
2.  <span data-ttu-id="d6c05-108">フィルター式を設定し、クリックする送信ポートを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="d6c05-108">Right-click the send port that you want to set the filter expression for, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="d6c05-109">送信ポートのプロパティ ダイアログ ボックスのコンソール ツリーで、クリックして**フィルター**します。</span><span class="sxs-lookup"><span data-stu-id="d6c05-109">In the console tree of the Send Port Properties dialog box, click **Filters**.</span></span>  
  
4.  <span data-ttu-id="d6c05-110">テキスト ボックスをクリックして、**プロパティ**列からコンテキスト プロパティをクリックして、**プロパティ**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="d6c05-110">Click the text box in the **Property** column, and then select the context property from the **Property** drop-down list.</span></span>  
  
5.  <span data-ttu-id="d6c05-111">をクリックして、**演算子**プロパティに、行のボックスし、ドロップダウン リストから、プロパティの演算子を選択します。</span><span class="sxs-lookup"><span data-stu-id="d6c05-111">Click the **Operator** box in the row for the property, and select the operator for the property from the drop-down list.</span></span>  
  
6.  <span data-ttu-id="d6c05-112">をクリックして、**値** ボックスに、プロパティの行と値の式を入力します。</span><span class="sxs-lookup"><span data-stu-id="d6c05-112">Click the **Value** box in the row for the property, and type a value expression.</span></span>  
  
7.  <span data-ttu-id="d6c05-113">フィルター式に対して別の句を追加する必要がある場合にクリックして、 **Group By**  ボックスに、プロパティの行と選択**と**または**または**の関係を判断する、句。</span><span class="sxs-lookup"><span data-stu-id="d6c05-113">If you need to add another  clause for the filter expression, click the **Group By** box in the row for the property, and select **And** or **Or** to determine the relationship of the clauses.</span></span>  
  
8.  <span data-ttu-id="d6c05-114">手順 4 ~ 6 をもう 1 つのフィルター句を追加します。</span><span class="sxs-lookup"><span data-stu-id="d6c05-114">Repeat steps 4 through 6 to add another filter clause.</span></span>  
  
9. <span data-ttu-id="d6c05-115">フィルター式が、ウィンドウの下部で正しいことを確認、**フィルター**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="d6c05-115">Verify that the filter expression is correct in the pane at the bottom of the **Filters** pane.</span></span>  
  
10. <span data-ttu-id="d6c05-116">すべてのフィルター句を追加したら、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="d6c05-116">When you have added all filter clauses, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6c05-117">参照</span><span class="sxs-lookup"><span data-stu-id="d6c05-117">See Also</span></span>  
 <span data-ttu-id="d6c05-118">[HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="d6c05-118">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 [<span data-ttu-id="d6c05-119">コンテキスト プロパティの使用</span><span class="sxs-lookup"><span data-stu-id="d6c05-119">Using Context Properties</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-context-properties.md)
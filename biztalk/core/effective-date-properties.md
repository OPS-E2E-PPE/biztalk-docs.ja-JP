---
title: 発効日のプロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- effective-dated items
- getHistoryItems parameter
- Effective Date
- EFFDT
- planned items, scheduling and tracking
ms.assetid: 0d9a153c-7ea5-41cf-9e4e-055e1c18f64b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42373f55391f8bf3401d18e0a964005def222a8d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389099"
---
# <a name="effective-date-properties"></a><span data-ttu-id="06874-102">発効日のプロパティ</span><span class="sxs-lookup"><span data-stu-id="06874-102">Effective Date Properties</span></span>
<span data-ttu-id="06874-103">PeopleSoft Enterprise では、スケジュールを設定し、計画済み項目有効日 (省略表記 EFFDT) と呼ばれる特殊なプロパティを使用しての追跡機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="06874-103">PeopleSoft Enterprise provides the ability to schedule and keep track of planned items by using a special property called Effective Date (abbreviated EFFDT).</span></span> <span data-ttu-id="06874-104">このような項目は有効か単予定、その日付が PeopleSoft の現在の日付の前後のかによってです。</span><span class="sxs-lookup"><span data-stu-id="06874-104">Such items are either in effect or merely planned, depending on whether their date is before or after the PeopleSoft current date.</span></span>  
  
 <span data-ttu-id="06874-105">コンポーネント インターフェイスのプロパティにこのような effective-dated 項目 (つまり、EFFDT の名前を持つフィールド) が含まれている場合、アダプターによって、呼び出し元の値または値のみの完全なセットに取得をまだ有効な変更することもできます.</span><span class="sxs-lookup"><span data-stu-id="06874-105">If the properties of a component interface contain such effective-dated items (that is, a field with a name of EFFDT), the adapter makes it possible for callers to retrieve the complete set of values or only those values not yet effective—those that can still be changed.</span></span>  
  
## <a name="gethistoryitems-parameter"></a><span data-ttu-id="06874-106">getHistoryItems パラメーター</span><span class="sxs-lookup"><span data-stu-id="06874-106">getHistoryItems Parameter</span></span>  
 <span data-ttu-id="06874-107">発効日を含むプロパティを持つコンポーネント インターフェイスでは、アダプターと呼ばれる追加のパラメーターを提供します`getHistoryItems`、Get 操作をします。</span><span class="sxs-lookup"><span data-stu-id="06874-107">For component interfaces with properties that include an effective date, the adapter provides an additional parameter, called `getHistoryItems`, to the Get operations.</span></span> <span data-ttu-id="06874-108">このパラメーターは、Boolean 型とを True に設定されている場合、すべて、effective-dated 項目が返されます。</span><span class="sxs-lookup"><span data-stu-id="06874-108">This parameter is of type Boolean, and if it is set to True, all effective-dated items are returned.</span></span> <span data-ttu-id="06874-109">すべての過去、現在および将来の発効項目が含まれます。</span><span class="sxs-lookup"><span data-stu-id="06874-109">These include all past, current, and future effective-dated items.</span></span>  
  
 <span data-ttu-id="06874-110">場合、`getHistoryItems`パラメーターは、False に設定されて、現在および将来の発効項目のみが返されます。</span><span class="sxs-lookup"><span data-stu-id="06874-110">If the `getHistoryItems` parameter is set to False, only the current and future effective-dated items are returned.</span></span> <span data-ttu-id="06874-111">追加または (過去のアイテムを変更できない) ために、これらの項目を変更する場合は False を選択します。</span><span class="sxs-lookup"><span data-stu-id="06874-111">Choose False if your intention is to add or change these items (because past items cannot be changed).</span></span>  
  
 <span data-ttu-id="06874-112">複数発効項目を同じ発効日を持つこともできます。</span><span class="sxs-lookup"><span data-stu-id="06874-112">It is also possible to have multiple effective-dated items having the same effective date.</span></span> <span data-ttu-id="06874-113">このような状況で効果的なシーケンス (EFFSEQ)、追加のプロパティを指定も必要があります。</span><span class="sxs-lookup"><span data-stu-id="06874-113">In this situation, an additional property, Effective Sequence (EFFSEQ), must also be provided.</span></span> <span data-ttu-id="06874-114">EFFSEQ の値は、有効日が同じ項目を区別するために一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="06874-114">The values of the EFFSEQ must be unique to differentiate items with the same effective date.</span></span> <span data-ttu-id="06874-115">詳細については、PeopleSoft のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="06874-115">See the PeopleSoft documentation for more information.</span></span>  
  
## <a name="modifying-past-effective-dated-items"></a><span data-ttu-id="06874-116">過去の発効日が指定された項目を変更します。</span><span class="sxs-lookup"><span data-stu-id="06874-116">Modifying Past Effective-Dated Items</span></span>  
 <span data-ttu-id="06874-117">`correctionMode`両方の引数、 [UpdateEx](../core/updateex-method.md)と[DeleteOnly](../core/deleteonly-method.md)メソッドは、過去の有効日が指定された項目を変更できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="06874-117">The `correctionMode` argument in both the [UpdateEx](../core/updateex-method.md) and [DeleteOnly](../core/deleteonly-method.md) methods control whether past effective dated items can be modified.</span></span> <span data-ttu-id="06874-118">設定されている場合は true、すべての項目変更できます。</span><span class="sxs-lookup"><span data-stu-id="06874-118">If it is set to true, all items can be modified.</span></span> <span data-ttu-id="06874-119">それ以外の場合、有効日が指定された項目には、例外が生成されます。 過去の変更。</span><span class="sxs-lookup"><span data-stu-id="06874-119">Otherwise, modifying past effective dated item generates an exception.</span></span>  
  
 <span data-ttu-id="06874-120">非推奨の呼び出し時に`Update`effective-dated 項目を含むコンポーネント インターフェイスのメソッドは、する必要がありますように注意する現在の有効な日付または呼び出しで例外で失敗 PeopleSoft より前の値の有効な日付を含める必要はありません。</span><span class="sxs-lookup"><span data-stu-id="06874-120">When calling the deprecated `Update` method on a component interface that has effective-dated items, you must take care not to include any effective dates of a value earlier than the PeopleSoft current effective date, or the call fails with an exception.</span></span> <span data-ttu-id="06874-121">ただし、発効の現在の項目を含めるようにプロパティを設定するときにバイパスされますができます。</span><span class="sxs-lookup"><span data-stu-id="06874-121">However, the current effective-dated item can be included as it is bypassed when setting properties.</span></span> <span data-ttu-id="06874-122">Effective Sequence が存在する場合は、プロパティを設定するときに、すべて現在、effective-dated 項目が有効なシーケンスを一致するサーバーではスキップされます。</span><span class="sxs-lookup"><span data-stu-id="06874-122">If Effective Sequence exists, then all current effective-dated items with matching Effective Sequences in the server are skipped when setting properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06874-123">参照</span><span class="sxs-lookup"><span data-stu-id="06874-123">See Also</span></span>  
 [<span data-ttu-id="06874-124">付録 a:コンポーネント インターフェイス メソッド</span><span class="sxs-lookup"><span data-stu-id="06874-124">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)
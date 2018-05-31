---
title: 発効日プロパティ |Microsoft ドキュメント
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
ms.openlocfilehash: 34f1c4cf3579a3381c846ddbb9896b2e5be26f6b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240146"
---
# <a name="effective-date-properties"></a><span data-ttu-id="0b654-102">発効日のプロパティ</span><span class="sxs-lookup"><span data-stu-id="0b654-102">Effective Date Properties</span></span>
<span data-ttu-id="0b654-103">PeopleSoft Enterprise には、Effective Date (省略表記 EFFDT) と呼ばれる特殊なプロパティを使用して、計画済み項目のスケジュール作成と追跡を行う機能があります。</span><span class="sxs-lookup"><span data-stu-id="0b654-103">PeopleSoft Enterprise provides the ability to schedule and keep track of planned items by using a special property called Effective Date (abbreviated EFFDT).</span></span> <span data-ttu-id="0b654-104">計画済み項目は、日付が PeopleSoft の現在の日付よりも前か後かによって、既に有効になっている項目であるか、単に計画されているだけの項目であるかが決定します。</span><span class="sxs-lookup"><span data-stu-id="0b654-104">Such items are either in effect or merely planned, depending on whether their date is before or after the PeopleSoft current date.</span></span>  
  
 <span data-ttu-id="0b654-105">コンポーネント インターフェイスのプロパティに、発効日が指定された項目 (つまり、EFFDT という名前のフィールド) が含まれている場合、呼び出し元はアダプターを介して、値の完全なセットを取得するか、まだ有効になっていない (まだ変更可能な) 値だけを取得できます。</span><span class="sxs-lookup"><span data-stu-id="0b654-105">If the properties of a component interface contain such effective-dated items (that is, a field with a name of EFFDT), the adapter makes it possible for callers to retrieve the complete set of values or only those values not yet effective—those that can still be changed.</span></span>  
  
## <a name="gethistoryitems-parameter"></a><span data-ttu-id="0b654-106">getHistoryItems パラメーター</span><span class="sxs-lookup"><span data-stu-id="0b654-106">getHistoryItems Parameter</span></span>  
 <span data-ttu-id="0b654-107">発効日を含むプロパティを持つコンポーネント インターフェイスには、Get 操作用の `getHistoryItems` という追加のパラメーターがアダプターによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="0b654-107">For component interfaces with properties that include an effective date, the adapter provides an additional parameter, called `getHistoryItems`, to the Get operations.</span></span> <span data-ttu-id="0b654-108">このパラメーターはブール値型であり、True に設定されています (つまり、発効日が指定されたすべての項目が返されます)。</span><span class="sxs-lookup"><span data-stu-id="0b654-108">This parameter is of type Boolean, and if it is set to True, all effective-dated items are returned.</span></span> <span data-ttu-id="0b654-109">返されるのは、過去、現在、および将来の発効日が指定されたすべての項目です。</span><span class="sxs-lookup"><span data-stu-id="0b654-109">These include all past, current, and future effective-dated items.</span></span>  
  
 <span data-ttu-id="0b654-110">`getHistoryItems` パラメーターが False に設定されている場合は、現在および将来の発効日が指定された項目のみが返されます。</span><span class="sxs-lookup"><span data-stu-id="0b654-110">If the `getHistoryItems` parameter is set to False, only the current and future effective-dated items are returned.</span></span> <span data-ttu-id="0b654-111">そのような項目を追加または変更する場合に、False を選択します (過去の項目は変更できません)。</span><span class="sxs-lookup"><span data-stu-id="0b654-111">Choose False if your intention is to add or change these items (because past items cannot be changed).</span></span>  
  
 <span data-ttu-id="0b654-112">また、複数の項目に同じ発効日が指定されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="0b654-112">It is also possible to have multiple effective-dated items having the same effective date.</span></span> <span data-ttu-id="0b654-113">この場合は、追加のプロパティとして Effective Sequence (EFFSEQ) も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b654-113">In this situation, an additional property, Effective Sequence (EFFSEQ), must also be provided.</span></span> <span data-ttu-id="0b654-114">同じ発効日を持つ複数の項目を区別するために、EFFSEQ の値は一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b654-114">The values of the EFFSEQ must be unique to differentiate items with the same effective date.</span></span> <span data-ttu-id="0b654-115">詳細については、PeopleSoft のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b654-115">See the PeopleSoft documentation for more information.</span></span>  
  
## <a name="modifying-past-effective-dated-items"></a><span data-ttu-id="0b654-116">過去の発効日が指定された項目の変更</span><span class="sxs-lookup"><span data-stu-id="0b654-116">Modifying Past Effective-Dated Items</span></span>  
 <span data-ttu-id="0b654-117">`correctionMode`両方の引数、 [UpdateEx](../core/updateex-method.md)と[DeleteOnly](../core/deleteonly-method.md)メソッドは、過去の有効日が指定された項目を変更できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="0b654-117">The `correctionMode` argument in both the [UpdateEx](../core/updateex-method.md) and [DeleteOnly](../core/deleteonly-method.md) methods control whether past effective dated items can be modified.</span></span> <span data-ttu-id="0b654-118">true に設定されている場合は、すべての項目を変更できます。</span><span class="sxs-lookup"><span data-stu-id="0b654-118">If it is set to true, all items can be modified.</span></span> <span data-ttu-id="0b654-119">それ以外の場合、過去の発効日が指定された項目を変更すると例外が生成されます。</span><span class="sxs-lookup"><span data-stu-id="0b654-119">Otherwise, modifying past effective dated item generates an exception.</span></span>  
  
 <span data-ttu-id="0b654-120">発効日が指定された項目を含むコンポーネント インターフェイスに対して、廃止された `Update` メソッドを呼び出す場合は、PeopleSoft の現在の日付よりも前の値を持つ発効日を対象に含めないように注意する必要があります。これに従わない場合は、例外が発生して呼び出しが失敗します。</span><span class="sxs-lookup"><span data-stu-id="0b654-120">When calling the deprecated `Update` method on a component interface that has effective-dated items, you must take care not to include any effective dates of a value earlier than the PeopleSoft current effective date, or the call fails with an exception.</span></span> <span data-ttu-id="0b654-121">ただし、発効日として現在の日付が指定された項目は、プロパティ設定時にバイパスされるので、含めてかまいません。</span><span class="sxs-lookup"><span data-stu-id="0b654-121">However, the current effective-dated item can be included as it is bypassed when setting properties.</span></span> <span data-ttu-id="0b654-122">Effective Sequence が設定されている場合、発効日として現在の日付が指定された項目のうち、サーバーの Effective Sequence に一致するすべての項目が、プロパティ設定時にスキップされます。</span><span class="sxs-lookup"><span data-stu-id="0b654-122">If Effective Sequence exists, then all current effective-dated items with matching Effective Sequences in the server are skipped when setting properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b654-123">参照</span><span class="sxs-lookup"><span data-stu-id="0b654-123">See Also</span></span>  
 [<span data-ttu-id="0b654-124">付録 a: コンポーネント インターフェイス メソッド</span><span class="sxs-lookup"><span data-stu-id="0b654-124">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)
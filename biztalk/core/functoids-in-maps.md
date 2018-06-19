---
title: マップの Functoid |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functoids
- functoids, about functoids
- functoid types, Record Count
- functoid types, Looping
- Looping functoids
- functoids, categories
- functoid types, Addition
- Record Count functoids
ms.assetid: 10ee8b62-cb20-4d26-9d86-b6564f30c297
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 976af2faed27e6cae8a57d9c7c83308d0519d81d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246042"
---
# <a name="functoids-in-maps"></a><span data-ttu-id="d56ab-102">マップの Functoid</span><span class="sxs-lookup"><span data-stu-id="d56ab-102">Functoids in Maps</span></span>
<span data-ttu-id="d56ab-103">BizTalk マッパーでは、送信元スキーマのレコードやフィールドから、送信先スキーマのレコードやフィールドへの複雑な構造の変換がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="d56ab-103">BizTalk Mapper supports complex structural transformations from records and fields in the source schema to records and fields in the destination schema.</span></span> <span data-ttu-id="d56ab-104">Functoid では、定義済みの数式、および引数と呼ばれる特定の値を使用して計算を実行します。</span><span class="sxs-lookup"><span data-stu-id="d56ab-104">Functoids perform calculations by using predefined formulas and specific values, called arguments.</span></span> <span data-ttu-id="d56ab-105">これらの計算は、レコードおよびフィールドの指定された順序に基づいて実行されます。</span><span class="sxs-lookup"><span data-stu-id="d56ab-105">These calculations are executed based on the designated order of the records and fields.</span></span>  
  
 <span data-ttu-id="d56ab-106">ツールボックスから Functoid を選択し、グリッド ページにドラッグして、送信元スキーマや送信先スキーマのノードにリンクすると、データの統合、日付または時間情報の変更、データの連結などの操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="d56ab-106">By selecting a functoid from the Toolbox, dragging it to the grid page, and linking it to nodes in the source schema and destination schema, data can be added together, date or time information can be modified, data can be concatenated, or other operations can be performed.</span></span> <span data-ttu-id="d56ab-107">たとえば、**加算**functoid は、値を追加および**レコード カウント**functoid がインスタンス メッセージ内のループ レコードの合計数を返します。</span><span class="sxs-lookup"><span data-stu-id="d56ab-107">For example, the **Addition** functoid adds values and the **Record Count** functoid returns the total count of a looping record in an instance message.</span></span> <span data-ttu-id="d56ab-108">ツールボックスに functoid のカテゴリが含まれます: 強化、変換、累積、データベース、日付/時刻、論理、数値演算、指数、および文字列。</span><span class="sxs-lookup"><span data-stu-id="d56ab-108">Categories of functoids that you can find in the Toolbox include: Advanced, Conversion, Cumulative, Database, Date/ Time, Logical, Mathematical, Scientific, and String.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d56ab-109">データベース Functoid を除くすべての Functoid はインライン C# です。</span><span class="sxs-lookup"><span data-stu-id="d56ab-109">All functoids are inline C# except for the Database functoids.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d56ab-110">送信先スキーマ ノードの例外を除いて、functoid からの入力を 1 つだけを受け入れる、**ループ**functoid です。</span><span class="sxs-lookup"><span data-stu-id="d56ab-110">Destination schema nodes accept only one input from a functoid with the exception of the **Looping** functoid.</span></span>  
  
 <span data-ttu-id="d56ab-111">このセクションのトピックでは、BizTalk Server の前のバージョンから Functoid を移行する方法、Functoid の説明、Functoid で実行できること、および使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d56ab-111">The topics in this section describe how to migrate functoids from previous versions of BizTalk Server, what functoids are, what they do, and how to use them.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d56ab-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d56ab-112">In This Section</span></span>  
  
-   [<span data-ttu-id="d56ab-113">Functoid カテゴリ</span><span class="sxs-lookup"><span data-stu-id="d56ab-113">Functoid Categories</span></span>](../core/functoid-categories.md)  
  
-   [<span data-ttu-id="d56ab-114">Functoid 入力パラメーター</span><span class="sxs-lookup"><span data-stu-id="d56ab-114">Functoid Input Parameters</span></span>](../core/functoid-input-parameters.md)  
  
-   [<span data-ttu-id="d56ab-115">基本 Functoid</span><span class="sxs-lookup"><span data-stu-id="d56ab-115">Basic Functoids</span></span>](../core/basic-functoids.md)  
  
-   [<span data-ttu-id="d56ab-116">高度な Functoid</span><span class="sxs-lookup"><span data-stu-id="d56ab-116">Advanced Functoids</span></span>](../core/advanced-functoids.md)  
  
-   [<span data-ttu-id="d56ab-117">カスケード Functoid</span><span class="sxs-lookup"><span data-stu-id="d56ab-117">Cascading Functoids</span></span>](../core/cascading-functoids.md)  
  
-   [<span data-ttu-id="d56ab-118">Functoid のプロパティ</span><span class="sxs-lookup"><span data-stu-id="d56ab-118">Functoid Properties</span></span>](../core/functoid-properties.md)  
  
-   [<span data-ttu-id="d56ab-119">Functoid の移行</span><span class="sxs-lookup"><span data-stu-id="d56ab-119">Migrating Functoids</span></span>](../core/migrating-functoids.md)
---
title: マップの Functoid |Microsoft Docs
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
ms.openlocfilehash: 45e066b759db92db1f51db81dc98816c3f757654
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387825"
---
# <a name="functoids-in-maps"></a><span data-ttu-id="59228-102">マップの Functoid</span><span class="sxs-lookup"><span data-stu-id="59228-102">Functoids in Maps</span></span>
<span data-ttu-id="59228-103">BizTalk マッパーでは、レコードおよび送信先スキーマのフィールドへの送信元スキーマのレコードやフィールドから複雑な構造の変換をサポートします。</span><span class="sxs-lookup"><span data-stu-id="59228-103">BizTalk Mapper supports complex structural transformations from records and fields in the source schema to records and fields in the destination schema.</span></span> <span data-ttu-id="59228-104">Functoid は、定義済みの数式および引数と呼ばれる特定の値を使用して計算を実行します。</span><span class="sxs-lookup"><span data-stu-id="59228-104">Functoids perform calculations by using predefined formulas and specific values, called arguments.</span></span> <span data-ttu-id="59228-105">これらの計算は、レコードおよびフィールドの指定された順序に基づいて実行されます。</span><span class="sxs-lookup"><span data-stu-id="59228-105">These calculations are executed based on the designated order of the records and fields.</span></span>  
  
 <span data-ttu-id="59228-106">ツールボックスから functoid を選択すると、グリッド ページにドラッグすること、および送信元スキーマおよび送信先スキーマ内のノードにリンクすることによってデータを同時に追加できる、日付または時刻の情報を変更できます。、データの連結、またはその他の操作を指定できます。実行されます。</span><span class="sxs-lookup"><span data-stu-id="59228-106">By selecting a functoid from the Toolbox, dragging it to the grid page, and linking it to nodes in the source schema and destination schema, data can be added together, date or time information can be modified, data can be concatenated, or other operations can be performed.</span></span> <span data-ttu-id="59228-107">など、**加算**functoid には、値が追加され、**レコード カウント**functoid が、インスタンス メッセージ内のループ レコードの合計数を返します。</span><span class="sxs-lookup"><span data-stu-id="59228-107">For example, the **Addition** functoid adds values and the **Record Count** functoid returns the total count of a looping record in an instance message.</span></span> <span data-ttu-id="59228-108">ツールボックスで検索できる functoid のカテゴリは次のとおりです。高度な変換、累積的なデータベース、日付/時刻、数学、科学、論理と文字列します。</span><span class="sxs-lookup"><span data-stu-id="59228-108">Categories of functoids that you can find in the Toolbox include: Advanced, Conversion, Cumulative, Database, Date/ Time, Logical, Mathematical, Scientific, and String.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59228-109">すべての functoid はインラインC#データベース functoid を除く。</span><span class="sxs-lookup"><span data-stu-id="59228-109">All functoids are inline C# except for the Database functoids.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59228-110">送信先スキーマ ノードは、例外として、functoid からの入力を 1 つだけを受け入れる、**ループ**functoid。</span><span class="sxs-lookup"><span data-stu-id="59228-110">Destination schema nodes accept only one input from a functoid with the exception of the **Looping** functoid.</span></span>  
  
 <span data-ttu-id="59228-111">このセクションのトピックでは、BizTalk Server の以前のバージョンから functoid を移行する方法、functoid には、実行こと、およびその使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="59228-111">The topics in this section describe how to migrate functoids from previous versions of BizTalk Server, what functoids are, what they do, and how to use them.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="59228-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="59228-112">In This Section</span></span>  
  
-   [<span data-ttu-id="59228-113">Functoid カテゴリ</span><span class="sxs-lookup"><span data-stu-id="59228-113">Functoid Categories</span></span>](../core/functoid-categories.md)  
  
-   [<span data-ttu-id="59228-114">Functoid 入力パラメーター</span><span class="sxs-lookup"><span data-stu-id="59228-114">Functoid Input Parameters</span></span>](../core/functoid-input-parameters.md)  
  
-   [<span data-ttu-id="59228-115">基本 Functoid</span><span class="sxs-lookup"><span data-stu-id="59228-115">Basic Functoids</span></span>](../core/basic-functoids.md)  
  
-   [<span data-ttu-id="59228-116">高度な Functoid</span><span class="sxs-lookup"><span data-stu-id="59228-116">Advanced Functoids</span></span>](../core/advanced-functoids.md)  
  
-   [<span data-ttu-id="59228-117">カスケード Functoid</span><span class="sxs-lookup"><span data-stu-id="59228-117">Cascading Functoids</span></span>](../core/cascading-functoids.md)  
  
-   [<span data-ttu-id="59228-118">Functoid のプロパティ</span><span class="sxs-lookup"><span data-stu-id="59228-118">Functoid Properties</span></span>](../core/functoid-properties.md)  
  
-   [<span data-ttu-id="59228-119">Functoid の移行</span><span class="sxs-lookup"><span data-stu-id="59228-119">Migrating Functoids</span></span>](../core/migrating-functoids.md)
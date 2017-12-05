---
title: "Functoid のインデックスを作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Max Occurs property
- Index functoids, about Index functoids
- Index functoids
ms.assetid: 0c8ba427-881c-4b1f-92b9-61992d2a29df
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a22881e7694fee872b7820b8b99157ef2cf20170
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="index-functoid"></a><span data-ttu-id="9454f-102">インデックス Functoid</span><span class="sxs-lookup"><span data-stu-id="9454f-102">Index Functoid</span></span>
<span data-ttu-id="9454f-103">**インデックス**functoid では、一連のレコードの特定のレコードから情報を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="9454f-103">The **Index** functoid enables you to select information from a specific record in a series of records.</span></span> <span data-ttu-id="9454f-104">各**インデックス**functoid が 1 つのフィールドから情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="9454f-104">Each **Index** functoid collects information from a single field.</span></span>  
  
 <span data-ttu-id="9454f-105">一般的に、1 つの入力ファイルには、特定のレコードが複数含まれます。</span><span class="sxs-lookup"><span data-stu-id="9454f-105">Certain records typically occur many times in an input file.</span></span> <span data-ttu-id="9454f-106">たとえば、気象レポートで、 **DailySummary**要素が何度も発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9454f-106">For example, in a weather report, the **DailySummary** element might occur many times.</span></span> <span data-ttu-id="9454f-107">**DailySummary**要素は、気温、大気圧、風速の属性を含めることがあります。</span><span class="sxs-lookup"><span data-stu-id="9454f-107">The **DailySummary** element might include attributes for the temperature, the barometric pressure, and the wind speed.</span></span> <span data-ttu-id="9454f-108">次のコードは、気象レポートの例です。</span><span class="sxs-lookup"><span data-stu-id="9454f-108">The following code is an example of a weather report.</span></span>  
  
```  
<ns0:WeatherReport xmlns:ns0="http://IndexFunctoid.WeatherReport">  
    <DailySummary Pressure="80" Windspeed="10" Temperature="20" />  
    <DailySummary Pressure="78" Windspeed="20" Temperature="23" />  
    <DailySummary Pressure="77" Windspeed="16" Temperature="24" />  
</ns0:WeatherReport>  
```  
  
 <span data-ttu-id="9454f-109">基になるスキーマで、 **Max Occurs**プロパティを**DailySummary**レコードを定期的またはループ レコードを示すためにバインド解除済みに設定します。</span><span class="sxs-lookup"><span data-stu-id="9454f-109">In the underlying schema, the **Max Occurs** property for the **DailySummary** record would be set to unbounded to indicate a recurring or looping record.</span></span> <span data-ttu-id="9454f-110">BizTalk マッパーでは、このレコードはループとしてコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="9454f-110">BizTalk Mapper compiles this record as a loop.</span></span>  
  
 <span data-ttu-id="9454f-111">最初の 2 つの気象情報を収集する場合を考えます**DailySummary**天気予報のレコードです。</span><span class="sxs-lookup"><span data-stu-id="9454f-111">Suppose you want to collect weather information for the first two **DailySummary** records of the weather report.</span></span> <span data-ttu-id="9454f-112">BizTalk マッパーで各属性、 **DailySummary**に、入力方向の送信元スキーマのレコードを接続することができます、**インデックス**functoid です。</span><span class="sxs-lookup"><span data-stu-id="9454f-112">In BizTalk Mapper, each attribute from the **DailySummary** record of the incoming source schema can be connected to an **Index** functoid.</span></span> <span data-ttu-id="9454f-113">各**インデックス**functoid を指定できます、 **DailySummary**レコードから情報を描画する: 最初または 2 番目です。</span><span class="sxs-lookup"><span data-stu-id="9454f-113">In turn, each **Index** functoid can specify the **DailySummary** record from which to draw the information: the first or second.</span></span> <span data-ttu-id="9454f-114">**インデックス**functoid を送信先スキーマの適切なフィールドに接続できます。</span><span class="sxs-lookup"><span data-stu-id="9454f-114">The **Index** functoids can then be connected to the appropriate fields of the destination schema.</span></span>  
  
 <span data-ttu-id="9454f-115">次に示します**インデックス**functoid をこのように使用します。</span><span class="sxs-lookup"><span data-stu-id="9454f-115">The following figure shows **Index** functoids used in this way.</span></span>  
  
 <span data-ttu-id="9454f-116">![](../core/media/ebiz-prog-map-index.gif "ebiz_prog_map_index")</span><span class="sxs-lookup"><span data-stu-id="9454f-116">![](../core/media/ebiz-prog-map-index.gif "ebiz_prog_map_index")</span></span>  
<span data-ttu-id="9454f-117">インデックス Functoid の例</span><span class="sxs-lookup"><span data-stu-id="9454f-117">Index Functoid Example</span></span>  
  
 <span data-ttu-id="9454f-118">最初の日付の日単位の概要情報を取得するには、上の設定の 3 つ**インデックス**functoid がある、インデックスの値を 1 に設定します。</span><span class="sxs-lookup"><span data-stu-id="9454f-118">To get the daily summary information for the first day, the upper set of three **Index** functoids have their index values set to 1.</span></span> <span data-ttu-id="9454f-119">2 日目の毎日の概要情報を取得するには、下に 3 つの設定**インデックス**functoid がある、インデックスの値を 2 に設定します。</span><span class="sxs-lookup"><span data-stu-id="9454f-119">To get the daily summary information for the second day, the lower set of three **Index** functoids have their index values set to 2.</span></span>  
  
 <span data-ttu-id="9454f-120">**インデックス**functoid を使用して、**構成\<Functoid\> Functoid**ダイアログ ボックスを入力パラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="9454f-120">**Index** functoids use the **Configure \<Functoid\> Functoid** dialog box to set their input parameters.</span></span> <span data-ttu-id="9454f-121">最初の入力パラメーターが、送信元スキーマのループ レコード内のフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="9454f-121">The first input parameter identifies a field within a looping record in the source schema.</span></span> <span data-ttu-id="9454f-122">2 番目以降の入力パラメーターでは、特定のレコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="9454f-122">The second and succeeding input parameters specify the particular record.</span></span> <span data-ttu-id="9454f-123">入れ子になった繰り返し構造内のレコードを選択するために、複数のインデックス値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="9454f-123">You can specify multiple index values to select a record within nested repeating structures.</span></span> <span data-ttu-id="9454f-124">最も内側の構造のインデックス値が 2 番目のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="9454f-124">The index value for the innermost structure is the second parameter.</span></span> <span data-ttu-id="9454f-125">内側から 2 つ目の構造のインデックス値が 3 番目のパラメーターで、以降も同様です。</span><span class="sxs-lookup"><span data-stu-id="9454f-125">The index value for the next outermost structure would be the third parameter, and so on.</span></span> <span data-ttu-id="9454f-126">たとえばを前述の**DailySummary**内だったレコードの**WeeklyData**レコード。</span><span class="sxs-lookup"><span data-stu-id="9454f-126">For example, suppose that the preceding **DailySummary** records were inside **WeeklyData** records.</span></span> <span data-ttu-id="9454f-127">取得する、**圧力**最初から**DailySummary** 、2 番目の**WeeklyData**、2 番目のパラメーター 1 になり、3 番目のパラメーターが 2 になります。</span><span class="sxs-lookup"><span data-stu-id="9454f-127">To retrieve the **Pressure** from the first **DailySummary** in the second **WeeklyData**, the second parameter would be 1 and the third parameter would be 2.</span></span>  
  
 <span data-ttu-id="9454f-128">この例では通知、**圧力**フィールドが繰り返されない。</span><span class="sxs-lookup"><span data-stu-id="9454f-128">Notice that this example assumes the **Pressure** field does not repeat.</span></span> <span data-ttu-id="9454f-129">インデックスが無効になる場合は、フィールドが繰り返すには、— カウントで開始、**圧力**フィールドではなく、**日ごとのサマリー**です。</span><span class="sxs-lookup"><span data-stu-id="9454f-129">If the field did repeat, the indices would be off—the count would begin with the **Pressure** field, rather than the **Daily Summary**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9454f-130">一般的にインデックス シーケンスの入力パラメーターは定数ですが、送信元スキーマのノードからのリンクを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="9454f-130">Although an index sequence input parameter is typically a constant, it is possible to use a link from a node in the source schema.</span></span> <span data-ttu-id="9454f-131">このリンクが 1 番目の入力パラメーターの親ではないループ レコードからのリンクの場合、インデックス シーケンスの入力値は、入力インスタンス メッセージのノードの最初のインスタンスから取得されます。</span><span class="sxs-lookup"><span data-stu-id="9454f-131">If this link comes from a looping record that is not a parent of the first input parameter, the index sequence input value comes from the first instance of the node in the input instance message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9454f-132">通常、インデックス シーケンスの入力値は、送信元ドキュメントの現在のコンテキストに関するものです。</span><span class="sxs-lookup"><span data-stu-id="9454f-132">The value of the index sequence input is always in relation to the current context in the source document.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9454f-133">**インデックス**functoid が、フィールド レベルからルート ノード直下の第 1 レベルの親ノードがある多くのインデックス値が必要です。</span><span class="sxs-lookup"><span data-stu-id="9454f-133">An **Index** functoid must have as many index values as there are parent nodes from the field level to the first level below the root node.</span></span> <span data-ttu-id="9454f-134">たとえば、複数の気象レポート インスタンス メッセージでは、2 つのインデックス値が必要です。</span><span class="sxs-lookup"><span data-stu-id="9454f-134">For example, in the multiple weather report instance message, two index values are required.</span></span> <span data-ttu-id="9454f-135">単一の気象レポート インスタンス メッセージでは、必要なインデックス値は 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="9454f-135">In the single weather report instance message, only one index value is required.</span></span> <span data-ttu-id="9454f-136">必要な数のインデックス値の設定に失敗した、**インデックス**functoid の最初の入力パラメーターに一致する送信元インスタンス メッセージの最初のノードに基づいて出力を作成する、**インデックス**functoid です。</span><span class="sxs-lookup"><span data-stu-id="9454f-136">Failure to set the required number of index values of an **Index** functoid creates output based on the first node in the source instance message that matches the first input parameter of the **Index** functoid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9454f-137">参照</span><span class="sxs-lookup"><span data-stu-id="9454f-137">See Also</span></span>  
 <span data-ttu-id="9454f-138">[インデックス Functoid をマップに追加する方法](../core/how-to-add-index-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="9454f-138">[How to Add Index Functoids to a Map](../core/how-to-add-index-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="9454f-139">[高度な Functoid](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="9454f-139">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="9454f-140">[繰り返し Functoid](../core/iteration-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="9454f-140">[Iteration Functoid](../core/iteration-functoid.md) </span></span>  
 [<span data-ttu-id="9454f-141">レコード カウント Functoid</span><span class="sxs-lookup"><span data-stu-id="9454f-141">Record Count Functoid</span></span>](../core/record-count-functoid.md)
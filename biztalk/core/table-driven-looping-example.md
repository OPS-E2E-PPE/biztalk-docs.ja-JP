---
title: テーブル ドリブン ループの例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Table Extractor functoids, code sample
- Table Looping functoids
- Table Extractor functoids
- Table Looping functoids, about Table Looping functoids
- Table Extractor functoids, about Table Extractor functoids
- code samples, Table Looping functoids
- Table Looping functoids, code sample
- code samples, Table Extractor functoids
ms.assetid: d890bdb1-12a6-4001-9748-737b1f2bab79
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 505738960cb47930c210398dd76ffe394fe71637
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291663"
---
# <a name="table-driven-looping-example"></a><span data-ttu-id="740c5-102">テーブル ドリブン ループの例</span><span class="sxs-lookup"><span data-stu-id="740c5-102">Table-Driven Looping Example</span></span>
<span data-ttu-id="740c5-103">マップを使用して、簡単な説明、**テーブル ループ**と**テーブル抽出**functoid。</span><span class="sxs-lookup"><span data-stu-id="740c5-103">This section briefly describes a map using the **Table Looping** and **Table Extractor** functoids.</span></span> <span data-ttu-id="740c5-104">詳細についてを選択すると、配置することで、リンク、および、functoid の構成を参照してください[テーブル ループの追加とテーブル抽出 Functoid をマップする方法](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)します。</span><span class="sxs-lookup"><span data-stu-id="740c5-104">For detailed information about selecting, placing, linking, and configuring the functoids, see [How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md).</span></span>  
  
 <span data-ttu-id="740c5-105">別の送付先と請求先のアドレスを必要とするドキュメントで使用する必要があるアドレスの一覧とします。</span><span class="sxs-lookup"><span data-stu-id="740c5-105">Suppose you have a list of addresses that you need to use in a document requiring separate ship-to and bill-to addresses.</span></span> <span data-ttu-id="740c5-106">次のように、アドレスがあります。</span><span class="sxs-lookup"><span data-stu-id="740c5-106">The addresses might appear like the following code.</span></span>  
  
```  
<ns0:Root xmlns:ns0="http://TableLoopingSample.Addresses">  
    <Address>  
        <Name>Kelly Focht</Name>  
        <Street>456 1st Ave</Street>  
        <City>Miami</City>  
        <State>FL</State>  
        <PostalCode>81406</PostalCode>  
    </Address>  
    <Address>  
        <Name>Wendy Wheeler</Name>  
        <Street>7890 Broadway</Street>  
        <City>Columbus</City>  
        <State>OH</State>  
        <PostalCode>46290</PostalCode>  
    </Address>  
</ns0:Root>  
```  
  
 <span data-ttu-id="740c5-107">1 つの形式の出力がかかる場合があります、アドレスの重複が属性でマークして、次のコードになります。</span><span class="sxs-lookup"><span data-stu-id="740c5-107">One form the output could take would be the following code, duplicating the addresses but marking them with attributes.</span></span>  
  
```  
<ns0:Root xmlns:ns0="http://TableLoopingSample.POAddresses">  
    <Address Type="ShipTo">  
        <Name>Kelly Focht</Name>  
        <Street>456 1st Ave</Street>  
        <City>Miami</City>  
        <State>FL</State>  
        <PostalCode>81406</PostalCode>  
    </Address>  
    <Address Type="BillTo">  
        <Name>Kelly Focht</Name>  
        <Street>456 1st Ave</Street>  
        <City>Miami</City><State>FL</State>  
        <PostalCode>81406</PostalCode>  
    </Address>  
    <Address Type="ShipTo">  
        <Name>Wendy Wheeler</Name>  
        <Street>7890 Broadway</Street>  
        <City>Columbus</City>  
        <State>OH</State>  
        <PostalCode>46290</PostalCode>  
    </Address>  
    <Address Type="BillTo">  
        <Name>Wendy Wheeler</Name>  
        <Street>7890 Broadway</Street>  
        <City>Columbus</City>  
        <State>OH</State>  
        <PostalCode>46290</PostalCode>  
    </Address>  
</ns0:Root>  
```  
  
 <span data-ttu-id="740c5-108">`The following figure shows a map using the`  **テーブル\*\*\*\*ループ**`functoid and`**テーブル\*\*\*\*エクス トラクター**   `functoids to generate the desired output instance message.`</span><span class="sxs-lookup"><span data-stu-id="740c5-108">`The following figure shows a map using the`  **Table** **Looping**  `functoid and`  **Table** **Extractor**  `functoids to generate the desired output instance message.`</span></span>  
  
 <span data-ttu-id="740c5-109">![テーブル ループとテーブル抽出 functoid をマップ](../core/media/tableloopingextractorfunctoid.gif "tableloopingextractorfunctoid")</span><span class="sxs-lookup"><span data-stu-id="740c5-109">![Map the Table Looping and Table Extractor functoid](../core/media/tableloopingextractorfunctoid.gif "tableloopingextractorfunctoid")</span></span>  
<span data-ttu-id="740c5-110">Functoid およびテーブル抽出 Functoid</span><span class="sxs-lookup"><span data-stu-id="740c5-110">TableLooping and Extractor Functoids</span></span>  
  
 <span data-ttu-id="740c5-111">なお、**テーブル ループ**functoid が入力と出力の両方のスキーマのレコード レベルの要素にリンクします。</span><span class="sxs-lookup"><span data-stu-id="740c5-111">Notice that the **Table Looping** functoid links to the record-level element in both the input and output schemas.</span></span> <span data-ttu-id="740c5-112">リンクは、外側の構造の作成と、そのため、レコード内の要素の作成を設定します。</span><span class="sxs-lookup"><span data-stu-id="740c5-112">The link ensures the creation of the enclosing structure and, thus, the creation of the elements within the record.</span></span> <span data-ttu-id="740c5-113">1 つまた**テーブル抽出**functoid の出力スキーマのフィールドごとにします。</span><span class="sxs-lookup"><span data-stu-id="740c5-113">Also notice that there is one **Table Extractor** functoid for each field in the output schema.</span></span>  
  
 <span data-ttu-id="740c5-114">入力スキーマのレコードへのリンクは、最初のパラメーターで、**構成\<Functoid\> Functoid** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="740c5-114">The link to the record in the input schema is the first parameter in the **Configure \<Functoid\> Functoid**dialog box.</span></span>  
  
 <span data-ttu-id="740c5-115">2 番目のパラメーターは、functoid のグリッド テーブルの列の数: 1 つの列それぞれのアドレスの種類、名前、番地、市区町村、状態、および郵便番号。</span><span class="sxs-lookup"><span data-stu-id="740c5-115">The second parameter is the number of columns in the grid table of the functoid: one column each for the address type, name, street, city, state, and postal code.</span></span> <span data-ttu-id="740c5-116">次の 2 番目のパラメーターは、すべてのグリッド テーブルに表示される値の一覧です。</span><span class="sxs-lookup"><span data-stu-id="740c5-116">Following the second parameter is a list of all of the values that may appear in the grid table.</span></span> <span data-ttu-id="740c5-117">アドレスのフィールドへのリンクと共に、アドレスの種類 ("ShipTo"、"BillTo") の文字列定数が含まれます。</span><span class="sxs-lookup"><span data-stu-id="740c5-117">These include string constants for the address type ("ShipTo", "BillTo"), as well as links to the fields of the address.</span></span> <span data-ttu-id="740c5-118">住所のフィールドへのリンクが名前を持つことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="740c5-118">Notice that the links to the address fields have names.</span></span> <span data-ttu-id="740c5-119">マップ内のリンクの名前を付けるには、テーブルの構築が簡略化します。</span><span class="sxs-lookup"><span data-stu-id="740c5-119">Naming the links in the map simplifies constructing the table.</span></span> <span data-ttu-id="740c5-120">完全なパスを表示する場合は、**テーブル ループ Functoid の構成** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="740c5-120">Otherwise, full paths appear in the **Configure Table Looping Functoid** dialog box.</span></span>  
  
 <span data-ttu-id="740c5-121">構成した後、**テーブル ループ**functoid を使用してテーブルを構築することができます、**テーブル ループ Functoid の構成** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="740c5-121">After you have configured the **Table Looping** functoid, you can construct the table using the **Configure Table Looping Functoid** dialog box.</span></span> <span data-ttu-id="740c5-122">省略記号をクリックすると、ダイアログ ボックスが表示されます (**.**) ボタンに関連付けられている、**テーブル ループ グリッド**プロパティ、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="740c5-122">The dialog appears when you click the ellipsis (**…**) button associated with the **Table Looping Grid** property in the **Properties** window.</span></span>  
  
 <span data-ttu-id="740c5-123">指定されている 6 つの列があることに注意してください、**テーブル ループ Functoid の構成**ダイアログ: 出力スキーマのフィールドごとに 1 つの列。</span><span class="sxs-lookup"><span data-stu-id="740c5-123">Notice that there are six columns as specified in the **Configure Table Looping Functoid** dialog: one column for each field in the output schema.</span></span> <span data-ttu-id="740c5-124">ドロップダウン リストで 3 つ目以降のパラメーターで指定されたフィールドの値を示しています、**テーブル ループ Functoid の構成**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="740c5-124">The dropdown shows the possible values for a field, also as specified by the third and following parameters in the **Configure Table Looping Functoid** dialog.</span></span> <span data-ttu-id="740c5-125">テーブルには、出力スキーマのレコードの種類ごとに 1 つずつ、2 つの行があります。</span><span class="sxs-lookup"><span data-stu-id="740c5-125">The table has two rows, one for each type of record in the output schema.</span></span> <span data-ttu-id="740c5-126">2 つの行があるため、このマップには、入力レコードごとに 2 つのレコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="740c5-126">Because there are two rows, this map produces two records for every input record.</span></span> <span data-ttu-id="740c5-127">4 つの行があった場合は、各入力レコードの 4 つの出力レコードがあります。</span><span class="sxs-lookup"><span data-stu-id="740c5-127">If there were four rows, there would be four output records for each input record.</span></span>  
  
 <span data-ttu-id="740c5-128">として、**テーブル ループ**functoid が各レコードをレコードの値を持つテーブルに格納し、一度に 1 つの行を送信、**テーブル抽出**functoid。</span><span class="sxs-lookup"><span data-stu-id="740c5-128">As the **Table Looping** functoid takes each record, it fills in the table with the values from the record, and then sends one row at a time to the **Table Extractor** functoids.</span></span> <span data-ttu-id="740c5-129">**テーブル抽出**functoid のテーブルの行から 1 つの値を抽出各と、出力インスタンス メッセージでリンクされているフィールドに渡します。</span><span class="sxs-lookup"><span data-stu-id="740c5-129">The **Table Extractor** functoids each extract one value from the table row and pass it on to the linked field in the output instance message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="740c5-130">参照</span><span class="sxs-lookup"><span data-stu-id="740c5-130">See Also</span></span>  
 <span data-ttu-id="740c5-131">[テーブル ループ Functoid](../core/table-looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="740c5-131">[Table Looping Functoid](../core/table-looping-functoid.md) </span></span>  
 <span data-ttu-id="740c5-132">[テーブル抽出 Functoid](../core/table-extractor-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="740c5-132">[Table Extractor Functoid](../core/table-extractor-functoid.md) </span></span>  
 <span data-ttu-id="740c5-133">[テーブル ドリブン ループの構成](../core/table-driven-looping-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="740c5-133">[Table-Driven Looping Configuration](../core/table-driven-looping-configuration.md) </span></span>  
 <span data-ttu-id="740c5-134">[マップにテーブル抽出 Functoid およびテーブル ループを追加する方法](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="740c5-134">[How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="740c5-135">[高度な Functoid](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="740c5-135">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="740c5-136">[インデックス Functoid](../core/index-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="740c5-136">[Index Functoid](../core/index-functoid.md) </span></span>  
 <span data-ttu-id="740c5-137">[繰り返し Functoid](../core/iteration-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="740c5-137">[Iteration Functoid](../core/iteration-functoid.md) </span></span>  
 <span data-ttu-id="740c5-138">[ループ Functoid](../core/looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="740c5-138">[Looping Functoid](../core/looping-functoid.md) </span></span>  
 [<span data-ttu-id="740c5-139">レコード カウント Functoid</span><span class="sxs-lookup"><span data-stu-id="740c5-139">Record Count Functoid</span></span>](../core/record-count-functoid.md)
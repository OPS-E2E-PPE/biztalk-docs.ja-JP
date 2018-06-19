---
title: テーブルドリブン ループの例 |Microsoft ドキュメント
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
ms.openlocfilehash: e6989ac7e64cf28784d08f26aaf9e7af3a166a28
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "25974536"
---
# <a name="table-driven-looping-example"></a><span data-ttu-id="c3b41-102">テーブルドリブン ループの例</span><span class="sxs-lookup"><span data-stu-id="c3b41-102">Table-Driven Looping Example</span></span>
<span data-ttu-id="c3b41-103">このセクションを使用して、マップ、 **テーブル ループ** と **テーブル抽出** functoid です。</span><span class="sxs-lookup"><span data-stu-id="c3b41-103">This section briefly describes a map using the **Table Looping** and **Table Extractor** functoids.</span></span> <span data-ttu-id="c3b41-104">詳細についてを選択すると、配置、リンク、および、functoid の構成を参照してください[テーブル ループの追加、およびテーブル抽出 Functoid をマップする方法](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)です。</span><span class="sxs-lookup"><span data-stu-id="c3b41-104">For detailed information about selecting, placing, linking, and configuring the functoids, see [How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md).</span></span>  
  
 <span data-ttu-id="c3b41-105">出荷先住所と請求先住所を別々に掲載するドキュメントで使用される、住所の一覧を例として説明します。</span><span class="sxs-lookup"><span data-stu-id="c3b41-105">Suppose you have a list of addresses that you need to use in a document requiring separate ship-to and bill-to addresses.</span></span> <span data-ttu-id="c3b41-106">住所は、次のコードのように表されます。</span><span class="sxs-lookup"><span data-stu-id="c3b41-106">The addresses might appear like the following code.</span></span>  
  
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
  
 <span data-ttu-id="c3b41-107">次のコードは出力形式の例を示しています。ここでは、住所が複製され、各住所に属性が設定されています。</span><span class="sxs-lookup"><span data-stu-id="c3b41-107">One form the output could take would be the following code, duplicating the addresses but marking them with attributes.</span></span>  
  
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
  
 <span data-ttu-id="c3b41-108">`The following figure shows a map using the`  **テーブル** **ループ**  `functoid and`  **テーブル** **抽出**  `functoids to generate the desired output instance message.`</span><span class="sxs-lookup"><span data-stu-id="c3b41-108">`The following figure shows a map using the`  **Table** **Looping**  `functoid and`  **Table** **Extractor**  `functoids to generate the desired output instance message.`</span></span>  
  
 <span data-ttu-id="c3b41-109">![テーブル ループとテーブル抽出 functoid マップ](../core/media/tableloopingextractorfunctoid.gif "tableloopingextractorfunctoid")</span><span class="sxs-lookup"><span data-stu-id="c3b41-109">![Map the Table Looping and Table Extractor functoid](../core/media/tableloopingextractorfunctoid.gif "tableloopingextractorfunctoid")</span></span>  
<span data-ttu-id="c3b41-110">テーブル ループ Functoid とテーブル抽出 Functoid</span><span class="sxs-lookup"><span data-stu-id="c3b41-110">TableLooping and Extractor Functoids</span></span>  
  
 <span data-ttu-id="c3b41-111">注意して、 **テーブル ループ** functoid が入力と出力の両方のスキーマのレコード レベルの要素にリンクします。</span><span class="sxs-lookup"><span data-stu-id="c3b41-111">Notice that the **Table Looping** functoid links to the record-level element in both the input and output schemas.</span></span> <span data-ttu-id="c3b41-112">リンクによって、囲み構造が作成され、レコード内に要素が作成されます。</span><span class="sxs-lookup"><span data-stu-id="c3b41-112">The link ensures the creation of the enclosing structure and, thus, the creation of the elements within the record.</span></span> <span data-ttu-id="c3b41-113">またことがあることを確認 **テーブル抽出** functoid の出力スキーマ内の各フィールドです。</span><span class="sxs-lookup"><span data-stu-id="c3b41-113">Also notice that there is one **Table Extractor** functoid for each field in the output schema.</span></span>  
  
 <span data-ttu-id="c3b41-114">入力スキーマのレコードへのリンクは、最初のパラメーター、**構成\<Functoid\> Functoid** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="c3b41-114">The link to the record in the input schema is the first parameter in the **Configure \<Functoid\> Functoid**dialog box.</span></span>  
  
 <span data-ttu-id="c3b41-115">2 番目のパラメーターは、functoid のグリッド テーブルの列の数: 1 列ごとのアドレスの種類、名前、番地、市区町村、状態、および郵便番号。</span><span class="sxs-lookup"><span data-stu-id="c3b41-115">The second parameter is the number of columns in the grid table of the functoid: one column each for the address type, name, street, city, state, and postal code.</span></span> <span data-ttu-id="c3b41-116">2 つ目のパラメーターの後には、グリッド テーブルに表示されるすべての値の一覧が示されています。</span><span class="sxs-lookup"><span data-stu-id="c3b41-116">Following the second parameter is a list of all of the values that may appear in the grid table.</span></span> <span data-ttu-id="c3b41-117">一覧には、住所のフィールドへのリンクと共に、住所の種類 ("ShipTo" および "BillTo") に使用する文字列の定数が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c3b41-117">These include string constants for the address type ("ShipTo", "BillTo"), as well as links to the fields of the address.</span></span> <span data-ttu-id="c3b41-118">住所のフィールドへのリンクに名前があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c3b41-118">Notice that the links to the address fields have names.</span></span> <span data-ttu-id="c3b41-119">マップ内のリンクに名前を付けると、テーブルの構築がわかりやすくなります。</span><span class="sxs-lookup"><span data-stu-id="c3b41-119">Naming the links in the map simplifies constructing the table.</span></span> <span data-ttu-id="c3b41-120">完全なパスを表示するそれ以外の場合、 **[テーブル ループ Functoid** ] ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="c3b41-120">Otherwise, full paths appear in the **Configure Table Looping Functoid** dialog box.</span></span>  
  
 <span data-ttu-id="c3b41-121">構成した後、 **テーブル ループ** functoid を使用してテーブルを作成することができます、 **[テーブル ループ Functoid** ] ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="c3b41-121">After you have configured the **Table Looping** functoid, you can construct the table using the **Configure Table Looping Functoid** dialog box.</span></span> <span data-ttu-id="c3b41-122">省略記号ボタンをクリックすると、ダイアログ ボックスが表示されます (**...**) に関連付けられたボタン、 **テーブル ループ グリッド** プロパティに、 **プロパティ** ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="c3b41-122">The dialog appears when you click the ellipsis (**…**) button associated with the **Table Looping Grid** property in the **Properties** window.</span></span>  
  
 <span data-ttu-id="c3b41-123">指定されている 6 つの列があることに注意してください、 **テーブル ループ Functoid** ダイアログ: 出力スキーマのフィールドごとに 1 つの列です。</span><span class="sxs-lookup"><span data-stu-id="c3b41-123">Notice that there are six columns as specified in the **Configure Table Looping Functoid** dialog: one column for each field in the output schema.</span></span> <span data-ttu-id="c3b41-124">ドロップダウン リストは、3 番目以降のパラメーターで指定されたフィールドの値を示しています、 **テーブル ループ Functoid** ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="c3b41-124">The dropdown shows the possible values for a field, also as specified by the third and following parameters in the **Configure Table Looping Functoid** dialog.</span></span> <span data-ttu-id="c3b41-125">テーブルには、2 行 (出力スキーマの各種類のレコード) あります。</span><span class="sxs-lookup"><span data-stu-id="c3b41-125">The table has two rows, one for each type of record in the output schema.</span></span> <span data-ttu-id="c3b41-126">2 行存在するので、このマップは、入力レコードごとに 2 つのレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="c3b41-126">Because there are two rows, this map produces two records for every input record.</span></span> <span data-ttu-id="c3b41-127">4 行存在する場合は、入力レコードごとに 4 つの出力レコードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c3b41-127">If there were four rows, there would be four output records for each input record.</span></span>  
  
 <span data-ttu-id="c3b41-128">として、 **テーブル ループ** functoid は、各レコードは、これは、レコードの値を持つテーブルを入力しに一度に 1 つの行を送信、 **テーブル抽出** functoid です。</span><span class="sxs-lookup"><span data-stu-id="c3b41-128">As the **Table Looping** functoid takes each record, it fills in the table with the values from the record, and then sends one row at a time to the **Table Extractor** functoids.</span></span> <span data-ttu-id="c3b41-129">**テーブル抽出** functoid のテーブルの行から 1 つの値を抽出各と出力インスタンス メッセージにリンクされているフィールドを渡します。</span><span class="sxs-lookup"><span data-stu-id="c3b41-129">The **Table Extractor** functoids each extract one value from the table row and pass it on to the linked field in the output instance message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3b41-130">参照</span><span class="sxs-lookup"><span data-stu-id="c3b41-130">See Also</span></span>  
 <span data-ttu-id="c3b41-131">[テーブル ループ Functoid](../core/table-looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="c3b41-131">[Table Looping Functoid](../core/table-looping-functoid.md) </span></span>  
 <span data-ttu-id="c3b41-132">[テーブル抽出 Functoid](../core/table-extractor-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="c3b41-132">[Table Extractor Functoid](../core/table-extractor-functoid.md) </span></span>  
 <span data-ttu-id="c3b41-133">[テーブルドリブン ループの構成](../core/table-driven-looping-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="c3b41-133">[Table-Driven Looping Configuration](../core/table-driven-looping-configuration.md) </span></span>  
 <span data-ttu-id="c3b41-134">[テーブル ループを追加する方法と、マップにテーブル抽出 Functoid](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="c3b41-134">[How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="c3b41-135">[高度な Functoid](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="c3b41-135">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="c3b41-136">[インデックス Functoid](../core/index-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="c3b41-136">[Index Functoid](../core/index-functoid.md) </span></span>  
 <span data-ttu-id="c3b41-137">[繰り返し Functoid](../core/iteration-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="c3b41-137">[Iteration Functoid](../core/iteration-functoid.md) </span></span>  
 <span data-ttu-id="c3b41-138">[ループ Functoid](../core/looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="c3b41-138">[Looping Functoid](../core/looping-functoid.md) </span></span>  
 [<span data-ttu-id="c3b41-139">レコード カウント Functoid</span><span class="sxs-lookup"><span data-stu-id="c3b41-139">Record Count Functoid</span></span>](../core/record-count-functoid.md)
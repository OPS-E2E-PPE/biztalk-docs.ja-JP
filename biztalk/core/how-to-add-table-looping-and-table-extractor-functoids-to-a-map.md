---
title: "テーブル ループを追加し、テーブル抽出 Functoid をマップする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3c837ab8-55db-471a-af26-9fbd0497d7d4
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4b7844260b7ac5ab29f204a538e61cb99b0d017
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-table-looping-and-table-extractor-functoids-to-a-map"></a><span data-ttu-id="e8621-102">マップにテーブル ループ Functoid およびテーブル抽出 Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="e8621-102">How to Add Table Looping and Table Extractor Functoids to a Map</span></span>
<span data-ttu-id="e8621-103">**テーブル ループ**と**テーブル抽出**functoid は一緒に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e8621-103">The **Table Looping** and **Table Extractor** functoids are used together.</span></span> <span data-ttu-id="e8621-104">**テーブル ループ**functoid が構成する内部テーブルです。</span><span class="sxs-lookup"><span data-stu-id="e8621-104">The **Table Looping** functoid has an internal table you configure.</span></span> <span data-ttu-id="e8621-105">各入力レコードまたはフィールドの**テーブル ループ**functoid は一度に 1 つずつ、テーブルの行を出力します。</span><span class="sxs-lookup"><span data-stu-id="e8621-105">For each input record or field, the **Table Looping** functoid outputs the rows of the table, one at a time.</span></span> <span data-ttu-id="e8621-106">**テーブル抽出**functoid が行から目的の項目を抽出し、出力インスタンス メッセージに渡します。</span><span class="sxs-lookup"><span data-stu-id="e8621-106">The **Table Extractor** functoid extracts the desired item from a row and passes it on to the output instance message.</span></span>  
  
 <span data-ttu-id="e8621-107">概要については、**テーブル ループ**と**テーブル抽出**functoid を参照してください[テーブル ループ functoid とテーブル抽出 Functoid](../core/table-looping-and-table-extractor-functoids.md)です。</span><span class="sxs-lookup"><span data-stu-id="e8621-107">For conceptual information about the **Table Looping** and **Table Extractor** functoids, see [Table Looping and Table Extractor Functoids](../core/table-looping-and-table-extractor-functoids.md).</span></span>  
  
### <a name="to-add-the-table-looping-and-table-extractor-functoids-to-a-map-and-configure-them"></a><span data-ttu-id="e8621-108">テーブル ループ Functoid およびテーブル抽出 Functoid をマップに追加して構成するには</span><span class="sxs-lookup"><span data-stu-id="e8621-108">To add the Table Looping and Table Extractor functoids to a map and configure them</span></span>  
  
1.  <span data-ttu-id="e8621-109">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブです。</span><span class="sxs-lookup"><span data-stu-id="e8621-109">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
     <span data-ttu-id="e8621-110">選択したカテゴリに含まれる高度な Functoid の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8621-110">The list of advanced functoids in the chosen category appears.</span></span>  
  
2.  <span data-ttu-id="e8621-111">ドラッグ、**テーブル ループ**functoid (![](../core/media/advtablelooping.gif "advtablelooping")) をグリッド ページの適切な場所にツールボックスからです。</span><span class="sxs-lookup"><span data-stu-id="e8621-111">Drag the **Table Looping** functoid (![](../core/media/advtablelooping.gif "advtablelooping")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e8621-112">Functoid は表示されているグリッド ページに配置されます。</span><span class="sxs-lookup"><span data-stu-id="e8621-112">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="e8621-113">別のグリッド ページに functoid を配置する場合は、最初にそのグリッド ページを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8621-113">If you want to put the functoid onto a different grid page, you need to display that grid page first.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e8621-114">の出力、**テーブル ループ**functoid は 1 つ以上関連付けられている入力として機能**テーブル抽出**functoid の右側に余裕があるようにするを確認、**テーブル ループ** functoid、**テーブル抽出**functoid です。</span><span class="sxs-lookup"><span data-stu-id="e8621-114">Because the output of the **Table Looping** functoid serves as input to one or more associated **Table Extractor** functoids, make sure you leave room to the right of the **Table Looping** functoid for the **Table Extractor** functoids.</span></span>  
  
3.  <span data-ttu-id="e8621-115">送信元スキーマから、新たに追加するレコードまたはフィールドをドラッグ**テーブル ループ**functoid です。</span><span class="sxs-lookup"><span data-stu-id="e8621-115">Drag a record or field from the source schema to the newly added **Table Looping** functoid.</span></span> <span data-ttu-id="e8621-116">最初の入力パラメーターとして、**テーブル ループ**functoid、このレコードまたはフィールドがインスタンス メッセージ内の出現回数は、この functoid の出力から生成される回数を制御します。</span><span class="sxs-lookup"><span data-stu-id="e8621-116">As the first input parameter to the **Table Looping** functoid, the number of occurrences of this record or field in an instance message will control the number of times this functoid produces output.</span></span> <span data-ttu-id="e8621-117">たとえば、ループ レコードは、functoid にドラッグし、このレコードの 10 件のあるインスタンス メッセージが処理され、1 つの行の列のデータ ソースのテーブル グリッドが構成されている場合、**テーブル ループ**functoid は反復処理する 10 回によって抽出するための 10 の出力行を生成する、**テーブル抽出**簡単に構築されている functoid と許可 10 変換先を記録します。</span><span class="sxs-lookup"><span data-stu-id="e8621-117">For example, if a looping record is dragged to the functoid, and an instance message that has 10 occurrences of this record is processed, and the table grid has been configured with one row of sources of column data, the **Table Looping** functoid will iterate 10 times, producing 10 output rows for extraction by a **Table Extractor** functoid, and allowing 10 destination records to be easily constructed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e8621-118">各このような行の出力の各反復処理をするテーブル グリッドで、複数の行を構成する場合、**テーブル ループ**functoid です。</span><span class="sxs-lookup"><span data-stu-id="e8621-118">If you configure multiple rows in the table grid, each such row will be output for each iteration of the **Table Looping** functoid.</span></span> <span data-ttu-id="e8621-119">したがって、入力レコードの出現回数に、テーブル グリッドで構成された行数を掛けることによって、データ抽出に使用できるテーブルの出力行数を求めることができます。</span><span class="sxs-lookup"><span data-stu-id="e8621-119">So, the number of occurrences of an input record times the number of rows configured in the table grid yields the number of output table rows available for data extraction.</span></span>  
  
4.  <span data-ttu-id="e8621-120">変換先スキーマのレコードまたはフィールドをドラッグして、**テーブル ループ**functoid です。</span><span class="sxs-lookup"><span data-stu-id="e8621-120">Drag a record or field from the destination schema to the **Table Looping** functoid.</span></span> <span data-ttu-id="e8621-121">この関連付けにより、送信先スキーマにノードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e8621-121">This link ensures the creation of the node in the destination schema.</span></span>  
  
5.  <span data-ttu-id="e8621-122">新しく追加された選択**テーブル ループ**functoid、し、、**プロパティ**ウィンドウで、省略記号ボタンをクリックして (**.**) に関連付けられたボタンその**入力パラメーター**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="e8621-122">Select the newly added **Table Looping** functoid, and in the **Properties** window, click the ellipsis (**...**) button associated with its **Input Parameters** property.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e8621-123">または、Functoid を選択し、Ctrl キーを押しながら M キーを押し、次に Ctrl キーを押しながら T キーを押します。</span><span class="sxs-lookup"><span data-stu-id="e8621-123">Alternatively, you can select the functoid and then press CTRL+M, CTRL+T from the keyboard.</span></span> <span data-ttu-id="e8621-124">一覧マッパーのキーボード ショートカットについて[BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)です。</span><span class="sxs-lookup"><span data-stu-id="e8621-124">For a list of Mapper keyboard shortcuts see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
6.  <span data-ttu-id="e8621-125">**テーブル ループ Functoid**ダイアログ ボックスで、をクリックして、 ![functoid への定数入力パラメーターの追加](../core/media/add-input-parameters.gif "Add_input_parameters")クリックすると、2 つ目の作成入力パラメーター。</span><span class="sxs-lookup"><span data-stu-id="e8621-125">In the **Configure Table Looping Functoid** dialog box, click the ![Adding constant input parameters to a functoid](../core/media/add-input-parameters.gif "Add_input_parameters") button to create the second input parameter.</span></span> <span data-ttu-id="e8621-126">これを作成するテーブルで使用できる列の数を表す数値を入力**テーブル ループ**functoid です。</span><span class="sxs-lookup"><span data-stu-id="e8621-126">Type a number that represents the number of columns that will be available in the table you are creating for this **Table Looping** functoid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e8621-127">テーブルの列数の最大値は 228 です。</span><span class="sxs-lookup"><span data-stu-id="e8621-127">The maximum number of columns in the table is 228.</span></span>  
  
7.  <span data-ttu-id="e8621-128">**テーブル ループ Functoid の構成**ダイアログ ボックスで、をクリックして、 ![functoid への定数入力パラメーターの追加](../core/media/add-input-parameters.gif "Add_input_parameters")を任意の定数の入力ボタンをクリックします。構成されたテーブル グリッドに表示される値です。</span><span class="sxs-lookup"><span data-stu-id="e8621-128">In the **Configure Table Looping Functoid** dialog box, click the ![Adding constant input parameters to a functoid](../core/media/add-input-parameters.gif "Add_input_parameters") button to enter any constant values that appears in your configured table grid.</span></span> <span data-ttu-id="e8621-129">入力パラメーター リストの先頭で、第 1 パラメーターと第 2 パラメーターの値 (行数と列数) が正しい順序で入力されていれば、このダイアログ ボックスで定数を設定する順序は特に重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="e8621-129">The order in which you create these constants is not important in this dialog box as long as the first and second parameter values, the number of rows and columns, respectively, retain their positions at the beginning of the input parameter list.</span></span> <span data-ttu-id="e8621-130">完了したら、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="e8621-130">When complete, click **OK**.</span></span>  
  
     <span data-ttu-id="e8621-131">**[テーブル ループ Functoid** ] ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e8621-131">The **Configure Table Looping Functoid** dialog box closes.</span></span>  
  
8.  <span data-ttu-id="e8621-132">送信元スキーマから 0 個以上のレコードまたはフィールド ノードをドラッグ、**テーブル ループ**functoid を追加したばかりです。</span><span class="sxs-lookup"><span data-stu-id="e8621-132">Drag zero or more record or field nodes from the source schema to the **Table Looping** functoid that you recently added.</span></span> <span data-ttu-id="e8621-133">これらのレコードおよびフィールド ノードは、入力パラメーター リストの最後に追加されるため、後の手順でテーブル グリッドを構成したときに使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e8621-133">Each of these record and field nodes is added to the end of the input parameter list, and therefore will be available when the table grid is configured in a latter step.</span></span> <span data-ttu-id="e8621-134">先ほど追加したテーブル データの定数と同様、レコードおよびフィールド ノードを追加する順序は特に重要ではありません (行数と列数は正しい順序で入力されている必要があります)。</span><span class="sxs-lookup"><span data-stu-id="e8621-134">Like the table data constants added earlier (not the row and column count constants), the order in which these record and field nodes are added is not ultimately relevant.</span></span>  
  
9. <span data-ttu-id="e8621-135">リンクにラベルを設定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e8621-135">To label a link, follow these steps:</span></span>  
  
    -   <span data-ttu-id="e8621-136">表示されているグリッド ページでリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="e8621-136">Select a link in the displayed grid page.</span></span>  
  
    -   <span data-ttu-id="e8621-137">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウのわかりやすい名前を指定、**ラベル**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="e8621-137">In the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, provide a descriptive name for the **Label** property.</span></span> <span data-ttu-id="e8621-138">たとえば、"Second Author" というフィールドからのリンクに対しては、"link2ndAuthor" のような名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="e8621-138">For example, you might give a name like "link2ndAuthor" to a link coming from a field called "Second Author".</span></span>  
  
10. <span data-ttu-id="e8621-139">新しく追加された選択**テーブル ループ**functoid、し、、**プロパティ**ウィンドウで、省略記号ボタンをクリックして (**.**) に関連付けられたボタン、**テーブル ループ グリッド**その functoid に関連付けられたプロパティ。</span><span class="sxs-lookup"><span data-stu-id="e8621-139">Select the newly added **Table Looping** functoid, and in the **Properties** window, click the ellipsis (**...**) button associated with the **Table Looping Grid** property associated with that functoid.</span></span>  
  
     <span data-ttu-id="e8621-140">**[テーブル ループ Functoid** ] ダイアログ ボックスが表示されます、**テーブル ループ グリッド**タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="e8621-140">The **Configure Table Looping Functoid** dialog box appears with the **Table Looping Grid** tab selected.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e8621-141">または、functoid を右クリックし、をクリックして**テーブル ループ グリッド**コンテキスト メニュー。</span><span class="sxs-lookup"><span data-stu-id="e8621-141">Alternatively, you can right-click the functoid, and then click **Configure Table Looping Grid** in the context menu.</span></span> <span data-ttu-id="e8621-142">**[テーブル ループ Functoid** ] ダイアログ ボックスが表示されます、**テーブル ループ グリッド**タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="e8621-142">The **Configure Table Looping Functoid** dialog box appears with the **Table Looping Grid** tab selected.</span></span>  
  
11. <span data-ttu-id="e8621-143">各テーブル セルに関連付けられたドロップダウン リストを使用し、グリッド内の少なくとも 1 つの行を構成します。</span><span class="sxs-lookup"><span data-stu-id="e8621-143">Use the drop-down lists associated with each table cell to configure at least one, and possibly multiple, rows in the grid.</span></span> <span data-ttu-id="e8621-144">ドロップダウン リストで使用できる選択肢は、定数および入力パラメーター 3 としておよび最大 6 ~ 8 の手順で構成されているリンク、**テーブル ループ**functoid です。</span><span class="sxs-lookup"><span data-stu-id="e8621-144">The choices available in the drop-down lists are the constants and links that you have configured in steps 6-8 as input parameters 3 and up to the **Table Looping** functoid.</span></span> <span data-ttu-id="e8621-145">第 1 と第 2 の入力パラメーターは、これらのドロップダウン リストには表示されません。完了したら、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="e8621-145">(Input parameters 1 and 2 do not appear in these drop-down lists.) When complete, click **OK**.</span></span>  
  
     <span data-ttu-id="e8621-146">**[テーブル ループ Functoid** ] ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e8621-146">The **Configure Table Looping Functoid** dialog box closes.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e8621-147">各行は、レコードまたはフィールドの最初の入力パラメーターとして指定のオカレンス数と共に、出力構造の 1 つのイテレーションを構成、**テーブル ループ**functoid です。</span><span class="sxs-lookup"><span data-stu-id="e8621-147">Each row constitutes one iteration of the output structure, in combination with the number of occurrences of the record or field specified as the first input parameter of the **Table Looping** functoid.</span></span> <span data-ttu-id="e8621-148">詳細については、手順 3 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8621-148">For more information, see step 3.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e8621-149">使用してアクセスする各列の値を選択する必要があります、**テーブル抽出**functoid です。</span><span class="sxs-lookup"><span data-stu-id="e8621-149">You must select a value for each column you intend to access using a **Table Extractor** functoid.</span></span> <span data-ttu-id="e8621-150">列で使用されていない場合、**テーブル抽出**functoid、維持、その列ではなく、削除を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8621-150">If a column is not used by a **Table Extractor** functoid, you should consider removing, rather than maintaining, that column.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e8621-151">テーブル グリッドに入力する順序は特に重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="e8621-151">The order of filling out the table grid is not important.</span></span>  
  
12. <span data-ttu-id="e8621-152">できるだけドラッグ**テーブル抽出**functoid (![](../core/media/advtableextractor.gif "advtableextractor")) を必要に応じて、表示されているグリッド ページのツールボックスからです。</span><span class="sxs-lookup"><span data-stu-id="e8621-152">Drag as many **Table Extractor** functoids (![](../core/media/advtableextractor.gif "advtableextractor")) from the Toolbox to the displayed grid page as needed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e8621-153">これらの入力**テーブル抽出**functoid に由来、**テーブル ループ**前の手順で追加した functoid に配置することを確認してください、**テーブル抽出**functoid の右側に、**テーブル ループ**表示されているグリッド ページで functoid です。</span><span class="sxs-lookup"><span data-stu-id="e8621-153">Because the input of these **Table Extractor** functoids comes from the **Table Looping** functoid added in a previous step, make sure that you place the **Table Extractor** functoids to the right of the **Table Looping** functoid in the displayed grid page.</span></span>  
  
13. <span data-ttu-id="e8621-154">いずれかの最初の入力パラメーターを作成する、**テーブル抽出**手順 9. で追加の functoid が関連のあるドラッグ**テーブル ループ**functoid の左側にします。</span><span class="sxs-lookup"><span data-stu-id="e8621-154">To create the first input parameter for one of the **Table Extractor** functoids added in step 9, drag it to the relevant **Table Looping** functoid to its left.</span></span>  
  
14. <span data-ttu-id="e8621-155">同じ 2 つ目の入力パラメーターを作成する**テーブル抽出**functoid、functoid を選択し、、**プロパティ**ウィンドウで、省略記号ボタンをクリックして (**...**) に関連付けられたボタンその**入力パラメーター**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="e8621-155">To create the second input parameter for the same **Table Extractor** functoid, select the functoid, and in the **Properties** window, click the ellipsis (**...**) button associated with its **Input parameters** property.</span></span>  
  
     <span data-ttu-id="e8621-156">**テーブル抽出 Functoid の構成** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8621-156">The **Configure Table Extractor Functoid** dialog box appears.</span></span>  
  
15. <span data-ttu-id="e8621-157">クリックして、 ![functoid への定数入力パラメーターの追加](../core/media/add-input-parameters.gif "Add_input_parameters")クリックすると、2 番目の入力パラメーターを作成します。</span><span class="sxs-lookup"><span data-stu-id="e8621-157">Click the ![Adding constant input parameters to a functoid](../core/media/add-input-parameters.gif "Add_input_parameters") button to create the second input parameter.</span></span> <span data-ttu-id="e8621-158">テーブル グリッドで、対応する列の番号を入力**テーブル ループ**functoid のデータを抽出します。</span><span class="sxs-lookup"><span data-stu-id="e8621-158">Type the number of the column in the table grid of the corresponding **Table Looping** functoid from which you want to extract data.</span></span> <span data-ttu-id="e8621-159">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8621-159">Click **OK**.</span></span>  
  
     <span data-ttu-id="e8621-160">**テーブル抽出 Functoid の構成** ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e8621-160">The **Configure Table Extractor Functoid** dialog box closes.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e8621-161">列番号は 1 から始まります。</span><span class="sxs-lookup"><span data-stu-id="e8621-161">Column numbers start at 1.</span></span>  
  
16. <span data-ttu-id="e8621-162">出力を使用する、**テーブル抽出**functoid は、ドラッグ、**テーブル抽出**functoid を送信先スキーマまたは送信先スキーマのレコードまたはフィールド ノードをドラッグすると、内のレコードまたはフィールドノード**テーブル抽出**functoid です。</span><span class="sxs-lookup"><span data-stu-id="e8621-162">To use the output of the **Table Extractor** functoid, drag the **Table Extractor**  functoid to a record or field node in the destination schema, or drag a record or field node in the destination schema to the **Table Extractor** functoid.</span></span> <span data-ttu-id="e8621-163">送信先スキーマ内にある、このレコードまたはフィールド ノードに対応する送信先インスタンス メッセージの要素や属性には、テーブル グリッドで指定されたセルからの値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="e8621-163">The element or attribute value in a destination instance message corresponding to this record or field node in the destination schema will be populated with the value from (in the case of constants), or the value indicated by (in the case of links), the specified cell in the table grid.</span></span>  
  
17. <span data-ttu-id="e8621-164">各について、手順 12、13、14 で、15、**テーブル抽出**functoid 手順 11 で追加します。</span><span class="sxs-lookup"><span data-stu-id="e8621-164">Repeat steps 12, 13, 14, and 15 for each of the **Table Extractor** functoids added in step 11.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8621-165">参照</span><span class="sxs-lookup"><span data-stu-id="e8621-165">See Also</span></span>  
 [<span data-ttu-id="e8621-166">マップへの高度な Functoid の追加</span><span class="sxs-lookup"><span data-stu-id="e8621-166">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)
---
title: テーブル ループを追加およびテーブル抽出 Functoid をマップする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c837ab8-55db-471a-af26-9fbd0497d7d4
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 171f9d637504dfe41445368e71f68256d6035685
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343053"
---
# <a name="how-to-add-table-looping-and-table-extractor-functoids-to-a-map"></a><span data-ttu-id="ab651-102">マップにテーブル抽出 Functoid およびテーブル ループを追加する方法</span><span class="sxs-lookup"><span data-stu-id="ab651-102">How to Add Table Looping and Table Extractor Functoids to a Map</span></span>
<span data-ttu-id="ab651-103">**テーブル ループ**と**テーブル抽出**functoid は一緒に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ab651-103">The **Table Looping** and **Table Extractor** functoids are used together.</span></span> <span data-ttu-id="ab651-104">**テーブル ループ**functoid が、内部テーブルを構成します。</span><span class="sxs-lookup"><span data-stu-id="ab651-104">The **Table Looping** functoid has an internal table you configure.</span></span> <span data-ttu-id="ab651-105">各入力レコードまたはフィールドを**テーブル ループ**functoid は、一度に 1 つずつと、テーブルの行を出力します。</span><span class="sxs-lookup"><span data-stu-id="ab651-105">For each input record or field, the **Table Looping** functoid outputs the rows of the table, one at a time.</span></span> <span data-ttu-id="ab651-106">**テーブル抽出**functoid が行から目的の項目を抽出し、出力インスタンス メッセージに渡します。</span><span class="sxs-lookup"><span data-stu-id="ab651-106">The **Table Extractor** functoid extracts the desired item from a row and passes it on to the output instance message.</span></span>  
  
 <span data-ttu-id="ab651-107">概念情報については、**テーブル ループ**と**テーブル抽出**functoid を参照してください[テーブル ループ functoid およびテーブル抽出 Functoid](../core/table-looping-and-table-extractor-functoids.md)します。</span><span class="sxs-lookup"><span data-stu-id="ab651-107">For conceptual information about the **Table Looping** and **Table Extractor** functoids, see [Table Looping and Table Extractor Functoids](../core/table-looping-and-table-extractor-functoids.md).</span></span>  
  
### <a name="to-add-the-table-looping-and-table-extractor-functoids-to-a-map-and-configure-them"></a><span data-ttu-id="ab651-108">マップに、テーブル ループ functoid およびテーブル抽出 functoid を追加し、構成するには</span><span class="sxs-lookup"><span data-stu-id="ab651-108">To add the Table Looping and Table Extractor functoids to a map and configure them</span></span>  
  
1. <span data-ttu-id="ab651-109">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブ。</span><span class="sxs-lookup"><span data-stu-id="ab651-109">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
    <span data-ttu-id="ab651-110">選択したカテゴリでの高度な functoid の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab651-110">The list of advanced functoids in the chosen category appears.</span></span>  
  
2. <span data-ttu-id="ab651-111">ドラッグ、**テーブル ループ**functoid (![](../core/media/advtablelooping.gif "advtablelooping")) ツールボックスからグリッド ページの適切な場所にします。</span><span class="sxs-lookup"><span data-stu-id="ab651-111">Drag the **Table Looping** functoid (![](../core/media/advtablelooping.gif "advtablelooping")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ab651-112">Functoid は表示されているグリッド ページに配置されます。</span><span class="sxs-lookup"><span data-stu-id="ab651-112">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="ab651-113">別のグリッド ページに functoid を配置する場合は、最初にそのグリッド ページを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab651-113">If you want to put the functoid onto a different grid page, you need to display that grid page first.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ab651-114">の出力、**テーブル ループ**functoid が 1 つ以上関連付けられている入力として機能**テーブル抽出**functoid の右側に余裕を確認、**テーブル ループ** functoid、**テーブル抽出**functoid。</span><span class="sxs-lookup"><span data-stu-id="ab651-114">Because the output of the **Table Looping** functoid serves as input to one or more associated **Table Extractor** functoids, make sure you leave room to the right of the **Table Looping** functoid for the **Table Extractor** functoids.</span></span>  
  
3. <span data-ttu-id="ab651-115">新しく追加した送信元スキーマからレコードまたはフィールドをドラッグして**テーブル ループ**functoid。</span><span class="sxs-lookup"><span data-stu-id="ab651-115">Drag a record or field from the source schema to the newly added **Table Looping** functoid.</span></span> <span data-ttu-id="ab651-116">最初の入力パラメーターとして、**テーブル ループ**functoid、レコードまたはインスタンス メッセージ内のフィールドの出現回数にこの functoid には、出力が生成されます。 回数を制御します。</span><span class="sxs-lookup"><span data-stu-id="ab651-116">As the first input parameter to the **Table Looping** functoid, the number of occurrences of this record or field in an instance message will control the number of times this functoid produces output.</span></span> <span data-ttu-id="ab651-117">たとえば、ループ レコードは、functoid にドラッグし、このレコードの 10 件のあるインスタンス メッセージを処理し、テーブル グリッドが 1 つの列のデータ ソースの行で構成されて、**テーブル ループ**functoid に処理され、10 回がによって抽出の 10 個の出力行を生成、**テーブル抽出**簡単に構築されている functoid と許可 10 の変換先を記録します。</span><span class="sxs-lookup"><span data-stu-id="ab651-117">For example, if a looping record is dragged to the functoid, and an instance message that has 10 occurrences of this record is processed, and the table grid has been configured with one row of sources of column data, the **Table Looping** functoid will iterate 10 times, producing 10 output rows for extraction by a **Table Extractor** functoid, and allowing 10 destination records to be easily constructed.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ab651-118">このような各の行の各反復処理の出力になります、テーブル グリッドで複数の行を構成する場合、**テーブル ループ**functoid。</span><span class="sxs-lookup"><span data-stu-id="ab651-118">If you configure multiple rows in the table grid, each such row will be output for each iteration of the **Table Looping** functoid.</span></span> <span data-ttu-id="ab651-119">そのため、テーブル グリッドで構成されている行の数の数を生成する、入力レコード回の出現回数は、データ抽出に使用可能なテーブルの行を出力します。</span><span class="sxs-lookup"><span data-stu-id="ab651-119">So, the number of occurrences of an input record times the number of rows configured in the table grid yields the number of output table rows available for data extraction.</span></span>  
  
4. <span data-ttu-id="ab651-120">変換先スキーマのレコードまたはフィールドをドラッグして、**テーブル ループ**functoid。</span><span class="sxs-lookup"><span data-stu-id="ab651-120">Drag a record or field from the destination schema to the **Table Looping** functoid.</span></span> <span data-ttu-id="ab651-121">このリンクにより、送信先スキーマのノードを作成します。</span><span class="sxs-lookup"><span data-stu-id="ab651-121">This link ensures the creation of the node in the destination schema.</span></span>  
  
5. <span data-ttu-id="ab651-122">新しく追加された選択**テーブル ループ**functoid、し、**プロパティ**ウィンドウで、省略記号をクリックします (**...**) ボタンに関連付けられているその**入力パラメーター**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="ab651-122">Select the newly added **Table Looping** functoid, and in the **Properties** window, click the ellipsis (**...**) button associated with its **Input Parameters** property.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ab651-123">または、functoid を選択して、CTRL + M, CTRL + T、キーボードからキーを押します。</span><span class="sxs-lookup"><span data-stu-id="ab651-123">Alternatively, you can select the functoid and then press CTRL+M, CTRL+T from the keyboard.</span></span> <span data-ttu-id="ab651-124">一連のマッパーのキーボード ショートカットを参照してください[BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)します。</span><span class="sxs-lookup"><span data-stu-id="ab651-124">For a list of Mapper keyboard shortcuts see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
6. <span data-ttu-id="ab651-125">**テーブル ループ Functoid の構成**ダイアログ ボックスで、をクリックして、 ![functoid への定数入力パラメーターの追加](../core/media/add-input-parameters.gif "Add_input_parameters")クリックを 2 つ目の作成入力パラメーター。</span><span class="sxs-lookup"><span data-stu-id="ab651-125">In the **Configure Table Looping Functoid** dialog box, click the ![Adding constant input parameters to a functoid](../core/media/add-input-parameters.gif "Add_input_parameters") button to create the second input parameter.</span></span> <span data-ttu-id="ab651-126">これを作成するテーブルで使用可能な列の数を表す数値を入力**テーブル ループ**functoid。</span><span class="sxs-lookup"><span data-stu-id="ab651-126">Type a number that represents the number of columns that will be available in the table you are creating for this **Table Looping** functoid.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ab651-127">テーブル内の列の最大数は、228 です。</span><span class="sxs-lookup"><span data-stu-id="ab651-127">The maximum number of columns in the table is 228.</span></span>  
  
7. <span data-ttu-id="ab651-128">**テーブル ループ Functoid の構成**ダイアログ ボックスで、をクリックして、 ![functoid への定数入力パラメーターの追加](../core/media/add-input-parameters.gif "Add_input_parameters")ボタンを押して任意の定数構成されたテーブル グリッドに表示される値。</span><span class="sxs-lookup"><span data-stu-id="ab651-128">In the **Configure Table Looping Functoid** dialog box, click the ![Adding constant input parameters to a functoid](../core/media/add-input-parameters.gif "Add_input_parameters") button to enter any constant values that appears in your configured table grid.</span></span> <span data-ttu-id="ab651-129">これらの定数を作成する順序は、入力パラメーター リストの先頭の位置をそれぞれ保持番目と 2 番目のパラメーターの値、行と列の数と、このダイアログ ボックスで重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="ab651-129">The order in which you create these constants is not important in this dialog box as long as the first and second parameter values, the number of rows and columns, respectively, retain their positions at the beginning of the input parameter list.</span></span> <span data-ttu-id="ab651-130">完了したら、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="ab651-130">When complete, click **OK**.</span></span>  
  
    <span data-ttu-id="ab651-131">**テーブル ループ Functoid の構成** ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ab651-131">The **Configure Table Looping Functoid** dialog box closes.</span></span>  
  
8. <span data-ttu-id="ab651-132">0 個以上のレコードまたはフィールド ノードをドラッグして、送信元スキーマから、**テーブル ループ**functoid は最近追加しています。</span><span class="sxs-lookup"><span data-stu-id="ab651-132">Drag zero or more record or field nodes from the source schema to the **Table Looping** functoid that you recently added.</span></span> <span data-ttu-id="ab651-133">これらのレコードおよびフィールド ノードの各入力パラメーター リストの末尾に追加できしたがってはテーブル グリッドが、後の手順で構成されている場合。</span><span class="sxs-lookup"><span data-stu-id="ab651-133">Each of these record and field nodes is added to the end of the input parameter list, and therefore will be available when the table grid is configured in a latter step.</span></span> <span data-ttu-id="ab651-134">テーブル データ定数前に追加 (行と列数は定数されません) のようには、これらのレコードおよびフィールド ノードを追加する順序は最終的に関連するではありません。</span><span class="sxs-lookup"><span data-stu-id="ab651-134">Like the table data constants added earlier (not the row and column count constants), the order in which these record and field nodes are added is not ultimately relevant.</span></span>  
  
9. <span data-ttu-id="ab651-135">リンクのラベル付け、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ab651-135">To label a link, follow these steps:</span></span>  
  
   - <span data-ttu-id="ab651-136">表示されているグリッド ページで、リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="ab651-136">Select a link in the displayed grid page.</span></span>  
  
   - <span data-ttu-id="ab651-137">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウのわかりやすい名前を指定、**ラベル**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="ab651-137">In the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, provide a descriptive name for the **Label** property.</span></span> <span data-ttu-id="ab651-138">たとえば、"Second Author"という名前のフィールドからのリンクを"link2ndAuthor"のような名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="ab651-138">For example, you might give a name like "link2ndAuthor" to a link coming from a field called "Second Author".</span></span>  
  
10. <span data-ttu-id="ab651-139">新しく追加された選択**テーブル ループ**functoid、し、**プロパティ**ウィンドウで、省略記号をクリックします (**...**) ボタンに関連付けられている、**テーブル ループ グリッド**functoid に関連付けられているプロパティ。</span><span class="sxs-lookup"><span data-stu-id="ab651-139">Select the newly added **Table Looping** functoid, and in the **Properties** window, click the ellipsis (**...**) button associated with the **Table Looping Grid** property associated with that functoid.</span></span>  
  
     <span data-ttu-id="ab651-140">**テーブル ループ Functoid の構成** ダイアログ ボックスが表示されます、**テーブル ループ グリッド**タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="ab651-140">The **Configure Table Looping Functoid** dialog box appears with the **Table Looping Grid** tab selected.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ab651-141">または、functoid を右クリックし をクリックし、**テーブル ループ グリッドの構成**のコンテキスト メニュー。</span><span class="sxs-lookup"><span data-stu-id="ab651-141">Alternatively, you can right-click the functoid, and then click **Configure Table Looping Grid** in the context menu.</span></span> <span data-ttu-id="ab651-142">**テーブル ループ Functoid の構成** ダイアログ ボックスが表示されます、**テーブル ループ グリッド**タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="ab651-142">The **Configure Table Looping Functoid** dialog box appears with the **Table Looping Grid** tab selected.</span></span>  
  
11. <span data-ttu-id="ab651-143">グリッドで、少なくとも 1 つと可能性があります複数、行を構成するのにには、各テーブル セルに関連付けられているドロップダウン リストを使用します。</span><span class="sxs-lookup"><span data-stu-id="ab651-143">Use the drop-down lists associated with each table cell to configure at least one, and possibly multiple, rows in the grid.</span></span> <span data-ttu-id="ab651-144">ドロップダウン リストで使用できる選択肢は、定数と 3 の入力パラメーターとして、最大 6 ~ 8 の手順で構成したリンク、**テーブル ループ**functoid。</span><span class="sxs-lookup"><span data-stu-id="ab651-144">The choices available in the drop-down lists are the constants and links that you have configured in steps 6-8 as input parameters 3 and up to the **Table Looping** functoid.</span></span> <span data-ttu-id="ab651-145">(1 と 2 の入力パラメーターは表示されませんでこれらのドロップダウン リストです。)完了したら、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="ab651-145">(Input parameters 1 and 2 do not appear in these drop-down lists.) When complete, click **OK**.</span></span>  
  
     <span data-ttu-id="ab651-146">**テーブル ループ Functoid の構成** ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ab651-146">The **Configure Table Looping Functoid** dialog box closes.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ab651-147">各行の最初の入力パラメーターとして指定されたフィールドまたはレコードの出現回数と組み合わせて、出力構造体の 1 つのイテレーションの構成、**テーブル ループ**functoid。</span><span class="sxs-lookup"><span data-stu-id="ab651-147">Each row constitutes one iteration of the output structure, in combination with the number of occurrences of the record or field specified as the first input parameter of the **Table Looping** functoid.</span></span> <span data-ttu-id="ab651-148">詳細については、手順 3 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab651-148">For more information, see step 3.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ab651-149">使用してアクセスする各列の値を選択する必要があります、**テーブル抽出**functoid。</span><span class="sxs-lookup"><span data-stu-id="ab651-149">You must select a value for each column you intend to access using a **Table Extractor** functoid.</span></span> <span data-ttu-id="ab651-150">列が使用されていない場合、**テーブル抽出**functoid は、その列を維持するのではなく、削除を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab651-150">If a column is not used by a **Table Extractor** functoid, you should consider removing, rather than maintaining, that column.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ab651-151">テーブル グリッドを入力する順序は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="ab651-151">The order of filling out the table grid is not important.</span></span>  
  
12. <span data-ttu-id="ab651-152">多くのドラッグ**テーブル抽出**functoid (![](../core/media/advtableextractor.gif "advtableextractor")) に応じて、表示されているグリッド ページにツールボックスから。</span><span class="sxs-lookup"><span data-stu-id="ab651-152">Drag as many **Table Extractor** functoids (![](../core/media/advtableextractor.gif "advtableextractor")) from the Toolbox to the displayed grid page as needed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ab651-153">ため、これらの入力**テーブル抽出**から functoid には、**テーブル ループ**前の手順で追加の functoid に配置することを確認、**テーブル抽出**functoid の右側に、**テーブル ループ**表示されているグリッド ページで functoid。</span><span class="sxs-lookup"><span data-stu-id="ab651-153">Because the input of these **Table Extractor** functoids comes from the **Table Looping** functoid added in a previous step, make sure that you place the **Table Extractor** functoids to the right of the **Table Looping** functoid in the displayed grid page.</span></span>  
  
13. <span data-ttu-id="ab651-154">いずれかの最初の入力パラメーターを作成する、**テーブル抽出**、手順 9. で追加の functoid が関連のあるドラッグ**テーブル ループ**functoid の左側にします。</span><span class="sxs-lookup"><span data-stu-id="ab651-154">To create the first input parameter for one of the **Table Extractor** functoids added in step 9, drag it to the relevant **Table Looping** functoid to its left.</span></span>  
  
14. <span data-ttu-id="ab651-155">同じ 2 つ目の入力パラメーターを作成する**テーブル抽出**functoid、functoid を選択し、[、**プロパティ**ウィンドウで、省略記号をクリックします (**...]**) ボタンに関連付けられているその**入力パラメーター**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="ab651-155">To create the second input parameter for the same **Table Extractor** functoid, select the functoid, and in the **Properties** window, click the ellipsis (**...**) button associated with its **Input parameters** property.</span></span>  
  
     <span data-ttu-id="ab651-156">**テーブル抽出 Functoid の構成** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab651-156">The **Configure Table Extractor Functoid** dialog box appears.</span></span>  
  
15. <span data-ttu-id="ab651-157">をクリックして、 ![functoid への定数入力パラメーターの追加](../core/media/add-input-parameters.gif "Add_input_parameters") 2 番目の入力パラメーターを作成するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab651-157">Click the ![Adding constant input parameters to a functoid](../core/media/add-input-parameters.gif "Add_input_parameters") button to create the second input parameter.</span></span> <span data-ttu-id="ab651-158">テーブル グリッドの対応する列の番号を入力**テーブル ループ**functoid のデータを抽出します。</span><span class="sxs-lookup"><span data-stu-id="ab651-158">Type the number of the column in the table grid of the corresponding **Table Looping** functoid from which you want to extract data.</span></span> <span data-ttu-id="ab651-159">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab651-159">Click **OK**.</span></span>  
  
     <span data-ttu-id="ab651-160">**テーブル抽出 Functoid の構成** ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ab651-160">The **Configure Table Extractor Functoid** dialog box closes.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ab651-161">列番号は、1 から始まります。</span><span class="sxs-lookup"><span data-stu-id="ab651-161">Column numbers start at 1.</span></span>  
  
16. <span data-ttu-id="ab651-162">出力を使用する、**テーブル抽出**functoid をドラッグ、**テーブル抽出**functoid を送信先スキーマまたは送信先スキーマのレコードまたはフィールド ノードをドラッグすると、レコードまたはフィールドノード**テーブル抽出**functoid。</span><span class="sxs-lookup"><span data-stu-id="ab651-162">To use the output of the **Table Extractor** functoid, drag the **Table Extractor**  functoid to a record or field node in the destination schema, or drag a record or field node in the destination schema to the **Table Extractor** functoid.</span></span> <span data-ttu-id="ab651-163">この送信先スキーマのレコードまたはフィールド ノードに対応する送信先インスタンス メッセージに要素または属性の値が設定されます (定数) の場合からの値または値によって示される (リンクの場合) をで指定されたセルテーブル グリッドです。</span><span class="sxs-lookup"><span data-stu-id="ab651-163">The element or attribute value in a destination instance message corresponding to this record or field node in the destination schema will be populated with the value from (in the case of constants), or the value indicated by (in the case of links), the specified cell in the table grid.</span></span>  
  
17. <span data-ttu-id="ab651-164">各について、手順 12、13、14、15、**テーブル抽出**functoid 手順 11 で追加します。</span><span class="sxs-lookup"><span data-stu-id="ab651-164">Repeat steps 12, 13, 14, and 15 for each of the **Table Extractor** functoids added in step 11.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab651-165">参照</span><span class="sxs-lookup"><span data-stu-id="ab651-165">See Also</span></span>  
 [<span data-ttu-id="ab651-166">マップへの高度な Functoid の追加</span><span class="sxs-lookup"><span data-stu-id="ab651-166">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)
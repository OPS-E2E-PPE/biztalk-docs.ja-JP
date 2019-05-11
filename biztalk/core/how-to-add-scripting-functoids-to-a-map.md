---
title: マップにスクリプト Functoid を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.functiod.script
ms.assetid: eb96814a-b3fb-48f6-a947-ab595a270faa
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08febb4b004dac8fa6d963ce3843e9e2275467c0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387255"
---
# <a name="how-to-add-scripting-functoids-to-a-map"></a><span data-ttu-id="5b7c6-102">マップにスクリプト Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="5b7c6-102">How to Add Scripting Functoids to a Map</span></span>
<span data-ttu-id="5b7c6-103">**Scripting** functoid では、実行時に使用できない機能を実行するカスタム スクリプトまたはコードを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-103">The **Scripting** functoid enables you to use custom script or code at run time to perform functions otherwise not available.</span></span> <span data-ttu-id="5b7c6-104">使用しての実行時に COM オブジェクトを呼び出す場合など、 **Scripting** functoid と、独自のカスタム スクリプトを記述します。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-104">For example, you can call a COM object at run time by using the **Scripting** functoid and writing your own custom script.</span></span>  
  
 <span data-ttu-id="5b7c6-105">概念情報については、 **Scripting** functoid を参照してください[スクリプト Functoid の](../core/scripting-functoid.md)します。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-105">For conceptual information about the **Scripting** functoid, see [Scripting Functoid](../core/scripting-functoid.md).</span></span>  
  
### <a name="to-add-the-scripting-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="5b7c6-106">スクリプト functoid をマップに追加し、構成するには</span><span class="sxs-lookup"><span data-stu-id="5b7c6-106">To add the Scripting functoid to a map and configure it</span></span>  
  
1. <span data-ttu-id="5b7c6-107">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブ。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-107">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
    <span data-ttu-id="5b7c6-108">選択したカテゴリでの高度な functoid の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-108">The list of advanced functoids in the chosen category appears.</span></span>  
  
2. <span data-ttu-id="5b7c6-109">ドラッグ、 **Scripting** functoid ![](../core/media/bts-tls-scripting.gif "bts_tls_scripting")ツールボックスからグリッド ページの適切な場所にします。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-109">Drag the **Scripting** functoid ![](../core/media/bts-tls-scripting.gif "bts_tls_scripting") from the Toolbox to the appropriate location on a grid page.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5b7c6-110">Functoid は表示されているグリッド ページに配置されます。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-110">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="5b7c6-111">別のグリッド ページに functoid を配置する場合は、最初にその他のグリッド ページを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-111">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5b7c6-112">まとめて 1 つ以上の functoid を使用してマップを構築する場合は、左から右の相対的な配置を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-112">If you are constructing a map using more than one functoid together, you need to consider their relative left-to-right placement.</span></span> <span data-ttu-id="5b7c6-113">Functoids は左から順に実行されます。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-113">Functoids are executed from left to right.</span></span> <span data-ttu-id="5b7c6-114">1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-114">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3. <span data-ttu-id="5b7c6-115">選択、 **Scripting** functoid は、表示されているグリッド ページに追加したとしています。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-115">Select the **Scripting** functoid that you just added to the displayed grid page.</span></span>  
  
4. <span data-ttu-id="5b7c6-116">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウで、省略記号ボタンをクリックします (**.**) ボタンに関連付けられている、**スクリプト**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-116">In the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, click the ellipsis (**...**) button associated with the **Script** property.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5b7c6-117">または、functoid を右クリックし をクリックし、 **Functoid スクリプトの構成**のコンテキスト メニュー。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-117">Alternatively, you can right-click the functoid, and then click **Configure Functoid Script** in the context menu.</span></span> <span data-ttu-id="5b7c6-118">**スクリプト Functoid の構成** ダイアログ ボックスが表示されます、**スクリプト Functoid の構成**タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-118">The **Configure Scripting Functoid** dialog box appears with the **Script Functoid Configuration** tab selected.</span></span>  
  
5. <span data-ttu-id="5b7c6-119">**スクリプト Functoid の構成** ダイアログ ボックスで、**スクリプトの種類を選択します。** ドロップダウン ボックスの一覧で、スクリプトの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-119">In the **Configure Scripting Functoid** dialog box, in the **Select script type** drop-down list, select the type of your script.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5b7c6-120">スクリプトの種類の選択内容に応じて残りのダイアログ ボックスのフィールドのさまざまなサブセットを有効または無効にするされます。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-120">Depending on your selection of script type, different subsets of the remaining dialog box fields will be enabled and disabled.</span></span>  
  
6. <span data-ttu-id="5b7c6-121">選択した場合**外部アセンブリ**スクリプトの種類を使用して、**アセンブリをスクリプト**、**スクリプト クラス**、および**スクリプト メソッド**ドロップダウン関連付けるアセンブリ、クラス、およびメソッドをそれぞれ選択する、その順序でリスト、 **Scripting** functoid。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-121">If you selected **External Assembly** as the script type, use the **Script assembly**, **Script class**, and **Script method** drop-down lists, in that order, to select the assembly, class, and method, respectively, to associate with this **Scripting** functoid.</span></span>  
  
   > [!WARNING]
   >  <span data-ttu-id="5b7c6-122">外部アセンブリ内のコードは、スレッド セーフである必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-122">The code in the external assembly must be thread-safe.</span></span> <span data-ttu-id="5b7c6-123">ストレス条件下で、マップの複数のインスタンスを同時に実行される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-123">Under stress conditions, multiple instances of a map may be running concurrently.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5b7c6-124">アセンブリでは、選択した後、**スクリプト クラス**ドロップダウン リストにそのアセンブリのクラスで設定されます。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-124">After you have selected an assembly, the **Script class** drop-down list will be populated with the classes in that assembly.</span></span> <span data-ttu-id="5b7c6-125">同様に、選択した後、クラス、**スクリプト メソッド**ドロップダウン リストにそのクラスのメソッドで設定されます。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-125">Likewise, after you have selected a class, the **Script method** drop-down list will be populated with the methods in that class.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5b7c6-126">**インライン スクリプト**を選択すると、テキスト ボックスが無効になっている**外部アセンブリ**スクリプトの種類。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-126">The **Inline script** text box is disabled when you select **External Assembly** as the script type.</span></span>  
  
    <span data-ttu-id="5b7c6-127">以外の何かを選択した場合**外部アセンブリ**スクリプトの種類 (インラインの選択肢の 1 つ) を使用して、**インライン スクリプト**テキスト ボックスに、選択した言語でスクリプトを入力します。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-127">If you selected something other than **External Assembly** as the script type (one of the inline choices), use the **Inline script** text box to enter your script in the language you selected.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5b7c6-128">インライン言語の選択、 **Scripting** functoid には、c# .NET、JScript.NET、Visual Basic .NET、XSLT、および XSLT 呼び出しテンプレートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-128">The inline language choices for the **Scripting** functoid include C# .NET, JScript.NET, Visual Basic .NET, XSLT, and XSLT Call Template.</span></span>  
  
    <span data-ttu-id="5b7c6-129">C# を使用するスクリプトは、"using"ステートメントは許可されません。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-129">Scripting using C# does not allow "using" statements.</span></span> <span data-ttu-id="5b7c6-130">スクリプトは、特殊な .Net クラスを使用する必要がある場合、対応するアセンブリとその依存アセンブリに追加する「参照」に、BizTalk プロジェクトと、スクリプト コードは、完全修飾名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-130">If the script needs to use any special .Net classes, then the corresponding assemblies and their dependent assemblies should be added to "References" in the BizTalk project, and the script code should use fully qualified names.</span></span> <span data-ttu-id="5b7c6-131">カルチャに応じた小文字変換を実行するスクリプトを記述する場合は次に示すよう、対応するコード フラグメントが書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-131">If you write a script to perform culture-sensitive lowercase conversion, the corresponding code fragment should be written as below.</span></span> <span data-ttu-id="5b7c6-132">サポートされているすべてのスクリプト言語に同様の制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-132">Similar limitations apply to all supported scripting languages.</span></span>  
  
   ```  
   string x = y.ToLower(System.Globalization.CultureInfo.CurrentCulture);  
   ```  
  
    <span data-ttu-id="5b7c6-133">スクリプトでは、任意のアセンブリからクラスを使用する、マップを含む BizTalk プロジェクトで、対応するアセンブリとその依存アセンブリを「参照」を追加することを確認します。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-133">In the script, to use classes from any assembly, ensure you add the corresponding assembly and its dependent assemblies to “References” in the BizTalk project containing your map.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5b7c6-134">直接カスタム スクリプトを作成できますが、**インライン スクリプト**またはテキスト ボックスに、できる他の場所でスクリプトを作成およびに貼り付けます、**インライン スクリプト**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-134">You can create your custom script directly in the **Inline script** text box, or you can create your script elsewhere, and paste it into the **Inline script** text box.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5b7c6-135">**アセンブリをスクリプト**、**スクリプト クラス**、および**スクリプト メソッド**インライン オプションのいずれかを選択すると、ドロップダウン リストが無効になります (以外は何か**外部アセンブリ**) スクリプトの種類。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-135">The **Script assembly**, **Script class**, and **Script method** drop-down lists are disabled when you select one of the inline choices (something other than **External Assembly**) as the script type.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="5b7c6-136">最初の関数は、メインまたはプライマリ関数として扱われます場合、複数の関数を含むスクリプトを作成します。主な機能の実行時に呼び出される場合、その他の関数がのみ呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-136">If you create a script containing multiple functions, the first function will be treated as the main or primary function; other functions are only called if they are called in the execution of the primary function.</span></span>  
  
    <span data-ttu-id="5b7c6-137">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-137">Click **OK**.</span></span>  
  
7. <span data-ttu-id="5b7c6-138">スクリプトまたは外部アセンブリに関連付けられているメソッドは、入力パラメーターを必要とする場合は、適切な数と種類の入力リンクを基本 functoid の場合と同様作成します。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-138">If your script or the associated method in an external assembly requires input parameters, create the appropriate number and type of input links as you would for a basic functoid.</span></span>  
  
8. <span data-ttu-id="5b7c6-139">ほとんどの状況で、 **Scripting** functoid は、送信先スキーマのフィールドを設定するために使用する出力値を生成または別の functoid に入力として多くの同じ基本的な functoid の方法の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5b7c6-139">In most circumstances, your **Scripting** functoid will produce an output value used to populate a field in the destination schema, or as input to another functoid, in much the same way that basic functoids do.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b7c6-140">参照</span><span class="sxs-lookup"><span data-stu-id="5b7c6-140">See Also</span></span>  
 [<span data-ttu-id="5b7c6-141">マップへの高度な Functoid の追加</span><span class="sxs-lookup"><span data-stu-id="5b7c6-141">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)
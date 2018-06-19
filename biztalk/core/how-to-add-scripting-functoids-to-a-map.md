---
title: スクリプト Functoid をマップに追加する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: e66e6ed25fd44b1e89fe5500346a7ad01d5d7ff0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248474"
---
# <a name="how-to-add-scripting-functoids-to-a-map"></a><span data-ttu-id="d8524-102">マップにスクリプト Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="d8524-102">How to Add Scripting Functoids to a Map</span></span>
<span data-ttu-id="d8524-103">**スクリプト**functoid では、実行時に使用できない機能を実行するカスタム スクリプトまたはコードを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="d8524-103">The **Scripting** functoid enables you to use custom script or code at run time to perform functions otherwise not available.</span></span> <span data-ttu-id="d8524-104">使用しての実行時に COM オブジェクトを呼び出すなど、**スクリプト**functoid し、独自のカスタム スクリプトを記述します。</span><span class="sxs-lookup"><span data-stu-id="d8524-104">For example, you can call a COM object at run time by using the **Scripting** functoid and writing your own custom script.</span></span>  
  
 <span data-ttu-id="d8524-105">概要については、**スクリプト**functoid を参照してください[スクリプト Functoid の](../core/scripting-functoid.md)します。</span><span class="sxs-lookup"><span data-stu-id="d8524-105">For conceptual information about the **Scripting** functoid, see [Scripting Functoid](../core/scripting-functoid.md).</span></span>  
  
### <a name="to-add-the-scripting-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="d8524-106">マップにスクリプト Functoid を追加して構成するには</span><span class="sxs-lookup"><span data-stu-id="d8524-106">To add the Scripting functoid to a map and configure it</span></span>  
  
1.  <span data-ttu-id="d8524-107">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブです。</span><span class="sxs-lookup"><span data-stu-id="d8524-107">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
     <span data-ttu-id="d8524-108">選択したカテゴリに含まれる高度な Functoid の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8524-108">The list of advanced functoids in the chosen category appears.</span></span>  
  
2.  <span data-ttu-id="d8524-109">ドラッグ、**スクリプト**functoid![](../core/media/bts-tls-scripting.gif "bts_tls_scripting")グリッド ページの適切な場所にツールボックスからです。</span><span class="sxs-lookup"><span data-stu-id="d8524-109">Drag the **Scripting** functoid ![](../core/media/bts-tls-scripting.gif "bts_tls_scripting") from the Toolbox to the appropriate location on a grid page.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d8524-110">Functoid は表示されているグリッド ページに配置されます。</span><span class="sxs-lookup"><span data-stu-id="d8524-110">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="d8524-111">別のグリッド ページに functoid を配置する場合は、その他のグリッド ページを最初に表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8524-111">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d8524-112">一緒に複数の functoid を使用してマップを構築する場合は、相対左から右への配置を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8524-112">If you are constructing a map using more than one functoid together, you need to consider their relative left-to-right placement.</span></span> <span data-ttu-id="d8524-113">Functoids は左から順に実行されます。</span><span class="sxs-lookup"><span data-stu-id="d8524-113">Functoids are executed from left to right.</span></span> <span data-ttu-id="d8524-114">1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。</span><span class="sxs-lookup"><span data-stu-id="d8524-114">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3.  <span data-ttu-id="d8524-115">選択、**スクリプト**表示されているグリッド ページに追加した functoid です。</span><span class="sxs-lookup"><span data-stu-id="d8524-115">Select the **Scripting** functoid that you just added to the displayed grid page.</span></span>  
  
4.  <span data-ttu-id="d8524-116">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウで、省略記号ボタン (**.**) に関連付けられたボタン、**スクリプト**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="d8524-116">In the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, click the ellipsis (**...**) button associated with the **Script** property.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d8524-117">または、functoid を右クリックし、をクリックして**Functoid スクリプトの**コンテキスト メニュー。</span><span class="sxs-lookup"><span data-stu-id="d8524-117">Alternatively, you can right-click the functoid, and then click **Configure Functoid Script** in the context menu.</span></span> <span data-ttu-id="d8524-118">**スクリプト Functoid の構成** ダイアログ ボックスが表示されます、**スクリプト Functoid の構成**タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="d8524-118">The **Configure Scripting Functoid** dialog box appears with the **Script Functoid Configuration** tab selected.</span></span>  
  
5.  <span data-ttu-id="d8524-119">**スクリプト Functoid の構成** ダイアログ ボックスで、**スクリプトの種類を選択して**ドロップダウン ボックスの一覧で、スクリプトの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8524-119">In the **Configure Scripting Functoid** dialog box, in the **Select script type** drop-down list, select the type of your script.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d8524-120">選択されるスクリプトの種類に応じて、残りのダイアログ ボックス フィールドのさまざまなサブセットが有効および無効になります。</span><span class="sxs-lookup"><span data-stu-id="d8524-120">Depending on your selection of script type, different subsets of the remaining dialog box fields will be enabled and disabled.</span></span>  
  
6.  <span data-ttu-id="d8524-121">選択した場合は**外部アセンブリ**スクリプトの種類を使用して、**スクリプト アセンブリ**、**スクリプト クラス**、および**スクリプト メソッド**ドロップダウンこれに関連付ける、それぞれアセンブリ、クラス、およびメソッドを選択する、その順序でリスト**スクリプト**functoid です。</span><span class="sxs-lookup"><span data-stu-id="d8524-121">If you selected **External Assembly** as the script type, use the **Script assembly**, **Script class**, and **Script method** drop-down lists, in that order, to select the assembly, class, and method, respectively, to associate with this **Scripting** functoid.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="d8524-122">外部アセンブリのコードは、スレッド セーフであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="d8524-122">The code in the external assembly must be thread-safe.</span></span> <span data-ttu-id="d8524-123">ストレス条件下では、マップの複数のインスタンスが同時に実行される場合があります。</span><span class="sxs-lookup"><span data-stu-id="d8524-123">Under stress conditions, multiple instances of a map may be running concurrently.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d8524-124">アセンブリを選択した後、**スクリプト クラス**ドロップダウン リストにそのアセンブリのクラスと設定されます。</span><span class="sxs-lookup"><span data-stu-id="d8524-124">After you have selected an assembly, the **Script class** drop-down list will be populated with the classes in that assembly.</span></span> <span data-ttu-id="d8524-125">同様に、選択した後、クラス、**スクリプト メソッド**ドロップダウン リストにそのクラスのメソッドで設定されます。</span><span class="sxs-lookup"><span data-stu-id="d8524-125">Likewise, after you have selected a class, the **Script method** drop-down list will be populated with the methods in that class.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d8524-126">**インライン スクリプト**を選択すると、テキスト ボックスが無効になっている**外部アセンブリ**スクリプトの種類。</span><span class="sxs-lookup"><span data-stu-id="d8524-126">The **Inline script** text box is disabled when you select **External Assembly** as the script type.</span></span>  
  
     <span data-ttu-id="d8524-127">以外の何かを選択した場合**外部アセンブリ**(インラインの選択肢の 1 つ) スクリプトの種類を使用して、**インライン スクリプト**選択した言語で、スクリプトを入力するテキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="d8524-127">If you selected something other than **External Assembly** as the script type (one of the inline choices), use the **Inline script** text box to enter your script in the language you selected.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d8524-128">インライン言語の選択、**スクリプト**functoid には、c# .NET、JScript.NET、Visual Basic .NET、XSLT、および XSLT 呼び出しテンプレートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d8524-128">The inline language choices for the **Scripting** functoid include C# .NET, JScript.NET, Visual Basic .NET, XSLT, and XSLT Call Template.</span></span>  
  
     <span data-ttu-id="d8524-129">C# でスクリプトを記述する場合、"using" ステートメントは使用できません。</span><span class="sxs-lookup"><span data-stu-id="d8524-129">Scripting using C# does not allow "using" statements.</span></span> <span data-ttu-id="d8524-130">スクリプトで特殊な .NET クラスを使用する必要がある場合は、対応するアセンブリとその依存アセンブリを BizTalk プロジェクトの "参照" に追加し、スクリプト コードでは完全修飾名を使用してください。</span><span class="sxs-lookup"><span data-stu-id="d8524-130">If the script needs to use any special .Net classes, then the corresponding assemblies and their dependent assemblies should be added to "References" in the BizTalk project, and the script code should use fully qualified names.</span></span> <span data-ttu-id="d8524-131">カルチャに応じた小文字変換を実行するスクリプトを記述する場合は、対応する次のようなコードを記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8524-131">If you write a script to perform culture-sensitive lowercase conversion, the corresponding code fragment should be written as below.</span></span> <span data-ttu-id="d8524-132">同様の制限は、サポートされるすべてのスクリプト言語に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d8524-132">Similar limitations apply to all supported scripting languages.</span></span>  
  
    ```  
    string x = y.ToLower(System.Globalization.CultureInfo.CurrentCulture);  
    ```  
  
     <span data-ttu-id="d8524-133">このスクリプトでは、任意のアセンブリのクラスを使用するために、マップが含まれる BizTalk プロジェクトの "参照" に、対応するアセンブリとその依存アセンブリを追加します。</span><span class="sxs-lookup"><span data-stu-id="d8524-133">In the script, to use classes from any assembly, ensure you add the corresponding assembly and its dependent assemblies to “References” in the BizTalk project containing your map.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d8524-134">直接カスタム スクリプトを作成できますが、**インライン スクリプト**テキスト ボックス、またはすることができます他の場所でスクリプトを作成し、貼り付けます、**インライン スクリプト**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="d8524-134">You can create your custom script directly in the **Inline script** text box, or you can create your script elsewhere, and paste it into the **Inline script** text box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d8524-135">**スクリプト アセンブリ**、**スクリプト クラス**、および**スクリプト メソッド**インライン選択肢の 1 つを選択すると、ドロップダウン リストが無効になります (以外は何か**外部アセンブリ**) スクリプトの種類。</span><span class="sxs-lookup"><span data-stu-id="d8524-135">The **Script assembly**, **Script class**, and **Script method** drop-down lists are disabled when you select one of the inline choices (something other than **External Assembly**) as the script type.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="d8524-136">複数の関数を含むスクリプトを作成すると、最初の関数がメイン関数または主要な関数として扱われます。他の関数は、主要な関数の実行時にのみ呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d8524-136">If you create a script containing multiple functions, the first function will be treated as the main or primary function; other functions are only called if they are called in the execution of the primary function.</span></span>  
  
     <span data-ttu-id="d8524-137">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8524-137">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="d8524-138">スクリプトまたは外部アセンブリの関連付けられているメソッドに入力パラメーターが必要な場合は、基本的な Functoid の処理と同様に、適切な数および種類の入力リンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="d8524-138">If your script or the associated method in an external assembly requires input parameters, create the appropriate number and type of input links as you would for a basic functoid.</span></span>  
  
8.  <span data-ttu-id="d8524-139">ほとんどの状況で、**スクリプト**functoid、送信先スキーマのフィールドの設定に使用する値を出力が生成されますか、別の functoid に入力としてほぼ同じ基本的な functoid 方法です。</span><span class="sxs-lookup"><span data-stu-id="d8524-139">In most circumstances, your **Scripting** functoid will produce an output value used to populate a field in the destination schema, or as input to another functoid, in much the same way that basic functoids do.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8524-140">参照</span><span class="sxs-lookup"><span data-stu-id="d8524-140">See Also</span></span>  
 [<span data-ttu-id="d8524-141">マップへの高度な Functoid の追加</span><span class="sxs-lookup"><span data-stu-id="d8524-141">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)
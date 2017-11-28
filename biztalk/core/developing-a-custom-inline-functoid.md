---
title: "インラインのカスタム Functoid の開発 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4533f09f-b62d-4b09-b7de-44541c6cf053
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a742e6a53b5fb81d92922ff94e7754239f723ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="developing-a-custom-inline-functoid"></a><span data-ttu-id="2d1b3-102">インライン型のカスタム Functoid の開発</span><span class="sxs-lookup"><span data-stu-id="2d1b3-102">Developing a Custom Inline Functoid</span></span>
<span data-ttu-id="2d1b3-103">インライン型のカスタム Functoid は、参照型のカスタム Functoid のように、アセンブリ、クラス、メソッド名などを参照するのではなく、実装コードを直接マップにコピーすることによって機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-103">Custom inline functoids provide functionality by copying implementation code directly into a map and not by referencing an assembly, class, and method name like a custom referenced functoid.</span></span>  
  
## <a name="building-inline-script"></a><span data-ttu-id="2d1b3-104">インライン スクリプトの作成</span><span class="sxs-lookup"><span data-stu-id="2d1b3-104">Building Inline Script</span></span>  
 <span data-ttu-id="2d1b3-105">マップに追加するためのスクリプトは、2 とおりの方法で作成できます。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-105">There are two ways to provide script for inclusion into the map.</span></span> <span data-ttu-id="2d1b3-106">カスタム Functoid のパラメーター数が可変であるかどうかに応じて、次のいずれかの方法を選択してください。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-106">Choose from the following methods, based on whether your custom functoid supports a variable number of parameters:</span></span>  
  
-   <span data-ttu-id="2d1b3-107">オーバーライド**GetInlineScriptBuffer**ときに、カスタム functoid が入力パラメーター数が変数を受け入れるし、設定する、 **HasVariableInputs**プロパティを`true`です。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-107">Override **GetInlineScriptBuffer** when your custom functoid accepts a variable number of input parameters and you have set the **HasVariableInputs** property to `true`.</span></span> <span data-ttu-id="2d1b3-108">たとえば、任意の数の文字列を連結したり、一連の値から最大値を探したりする場合に、この方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-108">For example, use this method if you want to concatenate a variable number of strings or find the largest value in a set of values.</span></span>  
  
-   <span data-ttu-id="2d1b3-109">使用して**SetScriptBuffer**ときに、変数の数の入力パラメーターをサポートする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-109">Use **SetScriptBuffer** when you do not need to support a variable number of input parameters.</span></span> <span data-ttu-id="2d1b3-110">パラメーターをオプションにすることもできますが、パラメーターの総数は固定されます。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-110">You can still use optional parameters, but the total number of parameters is fixed.</span></span>  
  
 <span data-ttu-id="2d1b3-111">この 2 つの方法は、それぞれ実装方法が異なります。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-111">These two methods require different implementations.</span></span>  
  
### <a name="providing-inline-code-with-setscriptbuffer"></a><span data-ttu-id="2d1b3-112">SetScriptBuffer を使ったインライン コードの実装</span><span class="sxs-lookup"><span data-stu-id="2d1b3-112">Providing Inline Code with SetScriptBuffer</span></span>  
 <span data-ttu-id="2d1b3-113">インライン スクリプトを使用するようにカスタム Functoid を構成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-113">To configure your custom functoid to use inline script:</span></span>  
  
1.  <span data-ttu-id="2d1b3-114">呼び出す**AddScriptTypeSupport**で[Microsoft.BizTalk.BaseFunctoids.ScriptType](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.scripttype.aspx)インライン コードを有効にし、サポートされているスクリプトの種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-114">Call **AddScriptTypeSupport** with [Microsoft.BizTalk.BaseFunctoids.ScriptType](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.scripttype.aspx) to enable inline code and set the supported script type.</span></span>  
  
2.  <span data-ttu-id="2d1b3-115">呼び出す**SetScriptBuffer**のカスタム functoid を使用するコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-115">Invoke **SetScriptBuffer** to set the code to use for the custom functoid.</span></span> <span data-ttu-id="2d1b3-116">カスタムの累積 Functoid の場合は、パラメーターに `functionNumber` を指定して、この関数を 3 回呼び出します (累積 Functoid 以外のカスタム Functoid の場合は 1 回)。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-116">You will call this function three times with the `functionNumber` parameter for custom cumulative functoids and once for custom noncumulative functoids.</span></span>  
  
3.  <span data-ttu-id="2d1b3-117">使用して**SetScriptGlobalBuffer**インライン コードを使用する任意のグローバル変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-117">Use **SetScriptGlobalBuffer** to declare any global variables that your inline code uses.</span></span>  
  
4.  <span data-ttu-id="2d1b3-118">使用して**RequiredGlobalHelperFunctions**をカスタムのインライン型の functoid が必要なヘルパー関数を示します。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-118">Use **RequiredGlobalHelperFunctions** to indicate the helper functions that your custom inline functoid requires.</span></span>  
  
 <span data-ttu-id="2d1b3-119">スクリプトは、StringBuilder または定数を使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-119">You can build your script by using StringBuilder or constants.</span></span> <span data-ttu-id="2d1b3-120">スクリプト コードを作成する方法の 1 つとして、参照型のカスタム Functoid を最初に記述し、バグをすべて解決してから、カスタム関数を文字列定数にコピーすることによってインライン化する方法が考えられます。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-120">One approach to writing script code is to write a custom referenced functoid first and, when all bugs are eliminated, convert it to inline by copying your functions into string constants.</span></span>  
  
### <a name="providing-inline-code-with-getinlinescriptbuffer"></a><span data-ttu-id="2d1b3-121">GetInlineScriptBuffer を使ったインライン コードの実装</span><span class="sxs-lookup"><span data-stu-id="2d1b3-121">Providing Inline Code with GetInlineScriptBuffer</span></span>  
 <span data-ttu-id="2d1b3-122">オーバーライドして、カスタムのインライン型の functoid は、可変個のパラメーターをサポートする場合**GetInlineScriptBuffer**です。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-122">If your custom inline functoid supports a variable number of parameters, you will override **GetInlineScriptBuffer**.</span></span> <span data-ttu-id="2d1b3-123">インライン スクリプトを使用するようにカスタム Functoid を構成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-123">To configure your custom functoid to use inline script:</span></span>  
  
1.  <span data-ttu-id="2d1b3-124">カスタム functoid が設定して変数の入力を持つことを宣言、コンス トラクターで**HasVariableInputs**に`true`です。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-124">In the constructor, declare that your custom functoid has variable inputs by setting **HasVariableInputs** to `true`.</span></span>  
  
2.  <span data-ttu-id="2d1b3-125">コンス トラクターを呼び出して**AddScriptTypeSupport**で[Microsoft.BizTalk.BaseFunctoids.ScriptType](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.scripttype.aspx)インライン コードを有効にし、サポートされているスクリプトの種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-125">In the constructor, call **AddScriptTypeSupport** with [Microsoft.BizTalk.BaseFunctoids.ScriptType](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.scripttype.aspx) to enable inline code and set the supported script type.</span></span>  
  
3.  <span data-ttu-id="2d1b3-126">オーバーライド**GetInlineScriptBuffer**を作成して、カスタム functoid のマップで使用するコードを返します。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-126">Override **GetInlineScriptBuffer** to construct and return the code to use in the map for your custom functoid.</span></span> <span data-ttu-id="2d1b3-127">パラメーターの `scriptType` と `numParams` を調べて、適切なコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-127">Use the parameters to build the correct code by checking the `scriptType` and `numParams`.</span></span> <span data-ttu-id="2d1b3-128">最後のパラメーターで`functionNumber`0 にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-128">The final parameter, `functionNumber`, should be 0.</span></span> <span data-ttu-id="2d1b3-129">これは、累積的な関数が入力の数が固定されている、このメカニズムを使用しないためです。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-129">This is because cumulative functions have a fixed number of inputs and do not use this mechanism.</span></span>  
  
4.  <span data-ttu-id="2d1b3-130">使用して**SetScriptGlobalBuffer**インライン コードを使用するグローバル変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-130">Use **SetScriptGlobalBuffer** to declare global variables that your inline code uses.</span></span>  
  
5.  <span data-ttu-id="2d1b3-131">使用して**RequiredGlobalHelperFunctions**をカスタムのインライン型の functoid が必要なヘルパー関数を示します。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-131">Use **RequiredGlobalHelperFunctions** to indicate the helper functions that your custom inline functoid requires.</span></span>  
  
 <span data-ttu-id="2d1b3-132">次のコードは、`numParams` で指定された数のパラメーターを使用する C# の関数を作成します。関数の本体は省略してあります。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-132">The following code fragment builds a C# function with the number of parameters passed in `numParams` but with no function body.</span></span> <span data-ttu-id="2d1b3-133">このコードを実際に利用する場合、コード例をソリューションにコピーし、何らかの処理を行う (受け取ったパラメーターを処理して値を返す) コードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-133">To use this code fragment, copy the example to your solution and add code to do something with the parameters and return a value.</span></span>  
  
```  
// Override GetInlineScriptBuffer  
protected override string GetInlineScriptBuffer(ScriptType scriptType, int numParams, int functionNumber)  
{  
    // Is this one of the supported script types?  
    if(ScriptType.CSharp == scriptType)  
    {  
        // Assume functionNumber == 0  
        StringBuilder builder = new StringBuilder();  
        // Function declaration   
        builder.Append("public string MyFunction("  
        // Declare parameters using numParams  
        for(int i=0; i<numParams; i++)  
        {  
            // Separate params with a comma  
            if(i > 0)  
                builder.Append(", ");  
            // Declare parameters, param0 to paramNUMPARAM  
            builder.Append("string param" + i.ToString());  
        }  
        builder.Append(")\n");  
        // Function body; process params as needed  
        builder.Append("{\n");  
        builder.Append("}\n");  
        // Return script  
        return builder.ToString();  
    }  
    // scriptType is unsupported  
    return string.Empty;  
}  
```  
  
## <a name="testing-an-inline-script"></a><span data-ttu-id="2d1b3-134">インライン スクリプトのテスト</span><span class="sxs-lookup"><span data-stu-id="2d1b3-134">Testing an Inline Script</span></span>  
 <span data-ttu-id="2d1b3-135">開発作業には常にテストが伴います。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-135">Testing is an important consideration in any development effort.</span></span> <span data-ttu-id="2d1b3-136">インライン型のカスタム Functoid をテストするのは簡単ではありません。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-136">Custom inline functoids can be challenging to test.</span></span> <span data-ttu-id="2d1b3-137">このプロセスを簡単に行うには、次のいずれか、または両方の方法を使用してください。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-137">To simplify the process, use one or both of the following techniques:</span></span>  
  
-   <span data-ttu-id="2d1b3-138">インライン型のカスタム Functoid が使用されたマップの XSLT を調査する。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-138">Examine the XSLT of a map that uses the custom inline functoid.</span></span>  
  
-   <span data-ttu-id="2d1b3-139">インライン型のカスタム Functoid が使用されたマップの入力と出力を検証する。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-139">Verify the input and output of a map that uses the custom inline functoid.</span></span>  
  
### <a name="examine-the-xslt-of-a-map-that-uses-the-custom-inline-functoid"></a><span data-ttu-id="2d1b3-140">インライン型のカスタム Functoid が使用されたマップの XSLT を調査するには</span><span class="sxs-lookup"><span data-stu-id="2d1b3-140">Examine the XSLT of a Map That Uses the Custom Inline Functoid</span></span>  
 <span data-ttu-id="2d1b3-141">この方法を使用すると、ロジックに関する問題や、構文に関する間違いを検出できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-141">This technique often reveals problems with logic or subtle syntax issues.</span></span> <span data-ttu-id="2d1b3-142">また、マップでどのようなことが行われているのかを把握する場合にも利用できます。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-142">It also helps you to understand what happens in the map.</span></span>  
  
 <span data-ttu-id="2d1b3-143">マップの XSLT を表示するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-143">To view the XSLT for a map:</span></span>  
  
1.  <span data-ttu-id="2d1b3-144">Visual Studio の BizTalk プロジェクトからをクリックして、**ソリューション エクスプ ローラー**  タブで、インラインのカスタム functoid を使用するマップを右クリックし、をクリックして**マップの検証**です。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-144">From a Visual Studio BizTalk project, click the **Solution Explorer** tab, right-click a map that uses your custom inline functoid, and then click **Validate Map**.</span></span>  
  
2.  <span data-ttu-id="2d1b3-145">[出力] ウィンドウをスクロールして、XSLT ファイルの URL を探します。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-145">Scroll the Output window to find the URL for the XSLT file.</span></span> <span data-ttu-id="2d1b3-146">Ctrl キーを押し、URL をクリックすると、ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-146">Press CTRL and click the URL to view the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2d1b3-147">ただし、XSLT ファイルに変更を加えても、カスタム Functoid には一切反映されません。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-147">Remember that any changes made to the XSLT file will not be reflected in your custom functoid.</span></span>  
  
### <a name="test-a-map-that-uses-the-custom-inline-functoid"></a><span data-ttu-id="2d1b3-148">インライン型のカスタム Functoid が使用されたマップをテストするには</span><span class="sxs-lookup"><span data-stu-id="2d1b3-148">Test a Map That Uses the Custom Inline Functoid</span></span>  
 <span data-ttu-id="2d1b3-149">これは、マップとカスタムのインライン型の functoid が正しく機能するかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-149">This tests whether the map and custom inline functoid work as expected.</span></span>  
  
 <span data-ttu-id="2d1b3-150">マップをテストするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-150">To test a map:</span></span>  
  
1.  <span data-ttu-id="2d1b3-151">Visual Studio の BizTalk プロジェクトからをクリックして、**ソリューション エクスプ ローラー**  タブで、インラインのカスタム functoid を使用するマップを右クリックし、をクリックして**マップのテスト**です。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-151">From a Visual Studio BizTalk project, click the **Solution Explorer** tab, right-click a map that uses your custom inline functoid, and then click **Test Map**.</span></span>  
  
2.  <span data-ttu-id="2d1b3-152">[出力] ウィンドウをスクロールして、出力ファイルの URL を探します。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-152">Scroll the Output window to find the URL for the output file.</span></span> <span data-ttu-id="2d1b3-153">Ctrl キーを押し、URL をクリックすると、ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-153">Press CTRL and click the URL to view the file.</span></span>  
  
 <span data-ttu-id="2d1b3-154">入力値と出力値をチェックして、マップが想定したとおりに動作しているかどうかを検証します。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-154">You can check input and output values to verify that the map behaved as expected.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d1b3-155">例</span><span class="sxs-lookup"><span data-stu-id="2d1b3-155">Example</span></span>  
 <span data-ttu-id="2d1b3-156">2 つの文字列を連結するインライン型のカスタム Functoid の作成方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-156">The following example illustrates how to create a custom inline functoid for concatenating two strings.</span></span> <span data-ttu-id="2d1b3-157">ここでは、3 つの文字列リソースと 16x16 ピクセルのビットマップ リソースが格納されたリソース ファイルがあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="2d1b3-157">It relies on a resource file containing three string resources and a 16x16-pixel bitmap resource.</span></span>  
  
```  
using System;  
using Microsoft.BizTalk.BaseFunctoids;  
using System.Reflection;  
using System.Text;  
  
namespace Microsoft.Samples.BizTalk.CustomFunctoid  
{  
    /// <summary>  
    /// Performs a string concatenation using inline code.  
    /// </summary>  
    public class CustomStringConcatFunctoid : BaseFunctoid  
    {  
        public CustomStringConcatFunctoid()  
            : base()  
        {  
            //ID for this functoid  
            this.ID = 6001;  
  
            // Resource assembly must be ProjectName.ResourceName if building with VS.Net  
            SetupResourceAssembly("Microsoft.Samples.BizTalk.CustomFunctoid.CustomFunctoidResources", Assembly.GetExecutingAssembly());  
  
            // Pass the resource ID names for functoid name, tooltip  
            // description and the 16x16 bitmap for the Map palette  
            SetName("IDS_CUSTOMSTRINGCONCATFUNCTOID_NAME");  
            SetTooltip("IDS_CUSTOMSTRINGCONCATFUNCTOID_TOOLTIP");  
            SetDescription("IDS_CUSTOMSTRINGCONCATFUNCTOID_DESCRIPTION");  
            SetBitmap("IDB_CUSTOMSTRINGCONCATFUNCTOID_BITMAP");  
  
            // Put this string handling function under the String   
            // Functoid tab in the Visual Studio toolbox for functoids  
            this.Category = FunctoidCategory.String;  
  
            // 2 required parameters, no optional parameters  
            this.SetMinParams(2);  
            this.SetMaxParams(2);  
  
            // Functoid accepts two inputs  
            AddInputConnectionType(ConnectionType.AllExceptRecord);  
            AddInputConnectionType(ConnectionType.AllExceptRecord);  
  
            // Set the output connection type  
            this.OutputConnectionType = ConnectionType.AllExceptRecord;  
  
            // Declare support for CSharp inline function and  
            // pass the method implementation to the buffer  
            AddScriptTypeSupport(ScriptType.CSharp);  
            SetScriptBuffer(ScriptType.CSharp, GetCSharpBuffer());  
        }  
  
        private string GetCSharpBuffer()  
        {  
            StringBuilder builder = new StringBuilder();  
  
            builder.Append("public string ConCatStrings(string val1, string val2)\n");  
            builder.Append("{\n");  
            builder.Append("    return val2+val1;\n");  
            builder.Append("}\n");  
  
            return builder.ToString();  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d1b3-158">参照</span><span class="sxs-lookup"><span data-stu-id="2d1b3-158">See Also</span></span>  
 <span data-ttu-id="2d1b3-159">[BaseFunctoid の使用](../core/using-basefunctoid.md) </span><span class="sxs-lookup"><span data-stu-id="2d1b3-159">[Using BaseFunctoid](../core/using-basefunctoid.md) </span></span>  
 <span data-ttu-id="2d1b3-160">[Functoid が参照されているカスタムの開発](../core/developing-a-custom-referenced-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="2d1b3-160">[Developing a Custom Referenced Functoid](../core/developing-a-custom-referenced-functoid.md) </span></span>  
 [<span data-ttu-id="2d1b3-161">カスタム Functoid (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="2d1b3-161">Custom Functoid (BizTalk Server Sample)</span></span>](../core/custom-functoid-biztalk-server-sample.md)
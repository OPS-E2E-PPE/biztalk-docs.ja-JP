---
title: インラインのカスタム Functoid の開発 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4533f09f-b62d-4b09-b7de-44541c6cf053
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd6e208cd894c2b307bd2c601b7d8bd774e204ce
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976699"
---
# <a name="developing-a-custom-inline-functoid"></a>インライン型のカスタム Functoid の開発
インライン型のカスタム Functoid は、参照型のカスタム Functoid のように、アセンブリ、クラス、メソッド名などを参照するのではなく、実装コードを直接マップにコピーすることによって機能を提供します。  
  
## <a name="building-inline-script"></a>インライン スクリプトの作成  
 マップに追加するためのスクリプトは、2 とおりの方法で作成できます。 カスタム Functoid のパラメーター数が可変であるかどうかに応じて、次のいずれかの方法を選択してください。  
  
- オーバーライド**GetInlineScriptBuffer**カスタム functoid が入力パラメーターの変数の数を受け付けるし、設定した場合、 **HasVariableInputs**プロパティを`true`します。 たとえば、任意の数の文字列を連結したり、一連の値から最大値を探したりする場合に、この方法を使用します。  
  
- 使用**SetScriptBuffer**入力パラメーター数が変数をサポートする必要がない場合。 パラメーターをオプションにすることもできますが、パラメーターの総数は固定されます。  
  
  この 2 つの方法は、それぞれ実装方法が異なります。  
  
### <a name="providing-inline-code-with-setscriptbuffer"></a>SetScriptBuffer を使ったインライン コードの実装  
 インライン スクリプトを使用するようにカスタム Functoid を構成するには、次の手順に従います。  
  
1. 呼び出す**AddScriptTypeSupport**で[Microsoft.BizTalk.BaseFunctoids.ScriptType](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.scripttype.aspx)インライン コードを有効にし、サポートされているスクリプトの種類を設定します。  
  
2. 呼び出す**SetScriptBuffer**カスタム functoid を使用するコードを設定します。 カスタムの累積 Functoid の場合は、パラメーターに `functionNumber` を指定して、この関数を 3 回呼び出します (累積 Functoid 以外のカスタム Functoid の場合は 1 回)。  
  
3. 使用**SetScriptGlobalBuffer**インライン コードを使用する任意のグローバル変数を宣言します。  
  
4. 使用**RequiredGlobalHelperFunctions**をインラインのカスタム functoid が必要なヘルパー関数を示します。  
  
   スクリプトは、StringBuilder または定数を使用して作成できます。 スクリプト コードを作成する方法の 1 つとして、参照型のカスタム Functoid を最初に記述し、バグをすべて解決してから、カスタム関数を文字列定数にコピーすることによってインライン化する方法が考えられます。  
  
### <a name="providing-inline-code-with-getinlinescriptbuffer"></a>GetInlineScriptBuffer を使ったインライン コードの実装  
 オーバーライドして、カスタムのインライン型の functoid では、可変個のパラメーターをサポートする場合**GetInlineScriptBuffer**します。 インライン スクリプトを使用するようにカスタム Functoid を構成するには、次の手順に従います。  
  
1. コンストラクターの宣言、カスタム functoid を設定して変数の入力の**HasVariableInputs**に`true`します。  
  
2. コンストラクターの呼び出し**AddScriptTypeSupport**で[Microsoft.BizTalk.BaseFunctoids.ScriptType](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.scripttype.aspx)インライン コードを有効にし、サポートされているスクリプトの種類を設定します。  
  
3. オーバーライド**GetInlineScriptBuffer**を構築して、カスタム functoid のマップで使用するコードを返します。 パラメーターの `scriptType` と `numParams` を調べて、適切なコードを作成します。 最後のパラメーターで`functionNumber`0 にする必要があります。 累積的な関数は、固定数の入力があるし、このメカニズムを使用しないためにです。  
  
4. 使用**SetScriptGlobalBuffer**インライン コードを使用するグローバル変数を宣言します。  
  
5. 使用**RequiredGlobalHelperFunctions**をインラインのカスタム functoid が必要なヘルパー関数を示します。  
  
   次のコードは、`numParams` で指定された数のパラメーターを使用する C# の関数を作成します。関数の本体は省略してあります。 このコードを実際に利用する場合、コード例をソリューションにコピーし、何らかの処理を行う (受け取ったパラメーターを処理して値を返す) コードを追加する必要があります。  
  
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
  
## <a name="testing-an-inline-script"></a>インライン スクリプトのテスト  
 開発作業には常にテストが伴います。 インライン型のカスタム Functoid をテストするのは簡単ではありません。 このプロセスを簡単に行うには、次のいずれか、または両方の方法を使用してください。  
  
-   インライン型のカスタム Functoid が使用されたマップの XSLT を調査する。  
  
-   インライン型のカスタム Functoid が使用されたマップの入力と出力を検証する。  
  
### <a name="examine-the-xslt-of-a-map-that-uses-the-custom-inline-functoid"></a>インライン型のカスタム Functoid が使用されたマップの XSLT を調査するには  
 この方法を使用すると、ロジックに関する問題や、構文に関する間違いを検出できる場合があります。 また、マップでどのようなことが行われているのかを把握する場合にも利用できます。  
  
 マップの XSLT を表示するには、次の手順に従います。  
  
1.  Visual Studio の BizTalk プロジェクトでは、クリックして、**ソリューション エクスプ ローラー**  タブで、インラインのカスタム functoid を使用するマップを右クリックし、順にクリックします**マップの検証**します。  
  
2.  [出力] ウィンドウをスクロールして、XSLT ファイルの URL を探します。 Ctrl キーを押し、URL をクリックすると、ファイルが表示されます。  
  
> [!NOTE]
>  ただし、XSLT ファイルに変更を加えても、カスタム Functoid には一切反映されません。  
  
### <a name="test-a-map-that-uses-the-custom-inline-functoid"></a>インライン型のカスタム Functoid が使用されたマップをテストするには  
 これは、マップとカスタム インライン型の functoid が正しく機能するかどうかをテストします。  
  
 マップをテストするには、次の手順に従います。  
  
1. Visual Studio の BizTalk プロジェクトからクリックして、**ソリューション エクスプ ローラー**  タブで、インラインのカスタム functoid を使用するマップを右クリックし、順にクリックします**マップのテスト**します。  
  
2. [出力] ウィンドウをスクロールして、出力ファイルの URL を探します。 Ctrl キーを押し、URL をクリックすると、ファイルが表示されます。  
  
   入力値と出力値をチェックして、マップが想定したとおりに動作しているかどうかを検証します。  
  
## <a name="example"></a>例  
 2 つの文字列を連結するインライン型のカスタム Functoid の作成方法を次に示します。 ここでは、3 つの文字列リソースと 16x16 ピクセルのビットマップ リソースが格納されたリソース ファイルがあることを前提としています。  
  
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
  
## <a name="see-also"></a>参照  
 [BaseFunctoid の使用](../core/using-basefunctoid.md)   
 [参照 Functoid、カスタムの開発](../core/developing-a-custom-referenced-functoid.md)   
 [カスタム Functoid (BizTalk Server サンプル)](../core/custom-functoid-biztalk-server-sample.md)
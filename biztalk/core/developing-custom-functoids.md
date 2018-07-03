---
title: カスタム Functoid の開発 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77419e1f-9f01-44ac-bf5b-a393f1d17f61
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc424533a859f33a139c081897164e9f5db25b2e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019897"
---
# <a name="developing-custom-functoids"></a>カスタム Functoid の開発
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には、さまざまな種類の操作をサポートする多くの Functoid が用意されていますが、あらかじめ用意されている Functoid ではなく、別のアプローチが必要になる場合もあります。 カスタム Functoid を使用すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のマッピング環境内で、さらに多くの種類の操作を実行できるようになります。 派生したクラスを使用して .NET アセンブリとして、各カスタム functoid がデプロイされた**Microsoft.BizTalk.BaseFunctoids**します。 1 つのアセンブリには複数のカスタム Functoid を含めることができます。  
  
 次のシナリオでは、カスタム Functoid の使用を検討してください。  
  
- 固有のレガシ API からのみアクセス可能なデータを使用している文字コード フィールドに対し、特殊な検証規則および変換規則を適用する場合。  
  
- カスタムのビジネス ロジックとキー管理を使用して、フィールドを暗号化または暗号化解除する必要がある場合。  
  
- 別のアプリケーションで使用するために、メッセージの一部からハッシュ コードを生成する必要がある場合。  
  
- 会計部門からの要求で、各部署に送信するメッセージに、製品の種類ごとの総売上に関する概要情報を含める必要がある場合。  
  
- 関連する複数の手順を結合したり、別のアプローチを使用したり、新しいクラス ライブラリを使用することによって、複雑なマップを単純化する場合。  
  
- 1 つのスクリプト Functoid 内で、複数のマップが同一のスクリプト コードを使用する場合。  
  
- 操作が失敗したときにイベント ログに書き込む必要がある場合。  
  
  カスタム Functoid は、インライン コードを使用してソリューションに直接統合することも、グローバル アセンブリ キャッシュに展開されたクラス ライブラリ内のメソッドを参照することによって間接的に統合することもできます。 統合の両方の種類に関係なく、 **BizTalk.BaseFunctoid**クラスし、同じ一連の一般的な手順に従います。  
  
1. 任意の .NET 言語を使用して新しいクラス ライブラリ プロジェクトを作成します。  
  
2. 厳密名ユーティリティ sn.exe を使用してキー ファイルを作成し、プロジェクトに割り当てます。  
  
3. Microsoft.BizTalk.BaseFunctoids.dll への参照を追加します。 このアセンブリに含まれる、 **BaseFunctoid**基本クラス。  
  
4. リソース ファイルを作成してプロジェクトに追加し、 Functoid 名、ツールヒント、および説明用の文字列リソースを追加します。 マップ デザイナー パレットの上で functoid を表す 16 x 16 ピクセルのイメージ リソースを追加します。  
  
5. 派生することで、functoid のクラスを実装**BaseFunctoid**、コンス トラクターの基本的なパラメーターを確立して、functoid のメソッドとサポート メソッドを記述します。 アセンブリには複数のカスタム Functoid を含めることができます。  
  
6. アセンブリを展開し、ツールボックス パレットから新しい Functoid を使用できることを確認します。 参照してください[を追加して、Visual Studio のツールボックスからカスタム Functoid を削除する](../core/adding-and-removing-custom-functoids-from-the-visual-studio-toolbox.md)します。  
  
   次に、Floor Functoid の例を示します。  
  
```  
/// <summary>  
/// Floor Functoid - finds the floor of input  
/// </summary>  
public class FloorFunctoid : BaseFunctoid  
{  
    public FloorFunctoid()  
        : base()  
    {  
        this.ID = 11001;  
        SetupResourceAssembly("MultipleFunctoids.Resource", Assembly.GetExecutingAssembly());  
  
        SetName("NAME_FLOOR");  
        SetDescription("DESCRIPTION_FLOOR");  
        SetTooltip("DESCRIPTION_FLOOR");  
        SetBitmap("IMAGE_FLOOR");  
  
        SetExternalFunctionName(GetType().Assembly.FullName, " MultipleFunctoids.FloorFunctoid", "MathFloor");  
        this.RequiredGlobalHelperFunctions = InlineGlobalHelperFunction.IsNumeric;  
  
        AddScriptTypeSupport(ScriptType.CSharp);  
        SetMinParams(1);  
        SetMaxParams(1);  
  
        this.Category = FunctoidCategory.Math;  
        this.OutputConnectionType = ConnectionType.AllExceptRecord;  
        AddInputConnectionType(ConnectionType.AllExceptRecord);  
        this.HasSideEffects = false;  
    }  
  
    /// <summary>  
    /// To create the C# function  
    /// </summary>  
    /// <param name="scriptType">Script type</param>  
    /// <param name="numParams">Number of parameters</param>  
    /// <param name="functionNumber">Functoid number</param>  
    /// <returns>C# script</returns>  
    protected override string GetInlineScriptBuffer(ScriptType scriptType, int numParams, int functionNumber)  
    {  
        if (ScriptType.CSharp == scriptType)  
        {  
            StringBuilder builder = new StringBuilder();  
  
            builder.Append("public string MathFloor(string input)\n");  
            builder.Append("{\n");  
            builder.Append("  if(string.IsNullOrEmpty(input))\n");  
            builder.Append("    return string.Empty;\n");  
            builder.Append("double d = 0.0;\n");  
            builder.Append("if (IsNumeric(input, ref d))\n");  
            builder.Append("    return Math.Floor(d).ToString(System.Globalization.CultureInfo.InvariantCulture);\n");  
            builder.Append("else\n");  
            builder.Append("    return string.Empty;\n");  
            builder.Append("}\n");  
  
            return builder.ToString();  
        }  
        else  
        {  
            return string.Empty;  
        }  
    }  
}  
  
```  
  
 このサンプルコードを C# プロジェクトの一部として使用する間、"アセンブリ名" は "MultipleFunctoids" に設定する必要があります。 C# プロジェクト (このコードを含む) には Resource.resx ファイルをインクルードしてください。  
  
```  
SetName("NAME_FLOOR");  
SetDescription("DESCRIPTION_FLOOR");  
SetTooltip("DESCRIPTION_FLOOR");  
SetBitmap("IMAGE_FLOOR");  
  
```  
  
 上記のコードで、"NAME_FLOOR"、"DESCRIPTION_FLOOR"、"DESCRIPTION_FLOOR" の各値は Resource.resx ファイルに埋め込まれたリソース文字列の "キー"です。 また、"IMAGE_FLOOR" は Resource.resx ファイルに埋め込まれた画像の名前です。 この画像は Functoid のアイコンとして機能します。  
  
 適切なリソース キーを指定しないか SetName メソッドを削除した場合、名前のないカスタム Functoid が作成されますが、これはお勧めできません。 SetDescription メソッドと SetTooltip メソッドについても同様です。 常にこれらのメソッドを適切に使用し、望ましくない操作は避けてください。 ただし、Functoid アイコンとして使用するのに適した画像がない場合は、SetBitmap メソッドをスキップすることができます。 そのような場合、既定のアイコンがカスタム Functoid により使用されますが、これは問題ありません (複数の Functoid にアイコンがない場合を除く)。  
  
 カスタム functoid を作成する方法の詳細については、次を参照してください。[カスタム Functoid (BizTalk Server サンプル)](../core/custom-functoid-biztalk-server-sample.md)します。  
  
> [!IMPORTANT]
>  一部の Functoid ID は標準/組み込みマッパー Functoid 用に予約されています。 通常、標準マッパー functoid は、1 から 10000 の Id を使用します。 カスタム functoid を作成するときに、functoid 10000 未満の Id を使用しません。  
  
## <a name="in-this-section"></a>このセクションの内容  
 このセクションには、次のトピックが含まれています。  
  
-   [BaseFunctoid の使用](../core/using-basefunctoid.md)  
  
-   [参照型のカスタム Functoid の開発](../core/developing-a-custom-referenced-functoid.md)  
  
-   [インライン型のカスタム Functoid の開発](../core/developing-a-custom-inline-functoid.md)  
  
-   [カスタムの累積 Functoid の開発](../core/developing-a-custom-cumulative-functoid.md)  
  
-   [Visual Studio ツールボックスに対するカスタム Functoid の追加と削除](../core/adding-and-removing-custom-functoids-from-the-visual-studio-toolbox.md)  
  
## <a name="see-also"></a>参照  
 [Functoid を使用した複雑なマッピングの作成](../core/using-functoids-to-create-more-complex-mappings.md)
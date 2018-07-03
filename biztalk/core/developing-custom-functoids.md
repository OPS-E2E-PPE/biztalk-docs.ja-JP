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
# <a name="developing-custom-functoids"></a><span data-ttu-id="e994c-102">カスタム Functoid の開発</span><span class="sxs-lookup"><span data-stu-id="e994c-102">Developing Custom Functoids</span></span>
<span data-ttu-id="e994c-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には、さまざまな種類の操作をサポートする多くの Functoid が用意されていますが、あらかじめ用意されている Functoid ではなく、別のアプローチが必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="e994c-103">Although [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides many functoids to support a range of diverse operations, you will likely encounter a situation that requires a different approach.</span></span> <span data-ttu-id="e994c-104">カスタム Functoid を使用すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のマッピング環境内で、さらに多くの種類の操作を実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e994c-104">Custom functoids provide a way for you to extend the range of operations available within the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mapping environment.</span></span> <span data-ttu-id="e994c-105">派生したクラスを使用して .NET アセンブリとして、各カスタム functoid がデプロイされた**Microsoft.BizTalk.BaseFunctoids**します。</span><span class="sxs-lookup"><span data-stu-id="e994c-105">Each custom functoid is deployed as a .NET assembly using classes derived from **Microsoft.BizTalk.BaseFunctoids**.</span></span> <span data-ttu-id="e994c-106">1 つのアセンブリには複数のカスタム Functoid を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e994c-106">An assembly can contain more than one custom functoid.</span></span>  
  
 <span data-ttu-id="e994c-107">次のシナリオでは、カスタム Functoid の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="e994c-107">You should consider using a custom functoid in the following scenarios:</span></span>  
  
- <span data-ttu-id="e994c-108">固有のレガシ API からのみアクセス可能なデータを使用している文字コード フィールドに対し、特殊な検証規則および変換規則を適用する場合。</span><span class="sxs-lookup"><span data-stu-id="e994c-108">You have special validation and conversion rules for a character code field using data that is only accessible through a proprietary legacy API.</span></span>  
  
- <span data-ttu-id="e994c-109">カスタムのビジネス ロジックとキー管理を使用して、フィールドを暗号化または暗号化解除する必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="e994c-109">You need to encrypt or decrypt fields using custom business logic and key management.</span></span>  
  
- <span data-ttu-id="e994c-110">別のアプリケーションで使用するために、メッセージの一部からハッシュ コードを生成する必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="e994c-110">You need to generate a hash code from part of the message for use in another application.</span></span>  
  
- <span data-ttu-id="e994c-111">会計部門からの要求で、各部署に送信するメッセージに、製品の種類ごとの総売上に関する概要情報を含める必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="e994c-111">Accounting requests that messages transmitted to their department include summary information about total sales by each product type.</span></span>  
  
- <span data-ttu-id="e994c-112">関連する複数の手順を結合したり、別のアプローチを使用したり、新しいクラス ライブラリを使用することによって、複雑なマップを単純化する場合。</span><span class="sxs-lookup"><span data-stu-id="e994c-112">You want to reduce the complexity of a map by combining several related steps, by using a different approach, or by using new class libraries.</span></span>  
  
- <span data-ttu-id="e994c-113">1 つのスクリプト Functoid 内で、複数のマップが同一のスクリプト コードを使用する場合。</span><span class="sxs-lookup"><span data-stu-id="e994c-113">More than one map is using the same script code in a script functoid.</span></span>  
  
- <span data-ttu-id="e994c-114">操作が失敗したときにイベント ログに書き込む必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="e994c-114">You need to write to the event log when an operation fails.</span></span>  
  
  <span data-ttu-id="e994c-115">カスタム Functoid は、インライン コードを使用してソリューションに直接統合することも、グローバル アセンブリ キャッシュに展開されたクラス ライブラリ内のメソッドを参照することによって間接的に統合することもできます。</span><span class="sxs-lookup"><span data-stu-id="e994c-115">Custom functoids can be integrated into a solution directly by using inline code or indirectly by reference to a method in a class library deployed into the global assembly cache.</span></span> <span data-ttu-id="e994c-116">統合の両方の種類に関係なく、 **BizTalk.BaseFunctoid**クラスし、同じ一連の一般的な手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e994c-116">Both types of integration rely on the **BizTalk.BaseFunctoid** class and follow the same set of general steps:</span></span>  
  
1. <span data-ttu-id="e994c-117">任意の .NET 言語を使用して新しいクラス ライブラリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="e994c-117">Create a new class library project using the .NET language of your choice.</span></span>  
  
2. <span data-ttu-id="e994c-118">厳密名ユーティリティ sn.exe を使用してキー ファイルを作成し、プロジェクトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e994c-118">Using the strong-naming utility sn.exe, create a keyfile and assign it to the project.</span></span>  
  
3. <span data-ttu-id="e994c-119">Microsoft.BizTalk.BaseFunctoids.dll への参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="e994c-119">Add a reference to Microsoft.BizTalk.BaseFunctoids.dll.</span></span> <span data-ttu-id="e994c-120">このアセンブリに含まれる、 **BaseFunctoid**基本クラス。</span><span class="sxs-lookup"><span data-stu-id="e994c-120">This assembly contains the **BaseFunctoid** base class.</span></span>  
  
4. <span data-ttu-id="e994c-121">リソース ファイルを作成してプロジェクトに追加し、</span><span class="sxs-lookup"><span data-stu-id="e994c-121">Create a resource file and add it to the project.</span></span> <span data-ttu-id="e994c-122">Functoid 名、ツールヒント、および説明用の文字列リソースを追加します。</span><span class="sxs-lookup"><span data-stu-id="e994c-122">Add string resources for the functoid name, tooltip, and description.</span></span> <span data-ttu-id="e994c-123">マップ デザイナー パレットの上で functoid を表す 16 x 16 ピクセルのイメージ リソースを追加します。</span><span class="sxs-lookup"><span data-stu-id="e994c-123">Add a 16x16-pixel image resource to represent the functoid on the map designer palette.</span></span>  
  
5. <span data-ttu-id="e994c-124">派生することで、functoid のクラスを実装**BaseFunctoid**、コンス トラクターの基本的なパラメーターを確立して、functoid のメソッドとサポート メソッドを記述します。</span><span class="sxs-lookup"><span data-stu-id="e994c-124">Implement the functoid class by deriving from **BaseFunctoid**, establishing basic parameters in the constructor, and then writing the functoid method and any supporting methods.</span></span> <span data-ttu-id="e994c-125">アセンブリには複数のカスタム Functoid を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e994c-125">The assembly can contain multiple custom functoids.</span></span>  
  
6. <span data-ttu-id="e994c-126">アセンブリを展開し、ツールボックス パレットから新しい Functoid を使用できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e994c-126">Deploy the assembly and ensure the new functoid is available from the Toolbox palette.</span></span> <span data-ttu-id="e994c-127">参照してください[を追加して、Visual Studio のツールボックスからカスタム Functoid を削除する](../core/adding-and-removing-custom-functoids-from-the-visual-studio-toolbox.md)します。</span><span class="sxs-lookup"><span data-stu-id="e994c-127">See [Adding and Removing Custom Functoids from the Visual Studio Toolbox](../core/adding-and-removing-custom-functoids-from-the-visual-studio-toolbox.md).</span></span>  
  
   <span data-ttu-id="e994c-128">次に、Floor Functoid の例を示します。</span><span class="sxs-lookup"><span data-stu-id="e994c-128">The following is an illustration for Floor functoid.</span></span>  
  
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
  
 <span data-ttu-id="e994c-129">このサンプルコードを C# プロジェクトの一部として使用する間、"アセンブリ名" は "MultipleFunctoids" に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e994c-129">While using this sample code as part of your C# project, the “Assembly name” must be set to “MultipleFunctoids”.</span></span> <span data-ttu-id="e994c-130">C# プロジェクト (このコードを含む) には Resource.resx ファイルをインクルードしてください。</span><span class="sxs-lookup"><span data-stu-id="e994c-130">Your C# project (containing this code) should include a Resource.resx file.</span></span>  
  
```  
SetName("NAME_FLOOR");  
SetDescription("DESCRIPTION_FLOOR");  
SetTooltip("DESCRIPTION_FLOOR");  
SetBitmap("IMAGE_FLOOR");  
  
```  
  
 <span data-ttu-id="e994c-131">上記のコードで、"NAME_FLOOR"、"DESCRIPTION_FLOOR"、"DESCRIPTION_FLOOR" の各値は Resource.resx ファイルに埋め込まれたリソース文字列の "キー"です。</span><span class="sxs-lookup"><span data-stu-id="e994c-131">In the above code, the values “NAME_FLOOR”, “DESCRIPTION_FLOOR”, and “DESCRIPTION_FLOOR” are the “keys” of resource strings embedded in Resource.resx file.</span></span> <span data-ttu-id="e994c-132">また、"IMAGE_FLOOR" は Resource.resx ファイルに埋め込まれた画像の名前です。</span><span class="sxs-lookup"><span data-stu-id="e994c-132">And, “IMAGE_FLOOR” is the name of an image embedded in the Resource.resx file.</span></span> <span data-ttu-id="e994c-133">この画像は Functoid のアイコンとして機能します。</span><span class="sxs-lookup"><span data-stu-id="e994c-133">This image will act as an icon for the functoid.</span></span>  
  
 <span data-ttu-id="e994c-134">適切なリソース キーを指定しないか SetName メソッドを削除した場合、名前のないカスタム Functoid が作成されますが、これはお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="e994c-134">If you do not specify proper resource keys, or if you delete the SetName method, then a nameless custom functoid is created, which is not a good practice.</span></span> <span data-ttu-id="e994c-135">SetDescription メソッドと SetTooltip メソッドについても同様です。</span><span class="sxs-lookup"><span data-stu-id="e994c-135">Same holds true for SetDescription and SetTooltip methods.</span></span> <span data-ttu-id="e994c-136">常にこれらのメソッドを適切に使用し、望ましくない操作は避けてください。</span><span class="sxs-lookup"><span data-stu-id="e994c-136">Always use these methods properly to avoid any unwanted garbage behavior.</span></span> <span data-ttu-id="e994c-137">ただし、Functoid アイコンとして使用するのに適した画像がない場合は、SetBitmap メソッドをスキップすることができます。</span><span class="sxs-lookup"><span data-stu-id="e994c-137">However, you may skip the SetBitmap method if you do not have any suitable images to be used as functoid icons.</span></span> <span data-ttu-id="e994c-138">そのような場合、既定のアイコンがカスタム Functoid により使用されますが、これは問題ありません (複数の Functoid にアイコンがない場合を除く)。</span><span class="sxs-lookup"><span data-stu-id="e994c-138">In such a case, a default icon is used by the custom functoid, which is harmless (unless there are multiple icon-less functoids).</span></span>  
  
 <span data-ttu-id="e994c-139">カスタム functoid を作成する方法の詳細については、次を参照してください。[カスタム Functoid (BizTalk Server サンプル)](../core/custom-functoid-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="e994c-139">For more information about how to create a custom functoid, see [Custom Functoid (BizTalk Server Sample)](../core/custom-functoid-biztalk-server-sample.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e994c-140">一部の Functoid ID は標準/組み込みマッパー Functoid 用に予約されています。</span><span class="sxs-lookup"><span data-stu-id="e994c-140">Certain functoid IDs are reserved by standard/inbuilt Mapper functoids.</span></span> <span data-ttu-id="e994c-141">通常、標準マッパー functoid は、1 から 10000 の Id を使用します。</span><span class="sxs-lookup"><span data-stu-id="e994c-141">Usually, the standard Mapper functoids use the IDs from 1 to 10000.</span></span> <span data-ttu-id="e994c-142">カスタム functoid を作成するときに、functoid 10000 未満の Id を使用しません。</span><span class="sxs-lookup"><span data-stu-id="e994c-142">While creating custom functoids, do not use the functoid IDs less than 10000.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e994c-143">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e994c-143">In This Section</span></span>  
 <span data-ttu-id="e994c-144">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e994c-144">This section contains:</span></span>  
  
-   [<span data-ttu-id="e994c-145">BaseFunctoid の使用</span><span class="sxs-lookup"><span data-stu-id="e994c-145">Using BaseFunctoid</span></span>](../core/using-basefunctoid.md)  
  
-   [<span data-ttu-id="e994c-146">参照型のカスタム Functoid の開発</span><span class="sxs-lookup"><span data-stu-id="e994c-146">Developing a Custom Referenced Functoid</span></span>](../core/developing-a-custom-referenced-functoid.md)  
  
-   [<span data-ttu-id="e994c-147">インライン型のカスタム Functoid の開発</span><span class="sxs-lookup"><span data-stu-id="e994c-147">Developing a Custom Inline Functoid</span></span>](../core/developing-a-custom-inline-functoid.md)  
  
-   [<span data-ttu-id="e994c-148">カスタムの累積 Functoid の開発</span><span class="sxs-lookup"><span data-stu-id="e994c-148">Developing a Custom Cumulative Functoid</span></span>](../core/developing-a-custom-cumulative-functoid.md)  
  
-   [<span data-ttu-id="e994c-149">Visual Studio ツールボックスに対するカスタム Functoid の追加と削除</span><span class="sxs-lookup"><span data-stu-id="e994c-149">Adding and Removing Custom Functoids from the Visual Studio Toolbox</span></span>](../core/adding-and-removing-custom-functoids-from-the-visual-studio-toolbox.md)  
  
## <a name="see-also"></a><span data-ttu-id="e994c-150">参照</span><span class="sxs-lookup"><span data-stu-id="e994c-150">See Also</span></span>  
 [<span data-ttu-id="e994c-151">Functoid を使用した複雑なマッピングの作成</span><span class="sxs-lookup"><span data-stu-id="e994c-151">Using Functoids to Create More Complex Mappings</span></span>](../core/using-functoids-to-create-more-complex-mappings.md)
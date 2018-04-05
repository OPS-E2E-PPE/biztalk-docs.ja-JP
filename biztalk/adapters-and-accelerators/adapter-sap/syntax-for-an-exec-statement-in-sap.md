---
title: SAP の EXEC ステートメントの構文 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- EXEC statement, syntax for
ms.assetid: 406b1100-39a0-4321-89c9-ec1b8a3cfdc6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 362aa1f81158c9d9f1135c9bff25c64d7d745953
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="syntax-for-an-exec-statement-in-sap"></a><span data-ttu-id="e9d82-102">SAP の EXEC ステートメントの構文</span><span class="sxs-lookup"><span data-stu-id="e9d82-102">Syntax for an EXEC Statement in SAP</span></span>
<span data-ttu-id="e9d82-103">次のセクションでは、に対して EXEC ステートメントを実装するための文法仕様をについて説明します、[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e9d82-103">The following section describes grammar specifications for implementing EXEC statements against the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span></span> <span data-ttu-id="e9d82-104">いくつかの場合、構文は若干異なること TRANSACT-SQL 構文に注意してください。</span><span class="sxs-lookup"><span data-stu-id="e9d82-104">Notice that in several cases, the syntax is somewhat different from Transact-SQL syntax.</span></span>  
  
```  
EXEC rfc_name {<argument_element>} [ , …n ]  {;}[0,1] [ OPTION <disabledatavalidation>, <firstresultset> ]  
```  
  
 <span data-ttu-id="e9d82-105">それぞれの文字の説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e9d82-105">where:</span></span>  
  
-   <span data-ttu-id="e9d82-106">**rfc_name**実行関数の呼び出しの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e9d82-106">**rfc_name** specifies the name of the function call to execute.</span></span>  
  
-   <span data-ttu-id="e9d82-107">**< argument_element >** :: = @param_name = [0, 1] \<const\> {[入力 (&) #124 です。出力]} [0, 1]</span><span class="sxs-lookup"><span data-stu-id="e9d82-107">**<argument_element>** ::= @param_name = [0,1] \<const\> {[ INPUT &#124; OUTPUT ]}[0,1]</span></span>  
  
    -   <span data-ttu-id="e9d82-108">**param_name**関数インターフェイスで定義されたパラメーター名を指定します。</span><span class="sxs-lookup"><span data-stu-id="e9d82-108">**param_name** specifies the parameter name defined in the function interface.</span></span>  
  
    -   <span data-ttu-id="e9d82-109">**\<const\>**  :: 整数 &#124; = real &#124; 文字列 &#124; しますか?</span><span class="sxs-lookup"><span data-stu-id="e9d82-109">**\<const\>** ::= integer &#124; real &#124; string &#124; ?</span></span> <span data-ttu-id="e9d82-110">&#124;です。NULL &#124;です。xml_element</span><span class="sxs-lookup"><span data-stu-id="e9d82-110">&#124; NULL &#124; xml_element</span></span>  
  
-   <span data-ttu-id="e9d82-111">**オプション**データを表示する方法のオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="e9d82-111">**OPTION**  provides option on how you want to present the data.</span></span> <span data-ttu-id="e9d82-112">使用可能なオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e9d82-112">The available options are:</span></span>  
  
    -   <span data-ttu-id="e9d82-113">**disabledatavalidation**オプション セットに、 **EnableSafeTyping** 、基になるプロパティのバインド[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e9d82-113">**disabledatavalidation** option sets the **EnableSafeTyping** binding property in the underlying [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="e9d82-114">安全な入力が有効になっているときに、DATS、TIM、および NUMC データ型が文字列として表されます。</span><span class="sxs-lookup"><span data-stu-id="e9d82-114">When safe typing is enabled the DATS, TIMS, and NUMC data types are represented as strings.</span></span> <span data-ttu-id="e9d82-115">このバインドのプロパティの詳細については、次を参照してください。 [mySAP Business Suite のバインドのプロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="e9d82-115">For more information about this binding property, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
    -   <span data-ttu-id="e9d82-116">**firstresultset**によって返される最初の結果セットを指定します、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e9d82-116">**firstresultset** specifies the first result set that is returned by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span> <span data-ttu-id="e9d82-117">ADO プロバイダー ソース上の任意のステートメントが実行されるときにのみ、最初の結果セットが返されましたがあります。</span><span class="sxs-lookup"><span data-stu-id="e9d82-117">When any statement is executed on an ADO Provider source, only the first result set returned is available.</span></span> <span data-ttu-id="e9d82-118">RFC EXEC のシナリオで通常テーブルの複数のパラメーターが返されますが、最初の結果セットだけの場合があるクライアント プログラムは、使用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e9d82-118">For RFC EXEC scenarios, usually multiple table parameters are returned but if only the first result set is available for the client program, which might not be of use.</span></span> <span data-ttu-id="e9d82-119">"Firstresultset"キーワードを指定すると、OPTION 句の一部として、クライアントは、プロバイダーを返す必要な最初のテーブル パラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e9d82-119">By specifying the “firstresultset” keyword as part of the OPTION clause, clients can specify the first table parameter that they want the Provider to return.</span></span> <span data-ttu-id="e9d82-120">例:</span><span class="sxs-lookup"><span data-stu-id="e9d82-120">For example:</span></span>  
  
        ```  
        EXEC Z_TEST_ALL_TYPES @P_IN='TestInput' OPTION 'disabledatavalidation', firstresultset TAB_ALLTYPES'  
        ```  
  
         <span data-ttu-id="e9d82-121">この例では、EXEC ステートメントは、返されるテーブルの最初のパラメーターが TAB_ALLTYPES をする必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="e9d82-121">In this example, the EXEC statement specifies that the first table parameter returned should be TAB_ALLTYPES.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e9d82-122">たとえば、常に 1 つの引用符で囲まれたオプションのキーワードの値を提供する必要があります '*disabledatavalidation*' です。</span><span class="sxs-lookup"><span data-stu-id="e9d82-122">You must always provide the values for the OPTION keyword within single quotes, for example, '*disabledatavalidation*'.</span></span>  
  
 <span data-ttu-id="e9d82-123">上記の構文では、複合型の入力を提供する xml_element を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e9d82-123">In the preceding syntax, xml_element can be used to provide input for complex types.</span></span> <span data-ttu-id="e9d82-124">Xml 要素の構造は別の構造とテーブルになります。</span><span class="sxs-lookup"><span data-stu-id="e9d82-124">The xml element structure will be different for structures and tables.</span></span> <span data-ttu-id="e9d82-125">構造体の xml_element には、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="e9d82-125">The xml_element for structure resembles the following:</span></span>  
  
```  
<PARAM_NAME>  
    <FIELDNAME_1 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">value</FIELDNAME_1>  
    <FIELDNAME_2 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">value</FIELDNAME_2>  
    ...  
    ...  
</ PARAM_NAME>  
```  
  
 <span data-ttu-id="e9d82-126">テーブルの xml_element には、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="e9d82-126">The xml_element for table resembles the following:</span></span>  
  
```  
<PARAM_NAME>  
    <STRUCT_NAME  xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
        <FIELDNAME_1>value</FIELDNAME_1>  
    <STRUCT_NAME/>  
    <STRUCT_NAME  xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
        <FIELDNAME_1>value</FIELDNAME_1>  
    <STRUCT_NAME/>  
    ...  
    ...  
</ PARAM_NAME>  
```  
  
 <span data-ttu-id="e9d82-127">たとえば、構造体型の XML 要素は、次するようになります。</span><span class="sxs-lookup"><span data-stu-id="e9d82-127">For example, the XML element for a structure type resembles the following:</span></span>  
  
```  
<INOUT_STRUCT>  
       <ACCPFIELD xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">2006</ACCPFIELD>  
       <CHARFIELD xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">John</CHARFIELD>                 
</INOUT_STRUCT>  
```  
  
 <span data-ttu-id="e9d82-128">同様に、テーブル型の XML 要素は、次するようになります。</span><span class="sxs-lookup"><span data-stu-id="e9d82-128">Similarly, the XML element for a table type resembles the following:</span></span>  
  
```  
<TAB_ALLTYPES>   
<ZZSTRUCTALLTYPES_RFC xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
       <ACCPFIELD>2006</ACCPFIELD>  
       <CHARFIELD>John</CHARFIELD>                          
</ZZSTRUCTALLTYPES_RFC>  
<ZZSTRUCTALLTYPES_RFC xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
       <ACCPFIELD>2007</ACCPFIELD>  
       <CHARFIELD>James</CHARFIELD>                          
</ZZSTRUCTALLTYPES_RFC>  
</TAB_ALLTYPES>  
```  
  
 <span data-ttu-id="e9d82-129">たとえば、ステートメントを参照してください[EXEC ステートメントの例](../../adapters-and-accelerators/adapter-sap/examples-for-exec-statement.md)です。</span><span class="sxs-lookup"><span data-stu-id="e9d82-129">For example statements, see [Examples for EXEC Statement](../../adapters-and-accelerators/adapter-sap/examples-for-exec-statement.md).</span></span>  
  
## <a name="handling-named-parameters"></a><span data-ttu-id="e9d82-130">名前付きパラメーターの処理</span><span class="sxs-lookup"><span data-stu-id="e9d82-130">Handling Named Parameters</span></span>  
 <span data-ttu-id="e9d82-131">EXEC クエリで名前付きパラメーターを指定するためのガイドラインを次に示します。</span><span class="sxs-lookup"><span data-stu-id="e9d82-131">The following are guidelines for specifying named parameters in EXEC queries:</span></span>  
  
-   <span data-ttu-id="e9d82-132">名前を付けることでパラメーターを指定する必要があります (たとえば、 @param_name= 値)。</span><span class="sxs-lookup"><span data-stu-id="e9d82-132">You must specify parameters by naming them (for example, @param_name=value).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e9d82-133">無名のパラメーターはサポートされていません</span><span class="sxs-lookup"><span data-stu-id="e9d82-133">Unnamed parameters are not supported</span></span>  
  
-   <span data-ttu-id="e9d82-134">既定値を使用して、パラメーターを定義するときは、パラメーターを指定せず、プロシージャを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e9d82-134">When a parameter is defined using a default value, you can execute the procedure without specifying a parameter.</span></span>  
  
-   <span data-ttu-id="e9d82-135">EXEC クエリでは、パラメーターを使用して、次のプロパティではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="e9d82-135">EXEC queries do not support using parameters with the following properties:</span></span>  
  
    -   <span data-ttu-id="e9d82-136">入れ子になった構造体 (構造体としてのフィールドを格納する構造) です。</span><span class="sxs-lookup"><span data-stu-id="e9d82-136">Nested structures (structures that contain structures as their fields).</span></span>  
  
    -   <span data-ttu-id="e9d82-137">入れ子になったテーブル。</span><span class="sxs-lookup"><span data-stu-id="e9d82-137">Nested tables.</span></span>  
  
    -   <span data-ttu-id="e9d82-138">構造体を含むテーブル。</span><span class="sxs-lookup"><span data-stu-id="e9d82-138">A table containing a structure.</span></span>  
  
    -   <span data-ttu-id="e9d82-139">テーブルを含む構造体。</span><span class="sxs-lookup"><span data-stu-id="e9d82-139">A structure containing a table.</span></span>  
  
    -   <span data-ttu-id="e9d82-140">構造体または複合文字列型のフィールドを持つテーブル`SSTRING`または`RAWSTRING`です。</span><span class="sxs-lookup"><span data-stu-id="e9d82-140">A structure or table that has fields with composite string types, for example `SSTRING` or `RAWSTRING`.</span></span>  
  
     <span data-ttu-id="e9d82-141">次の表では、RFC を実行するときに、RFC パラメーターの型とパラメーターの方向との間の論理なマッピングが一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="e9d82-141">The following table lists logical mappings between RFC parameter types and parameter directions when executing an RFC.</span></span>  
  
    |<span data-ttu-id="e9d82-142">RFC パラメーターの型</span><span class="sxs-lookup"><span data-stu-id="e9d82-142">RFC Param Type</span></span>|<span data-ttu-id="e9d82-143">クエリ キーワード</span><span class="sxs-lookup"><span data-stu-id="e9d82-143">Query Keyword</span></span>|<span data-ttu-id="e9d82-144">パラメーターの方向</span><span class="sxs-lookup"><span data-stu-id="e9d82-144">Parameter Direction</span></span>|  
    |--------------------|-------------------|-------------------------|  
    |<span data-ttu-id="e9d82-145">パラメーターをインポートします。</span><span class="sxs-lookup"><span data-stu-id="e9d82-145">Import parameters</span></span>|<span data-ttu-id="e9d82-146">何もない</span><span class="sxs-lookup"><span data-stu-id="e9d82-146">Nothing</span></span>|<span data-ttu-id="e9d82-147">Paramdirection.Input</span><span class="sxs-lookup"><span data-stu-id="e9d82-147">Paramdirection.Input</span></span>|  
    |<span data-ttu-id="e9d82-148">パラメーターをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="e9d82-148">Export parameters</span></span>|<span data-ttu-id="e9d82-149">出力</span><span class="sxs-lookup"><span data-stu-id="e9d82-149">Output</span></span>|<span data-ttu-id="e9d82-150">Paramdirection.Output</span><span class="sxs-lookup"><span data-stu-id="e9d82-150">Paramdirection.Output</span></span>|  
    |<span data-ttu-id="e9d82-151">テーブル パラメーター</span><span class="sxs-lookup"><span data-stu-id="e9d82-151">Table parameters</span></span>|<span data-ttu-id="e9d82-152">出力/何もしません。</span><span class="sxs-lookup"><span data-stu-id="e9d82-152">Output/Nothing</span></span>|<span data-ttu-id="e9d82-153">入力/出力</span><span class="sxs-lookup"><span data-stu-id="e9d82-153">InputOutput</span></span>|  
  
 <span data-ttu-id="e9d82-154">パラメーターを処理するための一般的なガイドラインを次に示します。</span><span class="sxs-lookup"><span data-stu-id="e9d82-154">The following are general guidelines for handling parameters:</span></span>  
  
-   <span data-ttu-id="e9d82-155">定数またはクエリ内のプレース ホルダーを使用して、パラメーター値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e9d82-155">You can specify parameter values either as constants or by using placeholders in the query.</span></span>  
  
-   <span data-ttu-id="e9d82-156">作成する必要がありますのプレース ホルダーをクエリを使用する場合、`SAPParameter`オブジェクトおよび対応するコマンド オブジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="e9d82-156">When using placeholders in the query, you must create a `SAPParameter` object and add it to the corresponding command object.</span></span> <span data-ttu-id="e9d82-157">その後、プレース ホルダーの名前をコンス トラクターに渡し方向と値は、コンテキストによって異なります。</span><span class="sxs-lookup"><span data-stu-id="e9d82-157">You then pass the placeholder name to the constructor; the direction and value depend on the context.</span></span>  
  
    -   <span data-ttu-id="e9d82-158">`Input`パラメーターで指定しないと、クエリ パラメーターの方向のキーワードです。</span><span class="sxs-lookup"><span data-stu-id="e9d82-158">For `Input` parameters, do not specify in the query a keyword for the parameter direction.</span></span> <span data-ttu-id="e9d82-159">`value`パラメーター オブジェクトのフィールドを設定する必要があります、またはプロバイダーは、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="e9d82-159">The `value` field of the parameter object must be set, or the provider will throw an exception.</span></span> <span data-ttu-id="e9d82-160">明示的に設定する必要がありますいない、`direction`ため、プロバイダーの既定値は、パラメーター オブジェクトのフィールド`Input`です。</span><span class="sxs-lookup"><span data-stu-id="e9d82-160">You must not explicitly set the `direction` field of the parameter object, because the provider defaults to `Input`.</span></span>  
  
    -   <span data-ttu-id="e9d82-161">他のパラメーターの形式を使用して`@paramname=@placeholder`を指定し、`Output`クエリで明示的にキーワード。</span><span class="sxs-lookup"><span data-stu-id="e9d82-161">For other parameters, use the form `@paramname=@placeholder` and specify the `Output` keyword explicitly in the query.</span></span> <span data-ttu-id="e9d82-162">次に追加する必要があります、`SAPParameter`プレース ホルダーに対応し、するか、パラメーターの方向を明示的に設定する`ParamDirection.Output`または`ParamDirection.InputOutput`パラメーターの型に応じて、します。</span><span class="sxs-lookup"><span data-stu-id="e9d82-162">You must then add a `SAPParameter` that corresponds with the placeholder and explicitly set the parameter direction to either `ParamDirection.Output` or `ParamDirection.InputOutput`, depending on the parameter type.</span></span>  
  
-   <span data-ttu-id="e9d82-163">パラメーター名とプレース ホルダー名は区別されません。</span><span class="sxs-lookup"><span data-stu-id="e9d82-163">Parameter names and placeholder names are not case-sensitive.</span></span>  
  
-   <span data-ttu-id="e9d82-164">異なる方向を持つ場合だけ、クエリ内のパラメーター名を繰り返すことはできません。</span><span class="sxs-lookup"><span data-stu-id="e9d82-164">Parameter names cannot be repeated in a query unless they have different directions.</span></span>  
  
-   <span data-ttu-id="e9d82-165">プレース ホルダー名は、クエリ内で繰り返すことはできません。</span><span class="sxs-lookup"><span data-stu-id="e9d82-165">Placeholder names cannot be repeated in a query.</span></span>  
  
## <a name="considerations-when-calling-an-exec-statement"></a><span data-ttu-id="e9d82-166">EXEC ステートメントを呼び出す際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="e9d82-166">Considerations When Calling an EXEC Statement</span></span>  
 <span data-ttu-id="e9d82-167">このセクションでは、EXEC ステートメントを使用する場合、点に注意する必要がありますポイントを一覧表示[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e9d82-167">This section lists the points that you must keep in mind when using the EXEC statement with [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
-   <span data-ttu-id="e9d82-168">EXEC ステートメントでは、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を返します`TIMS`.NET として値をフィールド`System.DateTime`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e9d82-168">For an EXEC statement, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] returns `TIMS` field values as .NET `System.DateTime` objects.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e9d82-169">SELECT ステートメントで、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]返します`TIMS`.NET として値をフィールド`System.TimeSpan`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e9d82-169">For a SELECT statement, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] returns `TIMS` field values as .NET `System.TimeSpan` objects.</span></span> <span data-ttu-id="e9d82-170">SELECT ステートメントの詳細については、次を参照してください。 [SAP の SELECT ステートメントの構文](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)です。</span><span class="sxs-lookup"><span data-stu-id="e9d82-170">For more information about the SELECT statement, see [Syntax for a SELECT Statement in SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9d82-171">参照</span><span class="sxs-lookup"><span data-stu-id="e9d82-171">See Also</span></span>  
 [<span data-ttu-id="e9d82-172">.NET Framework Data Provider for mySAP Business Suite について</span><span class="sxs-lookup"><span data-stu-id="e9d82-172">About the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)
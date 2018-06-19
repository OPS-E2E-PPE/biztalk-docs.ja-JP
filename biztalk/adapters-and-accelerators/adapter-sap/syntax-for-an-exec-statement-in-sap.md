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
ms.locfileid: "25966032"
---
# <a name="syntax-for-an-exec-statement-in-sap"></a>SAP の EXEC ステートメントの構文
次のセクションでは、に対して EXEC ステートメントを実装するための文法仕様をについて説明します、[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]です。 いくつかの場合、構文は若干異なること TRANSACT-SQL 構文に注意してください。  
  
```  
EXEC rfc_name {<argument_element>} [ , …n ]  {;}[0,1] [ OPTION <disabledatavalidation>, <firstresultset> ]  
```  
  
 それぞれの文字の説明は次のとおりです。  
  
-   **rfc_name**実行関数の呼び出しの名前を指定します。  
  
-   **< argument_element >** :: = @param_name = [0, 1] \<const\> {[入力 (&) #124 です。出力]} [0, 1]  
  
    -   **param_name**関数インターフェイスで定義されたパラメーター名を指定します。  
  
    -   **\<const\>**  :: 整数 &#124; = real &#124; 文字列 &#124; しますか? &#124;です。NULL &#124;です。xml_element  
  
-   **オプション**データを表示する方法のオプションを提供します。 使用可能なオプションは次のとおりです。  
  
    -   **disabledatavalidation**オプション セットに、 **EnableSafeTyping** 、基になるプロパティのバインド[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 安全な入力が有効になっているときに、DATS、TIM、および NUMC データ型が文字列として表されます。 このバインドのプロパティの詳細については、次を参照してください。 [mySAP Business Suite のバインドのプロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。  
  
    -   **firstresultset**によって返される最初の結果セットを指定します、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]です。 ADO プロバイダー ソース上の任意のステートメントが実行されるときにのみ、最初の結果セットが返されましたがあります。 RFC EXEC のシナリオで通常テーブルの複数のパラメーターが返されますが、最初の結果セットだけの場合があるクライアント プログラムは、使用できない可能性があります。 "Firstresultset"キーワードを指定すると、OPTION 句の一部として、クライアントは、プロバイダーを返す必要な最初のテーブル パラメーターを指定できます。 例:  
  
        ```  
        EXEC Z_TEST_ALL_TYPES @P_IN='TestInput' OPTION 'disabledatavalidation', firstresultset TAB_ALLTYPES'  
        ```  
  
         この例では、EXEC ステートメントは、返されるテーブルの最初のパラメーターが TAB_ALLTYPES をする必要がありますを指定します。  
  
    > [!IMPORTANT]
    >  たとえば、常に 1 つの引用符で囲まれたオプションのキーワードの値を提供する必要があります '*disabledatavalidation*' です。  
  
 上記の構文では、複合型の入力を提供する xml_element を使用できます。 Xml 要素の構造は別の構造とテーブルになります。 構造体の xml_element には、次のようになります。  
  
```  
<PARAM_NAME>  
    <FIELDNAME_1 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">value</FIELDNAME_1>  
    <FIELDNAME_2 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">value</FIELDNAME_2>  
    ...  
    ...  
</ PARAM_NAME>  
```  
  
 テーブルの xml_element には、次のようになります。  
  
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
  
 たとえば、構造体型の XML 要素は、次するようになります。  
  
```  
<INOUT_STRUCT>  
       <ACCPFIELD xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">2006</ACCPFIELD>  
       <CHARFIELD xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">John</CHARFIELD>                 
</INOUT_STRUCT>  
```  
  
 同様に、テーブル型の XML 要素は、次するようになります。  
  
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
  
 たとえば、ステートメントを参照してください[EXEC ステートメントの例](../../adapters-and-accelerators/adapter-sap/examples-for-exec-statement.md)です。  
  
## <a name="handling-named-parameters"></a>名前付きパラメーターの処理  
 EXEC クエリで名前付きパラメーターを指定するためのガイドラインを次に示します。  
  
-   名前を付けることでパラメーターを指定する必要があります (たとえば、 @param_name= 値)。  
  
    > [!NOTE]
    >  無名のパラメーターはサポートされていません  
  
-   既定値を使用して、パラメーターを定義するときは、パラメーターを指定せず、プロシージャを実行できます。  
  
-   EXEC クエリでは、パラメーターを使用して、次のプロパティではサポートされません。  
  
    -   入れ子になった構造体 (構造体としてのフィールドを格納する構造) です。  
  
    -   入れ子になったテーブル。  
  
    -   構造体を含むテーブル。  
  
    -   テーブルを含む構造体。  
  
    -   構造体または複合文字列型のフィールドを持つテーブル`SSTRING`または`RAWSTRING`です。  
  
     次の表では、RFC を実行するときに、RFC パラメーターの型とパラメーターの方向との間の論理なマッピングが一覧表示します。  
  
    |RFC パラメーターの型|クエリ キーワード|パラメーターの方向|  
    |--------------------|-------------------|-------------------------|  
    |パラメーターをインポートします。|何もない|Paramdirection.Input|  
    |パラメーターをエクスポートします。|出力|Paramdirection.Output|  
    |テーブル パラメーター|出力/何もしません。|入力/出力|  
  
 パラメーターを処理するための一般的なガイドラインを次に示します。  
  
-   定数またはクエリ内のプレース ホルダーを使用して、パラメーター値を指定できます。  
  
-   作成する必要がありますのプレース ホルダーをクエリを使用する場合、`SAPParameter`オブジェクトおよび対応するコマンド オブジェクトに追加します。 その後、プレース ホルダーの名前をコンス トラクターに渡し方向と値は、コンテキストによって異なります。  
  
    -   `Input`パラメーターで指定しないと、クエリ パラメーターの方向のキーワードです。 `value`パラメーター オブジェクトのフィールドを設定する必要があります、またはプロバイダーは、例外がスローされます。 明示的に設定する必要がありますいない、`direction`ため、プロバイダーの既定値は、パラメーター オブジェクトのフィールド`Input`です。  
  
    -   他のパラメーターの形式を使用して`@paramname=@placeholder`を指定し、`Output`クエリで明示的にキーワード。 次に追加する必要があります、`SAPParameter`プレース ホルダーに対応し、するか、パラメーターの方向を明示的に設定する`ParamDirection.Output`または`ParamDirection.InputOutput`パラメーターの型に応じて、します。  
  
-   パラメーター名とプレース ホルダー名は区別されません。  
  
-   異なる方向を持つ場合だけ、クエリ内のパラメーター名を繰り返すことはできません。  
  
-   プレース ホルダー名は、クエリ内で繰り返すことはできません。  
  
## <a name="considerations-when-calling-an-exec-statement"></a>EXEC ステートメントを呼び出す際の考慮事項  
 このセクションでは、EXEC ステートメントを使用する場合、点に注意する必要がありますポイントを一覧表示[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]です。  
  
-   EXEC ステートメントでは、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を返します`TIMS`.NET として値をフィールド`System.DateTime`オブジェクト。  
  
    > [!NOTE]
    >  SELECT ステートメントで、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]返します`TIMS`.NET として値をフィールド`System.TimeSpan`オブジェクト。 SELECT ステートメントの詳細については、次を参照してください。 [SAP の SELECT ステートメントの構文](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)です。  
  
## <a name="see-also"></a>参照  
 [.NET Framework Data Provider for mySAP Business Suite について](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)
---
title: SAP の EXEC ステートメントの構文 |Microsoft Docs
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
ms.openlocfilehash: 7da9395ec244f6877dc7902e0feae22f6d81b391
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020081"
---
# <a name="syntax-for-an-exec-statement-in-sap"></a>SAP の EXEC ステートメントの構文
次のセクションの説明に対する EXEC ステートメントを実装するための文法の仕様、[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]します。 いくつかの場合、構文が少し異なる TRANSACT-SQL 構文に注意してください。  
  
```  
EXEC rfc_name {<argument_element>} [ , …n ]  {;}[0,1] [ OPTION <disabledatavalidation>, <firstresultset> ]  
```  
  
 それぞれの文字の説明は次のとおりです。  
  
- **rfc_name**を実行する関数呼び出しの名前を指定します。  
  
- **< argument_element >** :: = @param_name = [0, 1] \<const\> {[入力&#124;出力]} [0, 1]  
  
  -   **param_name**関数インターフェイスで定義されたパラメーター名を指定します。  
  
  -   **\<const\>**  :: = 整数&#124;実際&#124;文字列&#124;でしょうか。 &#124;NULL &#124; xml_element  
  
- **オプション**データを表示する方法のオプションを提供します。 使用可能なオプションは次のとおりです。  
  
  - **disabledatavalidation**オプション セット、 **EnableSafeTyping** 、基になるプロパティのバインド[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 安全な入力が有効にすると、DATS、TIM、および NUMC データ型は文字列として表されます。 このバインドのプロパティの詳細については、[mySAP Business Suite のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)を参照してください。  
  
  - **firstresultset**によって返される最初の結果セットを指定します、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]します。 任意のステートメントは、ADO プロバイダーは、ソースで実行される、返される最初の結果だけが使用可能です。 RFC EXEC のシナリオで通常はテーブルの複数のパラメーターが返されますが最初の結果セットのみの場合は、クライアント プログラムが使用できない可能性があるために使用できます。 OPTION 句の一部として"firstresultset"キーワードを指定して、クライアントは、プロバイダーを返す必要な最初のテーブル パラメーターを指定できます。 以下に例を示します。  
  
    ```  
    EXEC Z_TEST_ALL_TYPES @P_IN='TestInput' OPTION 'disabledatavalidation', firstresultset TAB_ALLTYPES'  
    ```  
  
     この例では、EXEC ステートメントは、返されるテーブルの最初のパラメーターは TAB_ALLTYPES である必要がありますを指定します。  
  
  > [!IMPORTANT]
  >  たとえば、常に単一引用符で囲まれたオプションのキーワードの値を指定する必要があります '*disabledatavalidation*'。  
  
  上記の構文では、複合型の入力を提供する xml_element を使用できます。 Xml 要素の構造は、別の構造とテーブルになります。 構造体の xml_element には、次のようになります。  
  
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
  
 たとえば、ステートメントを参照してください[EXEC ステートメントの例](../../adapters-and-accelerators/adapter-sap/examples-for-exec-statement.md)します。  
  
## <a name="handling-named-parameters"></a>名前付きパラメーターの処理  
 次に、EXEC クエリの名前付きパラメーターを指定するためのガイドラインを示します。  
  
- 名前を指定してパラメーターを指定する必要があります (たとえば、 @param_name= 値)。  
  
  > [!NOTE]
  >  無名のパラメーターはサポートされていません  
  
- パラメーターを定義するには、既定値を使用するときは、パラメーターを指定せず、プロシージャを実行することができます。  
  
- EXEC クエリでは、パラメーターを使用して、次のプロパティではサポートされません。  
  
  - 入れ子になった構造体 (構造体そのフィールドにはが含まれている構造)。  
  
  - 入れ子になったテーブル。  
  
  - 構造体を含むテーブル。  
  
  - テーブルを含む構造体。  
  
  - 構造体または複合文字列の型のフィールドを持つテーブル`SSTRING`または`RAWSTRING`します。  
  
    次の表では、RFC を実行するときに、RFC パラメーターの型とパラメーターの方向との間の論理なマッピングが一覧表示します。  
  
  |RFC パラメーターの型|クエリ キーワード|パラメーターの方向|  
  |--------------------|-------------------|-------------------------|  
  |パラメーターをインポートします。|何もない|Paramdirection.Input|  
  |パラメーターをエクスポートします。|[出力]|Paramdirection.Output|  
  |テーブル パラメーター|出力/何もしません。|InputOutput|  
  
  次に、パラメーターを処理するための一般的なガイドラインを示します。  
  
- 定数またはクエリ内のプレース ホルダーを使用して、パラメーター値を指定できます。  
  
- 作成する必要があります、クエリ内のプレース ホルダーを使用する場合、`SAPParameter`オブジェクトおよび対応するコマンド オブジェクトに追加します。 コンス トラクターにし、プレース ホルダー名を渡す方向と値は、コンテキストに依存します。  
  
  -   `Input`パラメーターを指定しないクエリでパラメーターの方向のキーワード。 `value`パラメーター オブジェクトのフィールドを設定する必要があります、またはプロバイダー例外がスローされます。 明示的に設定する必要がありますいない、`direction`ため、プロバイダーの既定値は、パラメーター オブジェクトのフィールド`Input`します。  
  
  -   他のパラメーターの形式を使用して、`@paramname=@placeholder`を指定し、`Output`クエリで明示的にキーワード。 次に追加する必要があります、`SAPParameter`プレース ホルダーに対応し、するか、パラメーターの方向を明示的に設定する`ParamDirection.Output`または`ParamDirection.InputOutput`パラメーターの型に応じて、します。  
  
- パラメーターの名前とプレース ホルダー名は区別されません。  
  
- パラメーター名は、さまざまな方向を所有していない場合、クエリ内で繰り返すことはできません。  
  
- プレース ホルダー名は、クエリ内で繰り返すことはできません。  
  
## <a name="considerations-when-calling-an-exec-statement"></a>EXEC ステートメントの呼び出し時の考慮事項  
 このセクションでは、EXEC ステートメントを使用する場合、点に注意する必要がありますをポイント数を示します[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]します。  
  
- EXEC ステートメントでは、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]返します`TIMS`フィールドの値として .NET`System.DateTime`オブジェクト。  
  
  > [!NOTE]
  >  SELECT ステートメントの[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]返します`TIMS`フィールドの値として .NET`System.TimeSpan`オブジェクト。 SELECT ステートメントの詳細については、[SAP で SELECT ステートメントの構文](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)を参照してください。  
  
## <a name="see-also"></a>参照  
 [.NET Framework Data Provider for mySAP Business Suite について](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)
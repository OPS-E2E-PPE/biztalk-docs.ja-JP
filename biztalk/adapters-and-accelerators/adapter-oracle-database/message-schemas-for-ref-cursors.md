---
title: メッセージの REF CURSOR のスキーマ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- REF CURSORS, message schemas for
- IN REF CURSOR
- OUT REF CURSOR
- IN OUT REF CURSOR
ms.assetid: b62e7a9f-278c-41b3-90f0-2f621a34327b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bddfde0b0897c7d8c21a20126d2fa1d2f0f8c78
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214762"
---
# <a name="message-schemas-for-ref-cursors"></a>REF CURSOR のメッセージ スキーマ
REF CURSOR は、Oracle データベースに結果セットへのポインターを表す Oracle PL/SQL データ型です。 REF CURSOR 型は入力を有効にするデータのストリーミングを出力し、大量の PL/SQL コード ブロックとの間のデータを転送するために最適です。 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]アウト PL/SQL プロシージャと関数でとして厳密に型指定され、弱い型指定の REF CURSOR パラメーターを渡すと IN OUT パラメーターのサポートを提供します。  
  
 Oracle データベースでは、REF CURSOR 型は厳密に型指定されたまたは、弱い型指定を指定できます。  
  
-   厳密に型指定の REF CURSOR としての RETURN 句で宣言されて`TYPE StrongCurType IS REF CURSOR RETURN emp%ROWTYPE;`です。 厳密に型指定された REF カーソル変数では、その REF CURSOR 型が宣言されている型と一致するデータを含む結果セットを表すことができますのみです。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]厳密に型指定された結果 REF カーソルの厳密に型指定されたセットを返します。  
  
-   弱い型指定の REF CURSOR としての RETURN 句なしで宣言は`TYPE WeakCurType IS REF CURSOR;`します。 Oracle では、弱い型指定の REF CURSOR 変数の宣言に使用できる SYS_REFCURSOR と呼ばれる特別な REF カーソルの種類も提供します。 REF カーソル変数の弱い型指定には、あらゆる種類の行のデータを含む結果セットを表すことができます。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]弱い型指定の REF CURSOR の汎用レコードの弱い型指定の結果セットを返します。  
  
## <a name="in-ref-cursor-parameters"></a>REF CURSOR パラメーター  
 REF CURSOR でサーバーを作成、Oracle、ODP.NET API がないため、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]クライアント プログラムを作成し、REF CURSOR 変数の管理の機能を提供することはできません。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]ただし、REF CURSOR を返す PL/SQL コードのブロックを指定することによっての REF CURSOR パラメーターを関数やストアド プロシージャに渡すクライアントを有効にします。 アダプターでは、このコードを使用して作成し、Oracle サーバーで REF カーソル変数を開く関数を呼び出す、または IN パラメーターとしてこの変数を使用してストアド プロシージャを格納します。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] PL/SQL コード ブロックを含む文字列としての REF CURSOR パラメーターを表します。 このブロック内で REF カーソルの位置は疑問符 (?) で指定します。 PL/SQL のコード ブロックは、SQL クエリを含んだ開いて FOR ステートメントを含めることができます。関数またはプロシージャの呼び出しを含めることができますかで OUT パラメーターで開かれた REF カーソルが返されます。  
  
 ストアド プロシージャまたは REF カーソルをオープンする関数を呼び出すことによってで REF カーソルを指定する方法を次に示します。  
  
```  
<[IN_REF_CURSOR_PARAM_NAME]>begin [SP_NAME]([SP_PARAMS...], ?, [SP_PARAMS...]); end;</[IN_REF_CURSOR_PARAM_NAME]>  
  
Example:  
<EMP_RC>begin GETEMP(1, ?); end; </EMP_RC>  
```  
  
 REF カーソルをオープンする SELECT クエリを使用しての REF CURSOR を指定する方法を次に示します。  
  
```  
<IN_REF_CURSOR_PARAM_NAME>begin open ? for select [FIELD_NAMES] from [TABLE_NAME]; end;</IN_REF_CURSOR_PARAM_NAME>  
  
Example:  
<EMP_RC>begin open ? for select * from EMP; end;</EMP_RC>  
```  
  
## <a name="out-ref-cursor-parameters"></a>REF CURSOR パラメーターを  
 REF CURSOR 出力パラメーターに、いずれかとして厳密に型指定や、弱い型指定の結果セットが返されます。 返される結果の型は、Oracle サーバーでストアド プロシージャまたは関数定義で厳密に型指定されたか、弱い型指定の REF CURSOR として REF CURSOR パラメーターが宣言されているかどうかによって異なります。 REF CURSOR パラメーターの厳密に型指定された、厳密に型指定された結果セットが返され、弱い型指定の REF CURSOR パラメーターの厳密に型指定された結果セットが返されます (たとえば、パラメーター型で宣言されて、SYS_REFCURSOR)。  
  
 REF CURSOR 出力パラメーターの厳密に型指定された XML を次に示します。  
  
```  
<[PARAM_NAME]>  
 <[PARAM_NAME]RECORD>  
  <[COL1_NAME]>value1</[COL1_NAME]>  
  <[COL2_NAME]>value2</[COL2_NAME]>  
  ...  
 </[PARAM_NAME]RECORD>  
</[PARAM_NAME]>  
  
[PARAM_NAME] = OUT REF CURSOR parameter name; for example, EMP_REFCURSOR  
[COL_NAME] = Name of a column in the REF CURSOR type; for example, Name.  
```  
  
 弱い型指定の REF CURSOR 出力パラメーターの XML を次に示します。  
  
```  
<[PARAM_NAME]>  
 <GenRecordRow xmlns="oracledb">  
  <GenRecordColumn>  
   <ColumnName>COL_NAME</ColumnName>  
   <ColumnValue>COL_VALUE</ColumnValue>  
   <ColumnType>COL_TYPE</ColumnType>  
  </GenRecordColumn>  
  …  
 </GenRecordRow>  
 …  
</[PARAM_NAME]>  
  
[COL_NAME] = Name of column; for example, Name  
[COL_VALUE] = Column value; for example, Scott  
[COL_TYPE] = Column data type; for example, System.String  
```  
  
## <a name="in-out-ref-cursor-parameters"></a>REF CURSOR パラメーターを  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]の REF CURSOR パラメーターをモデル化文字列パラメーターと複合型としての REF CURSOR 出力パラメーターとしてサポートできない 1 つの型の REF CURSOR を IN パラメーター。 このため、REF CURSOR を IN パラメーターとして扱います 2 つの異なるパラメーター: 要求メッセージと応答メッセージの OUT パラメーターに IN パラメーター。  
  
 サービス モデルのプログラミングで名前の競合を避けるために、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] [PARAM_NAME] をという名前の指定されたパラメーター、2 つのパラメーターが作成されるため、要求メッセージで IN パラメーターに文字列"_IN"を追加します。  
  
-   [PARAM_NAME] _IN は、ストアド プロシージャまたは関数の要求メッセージ内で REF カーソル パラメーターです。 REF CURSOR を返す PL/SQL ステートメント (select クエリまたはストアド プロシージャまたは関数の呼び出し) が含まれています。  
  
-   [PARAM_NAME] は、ストアド プロシージャまたは関数の応答メッセージの REF CURSOR 出力パラメーターです。 厳密に型指定や、弱い型指定の結果セットとして除外 REF カーソルが含まれています。  
  
> [!IMPORTANT]
>  アダプターは、プロシージャまたは関数 [PARAM_NAME] _IN と [PARAM_NAME] という名前で OUT REF CURSOR パラメーターをという名前のパラメーターを含むをサポートできません。 これは、アダプターには、REF CURSOR パラメーターに入力を表す [PARAM_NAME] _IN をという名前のパラメーターが必要ですが、要求メッセージの両方のパラメーターを指定することはできません。  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter 用 Oracle Database のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)
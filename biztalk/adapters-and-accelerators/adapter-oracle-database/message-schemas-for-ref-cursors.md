---
title: REF CURSOR のメッセージ スキーマ |Microsoft Docs
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
ms.openlocfilehash: e41359bd9fa7a54a68de49bfe115ca7c563dfdb3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979019"
---
# <a name="message-schemas-for-ref-cursors"></a>REF CURSOR のメッセージ スキーマ
REF CURSOR は、結果セットで、Oracle データベースへのポインターを表す PL/SQL の Oracle データ型です。 REF カーソルの種類は、入力を有効にしてデータのストリーミングを出力しは大量のデータとの間の PL/SQL コード ブロックを転送するために最適です。 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] アウト PL/SQL プロシージャと、関数に厳密に型指定された、厳密に型指定の REF CURSOR パラメーターを渡すと IN OUT パラメーターのサポートを提供します。  
  
 Oracle データベースでは、REF CURSOR 型は厳密に型指定されたまたは、厳密に型指定を指定できます。  
  
- 厳密に型指定の REF CURSOR は、RETURN 句で宣言されて`TYPE StrongCurType IS REF CURSOR RETURN emp%ROWTYPE;`します。 REF CURSOR を厳密に型指定された変数は、その REF CURSOR 型が宣言されている型と一致するデータを含む結果セットを表すことができますのみです。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]厳密に型指定された結果 REF カーソルの厳密に型指定されたセットを返します。  
  
- RETURN 句なしで宣言は厳密に型指定の REF CURSOR`TYPE WeakCurType IS REF CURSOR;`します。 Oracle では、厳密に型指定の REF CURSOR 変数を宣言するために使用できる SYS_REFCURSOR と呼ばれる特殊な REF CURSOR 型も提供します。 REF カーソル変数の厳密に型指定には、あらゆる種類の行のデータを含む結果セットを表すことができます。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]厳密に型指定の REF CURSOR の汎用レコードの厳密に型指定の結果セットを返します。  
  
## <a name="in-ref-cursor-parameters"></a>REF CURSOR パラメーターで  
 Oracle サーバーで REF カーソルを作成する ODP.NET API がないため、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]クライアント プログラムを作成し、REF カーソル変数の管理の機能を提供することはできません。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]ただし、REF CURSOR を返す PL/SQL コードのブロックを指定することで関数やストアド プロシージャに IN REF CURSOR パラメーターを渡すのクライアントを有効にします。 アダプターでは、このコードを使用して作成し、Oracle サーバーで REF カーソル変数を開く関数を呼び出す、またはストアド プロシージャに IN パラメーターとして、この変数を使用します。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] PL/SQL コード ブロックを含む文字列としての REF CURSOR パラメーターを表します。 このブロック内で REF カーソルの位置は疑問符 (?) で指定します。 PL/SQL コード ブロックは、SQL クエリを含むオープン FOR ステートメントを含めることができます。関数またはプロシージャの呼び出しを含めることができますで OUT パラメーターに開かれた REF カーソルが返されます。  
  
 ストアド プロシージャまたは REF カーソルをオープンする関数を呼び出すことによってで REF カーソルを指定する方法を次に示します。  
  
```  
<[IN_REF_CURSOR_PARAM_NAME]>begin [SP_NAME]([SP_PARAMS...], ?, [SP_PARAMS...]); end;</[IN_REF_CURSOR_PARAM_NAME]>  
  
Example:  
<EMP_RC>begin GETEMP(1, ?); end; </EMP_RC>  
```  
  
 REF カーソルをオープンする SELECT クエリを使用して、内の REF CURSOR を指定する方法を次に示します。  
  
```  
<IN_REF_CURSOR_PARAM_NAME>begin open ? for select [FIELD_NAMES] from [TABLE_NAME]; end;</IN_REF_CURSOR_PARAM_NAME>  
  
Example:  
<EMP_RC>begin open ? for select * from EMP; end;</EMP_RC>  
```  
  
## <a name="out-ref-cursor-parameters"></a>REF CURSOR パラメーターを  
 REF CURSOR 出力パラメーターに、いずれかとして厳密に型指定された、または厳密に型指定の結果セットが返されます。 返される結果の型は、Oracle サーバーでストアド プロシージャまたは関数定義で厳密に型指定された、または厳密に型指定の REF CURSOR としての REF CURSOR パラメーターが宣言されているかどうかによって異なります。 REF CURSOR パラメーターの厳密に型指定された、厳密に型指定された結果セットが返され、厳密に型指定の REF CURSOR パラメーターの厳密に型指定の結果セットが返されます (SYS_REFCURSOR 型でパラメーター宣言など)。  
  
 REF CURSOR を厳密に型指定されたパラメーターの XML を次に示します。  
  
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
  
 REF CURSOR を厳密に型指定されたパラメーターの XML を次に示します。  
  
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
  
## <a name="in-out-ref-cursor-parameters"></a>REF CURSOR パラメーターを IN  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]モデル内の REF CURSOR パラメーターとして文字列と複合型としての REF CURSOR 出力パラメーターでは、REF CURSOR を IN パラメーターの 1 つの型をサポートすることはできません。 このため、異なる 2 つのパラメーターとしての REF CURSOR を IN パラメーターが処理: 要求メッセージと応答メッセージで OUT パラメーターに IN パラメーター。  
  
 サービス モデルのプログラミングで名前の競合を回避するために、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] [PARAM_NAME] という名前の指定されたパラメーターの場合は、2 つのパラメーターが作成されるように、要求メッセージで IN パラメーターに文字列"_IN"を追加します。  
  
-   [PARAM_NAME] _IN は、ストアド プロシージャまたは関数の要求メッセージ内で REF カーソル パラメーターです。 REF CURSOR を返す PL/SQL ステートメント (select クエリまたはストアド プロシージャまたは関数の呼び出し) が含まれています。  
  
-   [PARAM_NAME] は、ストアド プロシージャまたは関数の応答メッセージの REF CURSOR 出力パラメーターです。 厳密に型指定された、または厳密に型指定の結果セットとしてアウト REF カーソルが含まれています。  
  
> [!IMPORTANT]
>  アダプターは、プロシージャまたは IN パラメーターと REF CURSOR を IN パラメーター [PARAM_NAME] という名前の [PARAM_NAME] _IN という名前を含む関数をサポートできません。 これは、アダプターを REF CURSOR パラメーターへの入力を表す [PARAM_NAME] _IN という名前のパラメーターが必要ですが、要求メッセージの両方のパラメーターを指定することはできません。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for Oracle Database 用のメッセージとメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)
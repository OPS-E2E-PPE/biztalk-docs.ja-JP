---
title: SQLEXECUTE 操作のメッセージ スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SQLEXECUTE operations, message schemas for
ms.assetid: 744645f4-0674-44e0-bf8d-8df70086b0f1
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f753d2dcbd5782f456b099174e0369e37cca2e6f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981483"
---
# <a name="message-schemas-for-the-sqlexecute-operation"></a>SQLEXECUTE 操作のメッセージ スキーマ
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] LOB システムに存在する成果物の厳密に型指定されたメタデータを表示し、これらの成果物の標準的な操作を公開します。 ただし、アプリケーションが、アプリケーションでビジネス ロジックによって駆動される任意の SQL ステートメントの実行を必要がありますのシナリオがあります。 たとえば、しをたい場合があります。  
  
- 表示されませんがデータベースのアイテムに対して操作を実行、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 たとえば、CURVAL または Oracle のシーケンスの NEXTVAL を取得します。  
  
- データ定義言語の操作を実行します。たとえば、テーブルを作成します。  
  
- デザイン時になかったデータベース成果物に対して操作を実行します。たとえば、ビジネス ロジックによって作成される一時テーブル内のレコードを更新します。  
  
- によって表示される演算よりもテーブルでより複雑な DML 操作を実行、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; の例は、JOIN 句を含むクエリを実行します。  
  
  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェスのようなシナリオをサポートするために、SQLEXECUTE 操作と呼ばれる特別な操作です。 このオペレーションを使用しての任意の SQL ステートメントを指定することができます、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースで実行します。 SQL ステートメントへの入力パラメーターの複数のブロックを指定することもできます。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]パラメーターのセットごとに、SQL ステートメントを実行し、汎用的な (弱い型指定) のレコード セットとして出力を返します。  
  
> [!NOTE]
>  渡すことができ、プロシージャ、関数、および SQLEXECUTE 操作内のパッケージには、IN OUT パラメーター。 Oracle データベースで指定されたパラメーターで呼び出された成果物が実行されます。ただし、SQLEXECUTE 操作がタイムアウトの値を返されませんとクライアントの OUT パラメーター。 専用の操作を呼び出して実行をプロシージャ、関数、またはパッケージを呼び出す場合は、Microsoft にお勧めする[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]これら Oracle の成果物を公開します。  
  
 次の XML は、SQLEXECUTE 操作の構造を示しています。  
  
```  
<SQLEXECUTE xmlns="SQLEXECUTE">  
  <SQLSTATEMENT> [STATEMENT] </SQLSTATEMENT>  
  <PARAMETERSCHEMA>[PARAM_SPEC]</PARAMETERSCHEMA>  
  <PARAMETERSET>  
    <PARAMETERDATA>  
      <PARAMETER xmlns:c="http://schemas.microsoft.com/2003/10/Serialization/Arrays">  
        <c:string>[PARAM_VAL_1]</c:string>  
      </PARAMETER>  
    </PARAMETERDATA>  
    …  
  </PARAMETERSET>  
</SQLEXECUTE>  
```  
  
 [ステートメント]; を実行する SQL ステートメントを =たとえば、"選択 * emp から WHERE empno =: emp_no"。  
  
 [PARAM_SPEC] SQL ステートメントとそのデータ型は IN パラメーターの一覧を =たとえば、"emp_no 数"です。  
  
 [PARAM_VAL_1] = 最初のパラメーターの値。  
  
 各\<PARAMETERDATA\>セクションには、完全なセットが含まれています。\<パラメーター\>内のスキーマに一致する要素、 \<PARAMETERSCHEMA\>セクション。 \<PARAMETERSET\>複数含めることができます\<PARAMETERDATA\>セクション。 大文字と小文字の場合は、SQL ステートメントは各パラメーターのセットに対して 1 回の繰り返しで実行されます。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for Oracle Database 用のメッセージとメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)
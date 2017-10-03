---
title: "関数名と REF カーソル Parameters1 プロシージャに対する操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6801c1e-7992-40a0-bab7-87957840cedd
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dee169bca7546c404edaccce6b7a1835e3c209a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-functions-and-procedures-with-ref-cursor-parameters"></a>関数と REF CURSOR パラメーターを持つプロシージャに対する操作
REF CURSOR は、クエリを実行することによって生成されるサーバー側の結果セットへのポインターを表す PL/SQL データ型です。 REF カーソルの種類の入力と出力データのストリーミングとは大量の PL/SQL コードとの間のデータを転送するのに最適。 

## <a name="strongly-typed-and-weakly-typed-ref-cursors"></a>厳密に型指定され、弱い型指定の REF Cursor
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] PL/SQL プロシージャおよび関数として IN および OUT パラメーターに渡すことができる厳密に型指定され、弱い型指定の (SYS_REFCURSOR) REF Cursor のサポートを提供します。  
  
-   **REF CURSOR に**です。 アダプターのクライアントは、Oracle データベースで REF カーソルをオープンする PL/SQL コード (文字列) として指定することによっての REF CURSOR を使用する必要があります。 アダプターは、変数を作成および開かれた REF カーソルを設定し、関数またはその変数にプロシージャを呼び出します。 したがっての REF CURSOR パラメーター PL/SQL ストアド プロシージャ、関数は、REF CURSOR 出力変数とマークする入力値として PL/SQL コード ブロックを取得する文字列として表す必要があります、"?"。  
  
-   **REF CURSOR を**です。 REF CURSOR 出力パラメーターに、いずれかとして厳密に型指定や、弱い型指定の結果セットが返されます。 返される結果の型は、Oracle サーバーでストアド プロシージャまたは関数定義で厳密に型指定されたか、弱い型指定の REF CURSOR として REF CURSOR パラメーターが宣言されているかどうかによって異なります。  
  
-   **REF CURSOR 出力パラメーターで**です。  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]の REF CURSOR パラメーターをモデル化文字列パラメーターと複合型としての REF CURSOR 出力パラメーターとしてサポートできない 1 つの型の REF CURSOR を IN パラメーター。 このため、REF CURSOR を IN パラメーターとして扱います 2 つの異なるパラメーター: 要求メッセージと応答メッセージの OUT パラメーターに IN パラメーター。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)
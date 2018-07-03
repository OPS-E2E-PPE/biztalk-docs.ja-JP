---
title: REF カーソル Parameters1 関数とプロシージャに対する操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6801c1e-7992-40a0-bab7-87957840cedd
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7227d6fd100714c0b467f0b43537b364af98d37
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978651"
---
# <a name="operations-on-functions-and-procedures-with-ref-cursor-parameters"></a>関数および REF CURSOR パラメーターを使用したプロシージャに対する操作
REF CURSOR は、クエリの実行によって生成されるサーバー側の結果セットへのポインターを表す PL/SQL データ型です。 REF CURSOR 型はにより、入力データのストリーミングを出力して、大量の PL/SQL コードとの間のデータを転送するために最適です。 

## <a name="strongly-typed-and-weakly-typed-ref-cursors"></a>厳密に型指定された、厳密に型指定の REF Cursor
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] PL/SQL プロシージャや関数として IN および OUT パラメーターに渡すことができる厳密に型指定された、厳密に型指定の (SYS_REFCURSOR) REF Cursor のサポートを提供します。  
  
- **REF CURSOR の**します。 アダプター クライアントは、Oracle データベースで REF カーソルをオープンする PL/SQL コード (文字列) として指定することによって内の REF CURSOR を使用する必要があります。 アダプターは、変数を作成し、開かれた REF カーソルを設定し、関数または変数を持つプロシージャを呼び出します。 そのための REF CURSOR パラメーター PL/SQL ストアド プロシージャと関数を REF カーソルを変数とマークする入力値として PL/SQL コード ブロックを取得する文字列として表す必要があります、"?"。  
  
- **REF CURSOR を**します。 REF CURSOR 出力パラメーターに、いずれかとして厳密に型指定された、または厳密に型指定の結果セットが返されます。 返される結果の型は、Oracle サーバーでストアド プロシージャまたは関数定義で厳密に型指定された、または厳密に型指定の REF CURSOR としての REF CURSOR パラメーターが宣言されているかどうかによって異なります。  
  
- **REF CURSOR 出力パラメーターで**します。  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]モデル内の REF CURSOR パラメーターとして文字列と複合型としての REF CURSOR 出力パラメーターでは、REF CURSOR を IN パラメーターの 1 つの型をサポートすることはできません。 このため、異なる 2 つのパラメーターとしての REF CURSOR を IN パラメーターが処理: 要求メッセージと応答メッセージで OUT パラメーターに IN パラメーター。  
  
## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)
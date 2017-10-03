---
title: "関数と Oracle データベースの REF CURSOR パラメーターを持つプロシージャに対する操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IN REF CURSOR
- REF CURSOR
- OUT REF CURSOR
- IN OUT REF CURSOR
ms.assetid: 691c4aca-3454-41d6-b211-a4d37f215331
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a918553cd687d80a5898c7171981dffbcf7b092c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-functions-and-procedures-with-ref-cursor-parameters-in-oracle-database"></a>関数と Oracle データベースの REF CURSOR パラメーターを持つプロシージャに対する操作
REF CURSOR は、クエリを実行することによって生成されるサーバー側の結果セットへのポインターを表す PL/SQL データ型です。 REF カーソルの種類の入力と出力データのストリーミングとは大量の PL/SQL コードとの間のデータを転送するのに最適。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]でとして、PL/SQL プロシージャと関数を OUT を渡すことができる厳密に型指定され、弱い型指定の (SYS_REFCURSOR) REF カーソルまたはローカルの OUT パラメーターのサポートを提供します。  
  
-   **REF CURSOR に**です。 アダプターのクライアントは、Oracle データベースで REF カーソルをオープンする PL/SQL コード (文字列) として指定することによっての REF CURSOR を使用する必要があります。 アダプターは、変数を作成および開かれた REF カーソルを設定し、関数またはその変数にプロシージャを呼び出します。 したがっての REF CURSOR パラメーター PL/SQL ストアド プロシージャ、関数は、REF CURSOR 出力変数とマークする入力値として PL/SQL コード ブロックを取得する文字列として表す必要があります、"?"。  
  
-   **REF CURSOR を**です。 REF CURSOR 出力パラメーターに、いずれかとして厳密に型指定や、弱い型指定の結果セットが返されます。 返される結果の型は、Oracle サーバーでストアド プロシージャまたは関数定義で厳密に型指定されたか、弱い型指定の REF CURSOR として REF CURSOR パラメーターが宣言されているかどうかによって異なります。  
  
-   **REF CURSOR 出力パラメーターで**です。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]の REF CURSOR パラメーターをモデル化文字列パラメーターと複合型としての REF CURSOR 出力パラメーターとしてサポートできない 1 つの型の REF CURSOR を IN パラメーター。 このため、REF CURSOR を IN パラメーターとして扱います 2 つの異なるパラメーター: 要求メッセージと応答メッセージの OUT パラメーターに IN パラメーター。  
  
 詳細については。  
  
-   関数またはを使用して REF CURSOR パラメーターを使用するプロシージャを呼び出す、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[関数の呼び出しと BizTalk Server を使用して Oracle データベース内の REF CURSOR を持つプロシージャ](../../adapters-and-accelerators/adapter-oracle-database/run-functions-and-procedures-with-ref-cursors-in-oracle-db-using-biztalk-server.md)です。  
  
-   関数または WCF サービス モデルを使用して REF CURSOR パラメーターを使用するプロシージャを呼び出してを参照してください[実行操作を使用して REF CURSOR、WCF サービス モデルを使用して Oracle データベースで](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md)です。  
  
-   サポートされている REF CURSOR の XML 構造、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[REF CURSOR のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-ref-cursors.md)です。  
  
## <a name="see-also"></a>参照  
 [アダプターを使用して Oracle データベースへの接続します。](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-using-the-adapter.md)
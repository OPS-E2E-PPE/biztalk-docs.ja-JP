---
title: 関数と Oracle データベースの REF CURSOR パラメーターを使用したプロシージャに対する操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IN REF CURSOR
- REF CURSOR
- OUT REF CURSOR
- IN OUT REF CURSOR
ms.assetid: 691c4aca-3454-41d6-b211-a4d37f215331
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 847bf5f06f573b717a5845741fec35d163b66139
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376160"
---
# <a name="operations-on-functions-and-procedures-with-ref-cursor-parameters-in-oracle-database"></a>関数と Oracle データベースの REF CURSOR パラメーターを使用したプロシージャに対する操作
REF CURSOR は、クエリの実行によって生成されるサーバー側の結果セットへのポインターを表す PL/SQL データ型です。 REF CURSOR 型はにより、入力データのストリーミングを出力して、大量の PL/SQL コードとの間のデータを転送するために最適です。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] PL/SQL プロシージャと、関数、渡すことができる厳密に型指定された、厳密に型指定の (SYS_REFCURSOR) REF カーソルまたはローカルの OUT パラメーターのサポートを提供します。  
  
- **REF CURSOR の**します。 アダプター クライアントは、Oracle データベースで REF カーソルをオープンする PL/SQL コード (文字列) として指定することによって内の REF CURSOR を使用する必要があります。 アダプターは、変数を作成し、開かれた REF カーソルを設定し、関数または変数を持つプロシージャを呼び出します。 そのための REF CURSOR パラメーター PL/SQL ストアド プロシージャと関数を REF カーソルを変数とマークする入力値として PL/SQL コード ブロックを取得する文字列として表す必要があります、"?"。  
  
- **REF CURSOR を**します。 REF CURSOR 出力パラメーターに、いずれかとして厳密に型指定された、または厳密に型指定の結果セットが返されます。 返される結果の型は、Oracle サーバーでストアド プロシージャまたは関数定義で厳密に型指定された、または厳密に型指定の REF CURSOR としての REF CURSOR パラメーターが宣言されているかどうかによって異なります。  
  
- **REF CURSOR 出力パラメーターで**します。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]モデル内の REF CURSOR パラメーターとして文字列と複合型としての REF CURSOR 出力パラメーターでは、REF CURSOR を IN パラメーターの 1 つの型をサポートすることはできません。 このため、異なる 2 つのパラメーターとしての REF CURSOR を IN パラメーターが処理: 要求メッセージと応答メッセージで OUT パラメーターに IN パラメーター。  
  
  詳細については。  
  
- 呼び出す関数またはプロシージャを使用して REF CURSOR パラメーターを使用する、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[関数を呼び出すと、BizTalk Server を使用して Oracle データベース内の REF CURSOR を使用したプロシージャ](../../adapters-and-accelerators/adapter-oracle-database/run-functions-and-procedures-with-ref-cursors-in-oracle-db-using-biztalk-server.md)します。  
  
- 関数または WCF サービス モデルを使用して REF CURSOR パラメーターを使用するプロシージャを呼び出しを参照してください[実行操作を使用して REF CURSOR、WCF サービス モデルを使用して Oracle データベースで](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md)します。  
  
- サポートされている REF CURSOR の XML 構造、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[の REF CURSOR のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-ref-cursors.md)します。  
  
## <a name="see-also"></a>参照  
 [アダプターを使用して Oracle データベースに接続する](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-using-the-adapter.md)
---
title: 関数と Oracle データベースでストアド プロシージャに対する操作 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- REF CURSOR
- packaged functions and procedures
- operations, on functions and stored procedures
- stored procedure
- RECORD type
- overloaded functions and procedures
ms.assetid: 18072b58-65b2-4da5-9433-ea0da4e2d4f4
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78181aae7921cad3996e4bd408e604857a2bd15e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214954"
---
# <a name="operations-on-functions-and-stored-procedures-in-oracle-database"></a>関数と Oracle データベースでストアド プロシージャでの操作
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]次のように Oracle 関数、プロシージャ、およびパッケージをサポートしています。  
  
-   **関数**操作として表示されます。 操作の名前は、Oracle 関数の名前です。 出し、および OUT パラメーターはサポートし、同様に、値を返します。  
  
-   **プロシージャ**操作として表示されます。 操作の名前は、Oracle のプロシージャの名前です。 出し、および OUT パラメーターはサポートされています。  
  
-   **関数およびプロシージャをパッケージ化**操作として表示されます。 処理 (関数またはプロシージャ) の名前空間と名前は、Oracle パッケージの名前で修飾されます。 オーバー ロードは、(次の項目を参照してください) のパッケージでサポートされます。  
  
-   **オーバー ロードされた関数とプロシージャ**パッケージでの操作として表示されます。 それぞれのオーバー ロード関数またはプロシージャは、オーバー ロードを識別する名前に追加される文字列を確認します。 この文字列は、"overload1"、"overload2"、"overload3"と順序などの一部です。  
  
-   **REF CURSOR 型**はサポートされて IN、OUT、おりで OUT パラメーター プロシージャおよび関数、および関数の値を返します。 詳細については、次を参照してください。[関数および REF CURSOR パラメーターを持つプロシージャで操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md)です。  
  
-   **レコードの種類**はサポートされて IN、OUT、おりで OUT パラメーター プロシージャおよび関数、および関数の値を返します。 単純または複雑なの両方の (入れ子になった) レコードの種類がサポートされています。 [関数およびレコードの種類のプロシージャでの操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-record-types1.md)  
  
 詳細については。  
  
-   使用して、Oracle のプロシージャまたは関数を呼び出す[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[関数の呼び出しおよび BizTalk Server を使用して Oracle データベースでプロシージャ](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-biztalk-server.md)と[オーバー ロード関数の呼び出しとプロシージャを使用して Oracle データベースBizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-overloaded-functions-and-procedures-in-oracle-database-using-biztalk-server.md)です。  
  
-   WCF サービス モデルを使用して、Oracle のプロシージャまたは関数の呼び出しを参照してください[関数の呼び出しと、WCF サービス モデルを使用して Oracle データベースでプロシージャ](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)です。  
  
-   WCF チャネル モデルを使用して、Oracle のプロシージャまたは関数の呼び出しを参照してください[WCF チャネル モデルを使用して Oracle データベース内の関数を呼び出す](../../adapters-and-accelerators/adapter-oracle-database/invoke-a-function-in-oracle-database-using-the-wcf-channel-model.md)です。  
  
-   メッセージの構造と Oracle プロシージャと関数の呼び出しは、「を使用する SOAP アクション[関数およびプロシージャのメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md)です。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)
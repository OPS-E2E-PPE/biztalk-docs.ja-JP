---
title: 関数と Oracle データベースでストアド プロシージャに対する操作 |Microsoft Docs
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
ms.openlocfilehash: 2e091c31879fadef5c30ac25671297c3f18152b8
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528986"
---
# <a name="operations-on-functions-and-stored-procedures-in-oracle-database"></a>関数と Oracle データベースでストアド プロシージャに対する操作
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]次のように Oracle 関数、プロシージャ、およびパッケージをサポートしています。  
  
- **関数**操作として表示されます。 操作の名前は、Oracle 関数の名前です。 出し、および OUT パラメーターはサポートされてだけでなく、戻り値。  
  
- **プロシージャ**操作として表示されます。 操作の名前は、Oracle のプロシージャの名前です。 出し、および OUT パラメーターはサポートされています。  
  
- **関数およびプロシージャにパッケージ化**操作として表示されます。 (関数またはプロシージャ) の操作の名前空間と名前については、Oracle パッケージの名前で修飾します。 オーバー ロードは、(次の箇条書きを参照してください) パッケージでサポートされます。  
  
- **オーバー ロードされた関数とプロシージャ**パッケージでの操作として表示されます。 各オーバー ロード関数またはプロシージャがオーバー ロードを識別する名前の末尾に文字列を表示します。 この文字列は、シーケンス"overload1"、"overload2"、"overload3"の一部です。  
  
- **REF CURSOR 型**IN はサポートされておりで OUT パラメーターをプロシージャと関数、および関数の戻り値。 詳細については、次を参照してください。[関数および REF CURSOR パラメーターを使用したプロシージャに対する操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md)します。  
  
- **レコードの種類**IN はサポートされておりで OUT パラメーターをプロシージャと関数、および関数の戻り値。 単純および複雑な両方の (入れ子になった) レコードの種類がサポートされています。 [RECORD 型を使用した関数およびプロシージャに対する操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-record-types1.md)  
  
  詳細については。  
  
- 使用して、Oracle のプロシージャまたは関数を呼び出す[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[関数の呼び出しと BizTalk Server を使用して Oracle データベースでプロシージャ](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-biztalk-server.md)と[オーバー ロード関数を呼び出すとプロシージャを使用して Oracle データベースBizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-overloaded-functions-and-procedures-in-oracle-database-using-biztalk-server.md)します。  
  
- WCF サービス モデルを使用して、Oracle のプロシージャまたは関数の呼び出しを参照してください[関数を呼び出すと、WCF サービス モデルを使用して Oracle データベースでプロシージャ](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)します。  
  
- WCF チャネル モデルを使用して、Oracle のプロシージャまたは関数の呼び出しを参照してください[WCF チャネル モデルを使用して Oracle データベースで関数を呼び出す](../../adapters-and-accelerators/adapter-oracle-database/invoke-a-function-in-oracle-database-using-the-wcf-channel-model.md)します。  
  
- メッセージの構造と SOAP アクションのために Oracle プロシージャと関数の呼び出しは、「[関数およびプロシージャのメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md)します。  
  
## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)
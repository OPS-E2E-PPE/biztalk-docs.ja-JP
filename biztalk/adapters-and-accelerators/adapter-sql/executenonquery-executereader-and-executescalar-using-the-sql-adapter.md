---
title: ExecuteNonQuery、ExecuteReader、および ExecuteScalar を SQL アダプターを使用して操作を実行 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fda0544-a028-4a95-aae6-1f6a90764c5d
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f68f4378a4d89d2a997f5a78a524e4f6bfca2c18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222274"
---
# <a name="run-executenonquery-executereader-and-executescalar-operations-using-the-sql-adapter"></a>ExecuteNonQuery、ExecuteReader、および ExecuteScalar を SQL アダプターを使用して操作を実行します。
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]ルート レベルで、次の操作を公開します。  
  
-   **ExecuteNonQuery**: この操作を使用するすべての結果が返されるセットしたくない場合は、SQL Server で任意の SQL ステートメントを実行します。 この操作を使用するデータベース オブジェクトを作成または更新、挿入を実行することによって、データベース内のデータを変更したり、ステートメントを削除できます。 この操作の戻り値が Int32 データ型、および。  
  
    -   UPDATE、INSERT、および DELETE ステートメントでは、戻り値は、SQL ステートメントによって影響を受ける行の数です。  
  
    -   その他のすべての種類のステートメントでは、戻り値は **-1**です。  
  
-   **ExecuteReader**: この操作を使用する場合、結果セットに返されるデータセットの配列として、任意の場合は、SQL Server で任意の SQL ステートメントを実行します。 データセットについてで「データセット クラス」を参照してください。 [http://go.microsoft.com/fwlink/?LinkID=196853](http://go.microsoft.com/fwlink/?LinkID=196853)です。  
  
-   **ExecuteScalar**: この操作を 1 つの値を返す SQL Server での任意の SQL ステートメントの実行に使用します。 この操作は、SQL ステートメントによって返される結果セットの最初の行の最初の列でのみ、値を返します。  
  
    > [!NOTE]
    >  ExecuteReader に対する ExecuteScalar の利点を ExecuteScalar 操作の応答メッセージのペイロードが非常に小さくなってと比較するが ExecuteReader 操作によって返される 1 つ。 したがって、返される値を 1 つだけを必要とする場合は、ExecuteReader ではなく ExecuteScalar を使用する必要があります。  
  
 ExecuteNonQuery、ExecuteReader または ExecuteScalar 操作を使用すると、複数の SQL ステートメントを実行します。  
  
 使用してこれらの操作の実行の詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[ExecuteReader、ExecuteScalar、または BizTalk Server を使用して、ExecuteNonQuery 操作](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)です。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)
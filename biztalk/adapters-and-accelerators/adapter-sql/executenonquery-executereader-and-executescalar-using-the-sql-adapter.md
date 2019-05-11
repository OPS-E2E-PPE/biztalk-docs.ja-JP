---
title: ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作の SQL アダプターを使用しての実行 |Microsoft Docs
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
ms.openlocfilehash: 0e4a32828be8fbaaa65263c24aa98ff1cfd957ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369537"
---
# <a name="run-executenonquery-executereader-and-executescalar-operations-using-the-sql-adapter"></a>ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作の SQL アダプターを使用してを実行します。
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]ルート レベルでは、次の操作を公開します。  
  
- **ExecuteNonQuery**:この操作を使用して、すべての結果が返されるセットしたくない場合は、SQL Server で任意の SQL ステートメントを実行します。 この操作を使用して、データベース オブジェクトを作成または更新、挿入を実行することによってデータベース内のデータを変更またはステートメントを削除できます。 この操作の戻り値が Int32 データ型、および。  
  
  -   UPDATE、INSERT、および DELETE ステートメントでは、戻り値は、SQL ステートメントによって影響を受ける行の数です。  
  
  -   その他のすべての種類のステートメントでは、戻り値は **-1**します。  
  
- **ExecuteReader**:この操作を使用して、結果データセットの配列として存在する場合に返されるセットの場合は、SQL Server で任意の SQL ステートメントを実行します。 データセットの詳細についてを参照してください「DataSet クラス」 [ http://go.microsoft.com/fwlink/?LinkID=196853](http://go.microsoft.com/fwlink/?LinkID=196853)します。  
  
- **ExecuteScalar**:SQL server を 1 つの値を返す任意の SQL ステートメントを実行するのにには、この操作を使用します。 この操作は、SQL ステートメントによって返される結果セットの最初の行の最初の列でのみ、値を返します。  
  
  > [!NOTE]
  >  ExecuteReader 経由で ExecuteScalar の利点は、ExecuteScalar 操作の応答メッセージのペイロードが ExecuteReader 操作によって返されるものと比較されますかなり短くなります。 したがって、返される値の 1 つだけを必要とする場合は、ExecuteReader ではなく ExecuteScalar を使用する必要があります。  
  
  ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作を使用して、複数の SQL ステートメントを実行することができます。  
  
  使用してこれらの操作の実行の詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[ExecuteReader、executescalar、ExecuteNonQuery 操作を使用して BizTalk Server によって](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)します。  
  
## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)
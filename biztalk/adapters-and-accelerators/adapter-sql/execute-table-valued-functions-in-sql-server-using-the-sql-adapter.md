---
title: SQL アダプタを使用して SQL Server でテーブル値関数を実行 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fb8c81c-9384-4eba-b0a0-baed1782245b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e69877f214a2a4b700de22ec043094510707114d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222282"
---
# <a name="execute-table-valued-functions-in-sql-server-using-the-sql-adapter"></a>SQL アダプタを使用して SQL Server でテーブル値関数を実行します。
SQL Server で Transact SQL と CLR テーブル値関数での操作として表示された[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]です。 内の操作名、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]値関数で SQL Server テーブルの名前と同じであります。  
  
 テーブル値関数のすべてのパラメーターは、対応する操作で公開されます。 テーブル値関数の場合、入力パラメーターが指定されていない場合、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]内部的に DEFAULT キーワードを使用して関数を呼び出します。 これは、関数を定義する際に指定した既定値を使用して、テーブル値関数を実行することを意味します。  
  
 詳細については。  
  
-   使用して、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] BizTalk Server を SQL Server でのテーブル値関数を呼び出すと、次を参照してください。 [Invoking Table-Valued 関数を使用して BizTalk Server で、SQL Server で](../../adapters-and-accelerators/adapter-sql/invoke-table-valued-functions-in-sql-server-using-biztalk-server.md)です。  
  
-   メッセージの構造とテーブル値関数用の SOAP アクションを参照してください[プロシージャと関数のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md)です。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)
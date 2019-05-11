---
title: SQL アダプターを使用して SQL Server でのテーブル値関数の実行 |Microsoft Docs
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
ms.openlocfilehash: 48597c430bf2c77956476cbd689ec29bdc44b5af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369522"
---
# <a name="execute-table-valued-functions-in-sql-server-using-the-sql-adapter"></a>SQL アダプターを使用して SQL Server でのテーブル値関数の実行します。
SQL Server で Transact SQL と CLR テーブル値関数での操作として表示された[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]します。 内の操作名、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]値関数で SQL Server テーブルの名前と同じです。  
  
 テーブル値関数のすべてのパラメーターは、対応する操作で公開されます。 テーブル値関数の場合、入力パラメーターを指定しない場合、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]内部的に DEFAULT キーワードを使用して、関数を呼び出します。 これは、関数を定義するときに指定された既定値を使用して、テーブル値関数を実行することを意味します。  
  
 詳細については。  
  
- 使用して、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server でのテーブル値関数を呼び出すための BizTalk Server で、次を参照してください。 [Invoking Table-Valued 関数を使用して BizTalk Server によって SQL Server で](../../adapters-and-accelerators/adapter-sql/invoke-table-valued-functions-in-sql-server-using-biztalk-server.md)します。  
  
- メッセージの構造とテーブル値関数用の SOAP アクションを参照してください[プロシージャと関数のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md)します。  
  
## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)
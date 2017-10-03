---
title: "SQL アダプタを使用して SQL Server で複合操作を実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 906c6352-44f3-4624-9e32-aea3fbb7510d
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c36a1ff6e4b2c7d4d56855ce1531f99cd490a2a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="run-composite-operations-in-sql-server--using-the-sql-adapter"></a>SQL アダプタを使用して SQL Server での複合操作を実行します。
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]アダプター クライアントが、SQL Server データベースでの複合操作を実行できるようにします。 複合操作は、次の操作、および任意の順序で任意の数を含めることができます。  
  
-   テーブルおよびビューに対する Insert、Update、および Delete 操作。  
  
-   アダプターでの操作として表示されたストアド プロシージャです。  
  
 複合操作の操作は、*必要があります*テーブルとビューを 1 つのデータベースでのみを対象します。  
  
 詳細については。  
  
-   複合操作を実行する方法[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を使用して、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[SQL Server を使用して BizTalk Server での複合操作を実行](../../adapters-and-accelerators/adapter-sql/run-composite-operations-on-sql-server-using-biztalk-server.md)です。  
  
-   メッセージ複合操作のスキーマを参照してください[複合操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md)です。  
  
> [!IMPORTANT]
>  "N"を返す操作で複合操作ではさまざまな接続の数に設定し、"n+1"結果は複合操作が実行する必要があります。 したがって、ことを確認用に指定された値、 **MaxConnectionPoolSize** n+1 プロパティのバインドは以上です。 詳細については、 **MaxConnectionPoolSize**バインディング プロパティを参照してください[BizTalk Adapter for SQL Server のアダプターのバインドのプロパティについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)
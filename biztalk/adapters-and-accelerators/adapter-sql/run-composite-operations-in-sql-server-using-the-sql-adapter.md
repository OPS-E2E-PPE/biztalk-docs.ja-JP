---
title: SQL アダプターを使用して SQL Server で複合操作の実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 906c6352-44f3-4624-9e32-aea3fbb7510d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5acf0eca210bd163c0d74e7d8d873ec6009d40a5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999283"
---
# <a name="run-composite-operations-in-sql-server--using-the-sql-adapter"></a>SQL アダプターを使用して SQL Server で複合操作を実行します。
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]アダプター クライアントが SQL Server データベースでの複合操作を実行できるようにします。 複合操作では、および任意の順序で、次の操作の任意の数を含めることができます。  
  
- テーブルおよびビューに対する Insert、Update、および Delete 操作。  
  
- アダプターでの操作として表示されるストアド プロシージャ。  
  
  複合操作に含まれる操作*する必要があります*テーブルとビューでは、1 つのデータベースのみを対象します。  
  
  詳細については。  
  
- 複合操作を実行する方法[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を使用して、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[SQL Server を使用して BizTalk Server での複合操作を実行](../../adapters-and-accelerators/adapter-sql/run-composite-operations-on-sql-server-using-biztalk-server.md)します。  
  
- 複合操作のスキーマのメッセージを参照してください[複合操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md)します。  
  
> [!IMPORTANT]
>  "N"の数を返す複合操作での操作がある接続の数に設定し、"n+1"結果は複合操作が実行する必要があります。 そのため、することが必要に指定された値、 **MaxConnectionPoolSize**プロパティのバインドは、n+1 以上。 詳細については、 **MaxConnectionPoolSize**プロパティ、バインドを参照してください[for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。  
  
## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)
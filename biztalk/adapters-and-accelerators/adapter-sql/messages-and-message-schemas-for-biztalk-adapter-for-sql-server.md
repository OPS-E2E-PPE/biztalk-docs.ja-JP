---
title: メッセージと BizTalk adapter for SQL Server のメッセージ スキーマ |Microsoft Docs
description: BizTalk Server の SQL Server のアダプターで使用されるメッセージとデータの型の XML 構造
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e95c6342-5420-4fb8-9b41-7c87d27b5b68
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b01d2181423e479a7c39dc680cde34eba2db79fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368524"
---
# <a name="messages-and-message-schemas-for-biztalk-adapter-for-sql-server"></a>メッセージと BizTalk adapter for SQL Server のメッセージ スキーマ

## <a name="overview"></a>概要
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。 アプリケーションがそれを呼び出すことができ、アプリケーションで呼び出すことができます、さらに、操作を公開します。 これらの操作は、チャネル経由で SOAP メッセージを送信することによって呼び出されます。 応答が必要な場合、同じチャネル経由で SOAP メッセージで返されます。  
  
 として、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]標準を使用して、その操作とデータ型のメタデータを公開する[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]メカニズム。 このトピックのセクションでは、メッセージの XML 構造を記述して、データの種類を[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を使用します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SQL Server の基本的なデータ型](../../adapters-and-accelerators/adapter-sql/basic-sql-server-data-types.md)  
  
-   [テーブルとビューに対する挿入、更新、削除、選択の各操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)  
  
-   [プロシージャと関数のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md)  
  
-   [Polling 操作と TypedPolling 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-the-polling-and-typedpolling-operations.md)  
  
-   [クエリ通知のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-query-notification.md)  
  
-   [複合操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md)  
  
-   [ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/executenonquery-executereader-and-executescalar-message-schemas-in-sql.md)  
  

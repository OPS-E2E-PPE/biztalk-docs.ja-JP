---
title: "メッセージと BizTalk Adapter for SQL Server のメッセージ スキーマを |Microsoft ドキュメント"
description: "BizTalk Server の SQL Server のアダプターで使用されるメッセージとデータの型の XML 構造"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e95c6342-5420-4fb8-9b41-7c87d27b5b68
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b1e45f0a20500253e2ca831138a21efa24df3c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="messages-and-message-schemas-for-biztalk-adapter-for-sql-server"></a>メッセージと BizTalk Adapter for SQL Server のメッセージ スキーマ

## <a name="overview"></a>概要
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。 これは、アプリケーションがそれで呼び出すことができ、アプリケーションで呼び出すことができます、さらに、操作を公開します。 これらの操作がチャネル経由で SOAP メッセージを送信することによって呼び出されます。 応答が必要な場合、同じチャネル経由で SOAP メッセージで返されます。  
  
 として、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]標準を使用してその操作とデータ型のメタデータが公開[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]メカニズムです。 このトピックのセクションでは、メッセージの XML 構造の記述し、データの種類を[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を使用します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [基本的な SQL Server データ型](../../adapters-and-accelerators/adapter-sql/basic-sql-server-data-types.md)  
  
-   [メッセージ スキーマの挿入、更新、削除、およびテーブルおよびビューの操作の選択](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)  
  
-   [プロシージャおよび関数のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md)  
  
-   [ポーリングと TypedPolling 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-the-polling-and-typedpolling-operations.md)  
  
-   [クエリ通知のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-query-notification.md)  
  
-   [複合操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md)  
  
-   [ExecuteNonQuery、ExecuteReader、および ExecuteScalar 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/executenonquery-executereader-and-executescalar-message-schemas-in-sql.md)  
  

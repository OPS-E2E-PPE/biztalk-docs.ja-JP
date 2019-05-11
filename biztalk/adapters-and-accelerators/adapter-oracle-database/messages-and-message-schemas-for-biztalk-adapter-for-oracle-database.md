---
title: メッセージとメッセージ スキーマの BizTalk Adapter for Oracle Database |Microsoft Docs
description: BizTalk server、Oracle Database アダプターによって使用されるメッセージとデータの型の XML 構造
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fee0a531-b1e6-4b99-bb79-45368c401395
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 804143e55a69f775a6d1391f57cfce8cd12d7b3a
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529008"
---
# <a name="messages-and-message-schemas-for-biztalk-adapter-for-oracle-database"></a>メッセージと BizTalk adapter for Oracle データベースのメッセージ スキーマ

## <a name="overview"></a>概要
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。 アプリケーションがそれを呼び出すことができ、アプリケーションで呼び出すことができます、さらに、操作を公開します。 これらの操作は、チャネル経由で SOAP メッセージを送信することによって呼び出されます。 応答が必要な場合、同じチャネル経由で SOAP メッセージで返されます。  
  
 として、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]標準を使用して、その操作とデータ型のメタデータを公開する[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]メカニズム。 このトピックのセクションでは、メッセージの XML 構造を記述して、データの種類を[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を使用します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [基本的な Oracle データ型](../../adapters-and-accelerators/adapter-oracle-database/basic-oracle-data-types1.md)  
  
-   [テーブルとビューに対する挿入、更新、削除、選択の各基本操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)  
  
-   [特殊な LOB 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-special-lob-operations2.md)  
  
-   [関数およびプロシージャのメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md)  
  
-   [REF CURSOR のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-ref-cursors.md)  
  
-   [レコード型のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-record-types.md)  
  
-   [SQLEXECUTE 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md)  
  
-   [ポーリング操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-polling-operations2.md)  
  
-   [複合操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md)  
  
-   [通知操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-notification-operation1.md)  
  

---
title: "Biztalk SQL アダプターを使用してクエリ通知のメッセージ スキーマ |Microsoft ドキュメント"
description: "SQL アダプターを使用して、BizTalk で SQL Server データベースからクエリ通知を受信するには"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5183655-64d4-4767-a923-0a575e3708cd
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c78c817470bd8acd41f44204653c41e9012d154
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-query-notification"></a>クエリ通知のメッセージ スキーマ
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]サーフェスの SQL Server データベースからクエリ通知を受信する通知操作します。  
  
 バインドのプロパティを設定して通知の操作を構成する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 通知に関連するバインドのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。 設定する、 **NotificationStatement** SQL ステートメントを指定するプロパティのバインド (SELECT または EXEC\<ストアド プロシージャ >)、クエリ通知のです。 このクエリの結果セットは、通知の操作で自分のコードを厳密に型指定されたデータとして返されます。  
  
## <a name="message-structure-for-the-notification-operation"></a>通知操作のメッセージの構造  
 次の表は、通知操作の XML メッセージの構造を示します。  

**操作**:`Notification`

**XML メッセージ**:  
```xml
<?xml version="1.0" encoding="utf-8" ?>
  <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification">
    <Info>Value</Info>
    <Source>Value</Source>
    <Type>Value</Type>
 </Notification>
```

**説明**: これは、SQL Server によってアダプターのクライアントに送信される受信メッセージ。 メッセージ。

- `<Info>`タグは、通知の理由を示します。 たとえば、このタグ内の「挿入」値は、通知のステートメントで参照されるテーブルの 1 つ以上のデータが挿入されたことを示します。
- `<Source>`タグは、通知の送信元を示します。 たとえば、このタグで「データ」の値では、参照されたオブジェクト内のデータの変更を示します。 同様に、このタグで「オブジェクト」の値では、参照されたオブジェクトの変更を示します。
- `<Type>`タグは、データの変更の種類を示します。 クエリ通知メッセージは、2 つの種類: 変更および定期受信します。 A「変更」の値、`<Type>`タグを示すクエリの結果が変更された一方で「サブスクライブ」の値、`<Type>`タグは、サブスクリプション要求が失敗したことを示します。

  
## <a name="message-action-for-the-notification-operation"></a>通知操作のメッセージ アクション  
 通知操作のメッセージ アクションは「通知」  
  
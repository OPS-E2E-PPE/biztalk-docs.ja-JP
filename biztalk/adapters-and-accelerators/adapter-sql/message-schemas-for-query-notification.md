---
title: Biztalk SQL アダプターを使用してクエリ通知のメッセージ スキーマ |Microsoft Docs
description: SQL アダプタを使用して、BizTalk での SQL Server データベースからクエリ通知を受け取る
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5183655-64d4-4767-a923-0a575e3708cd
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be33d8990e5577fbb52cd1d294dff4c5257c3bdf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368432"
---
# <a name="message-schemas-for-query-notification"></a>クエリ通知のメッセージ スキーマ
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]サーフェスの SQL Server データベースからクエリ通知を受信する通知操作。  
  
 バインドのプロパティを設定して、通知の操作を構成する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 通知に関連するバインドのプロパティの詳細については、次を参照してください。 [for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。 設定する、 **NotificationStatement** SQL ステートメントを指定するプロパティのバインド (SELECT または EXEC\<ストアド プロシージャ\>) のクエリ通知します。 このクエリの結果セットは、通知の操作では、コードを厳密に型指定されたデータとして返されます。  
  
## <a name="message-structure-for-the-notification-operation"></a>通知操作のメッセージの構造  
 次の表では、通知操作の XML メッセージの構造を示します。  

**操作**: `Notification`

**XML メッセージ**:  
```xml
<?xml version="1.0" encoding="utf-8" ?>
  <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification">
    <Info>Value</Info>
    <Source>Value</Source>
    <Type>Value</Type>
 </Notification>
```

**説明**:これは、SQL Server によってアダプター クライアントに送信される受信メッセージです。 メッセージ。

- `<Info>`タグは、通知の理由を示します。 たとえば、このタグ内の"insert"値は、notification ステートメントで参照されるテーブルの 1 つ以上のデータが挿入されたことを示します。
- `<Source>`タグは、通知のソースを示します。 たとえば、このタグ内の「データ」の値では、参照先オブジェクトのデータの変更を示します。 同様に、このタグ内の「オブジェクト」の値では、参照先オブジェクトの変更を示します。
- `<Type>`タグは、データの変更の種類を示します。 クエリ通知メッセージが 2 つの型: 変更およびサブスクライブします。 A は値を「変更」、`<Type>`タグが、クエリの結果が変更されたことを示しますに「サブスクライブ」の値、`<Type>`タグは、サブスクリプション要求が失敗したことを示します。

  
## <a name="message-action-for-the-notification-operation"></a>通知操作のメッセージのアクション  
 通知操作のメッセージのアクションは、「通知します」  
  
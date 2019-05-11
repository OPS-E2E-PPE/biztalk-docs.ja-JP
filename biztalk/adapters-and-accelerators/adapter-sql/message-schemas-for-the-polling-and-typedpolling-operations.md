---
title: ポーリングと TypedPolling 操作では、BizTalk SQL アダプターのメッセージ スキーマ |Microsoft Docs
description: SQL アダプターの BizTalk アダプター パック (BAP) によって使用される構造をメッセージのポーリングと TypedPolling
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1e900307-2c9c-493b-81c9-67af3e143eeb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4930e854bcad679a3b6ab8c3e90150ad3e879c98
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368612"
---
# <a name="message-schemas-for-the-polling-and-typedpolling-operations"></a>Polling 操作と TypedPolling 操作のメッセージ スキーマ
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] Polling 操作と TypedPolling サーフェスの受信アダプターのクライアントに、ポーリング クエリの結果セットを返す操作。  
  
 バインドのプロパティを設定してポーリングと TypedPolling 操作を構成する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 これらのバインド プロパティの詳細については、次を参照してください。 [for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。 設定する、 **PollingStatement** SQL ステートメントを指定するプロパティのバインド (SELECT または EXEC\<ストアド プロシージャ\>) のポーリング クエリ。 このクエリの結果セットは、ポーリング操作では、コードへのデータと TypedPolling 操作で厳密に型指定されたデータとして返されます。 結果セットの構造は、アダプターが指定されたクエリのサーフェスをメタデータによって決定されます。  
  
## <a name="polling-message-structure"></a>メッセージの構造のポーリング 
  
**操作**: `Polling`

**XML メッセージ**:  
```xml
<?xml version="1.0" encoding="utf-8" ?>
  <Polling xmlns="http://schemas.microsoft.com/Sql/2008/05/Polling">
    <PolledData>
      <DataSet xmlns="http://schemas.datacontract.org/2004/07/System.Data">
        <any>[Value]</any>
        <any>[Value]</any>
        …
        </DataSet>
    </PolledData>
 </Polling>
```

**説明**:SQL Server によってアダプター クライアントに送信される受信メッセージ。  


## <a name="typedpolling-message-structure"></a>TypedPolling メッセージの構造 

**操作**: `TypedPolling`

**XML メッセージ**:  
```xml
<?xml version="1.0" encoding="utf-8" ?>
  <TypedPollingResultSet xmlns="http://schemas.microsoft.com/Sql/2008/05/TypedPolling">
    <COLUMN1>[Value]</Column1>
    <COLUMN2>[Value]</Column2>
    …
  </TypedPollingResultSet>
```

**説明**:厳密に型指定された受信メッセージを SQL Server によってアダプター クライアントに送信されます。
  
## <a name="message-action-for-the-polling-and-typedpolling-operations"></a>Polling 操作と TypedPolling 操作のメッセージのアクション  
 メッセージのアクションにします。  
  
-   ポーリング操作が「ポーリングします。」  
  
-   TypedPolling 操作は、"TypedPolling"  
  

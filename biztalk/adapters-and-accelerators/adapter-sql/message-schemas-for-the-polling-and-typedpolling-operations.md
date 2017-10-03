---
title: "メッセージのポーリングと biztalk SQL アダプターの TypedPolling 操作のスキーマ |Microsoft ドキュメント"
description: "ポーリングと TypedPolling メッセージの BizTalk アダプター パック (BAP) で SQL アダプターによって使用される構造体"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e900307-2c9c-493b-81c9-67af3e143eeb
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f18185e4bfaf5502537a68044579b0f7721cd23
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-the-polling-and-typedpolling-operations"></a>ポーリングと TypedPolling 操作のメッセージ スキーマ
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]サーフェスのポーリングと TypedPolling 受信アダプターのクライアントに、ポーリング クエリの結果セットを返す操作。  
  
 バインドのプロパティを設定して、ポーリングおよび TypedPolling 操作を構成する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 これらのバインド プロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。 設定する、 **PollingStatement** SQL ステートメントを指定するプロパティのバインド (SELECT または EXEC\<ストアド プロシージャ >)、ポーリング クエリのです。 ポーリング操作で、コードへのデータおよび TypedPolling 操作の厳密に型指定されたデータとして、このクエリの結果セットが返されます。 結果セットの構造は、アダプターが、指定されたクエリのサーフェスをメタデータによって決定されます。  
  
## <a name="polling-message-structure"></a>メッセージの構造のポーリング 
  
**操作**:`Polling`

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

**説明**: SQL Server によってアダプターのクライアントに送信される受信メッセージ。  


## <a name="typedpolling-message-structure"></a>TypedPolling メッセージの構造体 

**操作**:`TypedPolling`

**XML メッセージ**:  
```xml
<?xml version="1.0" encoding="utf-8" ?>
  <TypedPollingResultSet xmlns="http://schemas.microsoft.com/Sql/2008/05/TypedPolling">
    <COLUMN1>[Value]</Column1>
    <COLUMN2>[Value]</Column2>
    …
  </TypedPollingResultSet>
```

**説明**: SQL Server によってアダプターのクライアントに送信される厳密に型指定された受信メッセージ。
  
## <a name="message-action-for-the-polling-and-typedpolling-operations"></a>ポーリングと TypedPolling 操作のメッセージのアクション  
 メッセージ アクション、します。  
  
-   ポーリング操作は、「ポーリングしています。」  
  
-   TypedPolling 操作は"TypedPolling"  
  

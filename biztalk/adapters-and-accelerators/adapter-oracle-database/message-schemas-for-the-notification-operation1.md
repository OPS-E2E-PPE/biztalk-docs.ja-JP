---
title: 通知 Operation1 のメッセージ スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f98d76d0-6084-4de7-b6ff-124202ca92ab
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cdf371335a1242423c4497f186fa5764f5b2fb2f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991691"
---
# <a name="message-schemas-for-the-notification-operation"></a>通知操作のメッセージ スキーマ
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle データベースからデータベース変更通知を受信する通知の操作を表示します。  
  
 バインドのプロパティを設定して、通知の操作を構成する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 通知に関連するバインドのプロパティの詳細については、[Oracle データベース アダプターのバインドのプロパティについて](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)を参照してください。 設定する、 **NotificationStatement**クエリ通知の SELECT ステートメントを指定するプロパティをバインドします。  
  
## <a name="message-structure-for-the-notification-operation"></a>通知操作のメッセージの構造  
 次の表では、通知操作の XML メッセージの構造を示します。  
  
|演算|XML メッセージ|説明|  
|---------------|-----------------|-----------------|  
|Notification|`<?xml version="1.0" encoding="utf-8" ?>  <Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification">    <Info>Value</Info>    <Source>Value</Source>    <Type>Value</Type> </Notification>`|これは、Oracle データベース アダプターのクライアントに送信される受信メッセージです。 メッセージ。<br /><br /> -`<Info>`タグは、通知の理由を示します。 たとえば、このタグ内の"insert"値は、notification ステートメントで参照されるテーブルの 1 つ以上のデータが挿入されたことを示します。<br /><br /> -`<Source>`タグは、通知のソースを示します。 たとえば、このタグ内の「データ」の値では、参照先オブジェクトのデータの変更を示します。 同様に、このタグ内の「オブジェクト」の値では、参照先オブジェクトの変更を示します。<br /><br /> -`<Type>`タグは、データの変更の種類を示します。 たとえば、"Update"の値、`<Type>`タグは、クエリの結果が更新されていることを示します。|  
  
## <a name="message-action-for-the-notification-operation"></a>通知操作のメッセージのアクション  
 通知操作のメッセージのアクションが"<http://Microsoft.LobServices.OracleDB/2007/03/Notification”>します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for Oracle Database 用のメッセージとメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)
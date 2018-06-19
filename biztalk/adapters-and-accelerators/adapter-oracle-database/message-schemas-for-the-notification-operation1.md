---
title: メッセージ通知 Operation1 のスキーマ |Microsoft ドキュメント
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
ms.openlocfilehash: dd0d7513a0a439d34d5bfb4722fec2b9025e676b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214098"
---
# <a name="message-schemas-for-the-notification-operation"></a>通知操作のメッセージ スキーマ
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle データベースからデータベースの変更通知を受信する通知操作を表示します。  
  
 バインドのプロパティを設定して通知の操作を構成する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。 通知に関連するバインドのプロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについてお読み](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)です。 設定する、 **NotificationStatement**クエリ通知の SELECT ステートメントを指定するプロパティをバインドします。  
  
## <a name="message-structure-for-the-notification-operation"></a>通知操作のメッセージの構造  
 次の表は、通知操作の XML メッセージの構造を示します。  
  
|操作|XML メッセージ|Description|  
|---------------|-----------------|-----------------|  
|Notification|`<?xml version="1.0" encoding="utf-8" ?>  <Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification">    <Info>Value</Info>    <Source>Value</Source>    <Type>Value</Type> </Notification>`|これは、Oracle データベースでアダプターのクライアントに送信される受信メッセージです。 メッセージ。<br /><br /> -`<Info>`タグは、通知の理由を示します。 たとえば、このタグ内の「挿入」値は、通知のステートメントで参照されるテーブルの 1 つ以上のデータが挿入されたことを示します。<br /><br /> -`<Source>`タグは、通知の送信元を示します。 たとえば、このタグで「データ」の値では、参照されたオブジェクト内のデータの変更を示します。 同様に、このタグで「オブジェクト」の値では、参照されたオブジェクトの変更を示します。<br /><br /> -`<Type>`タグは、データの変更の種類を示します。 たとえば、"Update"の値、`<Type>`タグは、クエリの結果が更新されていることを示します。|  
  
## <a name="message-action-for-the-notification-operation"></a>通知操作のメッセージ アクション  
 通知操作のメッセージ アクションは、"http://Microsoft.LobServices.OracleDB/2007/03/Notification"です。  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter 用 Oracle Database のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)
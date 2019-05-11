---
title: 通知 Operation2 のメッセージ スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dddab2ef-94db-46c8-95c1-57517681e8dd
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1226f31c43b3274c841f92473807d3d4bc709090
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530677"
---
# <a name="message-schemas-for-the-notification-operation"></a>通知操作のメッセージ スキーマ
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]Oracle E-business Suite で基になるデータベースからデータベース変更通知を受信する通知の操作を表示します。  
  
 バインドのプロパティを設定して、通知の操作を構成する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 通知に関連するバインドのプロパティの詳細については、次を参照してください。 [Oracle E-business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。 設定する、 **NotificationStatement**クエリ通知の SELECT ステートメントを指定するプロパティをバインドします。  
  
## <a name="message-structure-for-the-notification-operation"></a>通知操作のメッセージの構造  
 次の表では、通知操作の XML メッセージの構造を示します。  
  
|演算|XML メッセージ|説明|  
|---------------|-----------------|-----------------|  
|Notification|`<?xml version="1.0" encoding="utf-8" ?>  <Notification xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Notification">    <Info>Value</Info>    <Source>Value</Source>    <Type>Value</Type> </Notification>`|これは、Oracle E-business Suite アダプター クライアントに送信される受信メッセージです。 メッセージ。<br /><br /> -`<Info>`タグは、通知の理由を示します。 たとえば、このタグ内の"insert"値は、notification ステートメントで参照されるテーブルの 1 つ以上のデータが挿入されたことを示します。<br /><br /> -`<Source>`タグは、通知のソースを示します。 たとえば、このタグ内の「データ」の値では、参照先オブジェクトのデータの変更を示します。 同様に、このタグ内の「オブジェクト」の値では、参照先オブジェクトの変更を示します。<br /><br /> -`<Type>`タグは、データの変更の種類を示します。 たとえば、"Update"の値、`<Type>`タグは、クエリの結果が更新されていることを示します。|  
  
## <a name="message-action-for-the-notification-operation"></a>通知操作のメッセージのアクション  
 通知操作のメッセージのアクションは、「通知します」  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter for Oracle E-business Suite のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)
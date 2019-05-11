---
title: メッセージのポーリング Operations2 スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- POLLINGSTMT operation, message actions for
- POLLINGSTMT operation, message structure for
ms.assetid: b82edcc2-9437-4c7b-ba2b-7b966fff3f15
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5bde545d960537d264024d32fbdb053f6b4e2ba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376399"
---
# <a name="message-schemas-for-the-polling-operations"></a>ポーリング操作のメッセージ スキーマ
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]ポーリングによっては、Oracle データベースのターゲット オブジェクトに関連する、さまざまな受信操作を表示します。 テーブルとビューをポーリングするには、ストアド プロシージャ、関数、およびパッケージ化されたプロシージャと関数は、ポーリングの受信操作として公開されますが、1 つの POLLINGSTMT 操作に表示されます。  
  
 指定することができます、 **PollingId** POLLINGSTMT 操作の名前空間を修飾する接続 URI のクエリ文字列パラメーター。 POLLINGSTMT 操作の名前空間を修飾のみこのパラメーターを設定メッセージのアクションは変更されません。 Oracle データベース アダプターの接続 URI の詳細については、次を参照してください。 [Oracle Database 接続 URI の作成](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)です。  
  
 バインドのプロパティを設定してポーリング操作を構成する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 これらのバインド プロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについて](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)します。 設定する、 **PollingStatement** SQL ステートメント、ストアド プロシージャ、関数、またはポーリング クエリ用のパッケージ内のプロシージャを指定するプロパティをバインドします。 このクエリの結果セットは、ポーリング操作では、コードをデータとして返されます。  
  
## <a name="message-structure-for-the-polling-operations"></a>ポーリング操作のメッセージの構造  
 次の表では、さまざまなポーリング操作の XML メッセージの構造を示します。  
  
|操作|[対象になるオブジェクト]|XML メッセージ|説明|  
|---------------|-------------------|-----------------|-----------------|  
|POLLINGSTMT|-テーブル<br /><br /> ビュー|`<?xml version="1.0" encoding="utf-8" ?>  <POLLINGSTMT xmlns="[VERSION]/POLLINGSTMT[POLLING_ID]">   <POLLINGSTMTRECORD>     <POLLINGSTMTRECORD>       <FIELD1_NAME>val1</FIELD1_NAME>        <FIELD2_NAME>val2</FIELD2_NAME>       …     </POLLINGSTMTRECORD>      …    </POLLINGSTMTRECORD> </POLLINGSTMT>`|結果 POLLINGSTMTRECORD 型に格納されているセットの構造は、サーフェス SQL SELECT クエリ用のアダプター メタデータによって決まります。<br /><br /> POLLINGSTMT 操作の名前空間は、接続 URI の PollingId パラメーターによって決定されます。|  
|[CustomPollingOperation]|-ストアド プロシージャ<br /><br /> -関数<br /><br /> -パッケージ|**ストアド プロシージャ**<br /><br /> `<?xml version="1.0" encoding="utf-8" ?>  <[CustomPollingOperation] xmlns="[Version]/[SCHEMA]/PollingProcedure">    <[CustomPollingOperation]Result>      <PRM1>[Value]</PRM1>      <PRM2>[Value]</PRM2>      …    </[CustomPollingOperation]Result> </[CustomPollingOperation]>`<br /><br /> **関数**<br /><br /> `<?xml version="1.0" encoding="utf-8" ?> <[CustomPollingOperation] xmlns="[Version]/[Schema]/PollingFunction">    <[CustomPollingOperation]Result>      <COL1>[Value]</COL1]>      <COL2>[Value]</COL2>      …    </[CustomPollingOperation]Result> </[CustomPollingOperation]>`<br /><br /> **パッケージ**<br /><br /> `<?xml version="1.0" encoding="utf-8" ?>  <[CustomPollingOperation] xmlns="[Version]/[Schema]/PollingPackage/[PACKAGE_NAME]/">    <[CustomPollingOperation]Result>[Value]</[CustomPollingOperation]Result> </[CustomPollingOperation]>`|ポーリング操作の結果セットの構造については、対象オブジェクト内の要素のデータ型によって決まります。|  
  
 [バージョン] =http://Microsoft.LobServices.OracleDB/2007/03します。  
  
 [CustomPollingOperation] = ストアド プロシージャ、関数、またはパッケージ化されたプロシージャまたは関数名、ポーリングの受信操作として公開されると同じです。  
  
 [スキーマ] = Oracle スキーマの名前。 たとえば、SCOTT です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for Oracle Database 用のメッセージとメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)
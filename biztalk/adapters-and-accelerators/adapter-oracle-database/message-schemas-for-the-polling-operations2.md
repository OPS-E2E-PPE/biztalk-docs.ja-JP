---
title: ポーリング Operations2 のメッセージ スキーマ |Microsoft ドキュメント
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
ms.openlocfilehash: beb28e7b769c16f1798023adb8b30c3e636a3407
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214602"
---
# <a name="message-schemas-for-the-polling-operations"></a>ポーリング操作のメッセージ スキーマ
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]ポーリングによっては、Oracle データベースのターゲット オブジェクトに関連するさまざまな受信操作を表示します。 テーブルとビューをポーリングするには、ストアド プロシージャ、関数、およびパッケージ化したプロシージャと関数は、ポーリングの受信操作として公開されますが、1 つの POLLINGSTMT 操作が確認できます。  
  
 指定することができます、 **PollingId**接続 POLLINGSTMT 操作の名前空間を修飾するために URI のクエリ文字列のパラメーターです。 POLLINGSTMT 操作の名前空間を修飾のみこのパラメーターを設定メッセージのアクションは変更されません。 Oracle データベース アダプターの接続 URI の詳細については、次を参照してください。 [Oracle Database 接続 URI を作成する](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)です。  
  
 バインドのプロパティを設定してポーリング操作を構成する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。 これらのバインド プロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについてお読み](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)です。 設定する、 **PollingStatement** SQL ステートメント、ストアド プロシージャ、関数、またはポーリング クエリ用のパッケージ内の手順を指定するプロパティをバインドします。 このクエリの結果セットは、ポーリング操作で自分のコードをデータとして返されます。  
  
## <a name="message-structure-for-the-polling-operations"></a>ポーリング操作のメッセージの構造  
 次の表は、さまざまな操作をポーリングの XML メッセージの構造を示します。  
  
|操作|[対象になるオブジェクト]|XML メッセージ|Description|  
|---------------|-------------------|-----------------|-----------------|  
|POLLINGSTMT|-テーブル<br /><br /> -ビュー|`<?xml version="1.0" encoding="utf-8" ?>  <POLLINGSTMT xmlns="[VERSION]/POLLINGSTMT[POLLING_ID]">   <POLLINGSTMTRECORD>     <POLLINGSTMTRECORD>       <FIELD1_NAME>val1</FIELD1_NAME>        <FIELD2_NAME>val2</FIELD2_NAME>       …     </POLLINGSTMTRECORD>      …    </POLLINGSTMTRECORD> </POLLINGSTMT>`|結果 POLLINGSTMTRECORD 型に含まれているセットの構造はサーフェス SQL SELECT クエリ用のアダプター メタデータによって決定されます。<br /><br /> POLLINGSTMT 操作の名前空間は、接続 URI の PollingId パラメーターによって決定されます。|  
|[CustomPollingOperation]|ストアド プロシージャ<br /><br /> 関数<br /><br /> -パッケージ|**ストアド プロシージャ**<br /><br /> `<?xml version="1.0" encoding="utf-8" ?>  <[CustomPollingOperation] xmlns="[Version]/[SCHEMA]/PollingProcedure">    <[CustomPollingOperation]Result>      <PRM1>[Value]</PRM1>      <PRM2>[Value]</PRM2>      …    </[CustomPollingOperation]Result> </[CustomPollingOperation]>`<br /><br /> **関数**<br /><br /> `<?xml version="1.0" encoding="utf-8" ?> <[CustomPollingOperation] xmlns="[Version]/[Schema]/PollingFunction">    <[CustomPollingOperation]Result>      <COL1>[Value]</COL1]>      <COL2>[Value]</COL2>      …    </[CustomPollingOperation]Result> </[CustomPollingOperation]>`<br /><br /> **パッケージ**<br /><br /> `<?xml version="1.0" encoding="utf-8" ?>  <[CustomPollingOperation] xmlns="[Version]/[Schema]/PollingPackage/[PACKAGE_NAME]/">    <[CustomPollingOperation]Result>[Value]</[CustomPollingOperation]Result> </[CustomPollingOperation]>`|ポーリング操作の結果セットの構造は、対象オブジェクト内の要素のデータ型によって決定されます。|  
  
 [バージョン] http://Microsoft.LobServices.OracleDB/2007/03 を = です。  
  
 [CustomPollingOperation] = ストアド プロシージャ、関数、またはパッケージ化されたプロシージャまたは関数名と受信ポーリング操作として公開されている同じになります。  
  
 [スキーマ] = Oracle スキーマの名前。 たとえば、SCOTT です。  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter 用 Oracle Database のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)
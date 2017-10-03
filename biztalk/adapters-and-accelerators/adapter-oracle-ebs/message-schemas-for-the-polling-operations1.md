---
title: "ポーリング Operations1 のメッセージ スキーマ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c572c4ec-0a3f-42b8-bebd-40eb584438ad
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee61aa47a7f991c140e0c0659b67da658a11a7ac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-the-polling-operations"></a>ポーリング操作のメッセージ スキーマ
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]ポーリングによっては、Oracle E-business Suite でターゲット オブジェクトに関連するさまざまな受信操作を表示します。 インターフェイス テーブル、インターフェイス ビュー、テーブル、およびビュー、PL/SQL Api、関数、およびストアド プロシージャの複数のカスタム ポーリング操作を持つことができますが、1 つのポーリング操作が確認できます。  
  
 バインドのプロパティを設定してポーリング操作を構成する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 これらのバインド プロパティの詳細については、次を参照してください。 [Oracle E-business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。 設定する、 **PollingStatement** SQL ステートメント、ストアド プロシージャ、関数、またはポーリング クエリ用のパッケージ内の手順を指定するプロパティをバインドします。 このクエリの結果セットは、ポーリング操作で自分のコードをデータとして返されます。  
  
## <a name="message-structure-for-the-polling-operations"></a>ポーリング操作のメッセージの構造  
 次の表は、さまざまな操作をポーリングの XML メッセージの構造を示します。  
  
> [!NOTE]
>  表の後に、エンティティの説明を参照してください。  
  
|操作|[対象になるオブジェクト]|XML メッセージ|Description|  
|---------------|-------------------|-----------------|-----------------|  
|ポーリング|インターフェイス テーブル<br /><br /> インターフェイス ビュー<br /><br /> -テーブル<br /><br /> -ビュー|`<?xml version="1.0" encoding="utf-8" ?>  <Poll xmlns="[Version]/[TargetObject]/[Schema]/[TargetObject_Name]">    <DATA>      <SelectRecord>        <Column1>[Value]</Column1>        <Column2>[Value]</Column2>        …        </SelectRecord>    </DATA> </Poll>`|たとえば、インターフェイスのテーブルに対してポーリング操作の XML メッセージがとおりになります。<br /><br /> `<?xml version="1.0" encoding="utf-8" ?>  <Poll xmlns="[Version]/InterfaceTables/[Schema]/[InterfaceTable_Name]">    <DATA>      <SelectRecord>        <Column1>[Value]</Column1>        <Column2>[Value]</Column2>        …        </SelectRecord>    </DATA> </Poll>`|  
|[CustomPollingOperation]|-PL/SQL Api<br /><br /> ストアド プロシージャ<br /><br /> 関数|**PL/SQL Api**<br /><br /> `<?xml version="1.0" encoding="utf-8" ?>  <[CustomPollingOperation] xmlns="[Version]/PollingPackageAPis/[Schema]/[PL/SQL API]">    <[CustomPollingOperation]Result>[Value]</[CustomPollingOperation]Result> </[CustomPollingOperation]>`<br /><br /> **関数**<br /><br /> `<?xml version="1.0" encoding="utf-8" ?> <[CustomPollingOperation] xmlns="[Version]/PollingFunctions/[Schema]">    <[CustomPollingOperation]Result>      <COL1>[Value]</COL1]>      <COL2>[Value]</COL2>      …    </[CustomPollingOperation]Result> </[CustomPollingOperation]>`<br /><br /> **ストアド プロシージャ**<br /><br /> `<?xml version="1.0" encoding="utf-8" ?>  <[CustomPollingOperation] xmlns="[Version]/PollingFunctions/[Schema]">    <[CustomPollingOperation]Result>      <PRM1>[Value]</PRM1>      <PRM2>[Value]</PRM2>      …    </[CustomPollingOperation]Result> </[CustomPollingOperation]>`|ポーリング操作の結果セットの構造は、対象オブジェクト内の要素のデータ型によって決定されます。|  
  
 エンティティの説明  
  
 [バージョン] http://schemas.microsoft.com/OracleEBS/2008/05 を = です。  
  
 [CustomPollingOperation] カスタム ポーリング操作の名前を = です。  
  
 [スキーマ] = Oracle スキーマの名前。 たとえば、SCOTT です。  
  
 [PL/SQL API]、カスタムのポーリング操作を実行するときの PL/SQL API の名前を = です。  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter for Oracle E-business Suite のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)
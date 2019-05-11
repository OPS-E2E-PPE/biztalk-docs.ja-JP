---
title: メッセージのポーリング Operations1 スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c572c4ec-0a3f-42b8-bebd-40eb584438ad
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0475c94ef6838e02e4f81f27df7ee9b2df70bfc1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375993"
---
# <a name="message-schemas-for-the-polling-operations"></a>ポーリング操作のメッセージ スキーマ
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]ポーリングによって Oracle E-business Suite 内のターゲット オブジェクトに関連する、さまざまな受信操作を表示します。 インターフェイス テーブル、インターフェイス ビュー、テーブルとビューは、PL/SQL Api、関数、およびストアド プロシージャの複数のカスタム ポーリング操作があることができますが、1 つのポーリング操作が表示されるようにします。  
  
 バインドのプロパティを設定してポーリング操作を構成する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 これらのバインド プロパティの詳細については、次を参照してください。 [Oracle E-business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。 設定する、 **PollingStatement** SQL ステートメント、ストアド プロシージャ、関数、またはポーリング クエリ用のパッケージ内のプロシージャを指定するプロパティをバインドします。 このクエリの結果セットは、ポーリング操作では、コードをデータとして返されます。  
  
## <a name="message-structure-for-the-polling-operations"></a>ポーリング操作のメッセージの構造  
 次の表では、さまざまなポーリング操作の XML メッセージの構造を示します。  
  
> [!NOTE]
>  表の後は、エンティティの説明を参照してください。  
  
|操作|[対象になるオブジェクト]|XML メッセージ|説明|  
|---------------|-------------------|-----------------|-----------------|  
|ポーリング|インターフェイス テーブル<br /><br /> インターフェイス ビュー<br /><br /> -テーブル<br /><br /> ビュー|`<?xml version="1.0" encoding="utf-8" ?>  <Poll xmlns="[Version]/[TargetObject]/[Schema]/[TargetObject_Name]">    <DATA>      <SelectRecord>        <Column1>[Value]</Column1>        <Column2>[Value]</Column2>        …        </SelectRecord>    </DATA> </Poll>`|たとえば、インターフェイス テーブルにポーリング操作の XML メッセージがとおりになります。<br /><br /> `<?xml version="1.0" encoding="utf-8" ?>  <Poll xmlns="[Version]/InterfaceTables/[Schema]/[InterfaceTable_Name]">    <DATA>      <SelectRecord>        <Column1>[Value]</Column1>        <Column2>[Value]</Column2>        …        </SelectRecord>    </DATA> </Poll>`|  
|[CustomPollingOperation]|-PL/SQL Api<br /><br /> -ストアド プロシージャ<br /><br /> -関数|**PL/SQL Api**<br /><br /> `<?xml version="1.0" encoding="utf-8" ?>  <[CustomPollingOperation] xmlns="[Version]/PollingPackageAPis/[Schema]/[PL/SQL API]">    <[CustomPollingOperation]Result>[Value]</[CustomPollingOperation]Result> </[CustomPollingOperation]>`<br /><br /> **関数**<br /><br /> `<?xml version="1.0" encoding="utf-8" ?> <[CustomPollingOperation] xmlns="[Version]/PollingFunctions/[Schema]">    <[CustomPollingOperation]Result>      <COL1>[Value]</COL1]>      <COL2>[Value]</COL2>      …    </[CustomPollingOperation]Result> </[CustomPollingOperation]>`<br /><br /> **ストアド プロシージャ**<br /><br /> `<?xml version="1.0" encoding="utf-8" ?>  <[CustomPollingOperation] xmlns="[Version]/PollingFunctions/[Schema]">    <[CustomPollingOperation]Result>      <PRM1>[Value]</PRM1>      <PRM2>[Value]</PRM2>      …    </[CustomPollingOperation]Result> </[CustomPollingOperation]>`|ポーリング操作の結果セットの構造については、対象オブジェクト内の要素のデータ型によって決まります。|  
  
 エンティティの説明  
  
 [バージョン] =http://schemas.microsoft.com/OracleEBS/2008/05します。  
  
 [CustomPollingOperation] = カスタム ポーリング操作の名前。  
  
 [スキーマ] = Oracle スキーマの名前。 たとえば、SCOTT です。  
  
 [PL/SQL API] = カスタム ポーリング操作を実行する、PL/SQL API の名前。  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter for Oracle E-business Suite のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)
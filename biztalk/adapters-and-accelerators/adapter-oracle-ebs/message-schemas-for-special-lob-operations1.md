---
title: "特殊な LOB Operations1 のメッセージ スキーマ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2e418a6-8bc7-42d9-9672-a9c149f32778
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b57e329d1de4740cac230cbb1e8151697d293dc7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="message-schemas-for-special-lob-operations"></a>特殊な LOB 操作のメッセージ スキーマ
Read_\<LOBColName\>と Update_\<LOBColName\>テーブルおよび LOB 列を含むビューの操作が表示された場所\<LOBColName\>テーブルの LOB 列は、または表示します。 これらの操作では、base64Binary でエンコードされたデータのストリームとして、LOB データを読み書きできます。 1 つの行に LOB データの 1 つの列上で動作します。  
  
 Read_ の概要については\<LOBColName\>と Update_\<LOBColName\>操作し、Oracle LOB データ型のサポートされている、次を参照してください[インターフェイス テーブル、インターフェイス ビュー、テーブルに対する操作と。LOB データを含むビュー](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)です。  
  
## <a name="message-structure-of-lob-data-type-operations"></a>LOB データ型の操作のメッセージの構造  
 次の表では、要求と応答メッセージの構造を示します、Read_ の\<LOBColName\>と Update_\<LOBColName\>操作します。 操作の対象テーブルでは、メッセージのアクションで指定され、ターゲットの名前空間にも表示されます。  
  
> [!NOTE]
>  表の後に、エンティティの説明を参照してください。  
  
|操作|XML メッセージ|Description|  
|---------------|-----------------|-----------------|  
|Read_\<LOBColName\>|`<Read_[LOBColName] xmlns="[VERSION]/Tables/[SCHEMA]/[TABLE_NAME]">  <FILTER>[WHERE_clause]</FILTER></Read_[LOBColName]>`|LOB データ、一致する行が where フィルター要素で指定された句が返されます。 Where 句が 1 つの行のみを一致する必要があります。 1 つ以上の一致する行がある場合、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]例外がスローされます。|  
|Read_\<LOBColName\>応答|`<Read_[LOBColName]Response xmlns="[VERSION]/Tables/[SCHEMA]/[TABLE_NAME]">  <Read_[LOBColName]Result>    [LOB_DATA]  </Read_[LOBColName]Result></Read_[LOBColName]Response>`|LOB データは、base64Binary でエンコードされたデータのストリームとして返されます。|  
|Update_\<LOBColName\>|`<Update_[LOBColName] xmlns="[VERSION]/Tables/[SCHEMA]/[TABLE_NAME]">  <FILTER>[WHERE_clause]</LOB_COLUMN>  <DATA>[Value]</DATA></Update_[LOBColName]>`|LOB データ where に一致する行のフィルター要素で指定されている句は、データで更新、\<データ\>要素。 Where 句が 1 つの行のみを一致する必要があります。 1 つ以上の一致する行がある場合、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]例外をスローします。<br /><br /> **注**BLOB 列の更新中に、\<データ\>要素に base64 でエンコードされた値が含まれて常にする必要があります。 CLOB、NCLOB、ため、\<データ\>要素は、文字列値を持つことができます。|  
|Update_\<LOBColName\>応答|`<Update_[LOBColName]Response xmlns="[VERSION]/Tables/[SCHEMA]/[TABLE_NAME]"></Update_[LOBColName]Response>`|空の応答が返されます。|  
  
 エンティティの説明  
  
 [バージョン]、メッセージのバージョン文字列を =たとえば、"http://schemas.microsoft.com/OracleEBS/2008/05"です。  
  
 [スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。  
  
 [TABLE_NAME] を対象となる、LOB の列を含むテーブルを =たとえば、顧客です。  
  
 [LOBCol_Name]、LOB の列の名前を =たとえば、写真。  
  
 [WHERE_clause] に Oracle データベースの SELECT ステートメントです 1 つの行に一致する WHERE 句を =。たとえば、ID = 1 です。  
  
 [LOB_DATA] base64Binary 型の列のデータ、LOB を = です。  
  
> [!IMPORTANT]
>  メッセージ構造、Read_\<LOBColName\>と Update_\<LOBColName\>ビューでの操作と同じテーブルが操作の名前空間は、テーブルではなく、ビューを指定する点を除いて`<ReadLOB xmlns ="[VERSION]/Views/[SCHEMA]/[VIEW_NAME]">`。  
  
## <a name="message-actions-for-lob-data-type-operations"></a>メッセージの動作の LOB データ型の操作  
 次の表は、メッセージ アクションで使用される、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] 、Read_ の\<LOBColName\>と Update_\<LOBColName\>テーブルに対する操作です。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]対象のテーブルを特定し、LOB 操作の列をテーブル名とメッセージのアクションで指定された LOB の列名を使用します。  
  
> [!NOTE]
>  表の後に、エンティティの説明を参照してください。  
  
|操作|操作|例|  
|---------------|------------|-------------|  
|Read_\<LOBColName\>|`Tables/ReadLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]`|`Tables/ReadLOB/SCOTT/CUSTOMER/Photo`|  
|Read_\<LOBColName\>応答|`Tables/ReadLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]/response`|`Tables/ReadLOB/SCOTT/CUSTOMER/Photo/response`|  
|Update_\<LOBColName\>|**BLOB の**:<br /><br /> `Tables/UpdateBLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]`<br /><br /> **CLOB や NCLOB を**:<br /><br /> `Tables/UpdateCLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]`|**BLOB の**:<br /><br /> `Tables/UpdateBLOB/SCOTT/CUSTOMER/Photo/`<br /><br /> **CLOB や NCLOB を**:<br /><br /> `Tables/UpdateCLOB/SCOTT/CUSTOMER/Photo1/`|  
|Update_\<LOBColName\>応答|**BLOB の**:<br /><br /> `Tables/UpdateBLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]/response`<br /><br /> **CLOB や NCLOB を**:<br /><br /> `Tables/UpdateCLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]/response`|**BLOB の**:<br /><br /> `Tables/UpdateBLOB/SCOTT/CUSTOMER/Photo/response`<br /><br /> **CLOB や NCLOB を**:<br /><br /> `Tables/UpdateCLOB/SCOTT/CUSTOMER/Photo1/response`|  
  
 エンティティの説明  
  
 [スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。  
  
 [TABLE_NAME] を対象となる、LOB の列を含むテーブルを =たとえば、顧客です。 (SCOTT です。CUSTOMER テーブルではインストール SQL スクリプトのサンプルに含まれています。)  
  
 [LOBCol_Name]、LOB の列の名前を =たとえば、写真。  
  
> [!IMPORTANT]
>  Read_ のメッセージ アクション\<LOBColName\>と Update_\<LOBColName\>操作ビューに似ていますが、テーブルは、使用されている操作のアクションは、テーブルではなく、ビューを指定します: `Views/ReadLOB/[SCHEMA]/[VIEW_NAME]/[LOBColName]` 。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for Oracle E-Business Suite 用のメッセージとメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)
---
title: 特殊な LOB Operations1 のメッセージ スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2e418a6-8bc7-42d9-9672-a9c149f32778
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc8461bf0f70515344206e677d2fa95d8c2858a1
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528958"
---
# <a name="message-schemas-for-special-lob-operations"></a>特殊な LOB 操作のメッセージ スキーマ
Read_\<LOBColName\>と Update_\<LOBColName\>テーブルと LOB の列を含むビューの操作が表示される場所\<LOBColName\>テーブルの LOB 列は、または表示します。 これらの操作では、base64Binary でエンコードされたデータのストリームとして LOB データを読み書きできます。 1 つの行の LOB データの 1 つの列で動作します。  
  
 Read_ の概要については\<LOBColName\>と Update_\<LOBColName\>操作と、Oracle LOB データ型のサポートされている、次を参照してください[インターフェイス テーブル、インターフェイス ビュー、テーブル、での操作と。LOB データを含むビュー](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)します。  
  
## <a name="message-structure-of-lob-data-type-operations"></a>LOB データ型の操作のメッセージの構造  
 次の表では、要求と応答メッセージの構造を示します、Read_ の\<LOBColName\>と Update_\<LOBColName\>操作。 操作の対象テーブルでは、メッセージのアクションで指定され、ターゲットの名前空間にも表示されます。  
  
> [!NOTE]
>  表の後は、エンティティの説明を参照してください。  
  
|           操作            |                                                                                  XML メッセージ                                                                                  |                                                                                                                                                                                                                                                              説明                                                                                                                                                                                                                                                              |
|--------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      Read_\<LOBColName\>       |                           `<Read_[LOBColName] xmlns="[VERSION]/Tables/[SCHEMA]/[TABLE_NAME]">  <FILTER>[WHERE_clause]</FILTER></Read_[LOBColName]>`                           |                                                                                                           LOB データの場所に一致する行のフィルター要素で指定した句が返されます。 Where 句は 1 つの行と一致する必要があります。 1 つ以上の一致する行がある場合、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]例外がスローされます。                                                                                                            |
|  Read_\<LOBColName\>応答  | `<Read_[LOBColName]Response xmlns="[VERSION]/Tables/[SCHEMA]/[TABLE_NAME]">  <Read_[LOBColName]Result>    [LOB_DATA]  </Read_[LOBColName]Result></Read_[LOBColName]Response>` |                                                                                                                                                                                                                                  LOB データは、base64Binary でエンコードされたデータのストリームとして返されます。                                                                                                                                                                                                                                   |
|     Update_\<LOBColName\>      |            `<Update_[LOBColName] xmlns="[VERSION]/Tables/[SCHEMA]/[TABLE_NAME]">  <FILTER>[WHERE_clause]</LOB_COLUMN>  <DATA>[Value]</DATA></Update_[LOBColName]>`            | LOB データの場所に一致する行でフィルター要素で指定した句は内のデータで更新、\<データ\>要素。 Where 句は 1 つの行と一致する必要があります。 1 つ以上の一致する行がある場合、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]例外をスローします。<br /><br /> **注**、BLOB 列の更新中に、\<データ\>要素が常に base64 でエンコードされた値を含めることが必要があります。 CLOB、NCLOB、ため、\<データ\>要素は、文字列値を持つことができます。 |
| Update_\<LOBColName\>応答 |                                 `<Update_[LOBColName]Response xmlns="[VERSION]/Tables/[SCHEMA]/[TABLE_NAME]"></Update_[LOBColName]Response>`                                  |                                                                                                                                                                                                                                                    空の応答が返されます。                                                                                                                                                                                                                                                     |
  
 エンティティの説明  
  
 [バージョン] = メッセージ バージョン文字列。たとえば、"<http://schemas.microsoft.com/OracleEBS/2008/05>"。  
  
 [スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。  
  
 [TABLE_NAME] を対象となる、LOB の列を含むテーブルを =たとえば、顧客です。  
  
 [LOBCol_Name]、LOB 列の名前を =たとえば、写真。  
  
 [WHERE_clause] に Oracle データベースの SELECT ステートメントは 1 つの行に一致する WHERE 句を =たとえば、ID = 1。  
  
 [LOB_DATA] base64Binary 型で、LOB 列のデータを = です。  
  
> [!IMPORTANT]
>  メッセージの構造、Read_ の\<LOBColName\>と Update_\<LOBColName\>ビューに対する操作ですと同じテーブルに対する操作の名前空間は、テーブルではなく、ビューを指定します。`<ReadLOB xmlns ="[VERSION]/Views/[SCHEMA]/[VIEW_NAME]">`.  
  
## <a name="message-actions-for-lob-data-type-operations"></a>LOB データ型の操作のメッセージのアクション  
 次の表は、メッセージのアクションで使用される、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] 、Read_ の\<LOBColName\>と Update_\<LOBColName\>テーブルに対する操作。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]対象のテーブルを特定し、LOB 操作の列をテーブル名とメッセージのアクションで指定された LOB の列名を使用します。  
  
> [!NOTE]
>  表の後は、エンティティの説明を参照してください。  
  
|操作|操作|例|  
|---------------|------------|-------------|  
|Read_\<LOBColName\>|`Tables/ReadLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]`|`Tables/ReadLOB/SCOTT/CUSTOMER/Photo`|  
|Read_\<LOBColName\>応答|`Tables/ReadLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]/response`|`Tables/ReadLOB/SCOTT/CUSTOMER/Photo/response`|  
|Update_\<LOBColName\>|**BLOB の**:<br /><br /> `Tables/UpdateBLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]`<br /><br /> **CLOB、NCLOB**:<br /><br /> `Tables/UpdateCLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]`|**BLOB の**:<br /><br /> `Tables/UpdateBLOB/SCOTT/CUSTOMER/Photo/`<br /><br /> **CLOB、NCLOB**:<br /><br /> `Tables/UpdateCLOB/SCOTT/CUSTOMER/Photo1/`|  
|Update_\<LOBColName\>応答|**BLOB の**:<br /><br /> `Tables/UpdateBLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]/response`<br /><br /> **CLOB、NCLOB**:<br /><br /> `Tables/UpdateCLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]/response`|**BLOB の**:<br /><br /> `Tables/UpdateBLOB/SCOTT/CUSTOMER/Photo/response`<br /><br /> **CLOB、NCLOB**:<br /><br /> `Tables/UpdateCLOB/SCOTT/CUSTOMER/Photo1/response`|  
  
 エンティティの説明  
  
 [スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。  
  
 [TABLE_NAME] を対象となる、LOB の列を含むテーブルを =たとえば、顧客です。 (SCOTT します。CUSTOMER テーブルではインストールのサンプルに含まれる SQL スクリプト。)  
  
 [LOBCol_Name]、LOB 列の名前を =たとえば、写真。  
  
> [!IMPORTANT]
>  Read_ のメッセージ アクション\<LOBColName\>と Update_\<LOBColName\>操作ビューに似ていますが、テーブルは、使用されている操作のアクションは、テーブルではなく、ビューを指定します: `Views/ReadLOB/[SCHEMA]/[VIEW_NAME]/[LOBColName]` .  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter for Oracle E-business Suite のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)
---
title: 特殊な LOB Operations2 のメッセージ スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- LOB data types, message structure of
- LOB data types, message actions for
ms.assetid: 031989d5-3209-41ab-8836-a40539781e74
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f9451b12da100081aa4bf820345aa7703c81dfd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376428"
---
# <a name="message-schemas-for-special-lob-operations"></a>特殊な LOB 操作のメッセージ スキーマ
テーブルとビューは LOB 列が含まれているため、ReadLOB および UpdateLOB 操作が表示されます。Oracle のラージ オブジェクト (LOB) データの格納に使用される列です。 これらの操作では、base64Binary でエンコードされたデータのストリームとして LOB データを読み書きできます。 1 つの行の LOB データの 1 つの列で動作します。  

 ReadLOB と UpdateLOB 操作とサポートされる Oracle LOB データ型の概要を参照してください。[テーブルと Oracle データベースで LOB データを含むビューで操作](../../adapters-and-accelerators/adapter-oracle-database/operations-on-tables-and-views-that-contain-lob-data-in-oracle-database.md)します。  

## <a name="message-structure-of-lob-data-type-operations"></a>LOB データ型の操作のメッセージの構造  
 次の表は、ReadLOB および UpdateLOB 操作の要求と応答メッセージの構造を示します。 操作の対象テーブルでは、メッセージのアクションで指定され、ターゲットの名前空間にも表示されます。  


|     操作      |                                                                                    XML メッセージ                                                                                     |                                                                                                                                                                                                                                                                                                                                説明                                                                                                                                                                                                                                                                                                                                 |
|--------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      ReadLOB       |                  `<ReadLOB xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   <LOB_COLUMN>[COL_NAME]</LOB_COLUMN>   <FILTER>[WHERE_clause]</LOB_COLUMN> </ReadLOB>`                  | 内の LOB データ、<br /><br /> -LOB_COLUMN 要素によって識別される列と、<br /><br /> -行の場所に一致するフィルター要素で指定した句<br /><br /> 返されます。<br /><br /> Where 句は 1 つの行と一致する必要があります。 1 つ以上の一致する行がある場合は、最初の一致する行に LOB データが返されます。<br /><br /> **重要な**ReadLOB 操作は、WCF サービス モデル内の LOB データの入力ストリームをサポートするために設計されています。 WCF チャネル モデルから LOB データを読み取るテーブルの選択操作を使用する必要がありますまたは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューション。 |
|  ReadLOB 応答  |                      `<ReadLOBResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   <ReadLOBResult>     [LOB_DATA]   </ReadLOBResult> </ReadLOBResponse>`                      |                                                                                                                                                                                                                            LOB データは、base64Binary でエンコードされたデータのストリームとして返されます。<br /><br /> **重要な**アダプターによって返される WSDL が ReadLOB 応答メッセージに対して、アダプターによって使用される実際のスキーマと一致しません。                                                                                                                                                                                                                            |
|     UpdateLOB      | `<UpdateLOB xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   <LOB_COLUMN>[COL_NAME]</LOB_COLUMN>   <FILTER>[WHERE_clause]</LOB_COLUMN>   <Stream>[LOB_DATA]</Stream> </UpdateLOB>` |                                                                                            内の LOB データ、<br /><br /> -LOB_COLUMN 要素によって識別される列と、<br /><br /> -行の場所に一致するフィルター要素で指定した句<br /><br /> ストリーム内の base64Binary でエンコードされたデータで更新されます。<br /><br /> Where 句は 1 つの行と一致する必要があります。 1 つ以上の一致する行がある場合、例外がスローされます。<br /><br /> **注**すべての指定した列と行のデータ、UpdateLOB 操作が置き換えられます。                                                                                             |
| UpdateLOB 応答 |                                              `<UpdateLOBResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]"> </UpdateLOBResponse>`                                              |                                                                                                                                                                                                                                                                                                                       空の応答が返されます。                                                                                                                                                                                                                                                                                                                       |

 [バージョン] = メッセージ バージョン文字列。たとえば、"<http://Microsoft.LobServices/OracleDB/2007/03>"。  

 [スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。  

 [TABLE_NAME] を対象となる、LOB の列を含むテーブルを =たとえば、EMP です。  

 [COL_NAME] 対象となる、LOB の列の名前を =たとえば、LOB_FIELD です。  

 [WHERE_clause] に Oracle データベースの SELECT ステートメントは 1 つの行に一致する WHERE 句を =たとえば、ID = 1。  

 [LOB_DATA] base64Binary 型で、LOB 列のデータを = です。  

> [!IMPORTANT]
>  ビューで ReadLOB と UpdateLOB の操作のメッセージの構造と同じテーブルで操作の名前空間は、テーブルではなく、ビューを指定する点を除いて:`<ReadLOB xmlns ="[VERSION]/[SCHEMA]/``View``/[VIEW_NAME]">`します。  

## <a name="message-actions-for-lob-data-type-operations"></a>LOB データ型の操作のメッセージのアクション  
 次の表は、メッセージのアクションで使用される、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]テーブルに対する ReadLOB と UpdateLOB 操作。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]操作の対象のテーブルを確認するメッセージのアクションで指定されたテーブル名を使用します。  

|操作|操作|例|  
|---------------|------------|-------------|  
|ReadLOB|`[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/ReadLOB`|`http:/Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER/ReadLOB`|  
|ReadLOB 応答|`[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/ReadLOB/response`|`http:/Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER/ReadLOB/response`|  
|UpdateLOB|`[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/UpdateLOB`|`http:/Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER/UpdateLOB`|  
|UpdateLOB 応答|`[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/UpdateLOB/response`|`http:/Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER/UpdateLOB/response`|  

 [バージョン] = メッセージ バージョン文字列。たとえば、"<http://Microsoft.LobServices.OracleDB/2007/03>"。  

 [スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。  

 [TABLE_NAME] を対象となる、LOB の列を含むテーブルを =たとえば、顧客です。 (SCOTT します。CUSTOMER テーブルではインストールのサンプルに含まれる SQL スクリプト。)  

> [!IMPORTANT]
>  ビューで、ReadLOB と UpdateLOB 操作のメッセージ アクション似ていますが、テーブルは、使用されている操作のアクションは、テーブルではなく、ビューを指定します:`[VERSION]/[SCHEMA]/View/[VIEW_NAME]/ReadLOB`します。  

## <a name="see-also"></a>参照  
 [BizTalk Adapter for Oracle Database 用のメッセージとメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)
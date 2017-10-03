---
title: "特殊な LOB Operations2 のメッセージ スキーマ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- LOB data types, message structure of
- LOB data types, message actions for
ms.assetid: 031989d5-3209-41ab-8836-a40539781e74
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 203ffc81b6dc85fcaf7b80ff097bbeb001b747cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-special-lob-operations"></a>特殊な LOB 操作のメッセージ スキーマ
テーブルおよび; LOB 列を含むビューの ReadLOB および UpdateLOB 操作が表示されます。Oracle ラージ オブジェクト (LOB) データの格納に使用される列です。 これらの操作では、base64Binary でエンコードされたデータのストリームとして、LOB データを読み書きできます。 1 つの行に LOB データの 1 つの列上で動作します。  
  
 ReadLOB および UpdateLOB の操作と、サポートされる Oracle LOB データ型の概要を参照してください。[テーブルと Oracle データベースでの LOB データを含むビューで操作](../../adapters-and-accelerators/adapter-oracle-database/operations-on-tables-and-views-that-contain-lob-data-in-oracle-database.md)です。  
  
## <a name="message-structure-of-lob-data-type-operations"></a>LOB データ型の操作のメッセージの構造  
 次の表は、ReadLOB および UpdateLOB の操作要求および応答メッセージの構造を示しています。 操作の対象テーブルでは、メッセージのアクションで指定され、ターゲットの名前空間にも表示されます。  
  
|操作|XML メッセージ|Description|  
|---------------|-----------------|-----------------|  
|ReadLOB|`<ReadLOB xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   <LOB_COLUMN>[COL_NAME]</LOB_COLUMN>   <FILTER>[WHERE_clause]</LOB_COLUMN> </ReadLOB>`|内の LOB データ、<br /><br /> -LOB_COLUMN 要素によって識別される列と<br /><br /> -where に一致する行フィルター要素で指定された句<br /><br /> 返されます。<br /><br /> Where 句が 1 つの行のみを一致する必要があります。 1 つ以上の一致する行がある場合は、最初の一致する行に LOB データが返されます。<br /><br /> **重要な**ReadLOB 操作は、WCF サービス モデルでの LOB データの入力ストリーミングをサポートするために設計されています。 WCF チャネル モデルから LOB データを読み取るテーブルの選択操作を使用する必要がありますまたは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションです。|  
|ReadLOB 応答|`<ReadLOBResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   <ReadLOBResult>     [LOB_DATA]   </ReadLOBResult> </ReadLOBResponse>`|LOB データは、base64Binary でエンコードされたデータのストリームとして返されます。<br /><br /> **重要な**アダプターによって返される WSDL がアダプターによって ReadLOB 応答メッセージで使用する実際のスキーマと一致しません。|  
|UpdateLOB|`<UpdateLOB xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   <LOB_COLUMN>[COL_NAME]</LOB_COLUMN>   <FILTER>[WHERE_clause]</LOB_COLUMN>   <Stream>[LOB_DATA]</Stream> </UpdateLOB>`|内の LOB データ、<br /><br /> -LOB_COLUMN 要素によって識別される列と<br /><br /> -where に一致する行フィルター要素で指定された句<br /><br /> ストリーム内の base64Binary でエンコードされたデータで更新されます。<br /><br /> Where 句が 1 つの行のみを一致する必要があります。 1 つ以上の一致する行がある場合、例外がスローされます。<br /><br /> **注**UpdateLOB 操作はすべての指定した列と行のデータを置き換えます。|  
|UpdateLOB 応答|`<UpdateLOBResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]"> </UpdateLOBResponse>`|空の応答が返されます。|  
  
 [バージョン]、メッセージのバージョン文字列を =たとえば、"http://Microsoft.LobServices/OracleDB/2007/03"です。  
  
 [スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。  
  
 [TABLE_NAME] を対象となる、LOB の列を含むテーブルを =たとえば、EMP です。  
  
 [COL_NAME] 対象となる、LOB の列の名前を =たとえば、LOB_FIELD です。  
  
 [WHERE_clause] に Oracle データベースの SELECT ステートメントです 1 つの行に一致する WHERE 句を =。たとえば、ID = 1 です。  
  
 [LOB_DATA] base64Binary 型の列のデータ、LOB を = です。  
  
> [!IMPORTANT]
>  ビューでは、ReadLOB と UpdateLOB 操作のメッセージの構造と同じテーブルが操作の名前空間は、テーブルではなく、ビューを指定する点を除いて:`<ReadLOB xmlns ="[VERSION]/[SCHEMA]/``View``/[VIEW_NAME]">`です。  
  
## <a name="message-actions-for-lob-data-type-operations"></a>メッセージの動作の LOB データ型の操作  
 次の表は、メッセージ アクションで使用される、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] ReadLOB と UpdateLOB での操作のテーブルです。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]メッセージ アクションで指定したテーブル名を使用して、操作の対象テーブルを確認します。  
  
|操作|操作|例|  
|---------------|------------|-------------|  
|ReadLOB|`[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/ReadLOB`|`http:/Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER/ReadLOB`|  
|ReadLOB 応答|`[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/ReadLOB/response`|`http:/Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER/ReadLOB/response`|  
|UpdateLOB|`[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/UpdateLOB`|`http:/Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER/UpdateLOB`|  
|UpdateLOB 応答|`[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/UpdateLOB/response`|`http:/Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER/UpdateLOB/response`|  
  
 [バージョン]、メッセージのバージョン文字列を =たとえば、"http://Microsoft.LobServices.OracleDB/2007/03"です。  
  
 [スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。  
  
 [TABLE_NAME] を対象となる、LOB の列を含むテーブルを =たとえば、顧客です。 (SCOTT です。CUSTOMER テーブルではインストール SQL スクリプトのサンプルに含まれています。)  
  
> [!IMPORTANT]
>  操作のアクションは、テーブルではなく、ビューを指定する点を除いては、ビューで、ReadLOB と UpdateLOB 操作のメッセージのアクションがテーブルで使用されるような:`[VERSION]/[SCHEMA]/View/[VIEW_NAME]/ReadLOB`です。  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter 用 Oracle Database のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)
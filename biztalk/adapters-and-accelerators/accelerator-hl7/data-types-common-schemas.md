---
title: データ型の一般的なスキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.X schemas, data types
- 2.X schemas, common schemas
- common schemas
ms.assetid: 6fd30cd3-9c4f-4391-9c79-a4dff11f2a46
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0d1645a6ef6de149f92da12f0574fe3af0f9c2b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255552"
---
# <a name="data-types-common-schemas"></a>データ型の一般的なスキーマ
**Datatypes_*\<バージョン\>*.xsd**スキーマ ファイル (場所*\<バージョン\>* HL7 バージョン番号です)HL7 の対応するバージョンのすべての HL7 基本と複合データ型の定義が含まれています。 Segments_*\<バージョン\>*.xsd ファイルでは、このファイルを使用して、対応する HL7 バージョンと一致します。 データ構造の Access データベースのテーブルの生成、DataTypes_*\<バージョン\>* スキーマの .xsd ファイルです。 次の例は、HL7 基本データ型のエントリ**ST**:  
  
```  
<xsd:simpleType name="ST">  
  <xsd:restriction base="xsd:string" />   
</xsd:simpleType>  
```  
  
 この例では定義**ST**として、**文字列**します。  
  
## <a name="see-also"></a>参照  
 [HL7 2.X の共通スキーマ ファイル](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md)   
 [セグメントの一般的なスキーマ](../../adapters-and-accelerators/accelerator-hl7/segments-common-schemas.md)   
 [テーブル値の一般的なスキーマ](../../adapters-and-accelerators/accelerator-hl7/table-values-common-schemas.md)
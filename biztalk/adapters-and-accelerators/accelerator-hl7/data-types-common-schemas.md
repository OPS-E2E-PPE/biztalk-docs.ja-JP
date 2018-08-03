---
title: データ型の共通のスキーマ |Microsoft ドキュメント
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
ms.openlocfilehash: 0e7d693cdf70f7d29a79aa8999dde49f408b8815
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
ms.locfileid: "25960968"
---
# <a name="data-types-common-schemas"></a>一般的なスキーマのデータ型します。
**Datatypes_*\<バージョン\>*.xsd**スキーマ ファイル (ここで*\<バージョン\>* HL7 バージョン番号です)HL7 の対応するバージョンのすべての HL7 基本と複合データ型の定義が含まれています。 Segments_*\<バージョン\>*.xsd ファイルでは、このファイルを使用して、対応する HL7 バージョンと一致します。 データ構造の Access データベースのテーブルを生成、DataTypes_*\<バージョン\>*.xsd スキーマ ファイルです。 次の例は、HL7 の基本データ型にエントリを**ST**:  
  
```  
<xsd:simpleType name="ST">  
  <xsd:restriction base="xsd:string" />   
</xsd:simpleType>  
```  
  
 この例で定義**ST**として、**文字列**です。  
  
## <a name="see-also"></a>参照  
 [HL7 2.X の共通スキーマ ファイル](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md)   
 [セグメントの一般的なスキーマ](../../adapters-and-accelerators/accelerator-hl7/segments-common-schemas.md)   
 [テーブル値の一般的なスキーマ](../../adapters-and-accelerators/accelerator-hl7/table-values-common-schemas.md)
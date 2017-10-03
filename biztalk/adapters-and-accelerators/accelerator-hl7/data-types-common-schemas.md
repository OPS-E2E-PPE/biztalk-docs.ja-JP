---
title: "データ型の共通のスキーマ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 2.X schemas, data types
- 2.X schemas, common schemas
- common schemas
ms.assetid: 6fd30cd3-9c4f-4391-9c79-a4dff11f2a46
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19ff35b515e70c21e2349ae54847ba312d7ce0f8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="data-types-common-schemas"></a>一般的なスキーマのデータ型します。
 **Datatypes_*\<バージョン >*.xsd * * スキーマ ファイル (ここで*\<バージョン >* HL7 のバージョン番号) の定義が含まれていますHL7 基本と複合データ型をすべて HL7 の対応するバージョンにします。 Segments_*\<バージョン >*.xsd ファイルでは、このファイルを使用して、対応する HL7 バージョンと一致します。 データ構造の Access データベースのテーブルを生成、DataTypes_*\<バージョン >*.xsd スキーマ ファイルです。 次の例は、HL7 の基本データ型にエントリを**ST**:  
  
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
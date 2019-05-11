---
title: 一般的なスキーマのセグメント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.X schemas, common schemas
- 2.X schemas, segments
- common schemas
ms.assetid: 6f66bce9-ead8-46c1-a66c-830750adc73b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f7bb3bbad38918679c56383720aea27001654d5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289515"
---
# <a name="segments-common-schemas"></a>セグメントの一般的なスキーマ
**Segments_\<*バージョン*\>.xsd**ファイルに datatypes_\<*バージョン*\>.xsd が含まれています、HL7 バージョンに関連するすべてのセグメントの定義。 各メッセージ スキーマは segments_\<*バージョン*\>.xsd。 HL7 メッセージ定義の各サブフォルダーの下で、segments_ を含める\<*バージョン*\>.xsd。 SegmentDataElements と DataElements アクセス データベースのテーブルの生成、segments_\<*バージョン*\>.xsd ファイルは、すべてのデータ型の Fields.xsd スキーマ ファイルへのポインターが含まれています。 スキーマ ファイル名の形式です。  
  
```  
  
<xxx>_<nnn>_<vaa>_GLO_DEF.xsd  
```  
  
 場所*xxx*メッセージの種類である*nnn* 、トリガー イベントは、 *vaa*バージョン番号は、GLO は、グローバル化を示します、DEF は、既定値を示します。 スキーマ ファイル *\<xxx\>*<em>*\<nnn\>*  \\</em>   *\<vaa\>*\_*\<glo\>*\_*\<def\>*.xsdisEventMessageTypeSegments SegmentDataElements Access データベース テーブルから生成され、セグメントへのポインターが含まれています\_\<*バージョン*\>スキーマの .xsd ファイルです。  
  
## <a name="see-also"></a>参照  
 [HL7 2.X の共通スキーマ ファイル](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md)   
 [データ型の一般的なスキーマ](../../adapters-and-accelerators/accelerator-hl7/data-types-common-schemas.md)   
 [テーブル値の一般的なスキーマ](../../adapters-and-accelerators/accelerator-hl7/table-values-common-schemas.md)
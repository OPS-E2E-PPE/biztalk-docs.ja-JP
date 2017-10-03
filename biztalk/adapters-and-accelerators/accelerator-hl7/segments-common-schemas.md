---
title: "一般的なスキーマのセグメント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 2.X schemas, common schemas
- 2.X schemas, segments
- common schemas
ms.assetid: 6f66bce9-ead8-46c1-a66c-830750adc73b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff61c73b51eb08d1e6f845980686b49b3440d88c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="segments-common-schemas"></a>セグメントの一般的なスキーマ
 **Segments_\<*バージョン*> * * .xsd ファイルを含む datatypes_\<*バージョン*> .xsd すべての定義が含まれると、HL7 バージョンに関連するセグメント。 各メッセージ スキーマを使用 segments_\<*バージョン*> .xsd です。 HL7 メッセージの定義は、各サブフォルダーの下にあるし、segments_ を含める\<*バージョン*> .xsd です。 SegmentDataElements と DataElements アクセス データベースのテーブルを生成、segments_\<*バージョン*> .xsd ファイルは、すべてのデータ型の Fields.xsd スキーマ ファイルへのポインターが含まれています。 スキーマ ファイル名の形式です。  
  
```  
  
<xxx>_<nnn>_<vaa>_GLO_DEF.xsd  
```  
  
 場所*xxx* 、メッセージの種類は、  *nnn* トリガー イベントは、 *vaa*バージョン番号は、グローバライズ、GLO を示します、DEF は、既定値を示します。 スキーマ ファイル *\<xxx >*_*\<nnn>*\_*\<vaa >* \_ *\<glo >*\_*\<def >*.xsdis EventMessageTypeSegments and SegmentDataElements Access データベースから生成されたテーブルし、へのポインターが含まれていますセグメント\_\<*バージョン*> .xsd スキーマ ファイルです。  
  
## <a name="see-also"></a>参照  
 [HL7 2.X の共通スキーマ ファイル](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md)   
 [一般的なスキーマのデータ型します。](../../adapters-and-accelerators/accelerator-hl7/data-types-common-schemas.md)   
 [テーブル値の一般的なスキーマ](../../adapters-and-accelerators/accelerator-hl7/table-values-common-schemas.md)
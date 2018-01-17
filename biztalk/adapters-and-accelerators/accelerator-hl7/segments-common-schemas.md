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
ms.openlocfilehash: 50bdcacfe1459ba4a236c3701b786d97217db8ef
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="segments-common-schemas"></a><span data-ttu-id="175d7-102">セグメントの一般的なスキーマ</span><span class="sxs-lookup"><span data-stu-id="175d7-102">Segments Common Schemas</span></span>
<span data-ttu-id="175d7-103">**Segments_\<*バージョン*\>.xsd** datatypes_ が含まれるファイル\<*バージョン*\>.xsd が含まれています、HL7 バージョンに関連するすべてのセグメントの定義。</span><span class="sxs-lookup"><span data-stu-id="175d7-103">The **segments_\<*version*\>.xsd** file includes datatypes_\<*version*\>.xsd and contains the definition of all the segments related to the HL7 version.</span></span> <span data-ttu-id="175d7-104">各メッセージ スキーマを使用 segments_\<*バージョン*\>.xsd です。</span><span class="sxs-lookup"><span data-stu-id="175d7-104">Each message schema uses segments_\<*version*\>.xsd.</span></span> <span data-ttu-id="175d7-105">HL7 メッセージの定義は、各サブフォルダーの下にあるし、segments_ を含める\<*バージョン*\>.xsd です。</span><span class="sxs-lookup"><span data-stu-id="175d7-105">HL7 message definitions are under each subfolder and include segments_\<*version*\>.xsd.</span></span> <span data-ttu-id="175d7-106">SegmentDataElements と DataElements アクセス データベースのテーブルを生成、segments_\<*バージョン*\>.xsd ファイルは、すべてのデータ型の Fields.xsd スキーマ ファイルへのポインターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="175d7-106">The SegmentDataElements and DataElements Access database tables generate the segments_\<*version*\>.xsd file, which includes a pointer to the Fields.xsd schema file for all data types.</span></span> <span data-ttu-id="175d7-107">スキーマ ファイル名の形式です。</span><span class="sxs-lookup"><span data-stu-id="175d7-107">The schema file name format is:</span></span>  
  
```  
  
<xxx>_<nnn>_<vaa>_GLO_DEF.xsd  
```  
  
 <span data-ttu-id="175d7-108">場所*xxx* 、メッセージの種類は、  *nnn* トリガー イベントは、 *vaa*バージョン番号は、グローバライズ、GLO を示します、DEF は、既定値を示します。</span><span class="sxs-lookup"><span data-stu-id="175d7-108">Where *xxx* is the message type, *nnn* is the trigger event, *vaa* is the version number, GLO indicates globalize, and DEF indicates default.</span></span> <span data-ttu-id="175d7-109">スキーマ ファイル *\<xxx\>*_*\<nnn\>*\_*\<vaa\>*  \_  *\<glo\>*\_*\<def\>*.xsdis から生成された、EventMessageTypeSegments と SegmentDataElements アクセス データベースのテーブルし、セグメントへのポインターが含まれています\_\<*バージョン*\>.xsd スキーマ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="175d7-109">The schema file *\<xxx\>*_*\<nnn\>*\_*\<vaa\>*\_*\<glo\>*\_*\<def\>*.xsdis generated from the EventMessageTypeSegments and SegmentDataElements Access database tables and includes a pointer to the Segments\_\<*version*\>.xsd schema file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="175d7-110">参照</span><span class="sxs-lookup"><span data-stu-id="175d7-110">See Also</span></span>  
 <span data-ttu-id="175d7-111">[HL7 2.X の共通スキーマ ファイル](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md) </span><span class="sxs-lookup"><span data-stu-id="175d7-111">[HL7 2.X Common Schema Files](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md) </span></span>  
 <span data-ttu-id="175d7-112">[一般的なスキーマのデータ型します。](../../adapters-and-accelerators/accelerator-hl7/data-types-common-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="175d7-112">[Data Types Common Schemas](../../adapters-and-accelerators/accelerator-hl7/data-types-common-schemas.md) </span></span>  
 [<span data-ttu-id="175d7-113">テーブル値の一般的なスキーマ</span><span class="sxs-lookup"><span data-stu-id="175d7-113">Table Values Common Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/table-values-common-schemas.md)
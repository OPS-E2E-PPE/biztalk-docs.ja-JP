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
ms.openlocfilehash: 46e961934b1595217b94aab82b2adae9fd3e456f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985483"
---
# <a name="segments-common-schemas"></a><span data-ttu-id="2e727-102">セグメントの一般的なスキーマ</span><span class="sxs-lookup"><span data-stu-id="2e727-102">Segments Common Schemas</span></span>
<span data-ttu-id="2e727-103">**Segments_\<*バージョン*\>.xsd**ファイルに datatypes_\<*バージョン*\>.xsd が含まれています、HL7 バージョンに関連するすべてのセグメントの定義。</span><span class="sxs-lookup"><span data-stu-id="2e727-103">The **segments_\<*version*\>.xsd** file includes datatypes_\<*version*\>.xsd and contains the definition of all the segments related to the HL7 version.</span></span> <span data-ttu-id="2e727-104">各メッセージ スキーマは segments_\<*バージョン*\>.xsd。</span><span class="sxs-lookup"><span data-stu-id="2e727-104">Each message schema uses segments_\<*version*\>.xsd.</span></span> <span data-ttu-id="2e727-105">HL7 メッセージ定義の各サブフォルダーの下で、segments_ を含める\<*バージョン*\>.xsd。</span><span class="sxs-lookup"><span data-stu-id="2e727-105">HL7 message definitions are under each subfolder and include segments_\<*version*\>.xsd.</span></span> <span data-ttu-id="2e727-106">SegmentDataElements と DataElements アクセス データベースのテーブルの生成、segments_\<*バージョン*\>.xsd ファイルは、すべてのデータ型の Fields.xsd スキーマ ファイルへのポインターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2e727-106">The SegmentDataElements and DataElements Access database tables generate the segments_\<*version*\>.xsd file, which includes a pointer to the Fields.xsd schema file for all data types.</span></span> <span data-ttu-id="2e727-107">スキーマ ファイル名の形式です。</span><span class="sxs-lookup"><span data-stu-id="2e727-107">The schema file name format is:</span></span>  
  
```  
  
<xxx>_<nnn>_<vaa>_GLO_DEF.xsd  
```  
  
 <span data-ttu-id="2e727-108">場所*xxx*メッセージの種類である*nnn* 、トリガー イベントは、 *vaa*バージョン番号は、GLO は、グローバル化を示します、DEF は、既定値を示します。</span><span class="sxs-lookup"><span data-stu-id="2e727-108">Where *xxx* is the message type, *nnn* is the trigger event, *vaa* is the version number, GLO indicates globalize, and DEF indicates default.</span></span> <span data-ttu-id="2e727-109">スキーマ ファイル *\<xxx\>*<em>*\<nnn\>*  \\</em>   *\<vaa\>*\_*\<glo\>*\_*\<def\>*.xsdisEventMessageTypeSegments SegmentDataElements Access データベース テーブルから生成され、セグメントへのポインターが含まれています\_\<*バージョン*\>スキーマの .xsd ファイルです。</span><span class="sxs-lookup"><span data-stu-id="2e727-109">The schema file *\<xxx\>*<em>*\<nnn\>*\\</em>*\<vaa\>*\_*\<glo\>*\_*\<def\>*.xsdis generated from the EventMessageTypeSegments and SegmentDataElements Access database tables and includes a pointer to the Segments\_\<*version*\>.xsd schema file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e727-110">参照</span><span class="sxs-lookup"><span data-stu-id="2e727-110">See Also</span></span>  
 <span data-ttu-id="2e727-111">[HL7 2.X の共通スキーマ ファイル](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md) </span><span class="sxs-lookup"><span data-stu-id="2e727-111">[HL7 2.X Common Schema Files](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md) </span></span>  
 <span data-ttu-id="2e727-112">[データ型の一般的なスキーマ](../../adapters-and-accelerators/accelerator-hl7/data-types-common-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="2e727-112">[Data Types Common Schemas](../../adapters-and-accelerators/accelerator-hl7/data-types-common-schemas.md) </span></span>  
 [<span data-ttu-id="2e727-113">テーブル値の一般的なスキーマ</span><span class="sxs-lookup"><span data-stu-id="2e727-113">Table Values Common Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/table-values-common-schemas.md)
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
# <a name="data-types-common-schemas"></a><span data-ttu-id="fca33-102">データ型の一般的なスキーマ</span><span class="sxs-lookup"><span data-stu-id="fca33-102">Data Types Common Schemas</span></span>
<span data-ttu-id="fca33-103">**Datatypes_*\<バージョン\>*.xsd**スキーマ ファイル (場所*\<バージョン\>* HL7 バージョン番号です)HL7 の対応するバージョンのすべての HL7 基本と複合データ型の定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fca33-103">The **datatypes_*\<version\>*.xsd** schema file (where *\<version\>* is the HL7 version number) contains the definition of all the HL7 elementary and composite data types for the corresponding HL7 version.</span></span> <span data-ttu-id="fca33-104">Segments_*\<バージョン\>*.xsd ファイルでは、このファイルを使用して、対応する HL7 バージョンと一致します。</span><span class="sxs-lookup"><span data-stu-id="fca33-104">The segments_*\<version\>*.xsd file uses this file to match the corresponding HL7 version.</span></span> <span data-ttu-id="fca33-105">データ構造の Access データベースのテーブルの生成、DataTypes_*\<バージョン\>* スキーマの .xsd ファイルです。</span><span class="sxs-lookup"><span data-stu-id="fca33-105">The DataStructures Access database table generates the DataTypes_*\<version\>*.xsd schema file.</span></span> <span data-ttu-id="fca33-106">次の例は、HL7 基本データ型のエントリ**ST**:</span><span class="sxs-lookup"><span data-stu-id="fca33-106">The following example is an entry for the HL7 elementary data type **ST**:</span></span>  
  
```  
<xsd:simpleType name="ST">  
  <xsd:restriction base="xsd:string" />   
</xsd:simpleType>  
```  
  
 <span data-ttu-id="fca33-107">この例では定義**ST**として、**文字列**します。</span><span class="sxs-lookup"><span data-stu-id="fca33-107">This example defines **ST** as a **string**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fca33-108">参照</span><span class="sxs-lookup"><span data-stu-id="fca33-108">See Also</span></span>  
 <span data-ttu-id="fca33-109">[HL7 2.X の共通スキーマ ファイル](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md) </span><span class="sxs-lookup"><span data-stu-id="fca33-109">[HL7 2.X Common Schema Files](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md) </span></span>  
 <span data-ttu-id="fca33-110">[セグメントの一般的なスキーマ](../../adapters-and-accelerators/accelerator-hl7/segments-common-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="fca33-110">[Segments Common Schemas](../../adapters-and-accelerators/accelerator-hl7/segments-common-schemas.md) </span></span>  
 [<span data-ttu-id="fca33-111">テーブル値の一般的なスキーマ</span><span class="sxs-lookup"><span data-stu-id="fca33-111">Table Values Common Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/table-values-common-schemas.md)
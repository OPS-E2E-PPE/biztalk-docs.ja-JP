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
ms.openlocfilehash: 0e7d693cdf70f7d29a79aa8999dde49f408b8815
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="data-types-common-schemas"></a><span data-ttu-id="0a8ab-102">一般的なスキーマのデータ型します。</span><span class="sxs-lookup"><span data-stu-id="0a8ab-102">Data Types Common Schemas</span></span>
<span data-ttu-id="0a8ab-103">**Datatypes_*\<バージョン\>*.xsd**スキーマ ファイル (ここで*\<バージョン\>* HL7 バージョン番号です)HL7 の対応するバージョンのすべての HL7 基本と複合データ型の定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0a8ab-103">The **datatypes_*\<version\>*.xsd** schema file (where *\<version\>* is the HL7 version number) contains the definition of all the HL7 elementary and composite data types for the corresponding HL7 version.</span></span> <span data-ttu-id="0a8ab-104">Segments_*\<バージョン\>*.xsd ファイルでは、このファイルを使用して、対応する HL7 バージョンと一致します。</span><span class="sxs-lookup"><span data-stu-id="0a8ab-104">The segments_*\<version\>*.xsd file uses this file to match the corresponding HL7 version.</span></span> <span data-ttu-id="0a8ab-105">データ構造の Access データベースのテーブルを生成、DataTypes_*\<バージョン\>*.xsd スキーマ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="0a8ab-105">The DataStructures Access database table generates the DataTypes_*\<version\>*.xsd schema file.</span></span> <span data-ttu-id="0a8ab-106">次の例は、HL7 の基本データ型にエントリを**ST**:</span><span class="sxs-lookup"><span data-stu-id="0a8ab-106">The following example is an entry for the HL7 elementary data type **ST**:</span></span>  
  
```  
<xsd:simpleType name="ST">  
  <xsd:restriction base="xsd:string" />   
</xsd:simpleType>  
```  
  
 <span data-ttu-id="0a8ab-107">この例で定義**ST**として、**文字列**です。</span><span class="sxs-lookup"><span data-stu-id="0a8ab-107">This example defines **ST** as a **string**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a8ab-108">参照</span><span class="sxs-lookup"><span data-stu-id="0a8ab-108">See Also</span></span>  
 <span data-ttu-id="0a8ab-109">[HL7 2.X の共通スキーマ ファイル](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md) </span><span class="sxs-lookup"><span data-stu-id="0a8ab-109">[HL7 2.X Common Schema Files](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md) </span></span>  
 <span data-ttu-id="0a8ab-110">[セグメントの一般的なスキーマ](../../adapters-and-accelerators/accelerator-hl7/segments-common-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="0a8ab-110">[Segments Common Schemas](../../adapters-and-accelerators/accelerator-hl7/segments-common-schemas.md) </span></span>  
 [<span data-ttu-id="0a8ab-111">テーブル値の一般的なスキーマ</span><span class="sxs-lookup"><span data-stu-id="0a8ab-111">Table Values Common Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/table-values-common-schemas.md)
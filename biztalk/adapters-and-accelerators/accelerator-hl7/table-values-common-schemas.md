---
title: テーブル値の一般的なスキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.X schemas, common schemas
- 2.X schemas, table values
- common schemas
ms.assetid: 2421e150-1bae-43bd-aba3-6322c679b22b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90c66ee201e5a73d8f632a8002a9a3627d1885f1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968067"
---
# <a name="table-values-common-schemas"></a>テーブル値の一般的なスキーマ
Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) を生成、 **tablevalues_*\<バージョン\>*.xsd** HL7 バージョンごとに、ファイルし、のルートにあるファイルを見つけますHL7 バージョン固有のフォルダー。 データ型の共通スキーマ ファイルでは、テーブル値の一般的なスキーマ ファイルを参照します。  
  
 これらのテーブル内の値、列挙値の形式です。 各列挙体は、メッセージ スキーマの 1 つまたは複数のフィールド内で許容される値を定義します。 テーブルは、スキーマを BizTalk エディターで開く、ノードをクリックし、確認メッセージのスキーマのノードに適用されますを参照してください、 **Base Data Type**プロパティ ペインでプロパティ。  
  
 このノードに使用できる値は、ただし、メッセージ スキーマのノードのプロパティ ペインで、列挙型を表示して確認することはできません。 テーブル値の一般的なスキーマ ファイルが列挙体を定義するためです。 列挙体を表示する をクリックして**tablevalues_*\<バージョン\>*.xsd** 、スキーマ ツリーの BizTalk エディターとし、省略記号ボタンをクリックします (**.**)、プロパティ ペインで列挙型の行にボタンをクリックします。  
  
## <a name="see-also"></a>参照  
 [HL7 2.X の共通スキーマ ファイル](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md)   
 [データ型の一般的なスキーマ](../../adapters-and-accelerators/accelerator-hl7/data-types-common-schemas.md)   
 [セグメントの一般的なスキーマ](../../adapters-and-accelerators/accelerator-hl7/segments-common-schemas.md)
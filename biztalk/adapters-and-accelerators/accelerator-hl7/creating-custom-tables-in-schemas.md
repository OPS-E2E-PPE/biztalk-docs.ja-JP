---
title: スキーマのカスタム テーブルの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, Z tables [Z objects]
- Z objects, creating Z tables
- 2.X schemas, creating Z tables
ms.assetid: d6ab8ac9-a835-4ec0-9ddd-76ff267a3cbd
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41efa501b1b937bcb179c61d6d21f1dd12deac88
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255724"
---
# <a name="creating-custom-tables-in-schemas"></a>スキーマのカスタム テーブルの作成
カスタムのテーブルを作成するには、tablevalues_ で\<*バージョン*\>.xsd 共通のスキーマ。 カスタム テーブルは、既存のデータ型、基本データ型、またはテーブルで定義されている列挙体の基本ことができます。  
  
### <a name="to-create-a-z-table"></a>Z テーブルを作成するには  
  
1.  ソリューション エクスプ ローラーで、一般的なデータ型のスキーマ ファイルを開く**tablevalues_\<*バージョン*\>.xsd**、 をクリックし、**開く**。  
  
2.  BizTalk エディターで、右クリックして**HL7DefinedTables**、 をポイント**スキーマ ノードの挿入**、 をクリックし、**子フィールド要素**します。  
  
3.  "Z"文字で始まるタグを持つテーブルを名前します。  
  
4.  プロパティ ペインで、必要に応じて、固有のプロパティの値を入力します。  
  
5.  列挙体を関連付けるプロパティ ペインで、テーブルに次のように設定します。 **Derived By**に**制限**、 をクリック**列挙**、の省略記号(...)ボタンをクリックします。**列挙体**、列挙エディタを格納する列挙値を入力します。 **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [Z オブジェクト HL7 2.X スキーマの拡張](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [宣言された Z セグメントの作成](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)   
 [スキーマでカスタム データ型の作成](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md)   
 [列挙の拡張](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)   
 [未宣言の Z セグメントの処理](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)
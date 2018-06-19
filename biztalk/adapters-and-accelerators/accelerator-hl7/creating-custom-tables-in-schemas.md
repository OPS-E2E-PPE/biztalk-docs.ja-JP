---
title: スキーマにカスタムのテーブルを作成 |Microsoft ドキュメント
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
ms.openlocfilehash: a663dd593123e647f2f466b6d472d60bb32be1be
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
ms.locfileid: "25960344"
---
# <a name="creating-custom-tables-in-schemas"></a>スキーマのカスタム テーブルの作成
カスタムのテーブルを作成するには、tablevalues_ で\<*バージョン*\>.xsd 共通のスキーマです。 既存のデータ型、基本データ型、またはテーブルで定義された列挙体のカスタムのテーブルを作成できます。  
  
### <a name="to-create-a-z-table"></a>Z テーブルを作成するには  
  
1.  ソリューション エクスプ ローラーで、共通のデータ型のスキーマ ファイルを開く**tablevalues_\<*バージョン*\>.xsd**、順にクリック**開く**です。  
  
2.  BizTalk エディターを右クリックして**HL7DefinedTables**、 をポイント**スキーマ ノードの挿入**、クリックして**子フィールド要素**です。  
  
3.  "Z"文字で始まるタグを持つテーブルを名前します。  
  
4.  プロパティ ウィンドウで、必要に応じて、特定のプロパティに対して使用値を入力します。  
  
5.  プロパティ ペインで、テーブルに列挙体を関連付けるには次のように設定します**Derived By**に**制限**、をクリックして**列挙**、の省略記号(...)ボタンをクリック。**列挙体**、列挙エディタを格納する列挙を目的の値を入力します。 **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [Z オブジェクトと HL7 2.X スキーマを拡張します。](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [宣言されている Z セグメントを作成します。](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)   
 [スキーマでカスタム データ型を作成します。](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md)   
 [列挙型を拡張します。](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)   
 [未宣言の Z セグメントの処理](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)
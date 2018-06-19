---
title: スキーマでのカスタム データ型の作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.X schemas, creating Z data types [Z objects]
- data types, creating [Z objects]
- Z objects, creating Z data types
ms.assetid: e545c849-d414-4d5d-bb56-d3f9d5238c70
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea38eb106b3554b72885355aaa9aef4928f4fda2
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
ms.locfileid: "25960680"
---
# <a name="creating-custom-data-types-in-schemas"></a>スキーマでカスタム データ型を作成します。
カスタム データ型を作成するには、datatypes_ で\<*バージョン*\>.xsd 共通のスキーマです。 既存のデータ型、基本データ型、またはテーブルで定義された列挙体のカスタム データ型を作成できます。  
  
### <a name="to-create-a-z-data-type"></a>Z データ型を作成するには  
  
1.  ソリューション エクスプ ローラーの Visual Studio で、共通のデータ型のスキーマ ファイルを開きます (**datatypes_\<*バージョン*\>.xsd**)、をクリックして**を開く**.  
  
2.  BizTalk エディターを右クリックして**HL7DefinedDataTypes**、 をポイント**スキーマ ノードの挿入**、クリックして**子レコード**をコンポーネントのデータ型を作成またはをクリックするには**子要素**を単純なデータ型を作成します。  
  
3.  "Z"で始まる 3 文字のタグを持つデータ型を名前します。  
  
4.  プロパティ ウィンドウで、使用値を入力**Base Data Type**、**データ型**、および必要に応じて、他のプロパティです。  
  
## <a name="see-also"></a>参照  
 [Z オブジェクトと HL7 2.X スキーマを拡張します。](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [宣言されている Z セグメントを作成します。](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)   
 [スキーマのカスタム テーブルの作成](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)   
 [列挙型を拡張します。](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)   
 [未宣言の Z セグメントの処理](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)
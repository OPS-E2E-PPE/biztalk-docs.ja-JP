---
title: スキーマでカスタム データ型の作成 |Microsoft Docs
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
ms.openlocfilehash: ad862866b6fb15bfc1c4be92f6fee1c49621880b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255645"
---
# <a name="creating-custom-data-types-in-schemas"></a>スキーマでカスタム データ型の作成
カスタム データ型を作成するには、datatypes_ で\<*バージョン*\>.xsd 共通のスキーマ。 既存のデータ型、基本データ型、またはテーブルで定義されている列挙体のカスタム データ型を基にできます。  
  
### <a name="to-create-a-z-data-type"></a>Z のデータ型を作成するには  
  
1.  ソリューション エクスプ ローラーの Visual Studio で、一般的なデータ型のスキーマ ファイルを開きます (**datatypes_\<*バージョン*\>.xsd**)、をクリックし、 **を開く**.  
  
2.  BizTalk エディターで、右クリックして**HL7DefinedDataTypes**、 をポイント**スキーマ ノードの挿入**、順にクリックします**子レコード**コンポーネントのデータ型を作成またはをクリックします。**子要素**単純なデータ型を作成します。  
  
3.  "Z"で始まる 3 文字のタグを持つデータ型を名前します。  
  
4.  [プロパティ] ウィンドウで使用値を入力**Base Data Type**、**データ型**、および必要に応じてその他のプロパティ。  
  
## <a name="see-also"></a>参照  
 [Z オブジェクト HL7 2.X スキーマの拡張](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [宣言された Z セグメントの作成](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)   
 [スキーマのカスタム テーブルの作成](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)   
 [列挙の拡張](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)   
 [未宣言の Z セグメントの処理](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)
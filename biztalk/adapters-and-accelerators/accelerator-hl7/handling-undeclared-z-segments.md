---
title: "宣言されていない Z セグメントの処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Z segments, 2.X schemas
- 2.X schemas, undeclared Z segments
- segments, undeclared [Z objects]
- Z objects, undeclared segments
ms.assetid: 8878bc93-1833-4bfc-b80e-305e4144739e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ff982aedee39ed60820a9f03db11d7e4d051a34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="handling-undeclared-z-segments"></a>宣言されていない Z セグメントの処理
Z セグメントの 2 種類があります: Z セグメントと宣言されていない Z セグメントを宣言します。 似ているローカルの目的で使用することでは使用する方法は大きく異なります。  
  
 メッセージ スキーマで宣言されている Z セグメントの定義を含めると[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) HL7 標準で定義されているスキーマと同じように、メッセージの処理に使用します。 宣言されていない Z セグメントを定義するスキーマがありません。 メッセージの最後に宣言されていない、Z セグメントを含めると[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]スキーマを処理することがなく通過します。 パーサーとシリアライザーは検証されませんが。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]バイナリ ラージ オブジェクト (BLOB) として扱われます。 のみチェック[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]はセグメントで宣言されていない Z BLOB に、既存の 3 文字スキーマ タグが含まれていないことの確認はします。  
  
 3 番目の部分、またはマルチパート メッセージの Z の一部として宣言されていない Z セグメントが含まれます。 メッセージには、ヘッダー、本文、および Z の一部が含まれています。 Z の一部では、文字"Z"で始まるセグメント ID を持ちます。  
  
> [!NOTE]
>  Zpart は、データを常に含める必要があります。 エラー条件でストリームの結果に null を指定します。 Zpart でデータが含まれていない場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]Zpart で「空」という単語を挿入します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]コンテキスト プロパティを使用して**ZPartPresent**を Z の一部をシリアル化するかどうかを判断します。  
  
> [!CAUTION]
>  [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]ANSI 文字の動作の Zsegment が予測可能な結果を ANSI 文字セットを持つ Zsegments をテストします。 ただし、Zsegments で他の文字セットを使用する場合があります、予期しない動作します。  
  
## <a name="see-also"></a>参照  
 [Z オブジェクトと HL7 2.X スキーマを拡張します。](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [宣言されている Z セグメントを作成します。](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)   
 [スキーマでカスタム データ型を作成します。](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md)   
 [スキーマのカスタム テーブルの作成](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)
---
title: 未宣言の Z セグメントの処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Z segments, 2.X schemas
- 2.X schemas, undeclared Z segments
- segments, undeclared [Z objects]
- Z objects, undeclared segments
ms.assetid: 8878bc93-1833-4bfc-b80e-305e4144739e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0903945fc9fdae1618f8548660c320187a0a71b8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255272"
---
# <a name="handling-undeclared-z-segments"></a>未宣言の Z セグメントの処理
Z セグメントの 2 種類があります: Z セグメントで宣言されていない Z セグメントを宣言します。 似ているローカルの目的で使用することで、使用する方法に非常に異なるです。  
  
 メッセージ スキーマ、および Microsoft BizTalk Accelerator for HL7 の宣言された Z セグメントの定義を含める ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])、HL7 標準によって定義されるスキーマと同じように、メッセージの処理に使用します。 未宣言の Z セグメントを定義するスキーマがありません。 メッセージの最後に宣言されていない Z セグメントを含めると[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]スキーマに対してそれを処理することがなく通過します。 パーサーとシリアライザーは検証されません。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] バイナリ ラージ オブジェクト (BLOB) として扱われます。 のみ確認[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]はセグメント未宣言の Z で、BLOB に、既存の 3 文字のスキーマのタグが含まれていないことの確認ができます。  
  
 3 番目の部分、またはマルチパート メッセージの Z の一部として宣言されていない Z セグメントが含まれます。 メッセージには、ヘッダー、本文、および Z の一部が含まれています。 Z の一部では、"Z"文字で始まるセグメント ID を持ちます。  
  
> [!NOTE]
>  Zpart は、データを常に含める必要があります。 エラー状態でストリームの結果の null を指定します。 データが含まれていない場合、Zpart [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Zpart で「空」という単語を挿入します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] コンテキスト プロパティを使用して**ZPartPresent** Z の一部をシリアル化するかどうかを判断します。  
> 
> [!CAUTION]
>  Microsoft では、ANSI 文字を含む Zsegment 動作が予測可能な結果を ANSI 文字セットで Zsegments をテストします。 ただし、Zsegments で他の文字セットを使用してが予期しない動作にあります。  
  
## <a name="see-also"></a>参照  
 [Z オブジェクト HL7 2.X スキーマの拡張](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [宣言された Z セグメントの作成](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)   
 [スキーマでカスタム データ型の作成](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md)   
 [スキーマでのカスタム テーブルの作成](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)
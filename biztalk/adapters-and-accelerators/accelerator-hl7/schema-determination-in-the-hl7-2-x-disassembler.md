---
title: HL7 2.X 逆アセンブラーのスキーマの決定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- header segments [2.X]
- 2.X messages, header segments
- messages, parsing messages
- MSH
- disassembler, parsing messages
- 2.X messages, MSH
ms.assetid: afd45c4c-2feb-44eb-b3bd-49fe114eb893
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fcdd3b0ba6565aff4d401c8e43ae2f86fc37384
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010259"
---
# <a name="schema-determination-in-the-hl7-2x-disassembler"></a>HL7 2.X 逆アセンブラーのスキーマ決定
HL7 2.X のメッセージには、本文のセグメント数と、省略可能な Z セグメントの後にヘッダー セグメント (MSH) が含まれます。 MSH には、21 のフィールドが含まれています。  
  
 メッセージが到着すると、2.X のエンジンを使用して、メッセージ本文を解析するスキーマを決定するヘッダーを読み取ります。 次の一連のイベントが発生します。  
  
1. 逆アセンブラーが MSH3 の値を読み取ります (送信元パーティ)、次の検証オプションを決定します。  
  
   1.  本文の XML の検証を実行するかどうか  
  
   2.  本文データのフィールドを入力するカスタム データを検証するかどうか  
  
   3.  末尾の本体に区切り記号を許可するかどうか  
  
   4.  ボディ スキーマのターゲットの名前空間には (**TargetNS**)  
  
2. 逆アセンブラーは、本文のルート ノード名を確認するには、MSH9 と MSH12 を読み取ります。 アルゴリズムは次のとおりです。  
  
   ```  
   Body schema type = TargetNS + "#" + MSH9.1 + MSH9.2 + MSH12.1 (with dots removed) + MSH12.2 (or GLO if the value is blank) + MSH12.3 (or DEF if the value is blank)  
   ```  
  
    Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 後続のメッセージ ヘッダー内の区切り記号は常に許可します。 エンジンは、それぞれの行の最初の 3 つの文字がセグメント識別子を調べます。 に保持ボディ スキーマを定義するすべてのセグメントの XML を生成します。 未定義のセグメントを見つけたときに、そのセグメントを Z セグメントとして扱います。 その時点からは、未定義のすべてのセグメントは、メッセージの Z の一部を構成します。 [次へ] の MSH では、このメッセージの終了をマークします。 バッチ メッセージの場合、[次へ] MSH または BTS (バッチ トレーラー セグメント タグ) は、メッセージの最後をマークします。 Z セグメントには、スキーマで宣言されているあるセグメントのみを含めることができます。 宣言されたセグメントが発生するエラーになります。  
  
## <a name="see-also"></a>参照  
 [メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [BTAHL72X フラット ファイル処理](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)
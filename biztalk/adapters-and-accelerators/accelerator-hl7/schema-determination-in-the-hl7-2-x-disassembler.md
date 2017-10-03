---
title: "HL7 2.X 逆アセンブラーでスキーマの決定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- header segments [2.X]
- 2.X messages, header segments
- messages, parsing messages
- MSH
- disassembler, parsing messages
- 2.X messages, MSH
ms.assetid: afd45c4c-2feb-44eb-b3bd-49fe114eb893
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6314f9651d09dbb041d2e8851565e904366c9efe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="schema-determination-in-the-hl7-2x-disassembler"></a>HL7 2.X 逆アセンブラーでスキーマの決定
HL7 2.X メッセージには、本文のセグメント数と任意の数の Z セグメント続くヘッダー セグメント (MSH) が含まれます。 MSH には、21 のフィールドが含まれています。  
  
 メッセージが到着すると、2.X エンジンは、ヘッダーを使用して、メッセージ本文を解析するスキーマを決定を読み取ります。 次の一連のイベントが発生します。  
  
1.  逆アセンブラーが MSH3 の値を読み取ります (送信元パーティ) を次の検証オプションを決定します。  
  
    1.  本文の XML 検証を実行するかどうか  
  
    2.  本文データにフィールドを入力カスタム データを検証するかどうか  
  
    3.  末尾の本体に区切り記号を許可するかどうか  
  
    4.  ボディ スキーマのターゲットの名前空間 (**TargetNS**)  
  
2.  逆アセンブラーでは、MSH9 と MSH12 本体のルート ノード名を特定し、読み取ります。 アルゴリズムは次のとおりです。  
  
    ```  
    Body schema type = TargetNS + "#" + MSH9.1 + MSH9.2 + MSH12.1 (with dots removed) + MSH12.2 (or GLO if the value is blank) + MSH12.3 (or DEF if the value is blank)  
    ```  
  
     [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 後続のメッセージ ヘッダー内の区切り記号を常に許可します。 エンジンはセグメント識別子は、それぞれの行の最初の 3 つの文字を調べます。 それ以降ボディ スキーマを定義するすべてのセグメントの XML を生成します。 未定義のセグメントが検出されると、そのセグメントが Z セグメントとして扱います。 その時点から、未定義のすべてのセグメントは、メッセージの Z 部分を構成します。 [次へ] の MSH では、このメッセージの最後をマークします。 [次へ] MSH または BTS (バッチ トレーラー セグメント タグ) は、バッチ メッセージのメッセージの最後をマークします。 Z セグメントには、スキーマで宣言されているセグメントのみを含めることができます。 宣言されたセグメントが発生するとエラーにすることをお勧めします。  
  
## <a name="see-also"></a>参照  
 [メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [BTAHL72X フラット ファイル処理](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)
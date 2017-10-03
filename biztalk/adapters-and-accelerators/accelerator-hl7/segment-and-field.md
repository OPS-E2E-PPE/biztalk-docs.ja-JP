---
title: "セグメント化し、フィールド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, segments
- messages, fields
- segments, messages
ms.assetid: e68864e6-590c-47f3-8c9e-81831aec2642
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ca948748bc30f8c8a56f7c257b775b37a990625
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="segment-and-field"></a>セグメントとフィールド
セグメント テーブルでは、HL7 のセグメントを定義します。 各セグメントの定義では、次に示すパターンに従います。  
  
|SEQ|LEN|DT|オプトイン|RP/#|TBL #|アイテム番号|要素名|  
|---------|---------|--------|---------|------------|-----------|------------|------------------|  
|1|4|SI|O|||00104|-ID PID を設定します。|  
|2|20|CX|B|||00105|患者の ID|  
|3|250|CX|R|Y||00106|患者の識別子の一覧|  
|4|20|CX|B|Y||00107|代替患者 ID - PID|  
|5|250|XPN|R|Y||00108|患者の名前|  
|..||||||||  
|..||||||||  
|37|80|ST|O|||01541|歪み|  
|38|250|CE|O|2|0429|01542|実稼働クラス コード|  
  
 HL7 には、各フィールドのテキストの定義も含まれています。 3 文字セグメント タグとシーケンス番号は、セグメント内の各フィールドを一意に識別します。 たとえばの場合は、患者の識別セグメント タグ PID とシーケンス番号「5」を一意に識別患者の名前 フィールドです。 XML エンコーディングとインターフェイス ドキュメント両方規則を使用してこのセグメント内のフィールドを識別します。 セグメントの定義には、コード化された要素に適用されるテーブル数と同様に、各フィールドのデータ型の宣言も含まれています。  
  
 新しいバージョンは、セグメントの末尾にフィールドを追加するのみとフィールドを削除することはできません。 追加されたフィールドは、既存のフィールドの機能を置き換えるもの、旧バージョンとの互換性のため、最初のフィールドが残ります。 (これで、"B"で確認できます、必要に応じての上に列 PID.2 および PID.3)。  
  
 次の関数の[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) これらの要件をサポートします。  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]すべての HL7 バージョン V2.1 から標準セグメントをサポートします。  
  
-   インターフェイス仕様を作成インターフェイスを実装すると、必須またはサポートされていないと、標準で省略可能な機能の要件に基づきがフィールドのラベルを付けることができます。  
  
-   Z を作成する、ローカライズの必要に応じてセグメントします。  
  
-   フィールドのセマンティクスを再定義するか、セグメントにフィールドを追加することができますのローカライズの必要な場所です。 不正なローカリゼーションの見出しを下回ったことに注意してください。 ただし、場合によっては、レガシ インターフェイス、またはレガシ システムをサポートするためにこの機能が必要。  
  
## <a name="see-also"></a>参照  
 [HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)
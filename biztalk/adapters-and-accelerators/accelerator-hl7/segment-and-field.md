---
title: セグメントとフィールド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, segments
- messages, fields
- segments, messages
ms.assetid: e68864e6-590c-47f3-8c9e-81831aec2642
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 527774808bc2015189015adc41a894824c5208ec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289638"
---
# <a name="segment-and-field"></a>セグメントとフィールド
セグメント テーブルは、HL7 セグメントを定義します。 各セグメントの定義は、次に示すパターンを示しています。  
  
|SEQ|LEN|DT|オプトイン|RP/#|TBL #|項目番号|要素名|  
|---------|---------|--------|---------|------------|-----------|------------|------------------|  
|1|4|SI|O|||00104|-ID PID を設定します。|  
|2|20|CX|B|||00105|患者の ID|  
|3|250|CX|R|Y||00106|患者の識別子の一覧|  
|4|20|CX|B|Y||00107|代替の患者 ID - PID|  
|5|250|XPN|R|Y||00108|患者の名前|  
|..||||||||  
|..||||||||  
|37|80|ST|O|||01541|歪み|  
|38|250|CE|O|2|0429|01542|実稼働クラス コード|  
  
 HL7 には、各フィールドのテキストの定義も含まれています。 3 文字のセグメント タグとシーケンス番号は、セグメント内の各フィールドを一意に識別します。 たとえばの場合は、患者の識別セグメント タグ PID とシーケンス番号「5」を一意に識別患者名フィールド。 この規則両方使用して、セグメント内のフィールドを識別するために、XML エンコーディングとインターフェイスのドキュメント。 セグメントの定義には、コード化された要素に適用されるテーブルの数と同様に、各フィールドのデータ型の宣言も含まれています。  
  
 新しいバージョンでは、フィールドは、セグメントの最後にのみ追加でき、フィールドを削除することはできません。 追加のフィールドには、既存のフィールドの機能が置き換えられます、最初のフィールドは、旧バージョンと互換性のままです。 (これで、"B"で確認できます、必要に応じて上記 PID.2 および列 PID.3)。  
  
 Microsoft BizTalk Accelerator for HL7 の次の関数 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) これらの要件をサポートします。  
  
- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] バージョン 2.1 以降からのすべての HL7 バージョンの標準的なセグメントをサポートします。  
  
- インターフェイスの仕様を作成して、インターフェイスを実装する際に必須またはサポートされていませんのいずれかとして、標準の省略可能な機能の要件に基づいてフィールドのラベルを付けることができます。  
  
- Z を作成するセグメントのローカライズの必要な場所。  
  
- フィールドのセマンティクスを再定義するか、セグメントにフィールドを追加することができますローカライズの必要な場所。 不正なローカライズの見出しの下にあるこのに注意してください。 ただし、場合によってはレガシ インターフェイス、またはレガシ システムへのインターフェイスをサポートするには、この機能が必要です。  
  
## <a name="see-also"></a>参照  
 [HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)
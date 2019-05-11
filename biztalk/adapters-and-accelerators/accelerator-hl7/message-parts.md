---
title: メッセージ部分 |Microsoft Docs
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
- messages, message parts
- segments, messages
ms.assetid: 2bb6557e-cd4a-42b7-8bc2-f8b53a59517e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c67694dbfe2e0cdfbc330e36d51dcf8e5a3fccd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303684"
---
# <a name="message-parts"></a>メッセージ部分
HL7 メッセージには次の部分が含まれています。 セグメント、データ フィールド、コンポーネント、および必要に応じてサブコンポーネント。 HL7 メッセージでは、次の階層構造があります。  
  
 Segment  
  
 データ フィールド  
  
 コンポーネント  
  
 サブコンポーネントの情報 (省略可能)  
  
 **セグメント**  
  
 セグメントは、データ フィールドの論理的なグループです。 メッセージの階層の最上位レベル (階層 1) でのセグメントがいます。 各セグメントは、3 文字のリテラル値を含む名前を持ちます。 次の表では、ADT メッセージの種類に含まれているセグメント名の例を示します。  
  
|セグメントのコード|説明|  
|------------------|-----------------|  
|MSH|メッセージ ヘッダー|  
|EVN|イベントの種類|  
|PID|患者の情報|  
  
 HL7 メッセージが、*メッセージ ヘッダー*と*本文*します。 MSH セグメントがメッセージのヘッダーを定義し、他のすべての種類のセグメントがメッセージの本文を形成します。  
  
 **データ フィールド**  
  
 データ フィールドは、メッセージの階層の深さ 2 で出現する文字の文字列です。 データ型は、データ フィールドを定義します。単純および複雑な。  
  
 次の例は、MSH.1 と EVN.1 データ フィールドを含む MSH および EVN セグメントの階層的なメッセージの構造を示しています。  
  
 MSH  
  
 MSH.1  
  
 EVN  
  
 EVN.1  
  
 **コンポーネントとサブコンポーネント**  
  
 コンポーネントとサブコンポーネントをさらに データ フィールド内のデータが含まれます。 コンポーネントとサブコンポーネントは、同じフィールド内で繰り返すことができます。  
  
## <a name="see-also"></a>参照  
 [HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)
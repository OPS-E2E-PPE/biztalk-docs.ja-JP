---
title: メッセージ部分 |Microsoft ドキュメント
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
ms.openlocfilehash: d9b6b02096a0cc75460552a6cd1dd56ef9e6c4e9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22205082"
---
# <a name="message-parts"></a>メッセージ部分
HL7 メッセージには、次の部分が含まれています。 セグメント、データ フィールド、コンポーネント、および必要に応じてこれらのサブコンポーネントです。 HL7 メッセージでは、次の階層構造があります。  
  
 Segment  
  
 データ フィールド  
  
 コンポーネント  
  
 サブコンポーネント (省略可能)  
  
 **セグメント**  
  
 セグメントは、データ フィールドの論理的なグループです。 セグメントは、メッセージの階層の最上位レベル (階層 1) でです。 各セグメントには、3 文字のリテラル値が含まれる、名前が付いています。 次の表は、ADT メッセージの種類に含まれているセグメント名の例を示します。  
  
|セグメント コード|Description|  
|------------------|-----------------|  
|MSH|メッセージ ヘッダー|  
|EVN|[イベントの種類]|  
|PID|患者の情報|  
  
 HL7 メッセージが、*メッセージ ヘッダー*と*本文*です。 MSH セグメントがメッセージのヘッダーを定義し、その他のすべての種類のセグメントがメッセージの本文を形成します。  
  
 **データ フィールド**  
  
 データ フィールドは、メッセージの階層の深さ 2 で発生する文字の文字列です。 データ型は、データ フィールドを定義します。 単純と複合型。  
  
 次の例は、MSH.1 と EVN.1 データ フィールドを含む、MSH および EVN セグメントの階層的なメッセージの構造を示しています。  
  
 MSH  
  
 MSH.1  
  
 EVN  
  
 EVN.1  
  
 **コンポーネントとサブコンポーネント**  
  
 コンポーネントとサブコンポーネントをさらにデータ フィールド内のデータが含まれています。 コンポーネントとサブコンポーネントは、同じフィールド内で繰り返すことができます。  
  
## <a name="see-also"></a>参照  
 [HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)
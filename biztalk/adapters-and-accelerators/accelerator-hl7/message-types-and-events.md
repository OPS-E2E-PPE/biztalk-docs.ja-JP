---
title: "メッセージの種類とイベント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, message events
- HL7, message types
- message types
- messages, message types
ms.assetid: d53d51d0-216d-472b-97b7-8a96b8013510
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b9880da0ca5fea84c5a2b3d6e9f3a43ace41970
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-types-and-events"></a>メッセージの種類およびイベント
HL7 標準が実際のイベントとしてまとめての特定のグループ化に関連するメッセージをグループ化*メッセージの種類*ADT です。 これらのメッセージには、患者の管理などのトリガー イベントが含まれます。 HL7 標準のバージョン 2.4 は、100 個を超えるメッセージの種類、それぞれの HL7 組織が割り当てられている 3 文字の一意のメッセージ型のコードを定義します。 HL7 標準のバージョンがきたよう HL7 組織が新しい機能を提供する新しいメッセージの種類を追加します。  
  
 すべてのメッセージ型とも呼ばれる、メッセージ イベントを含む*イベント*です。 特定のメッセージ型の中でグループ化されたメッセージの一意の型としてイベントを検討することができます。 たとえば、Admin 訪問/通知 (メッセージ イベント A01) および放電/終了 (メッセージ イベント A03) を参照してくださいは、患者管理メッセージの種類 (ADT) に含まれる一意のメッセージです。 HL7 組織が割り当てられているメッセージの各イベントは一意のイベントの 3 文字コード。  
  
 1 つだけのメッセージの種類は、特定のメッセージ イベントを含めることができます。 メッセージの種類は、複数のメッセージ イベントを含めることができます。 ただし、特定のメッセージ イベントの構造は、HL7 標準のバージョンによって異なることができます。  
  
## <a name="see-also"></a>参照  
 [HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [HL7 2. XML スキーマを使用します。](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)   
 [イベントを発生させるとメッセージ](../../adapters-and-accelerators/accelerator-hl7/trigger-events-and-messages.md)   
 [HL7 メッセージ](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)
---
title: メッセージの種類とイベント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, message events
- HL7, message types
- message types
- messages, message types
ms.assetid: d53d51d0-216d-472b-97b7-8a96b8013510
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 143223d0ed0f03d6eaa66141ea052ed701638e56
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303656"
---
# <a name="message-types-and-events"></a>メッセージの種類とイベント
HL7 標準が実際のイベントとしてまとめての特定のグループ化に関連するメッセージをグループ化*メッセージの種類*ADT します。 これらのメッセージには、患者の管理などのトリガー イベントが含まれます。 HL7 標準のバージョン 2.4 は、100 を超えるメッセージの種類、それぞれの HL7 組織が割り当てられている一意の 3 文字メッセージ型のコードを定義します。 HL7 標準のバージョンが発展すると、HL7 組織の新機能を提供する新しいメッセージの種類が追加されます。  
  
 すべてのメッセージ型とも呼ばれる、メッセージ イベントが含まれている*イベント*します。 イベント メッセージの特定のメッセージ型内でグループ化の一意の型として考えることができます。 たとえば、管理者のアクセス/通知 (メッセージ イベント A01) と放電/終了 (メッセージ イベント A03) を参照してくださいは、患者管理メッセージの種類 (ADT) に含まれる一意のメッセージが。 HL7 組織では、一意の 3 文字イベント コードを各メッセージ イベントを割り当ています。  
  
 1 つだけのメッセージの種類には、特定のメッセージ イベントを含めることができます。 メッセージの種類は、複数のメッセージ イベントを含めることができます。 ただし、特定のメッセージ イベントの構造は、HL7 標準のバージョン間で異なることができます。  
  
## <a name="see-also"></a>参照  
 [HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [HL7 2. XML スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)   
 [トリガー イベントとメッセージ](../../adapters-and-accelerators/accelerator-hl7/trigger-events-and-messages.md)   
 [HL7 メッセージング](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)
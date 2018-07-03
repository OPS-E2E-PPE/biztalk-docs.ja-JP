---
title: トリガー イベントとメッセージ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- health care organizations, HL7 messages
- trigger events
- messages, trigger events
- messages, about messages
ms.assetid: e93b397c-8cbe-4589-aa88-e474d7722174
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 309d420d97cdc22c4f0eaca30bb6426e295cbe33
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971611"
---
# <a name="trigger-events-and-messages"></a>トリガー イベントとメッセージ
デジタルの医療システムでは、アプリケーションは、ラボにおける注文または薬の順序の配置などの実際のイベントのため HL7 メッセージを作成します。 HL7 の組織には、医療保険の実際のイベントは、これらのアプリケーションが異種システムにまたがる場合でも、アプリケーション間でフローにデータの必要性を作成することを前提と HL7 標準が書き込まれます。 HL7 標準は、この実際のイベントを呼び出して、*トリガー イベント*します。 自動化されたシステムは、トリガー イベントを認識体系的にする必要があります。  
  
 この概念を展開するには、次のシナリオを検討してください。 病院に到着してすぐには、患者が病院では、患者の管理ソフトウェア アプリケーションを使用して登録します。 患者のレコードをコミットするには、アプリケーションが必要 (会計、ラボなど) には、他の病院アプリケーションを通知するために、患者の登録についてです。 アプリケーション間でこの情報を共有すると、それらのアプリケーションを使用するエンティティが必要なサービスで患者を提供できるように、必要があります。 動作は、患者を登録するには、トリガー イベントの一種です。 通常、Web アプリケーションは、送信された患者レコードのデータを含む、HL7 メッセージを作成してこのトリガー イベントを作成します。  
  
 トリガー イベントは、メッセージを処理するアプリケーションでアクションをトリガーする 1 つまたは複数のメッセージの作成時に常にあります。 トリガー イベントは、IT 担当者が埋め込まれている Microsoft BizTalk Accelerator for HL7 の配置シナリオに関連する ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 病院の基幹業務アプリケーション内で。 このような展開シナリオであっても[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]トリガー イベントをトリガー イベントを生成するメッセージのみ意識する必要はありません。  
  
## <a name="see-also"></a>参照  
 [HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [HL7 2. XML スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)   
 [HL7 メッセージング](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)
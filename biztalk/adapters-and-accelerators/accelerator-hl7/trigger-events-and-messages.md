---
title: イベントとメッセージをトリガー |Microsoft ドキュメント
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
ms.openlocfilehash: 188d7f1e09ae3f96c953c6a83bbad42ccdce3643
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206538"
---
# <a name="trigger-events-and-messages"></a>イベントを発生させるとメッセージ
デジタルの医療システムでは、アプリケーションは、ラボにおける注文または医薬品の注文の配置などの実際のイベントのため HL7 メッセージを作成します。 HL7 組織が医療保険の実際のイベント データをこれらのアプリケーションが異種システムにまたがる場合でも、アプリケーション間でやり取りの必要性を作成することを前提として、HL7 標準を作成しています。 HL7 標準は、この実際のイベントを呼び出して、*トリガー イベント*です。 自動化されたシステムでは、トリガー イベントが認識体系的にする必要があります。  
  
 この概念を展開するには、次のシナリオを検討してください。 病院では、到着するまでの患者に病院では、患者の管理ソフトウェア アプリケーションを使用して登録します。 患者のレコードをコミットするには、、アプリケーションは、患者の登録に関する他の病院アプリケーション (会計、ラボなど) を通知するために必要です。 アプリケーション間でこの情報を共有すると、それらのアプリケーションを使用するエンティティは、患者に必要なサービスを提供できるように、必要があります。 患者を登録する次の操作は、トリガー イベントの種類です。 通常、Web アプリケーションは、患者のレコードのデータを含む HL7 メッセージを作成することでこのイベントのトリガーを作成します。  
  
 トリガー イベントは、メッセージを処理するアプリケーションでアクションをトリガーする 1 つまたは複数のメッセージの作成時に常に発生することがします。 IT 担当者が埋め込まれている展開シナリオに関係のあるイベントを発生させる[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 病院基幹業務アプリケーション内で。 このような展開シナリオであっても[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]するトリガー イベントをトリガー イベントを生成するメッセージだけを認識する必要はありません。  
  
## <a name="see-also"></a>参照  
 [HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [HL7 2. XML スキーマを使用します。](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)   
 [HL7 メッセージ](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)
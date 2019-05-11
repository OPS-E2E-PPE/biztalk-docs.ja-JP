---
title: FIN Response Reconciliation の昇格させたプロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- promoted properties, FIN Response Reconciliation
- FIN Response Reconciliation, promoted properties
ms.assetid: 1a638e9e-61eb-482c-8856-b1aea36c449c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23d1460163b67618c3f7e15f1c8bd14ecdd97556
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377874"
---
# <a name="fin-response-reconciliation-promoted-properties"></a>FIN Response Reconciliation の昇格させたプロパティ
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FIN Response Reconciliation の機能には、次の昇格させたプロパティが含まれています。  
  
|昇格させた名|説明|データ型|値の範囲|使用例|  
|-------------------|-----------------|---------------|-----------------|-------------------|  
|**A4SWIFT_FRRFailed**|このプロパティは、メインのメッセージを送信するときに、負のシナリオでは昇格されます。|ブール値|True<br /><br /> False|FRR 送信ポートのフィルター式のカスタム ハンドラーに失敗したメッセージを送信するために使用します。|  
|**A4SWIFT_FrrFailedReason**|元のメッセージが処理されなかったことが正常に SAA/SWIFT によってを示します。|String|-   \<NAKErrorCode\><br />-   TimedOut<br />-TransportError<br />-   Delayed_NAK<br />-AbortReceived|FRR 送信ポートのフィルター式のカスタム ハンドラーに失敗したメッセージを送信するために使用します。|  
|**A4SWIFT_FRRCorrelationToken**|送信、MT の一意の関連付けトークンを示す*xxx*メッセージ。|String|-|FRR にこのプロパティを比較し、 **MQMD_CorrelID** FIN 応答のコンテキスト プロパティ。|  
|**A4SWIFT_SendingServiceType**|FRR サービス メッセージを送信することを示します。|String|A4SWIFT_FrrService|昇格するときに**A4SWIFT_FRRFailed**が True に設定します。|  
  
## <a name="see-also"></a>参照  
 [A4swift _ * 昇格させたプロパティ](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)   
 [Message Repair and New Submission の昇格プロパティ](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission-promoted-properties.md)
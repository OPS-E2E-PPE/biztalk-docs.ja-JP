---
title: "昇格させたプロパティの FIN 対応調整 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- promoted properties, FIN Response Reconciliation
- FIN Response Reconciliation, promoted properties
ms.assetid: 1a638e9e-61eb-482c-8856-b1aea36c449c
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14a3e3a004dcb9e58abde08345352c02f0914801
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="fin-response-reconciliation-promoted-properties"></a>昇格させたプロパティの FIN 対応調整
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FIN 対応調整の機能には、次の昇格させたプロパティが含まれています。  
  
|昇格の名前|Description|データ型|値の範囲|使用例|  
|-------------------|-----------------|---------------|-----------------|-------------------|  
|**A4SWIFT_FRRFailed**|メインのメッセージを送信するときに、このプロパティは、負の値のシナリオで昇格します。|ブール値|True<br /><br /> False|カスタム ハンドラーに障害が発生したメッセージを送信する FRR 送信ポートのフィルター式で使用します。|  
|**A4SWIFT_FrrFailedReason**|元のメッセージが処理されなかったことが正常に SAA/SWIFT によってを示します。|文字列|-   \<NAKErrorCode ><br />はタイムアウトしました<br />-TransportError<br />-Delayed_NAK<br />-AbortReceived|カスタム ハンドラーに障害が発生したメッセージを送信する FRR 送信ポートのフィルター式で使用します。|  
|**A4SWIFT_FRRCorrelationToken**|送信 MT の一意の関連付けトークンを示す*xxx*メッセージ。|文字列|-|FRR が、このプロパティを比較し、 **MQMD_CorrelID** FIN 応答のコンテキスト プロパティです。|  
|**A4SWIFT_SendingServiceType**|FRR サービス メッセージを送信することを示します。|文字列|A4SWIFT_FrrService|昇格させた場合**A4SWIFT_FRRFailed**が True に設定します。|  
  
## <a name="see-also"></a>参照  
 [A4SWIFT_ * 昇格させたプロパティ](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)   
 [Message Repair and New Submission の昇格させたプロパティ](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission-promoted-properties.md)
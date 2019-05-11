---
title: 受信確認エラーの状態 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, errors
- errors, acknowledgements
ms.assetid: 605c7fa0-2365-4cb6-92fb-6df570905ca8
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae28a26d62ec18f6cfb81db55442b8e440b5a93c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247719"
---
# <a name="acknowledgment-error-conditions"></a>受信確認エラーの状態
致命的なエラーで、次の条件が発生条件の場合に Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) (ACK) メッセージを受信確認の処理には。  
  
- MSH9 で必須のフィールドがありません。  
  
- MSH12 で必須のフィールドがありません。  
  
  致命的なエラー条件で、次の条件が発生します。 このような状況で[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]ACK が生成されますが、また、ACK が中断します。  
  
- MSH11 で必要なフィールドが見つかりません  
  
- MSH10 値がありません。  
  
- ヘッダーの省略可能なフィールドの列挙型のエラー。  
  
> [!NOTE]
>  AL または ER、MSH 15 が設定されている場合、ヘッダーにある列挙型のエラーの[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]コミット ACK の状態が生成されます**MSA_1 CR を =** します。  
  
## <a name="see-also"></a>参照  
 [作成して、受信確認の処理](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [ACK メッセージ スキーマの種類](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md)   
 [メッセージの受信確認セグメント](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md)   
 [ACK を受信するための送信ポートの設定](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)
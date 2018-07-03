---
title: 確認の構成の設定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, configuring
- configuring, acknowledgements
ms.assetid: 46e92560-7b1e-4d53-9de8-8ded4de90695
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06cedaee1ca0ad574920cfb646f69d63157c8e67
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968059"
---
# <a name="ack-configuration-settings"></a>ACK の構成設定
Microsoft[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]パーサーが取引先管理 (TPM) の設定に基づいて受信確認を生成します。 確認 (ACK) の設定は、パートナー情報に依存します。 スキーマの種類は使用されません。 ときに[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]AL、SU または ER、含む MSH15 フィールドで、確認メッセージを受け取る[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]ACK ヘッダーと TPM の構成の解析結果に基づいて、このメッセージの ACK を送信することがあります。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 確認のパートナーの設定を取得し、次の 5 つの値のいずれかを返します。  
  
> [!NOTE]
>  HL7 の仕様には、1 4 からと生成される ACK メッセージの MSH15 フィールドを設定する項目を使用することが定められています。 項目 5 が[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]の特定、ACK を生成しないようにを表します  
  
1.  AL – 常に  
  
2.  ありません – NE  
  
3.  SU-成功  
  
4.  ER – エラー  
  
5.  [いいえ] – ACK を生成できません。  
  
## <a name="ack-configuration-inconsistency"></a>ACK の構成の不一致  
 場合は、ACK 構成ユーザー インターフェイスの設定とメッセージ インスタンス MSH15、MSH16 フィールド内の値の間に不整合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]が必要な 2 つの確認の生成のトリガーのいずれかの場合は、ACK を送信します。 その他の不整合の場合、インスタンス内のデータは構成ユーザー インターフェイスで設定をオーバーライドします。  
  
## <a name="see-also"></a>参照  
 [メッセージの受信確認の構成](../../adapters-and-accelerators/accelerator-hl7/configuring-message-acknowledgments.md)   
 [受信確認の作成と処理](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)
---
title: "確認の構成の設定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- acknowledgements, configuring
- configuring, acknowledgements
ms.assetid: 46e92560-7b1e-4d53-9de8-8ded4de90695
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93dea42fd084f22b4644f0acbb21860d69f75027
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="ack-configuration-settings"></a>確認の構成の設定
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]パーサーが取引先管理 (TPM) の設定に基づいて受信確認を生成します。 確認 (ACK) の設定は、パートナー情報に依存します。 スキーマの種類は使用されません。 ときに[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]AL、SU または ER、含む MSH15 フィールドで、確認メッセージを受信[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]ACK ヘッダーと TPM の構成の解析結果に基づくこのメッセージの ACK を送信することがあります。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]パートナー ACK 設定を取得し、次の 5 つの値のいずれかを返します。  
  
> [!NOTE]
>  HL7 仕様では 1 4 からと生成される ACK メッセージの MSH15 フィールドを設定する項目を使用することが必須です。 項目 5 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]-特定され、確認を生成しないようにを表します  
  
1.  AL – 常に  
  
2.  NE – ことはありません。  
  
3.  SU – 成功  
  
4.  ER – エラー  
  
5.  いいえ-ACK を生成しません。  
  
## <a name="ack-configuration-inconsistency"></a>ACK の構成の不整合  
 場合は、ACK 構成ユーザー インターフェイスの設定と、メッセージ インスタンス MSH15 と MSH16 フィールド内の値の間で不整合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]が必要な 2 つの確認の生成のトリガーのいずれかの場合は、ACK を送信します。 その他の不一致の場合は、インスタンス内のデータが構成ユーザー インターフェイスで設定を上書きします。  
  
## <a name="see-also"></a>参照  
 [メッセージの受信確認を構成します。](../../adapters-and-accelerators/accelerator-hl7/configuring-message-acknowledgments.md)   
 [作成して、受信確認の処理](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)
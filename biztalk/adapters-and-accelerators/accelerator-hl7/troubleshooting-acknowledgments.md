---
title: 受信確認のトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, troubleshooting
- troubleshooting, acknowledgements
ms.assetid: faed356e-f5fc-4920-a9f9-82eca0ad7d67
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a66eba1221b30ec142cc44400c60cff6f66e62e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286526"
---
# <a name="troubleshooting-acknowledgments"></a>受信確認のトラブルシューティング
関連する問題に対処[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]受信確認。  
  
## <a name="acknowledgments-are-not-generated"></a>受信確認は生成されません。  
 受信確認 (Ack) しないされている生成された、または受信したいくつかの潜在的な原因があります。 次の潜在的な問題の一覧を確認します。  
  
### <a name="symptom"></a>現象  
 パーティ情報を更新するときに、受信確認は生成されません[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]受信確認を生成するエクスプ ローラーを構成します。  
  
**考えられる原因**:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]をキャッシュし、パーティの構成情報を 15 分ごとに更新します。  
  
**解像度**:キャッシュを更新するには少なくとも 15 分待ってから、または再起動[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の効果をすぐに変更します。  
  
### <a name="symptom"></a>現象  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Ack は生成されませんし、イベント ログにイベントのエラーが表示されます。  
  
**考えられる原因**:ときにバッチを生成できません ACK/メッセージをバッチに空の FHS11 フィールドが含まれています。  
  
**解像度**:正しく書式設定された、指定済み FHS11 フィールドをメッセージがあることを確認します。  
  
### <a name="symptom"></a>現象  
 アプリケーションが生成または ACK を受信することはできません。  
  
**考えられる原因**:メッセージの MSH3 フィールドに情報が正しくないように[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]Ack メッセージを送信するからです。  
  
**解像度**:正しく書式設定された、指定済み MSH3 フィールドをメッセージがあることを確認します。  
  
## <a name="acknowledgments-are-suspended-or-not-routed-to-the-send-party"></a>受信確認が中断されたり、送信パーティにルーティングされません。  
  
### <a name="symptom"></a>現象  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 双方向アダプターの受信確認を生成せずに、メッセージを送信します。  
  
**考えられる原因**:メッセージのサブスクリプションが正しく構成されていません。  
  
**解像度**:メッセージのサブスクリプションが存在し、構成されている正しくを確認します。  
  
## <a name="suspended-acknowledgments"></a>中断された受信確認  
  
### <a name="symptom"></a>現象  
 受信確認がエラー メッセージ「フィールドで見つかった区切り記号」中断などの区切り記号の文字を含む文字をエンコードするパーティを構成するときに@-! $。  
  
**考えられる原因**:メッセージには、ピリオド (.) またはハイフン (-) などの文字が含まれています。 確認を生成するときに[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]が含まれています"."と"-"のタイムスタンプ値。  
  
**解像度**:これらのエラーを回避するために、送信パイプラインでの検証を無効にします。  
  
## <a name="biztalk-server-generates-an-error-about-missing-ack-when-using-2-way-mllp-adapter"></a>BizTalk Server には、双方向の MLLP アダプターを使用するときに ACK が見つからない場合のエラーが生成されます。  
  
### <a name="symptom"></a>現象  
 イベント ログに以下のようなエラーが発生しました。  
  
 "エラーのためのネットワークから ACK を受信することができません"HRESULT からの例外。0xC0C01662""  
  
**考えられる原因**:1 方向を使用している受信し、双方向送信ポートは BizTalk は対応する受信ポートを双方向の送信ポートから受信したメッセージを返すありません。  
  
**解像度**:仕様では、これは、エラー メッセージは無視できます。  
  
## <a name="see-also"></a>参照  
[HL7 のトラブルシューティングと既知の問題](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)
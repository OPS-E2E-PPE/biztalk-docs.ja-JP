---
title: "受信確認のトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- acknowledgements, troubleshooting
- troubleshooting, acknowledgements
ms.assetid: faed356e-f5fc-4920-a9f9-82eca0ad7d67
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ecbbb22498cfd3d451c0b8c75c8e6f4502c2364d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-acknowledgments"></a>受信確認のトラブルシューティング
関連する問題に対処[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]受信確認します。  
  
## <a name="acknowledgments-are-not-generated"></a>受信確認は生成されません。  
 いない生成されたり、受信確認 (Ack) のいくつかの潜在的な原因があります。 次の潜在的な問題の一覧を確認します。  
  
### <a name="symptom"></a>現象  
 パーティ情報を更新するときに、受信確認は生成されません[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]受信確認を生成するエクスプ ローラーを構成します。  
  
**考えられる原因**:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]をキャッシュし、パーティの構成情報を 15 分ごとに更新します。  
  
**解像度**: キャッシュを更新、または再起動には少なくとも 15 分間待機[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]変更がすぐに有効にします。  
  
### <a name="symptom"></a>現象  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]Ack を生成し、エラー イベントがイベント ログに記録します。  
  
**考えられる原因**: ときにバッチの確認を生成できません/メッセージをバッチには、空の FHS11 フィールドが含まれています。  
  
**解像度**: メッセージが正しく書式設定とデータが設定された FHS11 フィールドを持つことを確認してください。  
  
### <a name="symptom"></a>現象  
 アプリケーションが生成または ACK を受信できません。  
  
**考えられる原因**: MSH3 フィールドに、メッセージの情報が正しくないように[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]Ack メッセージを送信するからです。  
  
**解像度**: メッセージが正しく書式設定とデータが設定された MSH3 フィールドを持つことを確認してください。  
  
## <a name="acknowledgments-are-suspended-or-not-routed-to-the-send-party"></a>受信確認が一時停止中または送信パーティにルーティングされません。  
  
### <a name="symptom"></a>現象  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]双方向アダプターの受信確認を生成せずにメッセージを送信します。  
  
**考えられる原因**: メッセージ サブスクリプションが正しく構成されていません。  
  
**解像度**: メッセージのサブスクリプションが存在し、構成正しくことを確認します。  
  
## <a name="suspended-acknowledgments"></a>中断された受信確認  
  
### <a name="symptom"></a>現象  
 「フィールドで見つかった区切り記号」のエラー メッセージで受信確認が中断されているなどの区切り文字が含まれている文字をエンコードしてパーティを構成した場合@-! $ です。  
  
**考えられる原因**: メッセージには、ピリオド (.) またはハイフン (-) などの文字が含まれています。 Ack を生成するときに[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]が含まれています"."と"-"のタイムスタンプ値。  
  
**解像度**: これらのエラーを避けるために、送信パイプラインで検証を無効にします。  
  
## <a name="biztalk-server-generates-an-error-about-missing-ack-when-using-2-way-mllp-adapter"></a>BizTalk Server には、両方向 MLLP アダプターを使用するときに ACK が見つからない場合のエラーが生成されます。  
  
### <a name="symptom"></a>現象  
 イベント ログに、次のようなエラーを取得します。  
  
 "エラーのためのネットワークからの ACK を受信することができません"HRESULT からの例外: 0xC0C01662""  
  
**考えられる原因**: 1 方向を使用している受信し、双方向送信ポートは BizTalk が 2 方向の送信ポートから受信したメッセージを返すの対応する受信ポート。  
  
**解像度**: 仕様では、これは、エラー メッセージを無視することができます。  
  
## <a name="see-also"></a>参照  
[HL7 のトラブルシューティングと既知の問題](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)
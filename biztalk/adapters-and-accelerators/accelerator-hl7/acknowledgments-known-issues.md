---
title: 受信確認の既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- known issues, acknowledgements
- acknowledgements, known issues
ms.assetid: cb45f80e-ba89-4b3f-a770-4b1cf9b8e220
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 708d809b57afb3d435da4eb9be247ab3e6c24b6a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65248259"
---
# <a name="acknowledgments-known-issues"></a>受信確認の既知の問題
このセクションには、受信確認 (ACK) エラーを回避するために役立つ有用な情報が含まれています。  
  
## <a name="hl7-v21-acknowledgment-message-accepted-even-if-it-contains-msa6-field"></a>MSA6 フィールドが含まれている場合でも、HL7 V2.1 受信確認メッセージが受け入れられる  
 Microsoft [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) MSA6 フィールドを格納する場合でも、HL7 V2.1 受信確認メッセージを受け取ります。  
  
## <a name="msa-01-value-not-generated-for-commit-acknowledgment-errors"></a>MSA-01 値がコミットの受信確認エラーは生成されません。  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] コミットの受信確認エラー (CE)、MSA-01 の受信確認コードを生成しません。  
  
## <a name="two-way-mllp-adapter-might-not-detect-a-problem-with-an-ack"></a>双方向の MLLP アダプターでは、ACK に問題が検出されない可能性も  
 ときに[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]ACK を受信アダプターを双方向の MLLP アダプター上には、有効性を確認で軽量の検証を実行します。 有効にすることが見つかると MSA1 フィールドが抽出され、その値に応じて、アダプター再試行、中断、または、ACK が応答していた元のメッセージを削除します。 ただし、アダプターによって実行される検証は完全な検証ではないためには、アダプターが ACK に問題を検出できません。 たとえば、アダプターでは、ACK が有効ですをパイプラインは、ACK が整形式でされなかったことを確認し、確認メッセージを中断する一方、元のメッセージを削除することを決定でした。  
  
## <a name="v2xml-acks-with-multiple-errors-will-fail-validation"></a>V2。複数のエラーで XML Ack 検証に失敗します  
 受信の V2 の場合。XML メッセージには、1 つ以上のエラーが含まれています、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]パーサーは、V2 生成可能性があります。Error フィールドに 1 つ以上のエラーで XML 確認します。 このような V2。XML の確認には、HL7 標準では、パーサーが、V2 での 1 つだけのエラーを報告できるを指定するために、検証は失敗します。XML の ACK エラー フィールドです。  
  
## <a name="mllp-performance-counters-do-not-count-acks"></a>MLLP パフォーマンス カウンターには Ack はカウントされません。  
 1 つのメジャーの[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]MLLP パフォーマンス カウンターが示すとおり、パフォーマンスが、MLLP アダプターによって処理されるメッセージの数。 この数は、受信または送信されるメッセージの数を測定します。 ただし、カウントの Ack を受信または送信の数を計測しません。  
  
## <a name="nak-generated-by-two-way-mllp-adapter"></a>双方向の MLLP アダプターによって生成された NAK  
 双方向の MLLP アダプター、メッセージを中断するときに[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]NAK (否定受信確認) を生成し、メッセージ ボックス データベースに配置されます。 これにより、予期しない動作可能性があります。 メッセージ ボックス データベースから、NAK を削除するか、別のメッセージにマップすることがあります。  
  
## <a name="data-type-of-an-ack-to-a-batch-message"></a>ACK をバッチ メッセージのデータ型  
 ACK メッセージのバッチ メッセージへの応答で生成された MSH10 フィールド (メッセージのコントロール ID) は、バッチ メッセージに MSH10 フィールドのデータ型に基づくのではなく、GUID になります。  
  
## <a name="generated-acknowledgments-doc-type"></a>受信確認の生成されたドキュメントの種類  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] ドキュメントの種類を使用して受信確認の生成 http://Microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF または http://Microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF します。 送信先のパーティは、別の名前空間を使用している場合は、送信ポートで本文マップを適用する必要があります。それ以外の場合、シリアル化エラーが発生する可能性があります。  
  
## <a name="see-also"></a>参照  
 [既知の問題](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)
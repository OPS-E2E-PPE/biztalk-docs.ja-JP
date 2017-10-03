---
title: "受信確認の既知の問題 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- known issues, acknowledgements
- acknowledgements, known issues
ms.assetid: cb45f80e-ba89-4b3f-a770-4b1cf9b8e220
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af5964e94f2ddc1d53d5259b174f8e551353711d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="acknowledgments-known-issues"></a>受信確認の既知の問題
このセクションには、受信確認 (ACK) のエラーを回避するために役立つ有用な情報が含まれています。  
  
## <a name="hl7-v21-acknowledgment-message-accepted-even-if-it-contains-msa6-field"></a>MSA6 フィールドが含まれている場合でも、HL7 V2.1 受信確認メッセージが受け入れられます  
 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 場合でも、MSA6 フィールドが含まれています、HL7 V2.1 受信確認メッセージを受け取ります。  
  
## <a name="msa-01-value-not-generated-for-commit-acknowledgment-errors"></a>MSA-01 値がコミット受信確認エラーは生成されません。  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]MSA 01、受信確認コード内のコミットの受信確認エラー (CE) を生成しません。  
  
## <a name="two-way-mllp-adapter-might-not-detect-a-problem-with-an-ack"></a>双方向の MLLP アダプターは、ACK に問題を検出できません可能性もあります。  
 ときに[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]ACK を受信する双方向の MLLP アダプターのアダプターがその有効性を決定する ACK の軽量な検証を実行します。 見つかった場合は有効である、MSA1 フィールドを抽出すると、およびその値に応じて、アダプター再試行、中断、または、ACK が応答していた元のメッセージを削除します。 ただし、アダプターによって実行される検証は完全な検証ではないため、可能であれば、アダプターでは、確認に問題は検出されません。 たとえば、アダプターには、ACK が有効であり、パイプラインは、ACK が整形式でできなかったことを確認および ACK メッセージが中断され、元のメッセージを削除でしたを決定します。  
  
## <a name="v2xml-acks-with-multiple-errors-will-fail-validation"></a>V2 です。複数のエラーのある XML Ack は検証に失敗します。  
 着信 V2 の場合。XML メッセージには、1 つ以上のエラーが含まれています、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]パーサーは、V2 を生成する可能性があります。エラー フィールドに 1 つ以上のエラーのための ACK を XML です。 このような V2 です。HL7 標準を指定して、パーサーが、V2 で 1 つだけのエラーを報告できるので、XML ACK では、検証は失敗します。XML ACK エラー フィールドです。  
  
## <a name="mllp-performance-counters-do-not-count-acks"></a>パフォーマンス カウンターの MLLP Ack はカウントされません。  
 1 つのメジャーの[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]MLLP パフォーマンス カウンターによって示される、パフォーマンスが MLLP アダプターによって処理されるメッセージの数。 この数は、受信または送信されたメッセージの数を計測します。 ただし、カウントは Ack を受信または送信の数を測定していません。  
  
## <a name="nak-generated-by-two-way-mllp-adapter"></a>双方向の MLLP アダプターによって生成された NAK  
 双方向の MLLP アダプター、メッセージを中断するときに[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]NAK (否定受信確認) を生成し、メッセージ ボックス データベースに格納します。 予期しない動作があります。 メッセージ ボックス データベースから、NAK を削除するか、別のメッセージにマップすることがあります。  
  
## <a name="data-type-of-an-ack-to-a-batch-message"></a>バッチ メッセージに ACK のデータ型  
 バッチ メッセージへの応答で生成される ACK メッセージのバッチ メッセージの MSH10 フィールドのデータ型に基づいているのではなく、GUID、MSH10 フィールド (メッセージ コントロール ID) になります。  
  
## <a name="generated-acknowledgments-doc-type"></a>生成された受信確認ドキュメントの種類  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]ドキュメント型 http:// を使用して受信確認の生成[!INCLUDE[btsCoName](../../includes/btsconame-md.md)].com/HealthCare/HL7/2X#ACK_24_GLO_DEF または http://[!INCLUDE[btsCoName](../../includes/btsconame-md.md)].com/HealthCare/HL7/2X #ACK_25_GLO_DEF です。 送信ポート; 本文マップを適用する必要があります、送信先パーティでは、別の名前空間を使用する場合それ以外の場合、シリアル化エラーが発生する可能性があります。  
  
## <a name="see-also"></a>参照  
 [既知の問題](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)
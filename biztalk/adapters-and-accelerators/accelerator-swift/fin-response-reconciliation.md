---
title: FIN Response Reconciliation |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ACKs
- FRR
- FIN Response Reconciliation
- SAA
- NAKs
- FRR, about FRR
- acknowledgements
- FIN Response Reconciliation, about FIN Response Reconciliation
- FIN Response Reconciliation, acknowledgements
ms.assetid: 987b932b-e487-4ca8-acd0-410d71df8e6d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c2b74012c5f33967773234902a7475b8052f769
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377851"
---
# <a name="fin-response-reconciliation"></a>FIN Response Reconciliation
機能は、FIN 応答の調整 (FRR)[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]によって送信された対応する元のメッセージを FIN 応答の整合性を保ちます[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]します。 元のメッセージの状態を確立し、により、この[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]状態に基づく手順を実行します。 調整なしこのはできません。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 認識、ことが正常に (または失敗)、元のメッセージに送信 SAA と、転送の状態を示す SAA から受け取った応答必要がありますが、2 つの間の接続を作成することはできません。 FRR では、その接続を確立します。  
  
 FIN 応答が受信確認 (Ack) または否定受信確認応答 (NAKs) に SAA によって送信された[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]、SAA に SWIFT ネットワークで送信され、しに SAA によって転送または[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]します。 これらの受信確認の有無は、メッセージのビジネスの状態を定義します。 ビジネス アクティビティ監視 (BAM) のレポートには、この状態を監視することができます。  
  
 FRR をカスタム アプリケーションの動作を実装することもできます。 カスタム ハンドラーは、FIN 応答の調整のセットを処理するための独自のロジックを実装できます。 MTS21_FIN_ACKNAK NAK メッセージの FRR が関連付けられたメッセージを処理するカスタム ハンドラーの例は、次を参照してください。 [FRR NAK ハンドラー サンプル](../../adapters-and-accelerators/accelerator-swift/frr-nak-handler-sample.md)します。  
  
 FRR オーケストレーションが既定でインストールされている、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]セットアップ プログラム。 必要があります、受信パイプラインを作成して、FRR システムを構成する受信場所、および送信ポート。 どのくらいの期間待機と、応答の遅延の NAKs の一般を指定する FRR を構成する必要があります。 FRR 構成と管理の詳細については、次を参照してください。 [FIN Response Reconciliation の構成](../../adapters-and-accelerators/accelerator-swift/configuring-fin-response-reconciliation.md)と[FIN Response Reconciliation の管理](../../adapters-and-accelerators/accelerator-swift/administering-fin-response-reconciliation.md)します。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [FIN 応答の種類](../../adapters-and-accelerators/accelerator-swift/fin-response-types.md)  
  
-   [FRR 処理](../../adapters-and-accelerators/accelerator-swift/frr-processing.md)  
  
-   [FRR オーケストレーション](../../adapters-and-accelerators/accelerator-swift/frr-orchestration.md)  
  
-   [バックエンド アプリケーションからのメッセージの FRR 受信場所](../../adapters-and-accelerators/accelerator-swift/frr-receive-location-for-messages-from-the-back-end-application.md)  
  
-   [SWIFT へのメッセージのための FRR 送信ポート](../../adapters-and-accelerators/accelerator-swift/frr-send-port-for-messages-to-swift.md)  
  
-   [SWIFT からのメッセージのための FRR 受信場所](../../adapters-and-accelerators/accelerator-swift/frr-receive-location-for-messages-from-swift.md)  
  
-   [カスタム ハンドラーへのメッセージのための FRR 送信ポート](../../adapters-and-accelerators/accelerator-swift/frr-send-ports-for-messages-to-the-custom-handlers.md)  
  
-   [調整されたメッセージ セットの処理](../../adapters-and-accelerators/accelerator-swift/handling-reconciled-message-sets.md)
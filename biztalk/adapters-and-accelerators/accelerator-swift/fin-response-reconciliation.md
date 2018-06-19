---
title: FIN 対応調整 |Microsoft ドキュメント
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
ms.openlocfilehash: 5452dbacb8a9a20c8d2e62d62f6043aaea2d18da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22208258"
---
# <a name="fin-response-reconciliation"></a>FIN 対応調整
機能は、FIN 対応調整 (FRR)[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]によって送信される対応する元のメッセージに FIN 応答の整合性を保ちます[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]です。 これは、元のメッセージの状態を確立でき、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]その状態に基づいた手順を実行します。 調整なしこのいない可能性があります。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]かわかることと、正常終了 (または失敗)、メッセージを送信元 SAA に、送信の状態を示す SAA から受け取った応答必要がありますが、2 つの間の接続を作成することはできません。 FRR は、その接続を確立します。  
  
 FIN 応答は受信確認 (Ack) または否定受信確認応答 (NAKs) に SAA によって送信された[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]、SAA に SWIFT ネットワークは、によって送信され、しに SAA によって転送または[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]です。 これらの確認の有無は、メッセージのビジネスの状態を定義します。 ビジネス アクティビティ監視 (BAM) のレポートには、このステータスを監視することができます。  
  
 FRR の周囲のカスタム アプリケーションの動作を実装することもできます。 カスタム ハンドラーは、FIN 応答の調整のセットを処理するための独自のロジックを実装できます。 MTS21_FIN_ACKNAK NAK メッセージと共に FRR が関連付けられたメッセージを処理するカスタム ハンドラーの例は、次を参照してください。 [FRR NAK ハンドラー サンプル](../../adapters-and-accelerators/accelerator-swift/frr-nak-handler-sample.md)です。  
  
 FRR オーケストレーションがで既定でインストールされている、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]セットアップ プログラム。 必要とする、受信パイプラインを作成して、FRR システムを構成する受信場所、送信ポート。 どのくらいの期間待機は遅延 NAKs、および応答の一般を指定する FRR を構成する必要があります。 FRR 構成と管理の詳細については、次を参照してください。 [FIN 対応調整を構成する](../../adapters-and-accelerators/accelerator-swift/configuring-fin-response-reconciliation.md)と[FIN 対応調整を管理する](../../adapters-and-accelerators/accelerator-swift/administering-fin-response-reconciliation.md)です。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [FIN 応答の種類](../../adapters-and-accelerators/accelerator-swift/fin-response-types.md)  
  
-   [FRR 処理](../../adapters-and-accelerators/accelerator-swift/frr-processing.md)  
  
-   [FRR オーケストレーション](../../adapters-and-accelerators/accelerator-swift/frr-orchestration.md)  
  
-   [FRR は、バックエンド アプリケーションからのメッセージの場所を受信します。](../../adapters-and-accelerators/accelerator-swift/frr-receive-location-for-messages-from-the-back-end-application.md)  
  
-   [SWIFT メッセージの送信ポートを FRR](../../adapters-and-accelerators/accelerator-swift/frr-send-port-for-messages-to-swift.md)  
  
-   [FRR は、SWIFT からのメッセージの場所を受信します。](../../adapters-and-accelerators/accelerator-swift/frr-receive-location-for-messages-from-swift.md)  
  
-   [カスタム ハンドラーへのメッセージの送信ポートを FRR](../../adapters-and-accelerators/accelerator-swift/frr-send-ports-for-messages-to-the-custom-handlers.md)  
  
-   [処理は、メッセージの設定を調整](../../adapters-and-accelerators/accelerator-swift/handling-reconciled-message-sets.md)
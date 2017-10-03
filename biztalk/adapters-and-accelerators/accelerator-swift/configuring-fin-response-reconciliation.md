---
title: "FIN 対応調整の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FIN Response Reconciliation, configuring
- configuring, FIN Response Reconciliation
ms.assetid: dc934530-76ff-4cdb-b182-46f9ea0343b7
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 384a2ea27e3d208864c8b16ec52562e6e1cfa28e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fin-response-reconciliation"></a>FIN 対応調整を構成します。
次のセクションを構成する手順を実行する必要があります、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] FIN 対応調整 (FRR) 機能を次の図に示すようにします。  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-frr-configuration.jpg "A4SWIFT_FRR_Configuration")  
  
 A4SWIFT のインストール ウィザードで、Message Repair および New Submission と FRR、または Message Repair and New Submission FRR、または Message Repair and New Submission せず FRR なしのインストールを選択できます。 その結果、このセクションの手順に限りませんをインストールしている Message Repair and New Submission を構成します。 」の手順を実行したこと、ただし、前提、 [A4SWIFT ランタイムを構成する](../../adapters-and-accelerators/accelerator-swift/configuring-the-a4swift-runtime.md)です。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [バインドおよび FRR オーケストレーションを開始します。](../../adapters-and-accelerators/accelerator-swift/binding-and-starting-the-frr-orchestration.md)  
  
-   [受信パイプラインの FRR の作成](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-pipeline.md)  
  
-   [バックエンド アプリケーションから受信するための受信場所の FRR を作成します。](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-location-for-receiving-from-the-back-end-application.md)  
  
-   [SWIFT から受信するための受信場所の FRR を作成します。](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-location-for-receiving-from-swift.md)  
  
-   [FRR 送信パイプラインを作成します。](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-pipeline.md)  
  
-   [SWIFT に送信するための FRR 送信ポートを作成します。](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-port-for-sending-to-swift.md)  
  
-   [カスタム ハンドラーに送信するための FRR 送信ポートの作成](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)
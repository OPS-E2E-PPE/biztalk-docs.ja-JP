---
title: FIN Response Reconciliation の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FIN Response Reconciliation, configuring
- configuring, FIN Response Reconciliation
ms.assetid: dc934530-76ff-4cdb-b182-46f9ea0343b7
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77f2260c8e6096e2bef926fea45aaf778f4bdfa3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997907"
---
# <a name="configuring-fin-response-reconciliation"></a>FIN Response Reconciliation の構成
Microsoft を構成するのには、次のセクションで手順を実行する必要があります[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]FIN 応答の調整 (FRR) 機能を次の図に示すようにします。  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-frr-configuration.jpg "A4SWIFT_FRR_Configuration")  
  
 A4SWIFT のインストール ウィザードでは、Message Repair および New Submission と FRR、または Message Repair and New Submission FRR、または Message Repair and New Submission せず FRR せずにインストールできます。 その結果、このセクションの手順をインストールおよび Message Repair and New Submission の構成が想定しないでください。 ただし、前提としている手順を実行したこと、 [A4SWIFT ランタイムの構成](../../adapters-and-accelerators/accelerator-swift/configuring-the-a4swift-runtime.md)します。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [FRR オーケストレーションのバインドと開始](../../adapters-and-accelerators/accelerator-swift/binding-and-starting-the-frr-orchestration.md)  
  
-   [FRR 受信パイプラインの作成](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-pipeline.md)  
  
-   [バックエンド アプリケーションからの受信用として FRR 受信場所を作成する](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-location-for-receiving-from-the-back-end-application.md)  
  
-   [SWIFT からの受信用として FRR 受信場所を作成する](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-location-for-receiving-from-swift.md)  
  
-   [FRR 送信パイプラインの作成](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-pipeline.md)  
  
-   [SWIFT への送信用として FRR 送信ポートを作成する](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-port-for-sending-to-swift.md)  
  
-   [カスタム ハンドラーへの送信用として FRR 送信ポートを作成する](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)
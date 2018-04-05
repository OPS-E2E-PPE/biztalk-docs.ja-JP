---
title: ネットワーク構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, network configuration
ms.assetid: fb6265b8-2e6d-4344-bb44-4f4fd995382d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83a9e8ffe6b278c91429835c3ae32c96d45ef22e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="network-configuration"></a>ネットワークの構成
このセクションでは、展開でネットワークを構成するための規範的なガイダンスを提供します。 詳細については、次を参照してください。[の展開の準備](../../adapters-and-accelerators/accelerator-swift/preparing-for-deployment.md)です。  
  
 スイッチの仮想ローカル エリア ネットワーク (Vlan) を定義して、適切なケーブルを接続します。 Vlan を定義すると、ネットワーク セグメントまたは層ごとに、スイッチのポートを指定します。 次の環境の各 VLAN を作成する必要があります。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]層の送受信  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]オーケストレーションとデータベース層  
  
-   企業ネットワーク  
  
 Vlan を定義した後は、スイッチ上の適切なポートに、サーバーからネットワーク ケーブルを接続できます。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [物理的なダイアグラム](../../adapters-and-accelerators/accelerator-swift/physical-diagram.md)  
  
-   [ネットワーク負荷分散](../../adapters-and-accelerators/accelerator-swift/network-load-balancing.md)
---
title: ネットワーク構成 |Microsoft Docs
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
ms.openlocfilehash: 8fb693b9718b7c92e24f3537bea7ef27267f9a05
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967443"
---
# <a name="network-configuration"></a>ネットワークの構成
このセクションでは、展開でネットワークを構成するための規範ガイダンスを提供します。 詳細については、次を参照してください。[展開の準備](../../adapters-and-accelerators/accelerator-swift/preparing-for-deployment.md)します。  

 スイッチに仮想ローカル エリア ネットワーク (Vlan) を定義し、適切なケーブルを接続します。 Vlan を定義するには、各ネットワーク セグメントまたはレベルのスイッチのポートを指定します。 次の環境ごとの VLAN を作成する必要があります。  

- [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 層の送受信  

- [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] オーケストレーションとデータベース層  

- 企業ネットワーク  

  Vlan を定義した後は、スイッチの適切なポートに、サーバーからネットワーク ケーブルを接続できます。  

  このセクションには、次のトピックが含まれています。  

- [物理的なダイアグラム](../../adapters-and-accelerators/accelerator-swift/physical-diagram.md)  

- [ネットワーク負荷分散](../../adapters-and-accelerators/accelerator-swift/network-load-balancing.md)

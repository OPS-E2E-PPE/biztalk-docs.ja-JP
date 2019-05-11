---
title: テスト結果。主要業績評価指標のネットワーク |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9bdbc2df-9d19-4ae8-b540-ec1b9a7cdbe9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fdf346b1a13838ca8e3ba3cbd8ec208e33670f6c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400657"
---
# <a name="test-results-networking-key-performance-indicators"></a>テスト結果。ネットワー キング主要業績評価指標
このトピックでは、ネットワーク主要業績評価指標 (KPI) テスト シナリオの中に確認されたをまとめたものです。 これらのテストで測定した、ネットワーク パフォーマンスの評価、 **\Network Interface (\*) \Bytes total/sec**パフォーマンス モニター カウンターおよび測定することによって、 **SQL Network interface \bytes total/sec (Avg)** VSTS 2008 ロード テスト コント ローラーによって返されます。  
  
## <a name="summary-of-network-key-performance-indicators"></a>ネットワークの主要業績評価指標の概要  
 **比較のネットワー キング主要業績評価指標 –** HYPER-V 仮想マシンで実行されている BizTalk Server のネットワーク スループットが範囲から約 70% に 96% のネットワーク スループット、物理的な BizTalk Server で行うことに監視、、特定のテスト環境によって異なります。 HYPER-V 仮想マシンで実行されている SQL Server のネットワーク スループットがから約 68% から 81% のネットワーク スループットを特定のテスト環境に応じてもう一度、物理 SQL Server で行うことの範囲に確認されました。 観察されたネットワークのスループット単位のデルタは、HYPER-V ハイパーバイザーのリソース要件に起因ことができます。  
  
 次の手順では、[ネットワーク最適化](../technical-guides/network-optimizations.md)によって測定される、HYPER-V 仮想マシン上のネットワーク スループットを最大化する**\Network Interface (\*) \Bytes total/sec**  
  
 次の図は、さまざまなテスト プラットフォームのネットワーク パフォーマンスを示しています。  
  
 ![主要業績評価指標をネットワーク](../technical-guides/media/networkkpi.gif "NetworkKPI")  
  
 次の表は、収集された KPI の各構成の相対的なパフォーマンスを示しています。 各結果セットは KPI のベースライン構成の割合として計算されます。  
  
|KPI (KPI)|仮想 BizTalk/物理 SQL|個別のホスト上の仮想 BizTalk/仮想 SQL|統合環境で仮想 BizTalk/仮想 SQL|  
|---------|-----------------------------------|----------------------------------------------------|--------------------------------------------------------------|  
|\Network Interface(*)\Bytes Total/sec (Total Avg Across all BizTalk Servers)|96%|82.1%|70.2%|  
|SQL Network interface \bytes total/sec (Avg)|95.5%|81.2%|68.4%|  
  
 ネットワーク パフォーマンスを評価する方法の詳細については、次を参照してください。、**ネットワーク パフォーマンスを測定する**」の「[チェックリスト。HYPER-V のパフォーマンスを測定する](../technical-guides/checklist-measuring-performance-on-hyper-v.md)します。
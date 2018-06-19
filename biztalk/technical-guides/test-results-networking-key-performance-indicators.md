---
title: 'テスト結果: ネットワー キング主要業績評価指標 |Microsoft ドキュメント'
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
ms.openlocfilehash: 3eb4e10c739178e6cd923f65b51f982e05ab7f56
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "22302586"
---
# <a name="test-results-networking-key-performance-indicators"></a>テスト結果: ネットワー キング主要業績評価指標
このトピックでは、ネットワーク主要業績評価指標 (KPI)、テスト シナリオで監視された概要を示します。 これらのテスト評価のネットワークのパフォーマンスによって測定される、 **\Network インターフェイス (\*) \Bytes total/sec**パフォーマンス モニター カウンター、および測定することによって、 **SQL Network interface \bytes total/sec (Avg)** VSTS 2008 ロード テスト コント ローラーによって返されます。  
  
## <a name="summary-of-network-key-performance-indicators"></a>ネットワークの主要業績評価指標の概要  
 **ネットワー キング主要業績評価指標-の比較**HYPER-V 仮想マシンで実行されている BizTalk Server のネットワーク スループットが確認された範囲にから約 70% から 96% の物理 BizTalk サーバーで達成されるネットワーク スループット、特定のテスト環境に応じて。 HYPER-V 仮想マシンで実行されている SQL Server のネットワーク スループットがから約 68% から 81% の物理 SQL server の特定のテスト環境に応じて再び達成されるネットワーク スループットの範囲内に確認されました。 観察対象のネットワークのスループットのデルタは、HYPER-V ハイパーバイザーのリソース要件を属性付けすることができます。  
  
 手順に従います[ネットワーク最適化](../technical-guides/network-optimizations.md)によって測定される、HYPER-V 仮想マシン上のネットワーク スループットを最大化**\Network インターフェイス (\*) \Bytes total/sec**  
  
 次の図は、さまざまなテスト プラットフォームでは、ネットワークのパフォーマンスを示しています。  
  
 ![ネットワー キング主要業績評価指標](../technical-guides/media/networkkpi.gif "NetworkKPI")  
  
 次の表は、収集される KPI のそれぞれの構成の相対的なパフォーマンスを示しています。 各結果セットは、KPI の基準構成の割合として計算されます。  
  
|KPI (KPI)|仮想 BizTalk/物理 SQL|個別のホスト上の仮想 BizTalk/仮想 SQL|統合環境で仮想 BizTalk/仮想 SQL|  
|---------|-----------------------------------|----------------------------------------------------|--------------------------------------------------------------|  
|\Network Interface(*)\Bytes Total/sec (Total Avg Across all BizTalk Servers)|96%|82.1%|70.2%|  
|SQL Network Interface\Bytes Total/sec (Avg )|95.5%|81.2%|68.4%|  
  
 ネットワークのパフォーマンスを評価する方法の詳細については、次を参照してください。、**ネットワーク パフォーマンスの測定**」の「[チェックリスト: Hyper-v でのパフォーマンスの測定](../technical-guides/checklist-measuring-performance-on-hyper-v.md)です。
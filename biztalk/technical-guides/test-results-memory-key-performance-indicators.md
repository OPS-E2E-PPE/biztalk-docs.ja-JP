---
title: "テスト結果: メモリ主要業績評価指標 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 224c40e5-08a7-4d30-b03a-4b6add5cde1f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4edf88023ee9e30e7fd0c808346b6231112f8ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="test-results-memory-key-performance-indicators"></a>テスト結果: メモリ主要業績評価指標
このトピックでは、メモリ主要業績評価指標 (KPI)、テスト シナリオで監視された概要を示します。 これらのテストで測定された使用可能なメモリの評価、 **\Memory\Available Mbytes**パフォーマンス モニター カウンターです。  
  
## <a name="summary-of-memory-key-performance-indicators"></a>メモリ主要業績評価指標の概要  
 **メモリ主要業績評価指標-の比較**SQL Server と BizTalk Server によって測定に使用できるメモリの合計、 **\Memory\Available Mbytes**パフォーマンス モニター カウンターがすべてにわたって一貫性シナリオをテストします。 物理的な BizTalk Server コンピューターと仮想マシンで実行されている BizTalk Server コンピューターで利用できるメモリの平均に利用可能なメモリの平均差は 2 つの BizTalk Server コンピューターがテストに使用したという事実が原因3 つの中に仮想マシンで実行されている BizTalk Server コンピューターは、テストに使用しました。  
  
 次の図は、さまざまなテスト プラットフォームでは、メモリのパフォーマンスを示しています。  
  
 ![メモリ主要業績評価指標](../technical-guides/media/memorykpi.gif "MemoryKPI")  
  
 次の表は、収集される KPI のそれぞれの構成の相対的なパフォーマンスを示しています。 各結果セットは、KPI の基準構成の割合として計算されます。  
  
|KPI (KPI)|仮想 BizTalk/物理 SQL|個別のホスト上の仮想 BizTalk/仮想 SQL|統合環境で仮想 BizTalk/仮想 SQL|  
|---------|-----------------------------------|----------------------------------------------------|--------------------------------------------------------------|  
|SQL Server 使用可能なメモリ (Mbytes) 各サーバー|100.1%|97.1%|103.2%|  
|BizTalk の合計使用可能なメモリ (バイト)|88.3%|95.9%|96%|  
|サーバーあたりの平均/BizTalk 使用可能なメモリ (バイト)|58.9%|63.9%|64%|  
  
 メモリのパフォーマンスを評価する方法の詳細については、次を参照してください。、**メモリ パフォーマンスの測定**」の「[チェックリスト: Hyper-v でのパフォーマンスの測定](../technical-guides/checklist-measuring-performance-on-hyper-v.md)です。
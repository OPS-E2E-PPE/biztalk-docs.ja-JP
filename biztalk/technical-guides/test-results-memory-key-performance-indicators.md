---
title: テスト結果。メモリ主要業績評価指標 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 224c40e5-08a7-4d30-b03a-4b6add5cde1f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38b62f71a013a4e2fa36c20f1d2197db7d2f3a3f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298463"
---
# <a name="test-results-memory-key-performance-indicators"></a>テスト結果。メモリ主要業績評価指標
このトピックでは、メモリ主要業績評価指標 (KPI) テスト シナリオの中に確認されたをまとめたものです。 これらのテストで測定された使用可能なメモリの評価、 **\Memory\Available Mbytes**パフォーマンス モニター カウンター。  
  
## <a name="summary-of-memory-key-performance-indicators"></a>メモリ主要業績評価指標の概要  
 **メモリ主要業績評価指標 – の比較**から SQL Server および BizTalk Server によって測定される使用可能なメモリの合計、 **\Memory\Available 領域のメガバイト数**全体が一貫性のパフォーマンス モニター カウンターシナリオをテストします。 物理的な BizTalk Server コンピューターを仮想マシンで実行されている BizTalk Server コンピューターで使用できるメモリの平均使用可能なメモリの平均の違いは 2 つの BizTalk Server コンピューターがテストに使用したという事実が原因3 つの中に仮想マシンで実行されている BizTalk Server コンピューターは、テストに使用されました。  
  
 次の図は、さまざまなテスト プラットフォームでのメモリ パフォーマンスを示しています。  
  
 ![メモリ主要業績評価指標](../technical-guides/media/memorykpi.gif "MemoryKPI")  
  
 次の表は、収集された KPI の各構成の相対的なパフォーマンスを示しています。 各結果セットは KPI のベースライン構成の割合として計算されます。  
  
|KPI (KPI)|仮想 BizTalk/物理 SQL|個別のホスト上の仮想 BizTalk/仮想 SQL|統合環境で仮想 BizTalk/仮想 SQL|  
|---------|-----------------------------------|----------------------------------------------------|--------------------------------------------------------------|  
|SQL Server 使用可能なメモリ (Mb 数)|100.1%|97.1%|103.2%|  
|BizTalk の合計使用可能なメモリ (Mb)|88.3%|95.9%|96%|  
|サーバーあたりの平均/BizTalk 使用可能なメモリ (Mb)|58.9%|63.9%|64%|  
  
 メモリ パフォーマンスを評価する方法の詳細については、次を参照してください。、**メモリ パフォーマンスを測定する**」の「[チェックリスト。HYPER-V のパフォーマンスを測定する](../technical-guides/checklist-measuring-performance-on-hyper-v.md)します。
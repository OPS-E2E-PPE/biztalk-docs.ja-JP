---
title: リンクの表示を最適化する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a9e16ff-01d3-4b7d-91c4-59d17266ee6d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da7eec1cb22dfea1522b94d1bbb948a627ed4ffa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335826"
---
# <a name="how-to-optimize-the-display-of-links"></a>リンクの表示を最適化する方法
スキーマが大きい場合、マップでは、ソース スキーマと送信先スキーマ間のリンクの数が多いを含めることができます。 マップ画面間で多数のリンクを使用するが困難リンクまたはで動作する必要があるオブジェクトを追跡します。 また、送信元スキーマ、リンク、functoid および送信先スキーマ間で、エンド ツー エンドの関係を追跡するための困難ができます。 BizTalk マッパーでより複雑で大規模なスキーマを管理し、ルイユ マップ内のリンクの表示を最適化できます。 このトピックでは、リンクを表示する方法の詳細を提供します。  
  
 とおりリンクを分類することができます。  
  
-   部分的にスコープ内  
  
-   完全にスコープ内  
  
-   完全にスコープ外  
  
## <a name="prerequisites"></a>前提条件  
 これらの手順では、BizTalk マッパーが実行されている必要があります。  
  
## <a name="to-view-the-links-partially-in-scope"></a>部分的にスコープ内のリンクを表示するには  
 グリッド画面に表示される少なくとも 1 つの終了しているリンクは「部分的にスコープ内。」と呼ばれます。  
  
 次の図は、"部分的にスコープ。"内にあるリンクを示しています。 これらのリンクは、グリッド ページの破線として表示されます。  
  
 グリッド画面に部分的に表示されているリンクをクリックし、グリッド ページはアップ/ダウンを自動的に移動すると、現在のビューにリレーションシップを表示します。  
  
 ![部分的にスコープ内のマッパー リンク](../core/media/mapper-partiallyinscope.gif "Mapper_PartiallyInScope")  
  
## <a name="to-view-the-links-completely-in-scope"></a>完全にスコープ内のリンクを表示するには  
 グリッド画面に両方の end (functoid、functoid、functoid、またはノードを functoid にノードをノード) 表示しているリンクは「完全にスコープ内。」と呼ばれます。  
  
 "ある DataCollection1"と"ST01"間のリンクを下の図は、完全にスコープであります。  
  
 リンクをクリックし、ターゲット ノードには、送信元ノードからのリレーションシップを選択します。  
  
 ![完全にスコープ内のマッパー リンク](../core/media/mapper-completelyinscope.gif "Mapper_CompletelyInScope")  
  
## <a name="to-view-the-links-completely-out-of-scope"></a>完全にスコープ外のリンクを表示するには  
 現在のマップ ビューに表示されるエンドポイントのどちらを持つリンクは"完全にスコープ外。"と呼ばれます。  
  
 次の図は、完全にスコープ外にあるリンクを示します。  
  
 これらのリンク、マップ画面に (どのリンクも表示されている) ためにを表示したくない場合をクリックしてオフにすることができます![リンクをすべて表示](../core/media/mapper-showhideoutscopelinks.gif "Mapper_ShowHideOutScopeLinks")マッパー上ユーティリティ リボンです。 これには、グリッド ビューに表示されているリンクの数が削減されます。  
  
 ![完全にスコープ外のマッパー リンク](../core/media/mapper-completelyoutscope.gif "Mapper_CompletelyOutScope")  
  
## <a name="see-also"></a>参照  
 [BizTalk マッパーの強化された機能の使用](../core/using-enhanced-features-in-biztalk-mapper.md)
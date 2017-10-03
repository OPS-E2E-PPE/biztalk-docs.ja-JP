---
title: "リンクの表示を最適化する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2a9e16ff-01d3-4b7d-91c4-59d17266ee6d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 689ab4c67bfe8cabc8109c373e899d391fdd56a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-optimize-the-display-of-links"></a>リンクの表示を最適化する方法
スキーマの規模が大きい場合、マップに含まれる送信元スキーマと送信先スキーマとのリンクの数が多数になる場合があります。 マップ画面全体で多くのリンクを使用する可能性がありますが難しいと感じてリンクまたはで動作する必要があるオブジェクトを追跡するためにします。 また、送信元スキーマ、リンク、Functoid、および送信先スキーマのエンドツーエンドの関係を追跡することも難しくなる可能性があります。 BizTalk マッパーでは、複雑で大規模なスキーマを効率的に管理し、マップ内のリンクの表示を最適化することができます。 このトピックでは、リンクの表示方法について詳しく説明します。  
  
 リンクは次のように分類することができます。  
  
-   部分的にスコープ内  
  
-   完全にスコープ内  
  
-   完全にスコープ外  
  
## <a name="prerequisites"></a>前提条件  
 これらの手順では、BizTalk マッパーが実行されている必要があります。  
  
## <a name="to-view-the-links-partially-in-scope"></a>部分的にスコープ内にあるリンクを表示するには  
 少なくとも一方の端がグリッド画面に表示されているリンクを、"部分的にスコープ内" にあるリンクと呼びます。  
  
 次の図は、"部分的にスコープ内" にあるリンクを示しています。 これらのリンクは、グリッド ページでは破線で表示されます。  
  
 グリッド画面に部分的に表示されているリンクをクリックすると、グリッド ページが自動的に上/下に移動して、現在のビューにリレーションシップが表示されます。  
  
 ![部分的にスコープ内のマッパー リンク](../core/media/mapper-partiallyinscope.gif "Mapper_PartiallyInScope")  
  
## <a name="to-view-the-links-completely-in-scope"></a>完全にスコープ内にあるリンクを表示するには  
 グリッド画面に両方の端 (ノードとノード、ノードと Functoid、Functoid と Functoid、または Functoid とノード) が表示されているリンクを、"完全にスコープ内" にあるリンクと呼びます。  
  
 次の図は、完全にスコープ内にある "DataCollection1" と "ST01" とのリンクを示しています。  
  
 リンクをクリックすると、送信元ノードから送信先ノードへのリレーションシップが選択されます。  
  
 ![完全にスコープ内のマッパー リンク](../core/media/mapper-completelyinscope.gif "Mapper_CompletelyInScope")  
  
## <a name="to-view-the-links-completely-out-of-scope"></a>完全にスコープ外にあるリンクを表示するには  
 現在のマップ ビューにどちらのエンド ポイントも表示されていないリンクを、"完全にスコープ外" にあるリンクと呼びます。  
  
 次の図は、完全にスコープ外にあるリンクを示しています。  
  
 これらのリンク、マップ画面に (どのリンクも表示されている) ためにを表示したくない場合、 をクリックしてオフにすることもできます![リンクをすべて表示](../core/media/mapper-showhideoutscopelinks.gif "Mapper_ShowHideOutScopeLinks")マッパー上表示するユーティリティ リボンです。 これによって、グリッド ビューに表示されるリンクの数を減らすことができます。  
  
 ![完全にスコープ外のマッパー リンク](../core/media/mapper-completelyoutscope.gif "Mapper_CompletelyOutScope")  
  
## <a name="see-also"></a>参照  
 [BizTalk マッパーの強化された機能を使用](../core/using-enhanced-features-in-biztalk-mapper.md)
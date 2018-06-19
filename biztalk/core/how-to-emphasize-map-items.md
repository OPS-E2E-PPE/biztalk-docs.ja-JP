---
title: マップ項目を強調する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2732b36-ca57-4566-ba26-da27a3082f32
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6bb03969a044c6a474f5d2d1c1e5e1a5067cf81
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
ms.locfileid: "22255442"
---
# <a name="how-to-emphasize-map-items"></a>マップ項目を強調する方法
BizTalk マッパーでマップ項目を選択すると、関連付けられたすべてのリンクと Functoid が強調表示されます。 これは、マップに多くのリンクが設定されていて、リレーションシップや関連するスキーマ項目を識別するのが難しい場合に便利です。  
  
 BizTalk マッパーでリンク、Functoid、またはスキーマ要素を選択すると、関連するリレーションシップとスキーマ要素が強調表示されます。 選択したマップ項目について、すべての受信リンクと送信リンクが (再帰的に) 太く強調され、その他すべてのマップ項目はグレー表示されます。次のスクリーンショットは、選択されたマップ項目が太くカラーで表示され、その他のマップ項目が薄く表示された状態を示しています。  
  
> [!NOTE]
>  ここでの関連するリレーションシップとは、選択されたマップ項目に直接または間接的にリンクされたリンク、Functoid、またはスキーマ要素を意味します。  
  
 ![マップ項目の強調](../core/media/mapper-intelliselect.gif "Mapper_IntelliSelect")  
  
## <a name="prerequisites"></a>前提条件  
 この操作では、BizTalk マッパーが実行されている必要があります。  
  
## <a name="to-emphasize-a-map-item"></a>マップ項目を強調表示するには  
  
-   マップ項目 (リンク、Functoid、またはスキーマ要素) をクリックします。 その他のすべてのリンクおよび functoid (スキーマのノードを含む) の現在のグリッド ページで選択されているマップ アイテムに関連付けられているが強調表示されたことを確認できます。  
  
     選択されたノードには、他のグリッド ページにもリレーションシップが存在する場合があります。 そのような場合、BizTalk マッパーでは現在のグリッド ページ内のインスタンスが強調表示されることに加えて、選択したノードと関連するリレーションシップが存在するページのタブも強調表示されます。  
  
## <a name="see-also"></a>参照  
 [BizTalk マッパーで強化された機能を使用します。](../core/using-enhanced-features-in-biztalk-mapper.md)
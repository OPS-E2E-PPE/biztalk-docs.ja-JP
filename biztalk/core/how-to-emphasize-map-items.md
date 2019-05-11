---
title: マップ項目を強調する方法 |Microsoft Docs
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
ms.openlocfilehash: 5be500ad36b27848733863ffde1a648d42c7db17
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385147"
---
# <a name="how-to-emphasize-map-items"></a>マップ項目を強調する方法
BizTalk マッパーでマップ アイテムを選択すると、すべての関連するリンクと functoid が強調表示されます。 これはリレーションシップと関連するスキーマ項目を識別するが難しいマップ リンクが多数に役立ちます。  
  
 リンク、functoid、またはスキーマ要素を選択すると、BizTalk マッパーは、関連するリレーションシップとスキーマ要素を強調します。 選択したマップ項目の太字で強調表示は、受信リンクと送信リンクが (再帰的に) すべてと他のすべてのマップ項目がグレーします。次のスクリーン ショットが太字で選択したマップ項目を表示し、色とその他のマップ項目が明るきます。  
  
> [!NOTE]
>  このコンテキストでは、関連するリレーションシップは、直接または間接的には、選択したマップ項目にリンクされているすべてのリンク、functoid、またはスキーマ要素を意味します。  
  
 ![マップ項目の強調](../core/media/mapper-intelliselect.gif "Mapper_IntelliSelect")  
  
## <a name="prerequisites"></a>前提条件  
 この操作では、BizTalk マッパーが実行されている必要があります。  
  
## <a name="to-emphasize-a-map-item"></a>マップ項目を強調するには  
  
-   マップ アイテム (リンク、functoid、またはスキーマ要素) をクリックします。 その他のすべてのリンクと functoid (スキーマ ノードを含む) に関連付けられた現在のグリッド ページで選択したマップ項目が強調表示されたことを確認できます。  
  
     場合によっては、選択したノードのある可能性がありますの他のグリッド ページ内に存在するリレーションシップ。 このような場合は、BizTalk マッパーは現在のグリッド ページ内のインスタンスが強調しも選択したノードに関連するリレーションシップが存在するページのタブが強調表示されます。  
  
## <a name="see-also"></a>参照  
 [BizTalk マッパーの強化された機能の使用](../core/using-enhanced-features-in-biztalk-mapper.md)
---
title: マップ内のスキーマのノードを照合する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 584f85d2-6198-4ef3-90d9-a322f1457d9a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1e2ce880489ca49b0b55d2e6f45b9e887d719a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253938"
---
# <a name="how-to-match-schema-nodes-in-a-map"></a>マップ内のスキーマ ノードを照合する方法
送信元スキーマまたは送信先スキーマが複雑な場合、要素をマップするのが難しいことがあります。 BizTalk マッパー、**指示一致**機能で、最適な一致を指摘することで複雑なスキーマ要素をマップすることができます。 このトピックでは、次の操作を実行する方法について説明します。  
  
> [!NOTE]
>  BizTalk マッパーは、スキーマ ノードに対して可能性のある一致を示します。 現在、この機能は English 名についてのみサポートされています。  
  
## <a name="prerequisites"></a>前提条件  
 作業を行うには、BizTalk マッパーが実行されている必要があります。  
  
### <a name="to-match-relevant-schema-nodes"></a>関連するスキーマ ノードを一致させるには  
  
1.  最善の一致を調べることや、をクリックする必要のあるスキーマ要素を右クリックして**指示一致**です。 BizTalk マッパーで、最善の一致 (7 つ) が強調表示され、その中で最適な一致が選択されます。  
  
     または、選択することができます**指示一致**BizTalk メニュー、または SHIFT キーを押し + スペース キー。  
  
     次の図は、送信先スキーマで選択したノードの推奨一致を示したものです。  
  
     ![推奨マッピング](../core/media/suggestive-mapping.gif "Suggestive_Mapping")  
  
    > [!NOTE]
    >  推奨一致の間を移動するには、Shift キーを押します。  
  
2.  ここでは次の操作が可能です。  
  
    -   Enter キーを押して、強調表示されている (可能な範囲で最善の) 一致を確定します。  
  
    -   上下矢印キーを使用して、強調表示されている一致の間を優先順位の順序で循環移動します。  
  
        > [!NOTE]
        >  下矢印キーを押すと次の最善一致に移動し、上矢印キーを押すと前の最善一致が強調表示されます。  
  
    -   Home キーを押すと、最初の一致に戻ります。  
  
## <a name="see-also"></a>参照  
 [BizTalk マッパーの強化された機能を使用](../core/using-enhanced-features-in-biztalk-mapper.md)
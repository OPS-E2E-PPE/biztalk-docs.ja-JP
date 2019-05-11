---
title: マップ内のスキーマのノードを照合する方法 |Microsoft Docs
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
ms.openlocfilehash: 3a25bf295a767f34b692d54fc922fb8fe489ecc1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336151"
---
# <a name="how-to-match-schema-nodes-in-a-map"></a>マップ内のスキーマ ノードを照合する方法
送信元または送信先スキーマが複雑なときに、要素をマップ難しいことができます。 BizTalk マッパー、**指示一致**機能で、最適な一致を提案して複雑なスキーマ要素をマップすることができます。 このトピックでは、次の操作を実行する方法について説明します。  
  
> [!NOTE]
>  BizTalk マッパーでは、スキーマのノードに一致する候補を提案します。 この機能は現在 English 名についてのみサポートされています。  
  
## <a name="prerequisites"></a>前提条件  
 これらの手順では、BizTalk マッパーが実行されている必要があります。  
  
### <a name="to-match-relevant-schema-nodes"></a>関連するスキーマのノードに一致するには  
  
1.  選択しをクリックして、最善の一致を知る必要があるスキーマ要素を右クリックして**指示一致**します。 BizTalk マッパーには、最適な一致 (7 つに制限付き)、選択されている最も最適な一致が強調表示されます。  
  
     または、選択**指示一致**BizTalk メニューのまたは SHIFT キーを押してから + スペース キー。  
  
     次の図は、送信先スキーマで選択したノードの一致を示したものを示します。  
  
     ![推奨マッピング](../core/media/suggestive-mapping.gif "Suggestive_Mapping")  
  
    > [!NOTE]
    >  一致を示したものの間を移動する SHIFT キーを保持します。  
  
2.  次のようになりました行えます。  
  
    -   Enter キーを押して、強調表示されている最適な (可能な場合) の一致を確認します。  
  
    -   上下矢印キーを使用して、順番に強調表示されている一致する優先順位の順序。  
  
        > [!NOTE]
        >  次の最適な一致をスキャンする下方向キーを押し、上矢印キーは、前の最適な一致を強調表示されます。  
  
    -   最上位の一致に戻りますホーム キーを押します。  
  
## <a name="see-also"></a>参照  
 [BizTalk マッパーの強化された機能の使用](../core/using-enhanced-features-in-biztalk-mapper.md)
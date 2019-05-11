---
title: スキーマ ツリー ビューを最適化する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab4ad6b5-5bbd-443b-9041-6cddf9d64735
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3655e3bdf60aafc243c2d415f70da26224140a67
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384467"
---
# <a name="how-to-optimize-the-schema-tree-view"></a>スキーマ ツリー ビューを最適化する方法
使用することができます、**関連ビュー**ソースの最適化や送信先スキーマ ツリーに BizTalk マッパーでします。 このトピックでは、操作を実行する方法について説明します。  
  
 関連ビューでは、折りたたむには、スキーマのよりコンパクトなビューを提供するのに関連のないスキーマ要素の兄弟要素を使用します。 これにより、スクロールし、スキーマとマップを使用するための要件に重点を置く必要があるがさらに削減されます。  
  
 関連ビューがスキーマが無効になっている図は、次のとおりです。 [スキーマ] ペインには、ノードがリレーションシップの一部がするかしないかどうかに関係なく、すべてのノードが表示されます。  
  
 ![関連ビューがオフになっている場合は、スキーマ](../core/media/off-schema-relevance-view.gif "Off_Schema_Relevance_View")  
  
 をクリックして、![関連ビューに切り替える](../core/media/mapper-intellitree.gif "Mapper_IntelliTree")関連ビューを有効にするマッパー ユーティリティ リボンのアイコン。 いずれかまたは両方、送信元スキーマとターゲット スキーマの関連ビューに切り替えることができます。ソースとターゲット スキーマのそれぞれのアイコンをクリックします。  
  
 スキーマの関連ビューに切り替えると。  
  
-   それらのいずれかのすべてのリンクがないすべてのレコード要素またはその子フィールド要素が折りたたまれています。  
  
-   すべてのリンクがないすべての連続したノードをひとまとめにしては置き換えられます、![ひとまとめにすると非表示ノード](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")アイコン。 BizTalk マッパーは、結合して 2 つの連続する関連のないノードの最小値を検索します。 まとめられたノードの一覧を表示するアイコンの上、マウスを移動することができます。 まとめられた複数のノードがある場合でも、ヒントは最初の 3 つのまとめられたノードの名前を一覧表示のみに注意してください。 すべてのノードをクリックして表示することができます、![ひとまとめにすると非表示ノード](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")アイコン。  
  
    > [!NOTE]
    >  ヒントの詳細については、次を参照してください。[ビュー ヒントとツールヒント方法](../core/how-to-view-infotip-and-tooltip.md)します。  
  
## <a name="prerequisites"></a>前提条件  
 この操作では、BizTalk マッパーが実行されている必要があります。  
  
## <a name="to-optimize-the-schema-tree-view"></a>スキーマ ツリー ビューを最適化するには  
 マッパー ユーティリティ リボンで、クリックして、それぞれ元/送信先スキーマの関連性ビューでに![関連ビューに切り替える](../core/media/mapper-intellitree.gif "Mapper_IntelliTree")アイコン。 次の図は、オンにすると、関連ビューを同じスキーマを示します。 すべての関連のないノードに置き換え、![ひとまとめにすると非表示ノード](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")アイコンでよりコンパクトにスキーマの表示を提供します。  
  
 ![関連ビューが ON の場合、スキーマ](../core/media/on-schema.gif "On_schema")  
  
 元または送信先のスキーマにまとめられたノードを展開すると、![ひとまとめにすると非表示ノード](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")変更![ひとまとめにすると表示されているノード](../core/media/switchoff-mapper-coalesence.jpg "SwitchOff_Mapper_Coalesence")アイコン。  
  
> [!NOTE]
>  CTRL + M、CTRL + E または CTRL + M、CTRL + C を展開または送信元スキーマのツリー ノードを折りたたみますキーを押すことができます。 同様に、CTRL + M、CTRL + E または CTRL + M、CTRL + C を展開または送信先スキーマ内のツリー ノードを折りたたみますキーを押すことができます。 ソースまたはターゲットのそれぞれの結合、CTRL + M キー、Ctrl + H または Ctrl + M、Ctrl キーを押しながら D キーを押すこともできます。 マッパーのキーボード ショートカットの一覧は、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk マッパーの強化された機能の使用](../core/using-enhanced-features-in-biztalk-mapper.md)
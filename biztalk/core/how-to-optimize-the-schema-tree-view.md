---
title: スキーマ ツリー ビューを最適化する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: aeeddd0893b80c1c7b37b2d0ee5f9f6cd68849d6
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
ms.locfileid: "22255346"
---
# <a name="how-to-optimize-the-schema-tree-view"></a>スキーマ ツリー ビューを最適化する方法
使用することができます、 **関連ビュー** 最適化元や送信先スキーマ ツリーに BizTalk マッパーでします。 このトピックでは、その操作の実行手順について説明します。  
  
 関連ビューでは、兄弟要素をまとめることにより関連のないスキーマ要素が折りたたまれ、スキーマがよりコンパクトに表示されます。 これにより、スクロール操作が減り、スキーマやマップの使用要件に集中しやすくなります。  
  
 次の図は、関連ビューが無効になっている場合のスキーマです。 スキーマ ペインには、ノードがリレーションシップの一部であるかどうかは関係なく、すべてのノードが表示されています。  
  
 ![関連ビューがオフになっている場合は、スキーマ](../core/media/off-schema-relevance-view.gif "Off_Schema_Relevance_View")  
  
 クリックして、![関連ビューに切り替える](../core/media/mapper-intellitree.gif "Mapper_IntelliTree")関連ビューをオンにするマッパー ユーティリティ リボンのアイコン。 送信元スキーマと送信先スキーマのそれぞれのアイコンをクリックすることで、送信元スキーマや送信先スキーマのいずれかまたは両方を関連ビューに切り替えることができます。  
  
 スキーマの関連ビューに切り替えると、次のようになります。  
  
-   その要素またはその子フィールド要素についてのリンクがないレコード要素はすべて折りたたまれます。  
  
-   すべてのリンクを持たないすべての連続したノードとして結合し、は置き換えられます、![ノードの非表示に結合された](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")アイコン。 BizTalk マッパーでは、関連のない 2 つ以上連続したノードを見つけて、1 つにまとめます。 アイコンの上にマウス ポインターを置くと、まとめられたノードの一覧が表示されます。 多数のノードが 1 つにまとめられているとしても、ヒントに表示されるのは、そのうち最初の 3 つのノードの名前だけです。 クリックしてすべてのノードを表示することができます、![ノードの非表示に結合された](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")アイコン。  
  
    > [!NOTE]
    >  ヒントの詳細については、次を参照してください。[ビュー ヒントとツールヒント ハウツー](../core/how-to-view-infotip-and-tooltip.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 この操作では、BizTalk マッパーが実行されている必要があります。  
  
## <a name="to-optimize-the-schema-tree-view"></a>スキーマのツリー ビューを最適化するには  
 マッパー ユーティリティ リボンで、送信元/送信先スキーマの関連ビューをクリックしてにそれぞれ![関連ビューに切り替える](../core/media/mapper-intellitree.gif "Mapper_IntelliTree")アイコン。 次の図は、関連ビューが有効になっている場合の同じスキーマです。 関連のないすべてのノードは置き換え、![ノードの非表示に結合された](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")アイコンでよりコンパクトなスキーマのビューを提供します。  
  
 ![関連ビューが ON の場合、スキーマ](../core/media/on-schema.gif "On_schema")  
  
 送信元または送信先のスキーマのまとめられたノードを展開すると、![ノードの非表示に結合された](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")変更![表示されているノードに結合された](../core/media/switchoff-mapper-coalesence.jpg "SwitchOff_Mapper_Coalesence")アイコン。  
  
> [!NOTE]
>  Ctrl + M キー、Ctrl + E キーを押すと送信元スキーマのツリー ノードが展開され、Ctrl + M キー、Ctrl + C キーを押すと、折りたたまれます。 同様に、Ctrl + M キー、Ctrl + E キーを押すと送信先スキーマのツリー ノードが展開され、Ctrl + M キー、Ctrl + C キーを押すと、折りたたまれます。 また、送信元または送信先のまとめられたノードについても、それぞれ Ctrl + M キー、Ctrl + H キーまたは Ctrl + M キー、Ctrl + D キーを押すことができます。 マッパーのキーボード ショートカットの一覧は、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk マッパーで強化された機能を使用します。](../core/using-enhanced-features-in-biztalk-mapper.md)
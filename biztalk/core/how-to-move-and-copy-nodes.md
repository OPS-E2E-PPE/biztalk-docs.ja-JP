---
title: 移動してノードをコピーする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e4f1ec14-c607-4da3-9139-73a61963b819
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a55901e9ba6b27d05dccce0e547df618123ab466
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254770"
---
# <a name="how-to-move-and-copy-nodes"></a>移動してノードをコピーする方法
既存のノードは、スキーマ ツリー内の別の場所に移動できます。 また、既存のノードをコピーして、スキーマ ツリー内の別の場所に貼り付けることによって作業を効率化することもできます。 このトピックでは、ノードの移動やコピーの操作手順について説明します。  
  
> [!NOTE]
>  BizTalk エディターでは、スキーマ内でのみノードのコピーと貼り付けができます。あるスキーマから別のスキーマにノードをコピーし、貼り付けることはできません。  
  
### <a name="to-move-a-node-within-a-schema"></a>スキーマ内でノードを移動するには  
  
1.  あらかじめスキーマ ツリーを展開し、移動するノードと、移動先の場所を表示しておきます。 展開と折りたたみ、スキーマ ツリー ビューの詳細については、次を参照してください。[スキーマ ツリー ビューの管理](../core/how-to-manage-the-schema-tree-view.md)です。  
  
2.  移動するノードをクリックし、ツリー内の別の場所にドラッグします。  
  
> [!NOTE]
>  スキーマ ツリー内でノードを上下にドラッグすると、その位置に応じてマウス ポインターの形状が変化します。 この矢印は、マウス ボタンを離したときにノードが挿入される位置 (ノードの前に挿入されるか、ノードの後に挿入されるか、またはノードの子として挿入されるか) を示しています。  
  
#### <a name="to-copy-a-node-within-a-schema"></a>スキーマ内でノードをコピーするには  
  
1.  コピー、およびをクリックするノードを右クリックして**コピー**です。  
  
2.  右クリックし、**レコード**コピーしたノードを挿入し、をクリックするノードまたはグループ ノード**貼り付け**です。  
  
     子ノードの最後にコピーされたノードのコピーが置かれる、**レコード**ノードまたは手順 2. で選択したグループ ノード。  
  
> [!NOTE]
>  切り取り/コピー/貼り付けの機能は、単一のスキーマ内でのみ機能します。 つまり、あるスキーマから別のスキーマへノードをコピーすることはできません。  
  
## <a name="see-also"></a>参照  
 [既存のノードの操作](../core/working-with-existing-nodes.md)
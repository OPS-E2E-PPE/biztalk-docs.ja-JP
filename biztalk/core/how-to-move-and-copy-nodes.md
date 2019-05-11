---
title: ノードのコピーに移動する方法 |Microsoft Docs
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
ms.openlocfilehash: fe123de8a55635aa06fc5f08ccc525690d945ec9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384529"
---
# <a name="how-to-move-and-copy-nodes"></a>ノードのコピーと移動する方法
既存のノードをスキーマ ツリーの別の場所に移動する必要がある場合は発生可能性があります。 既存のノードのコピーを作成し、スキーマ ツリーの別の場所に貼り付けたり、時間を節約できる可能性があります。 このトピックでは、これらのタスクを実行する手順を提供します。  
  
> [!NOTE]
>  BizTalk エディターでは、コピーと貼り付けノードのスキーマ間ではなく、スキーマ内でのみサポートしています。  
  
### <a name="to-move-a-node-within-a-schema"></a>スキーマ内のノードを移動するには  
  
1.  必要に応じて、ノードを移動して移動する場所の両方を表示するには、あるスキーマ ツリーを展開します。 展開と折りたたみ、スキーマ ツリー ビューの詳細については、次を参照してください。[スキーマ ツリー ビューの管理](../core/how-to-manage-the-schema-tree-view.md)します。  
  
2.  移動し、ツリーの別の場所にドラッグするノードを押したままにします。  
  
> [!NOTE]
>  ダウン、上下をマウス ポインターであるスキーマ ツリー ノードのドラッグを開始すると、または子矢印。 この矢印は、ノードの後に、またはノードの子として、ノードの前にいずれかのマウス ボタンを放すと、ノードを配置する場所を示します。  
  
#### <a name="to-copy-a-node-within-a-schema"></a>スキーマ内のノードをコピーするには  
  
1.  コピーするをクリックするノードを右クリックして**コピー**します。  
  
2.  右クリックし、**レコード**コピーのノードを挿入し、クリックするノードまたはグループ ノード**貼り付け**します。  
  
     子ノードの最後にコピーされたノードのコピーが置かれる、**レコード**ノードまたは手順 2 で選択したグループ ノード。  
  
> [!NOTE]
>  1 つのスキーマ内での切り取り/コピー/貼り付け機能のみ使用できます。 つまり、別のスキーマに 1 つのスキーマからノードをコピーすることはできません。  
  
## <a name="see-also"></a>参照  
 [既存のノードの操作](../core/working-with-existing-nodes.md)
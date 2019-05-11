---
title: SendPorts (DistributionList ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SendPorts node [binding file]
ms.assetid: 9cb645fa-cb9c-44eb-9f98-2fc507b2be67
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63fda2724291b15492ecb4d9a035d33cddc0b5d9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393349"
---
# <a name="sendports-distributionlist-node"></a>SendPorts (DistributionList ノード)
バインド ファイルの DistributionList ノードの SendPorts ノードは、配布リストに送信ポート参照のコンテナー ノードです。  
  
> [!NOTE]
>  同報リストは、送信ポート グループ、BizTalk 管理者と呼ばれます。  
  
## <a name="nodes-in-the-sendports-node"></a>SendPorts ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノードの種類**|**[データ型]**|**[説明]**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[SendPortRef](../core/sendportref-sendports-node.md)|レコード|SendPortRef (ComplexType)|同報リストによって行われた送信ポートへの参照のコンテナー ノードです。|任意|既定値: なし|
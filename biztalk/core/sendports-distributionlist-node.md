---
title: "SendPorts (DistributionList ノード) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SendPorts node [binding file]
ms.assetid: 9cb645fa-cb9c-44eb-9f98-2fc507b2be67
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9eaf692bd61913e604731fc2e2cea373fd31f48
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sendports-distributionlist-node"></a>SendPorts (DistributionList ノード)
バインド ファイルの DistributionList ノードの SendPorts ノードは、同報リスト内の送信ポート参照のコンテナー ノードです。  
  
> [!NOTE]
>  同報リストは、BizTalk 管理者では送信ポート グループと呼ばれます。  
  
## <a name="nodes-in-the-sendports-node"></a>SendPorts ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノード型**|**データ型**|**Description**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[SendPortRef](../core/sendportref-sendports-node.md)|レコード|SendPortRef (ComplexType)|同報リストによって参照される送信ポートのコンテナー ノードです。|任意|既定値: なし|
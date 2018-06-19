---
title: SendPortRef (SendPorts ノード) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SendPortRef node [binding file]
ms.assetid: 6c799b23-a9a4-4686-a04e-0450b4eef889
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9290a535ebcaf0c23097cacbd3412f64c2808f40
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269962"
---
# <a name="sendportref-sendports-node"></a>SendPortRef (SendPorts ノード)
バインド ファイルの SendPorts ノードの SendPortRef ノードには、同報リストによって参照される送信ポートの名前を指定します。  
  
> [!NOTE]
>  同報リストは、BizTalk 管理者では送信ポート グループと呼ばれます。  
  
## <a name="nodes-in-the-sendportref-node"></a>SendPortRef ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノード型**|**データ型**|**Description**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|名前|属性|xs:string|同報リストによって参照される送信ポートの名前を指定します。|任意|既定値: 空|
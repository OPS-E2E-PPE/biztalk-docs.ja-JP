---
title: SendPortRef (SendPorts ノード) |Microsoft Docs
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
ms.openlocfilehash: 63ddb7a4f33a13405be0ae555f85d2303e84bb23
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393375"
---
# <a name="sendportref-sendports-node"></a>SendPortRef (SendPorts ノード)
バインド ファイルの SendPorts ノードの SendPortRef ノードには、同報リストによって参照される送信ポートの名前を指定します。  
  
> [!NOTE]
>  同報リストは、送信ポート グループ、BizTalk 管理者と呼ばれます。  
  
## <a name="nodes-in-the-sendportref-node"></a>SendPortRef ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノードの種類**|**[データ型]**|**[説明]**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|名前|属性|xs:string|同報リストによって参照される送信ポートの名前を指定します。|任意|既定値: 空|
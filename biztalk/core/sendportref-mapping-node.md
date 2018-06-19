---
title: SendPortRef (Mapping ノード) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SendPortRef node [binding file]
ms.assetid: 0fbdf44f-6dde-4d1b-b861-cb2fe6d7529d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6448147db5e45278e33b3ccf3a17f019bfa2dc56
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269970"
---
# <a name="sendportref-mapping-node"></a>SendPortRef (Mapping ノード)
バインド ファイルの Mapping ノードの SendPortRef ノードには、親マッピング ノードが参照する送信ポートの名前が示されます。  
  
## <a name="nodes-in-the-sendportref-node"></a>SendPortRef ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノード型**|**データ型**|**Description**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|名前|属性|xs:string|親マッピング ノードによって参照される送信ポートの名前を指定します。|任意|既定値: 空|
---
title: SendPortRef (Port ノード) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SendPortRef node [binding file]
ms.assetid: cd9c3bf7-10a4-4567-a70c-fd74e4a3dc2c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: acaca0fa147f9bec7fce93c46581c96de24ef16e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269514"
---
# <a name="sendportref-port-node"></a>SendPortRef (Port ノード)
バインド ファイルの Port ノードの SendPortRef ノードには、サービスによって参照される送信ポートに関する情報が含まれます。  
  
## <a name="nodes-in-the-sendportref-node"></a>SendPortRef ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノード型**|**データ型**|**Description**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|名前|属性|xs:string|サービスによって参照される送信ポートの名前を指定します。|任意|既定値: 空|
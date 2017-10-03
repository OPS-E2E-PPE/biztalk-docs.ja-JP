---
title: "DistributionListRef (Port ノード) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: DistributionListRef node [binding file]
ms.assetid: 5d0d0121-1bcc-4c26-a1a3-8937ac7c282a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 665b8c2115c5c4681f7cff057481b6ce7da320ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="distributionlistref-port-node"></a>DistributionListRef (Port ノード)
バインド ファイルの Port ノードの DistributionListRef ノードには、サービスによって参照される同報リストに関する情報が含まれます。  
  
> [!NOTE]
>  配布リストは、BizTalk Server 管理コンソールで送信ポート グループと呼ばれます。  
  
## <a name="nodes-in-the-distributionlistref-node"></a>DistributionListRef ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノード型**|**データ型**|**Description**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|名前|属性|xs:string|サービスによって参照される同報リストの名前を指定します。|任意|既定値: 空|
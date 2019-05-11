---
title: DistributionListRef (Port ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DistributionListRef node [binding file]
ms.assetid: 5d0d0121-1bcc-4c26-a1a3-8937ac7c282a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77bdfe705ac85be0e97492f84e39378b8da944bf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351009"
---
# <a name="distributionlistref-port-node"></a>DistributionListRef (Port ノード)
バインド ファイルの Port ノードの DistributionListRef ノードには、サービスによって参照される同報リストに関する情報が含まれています。  
  
> [!NOTE]
>  配布リストは、BizTalk Server 管理コンソールで送信ポート グループと呼ばれます。  
  
## <a name="nodes-in-the-distributionlistref-node"></a>DistributionListRef ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノードの種類**|**[データ型]**|**[説明]**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|名前|属性|xs:string|サービスによって参照される同報リストの名前を指定します。|任意|既定値: 空|
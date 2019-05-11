---
title: DistributionList (DistributionListCollection ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DistributionList node [binding file]
ms.assetid: 51864a5c-1697-4804-ac18-8211494f3ff0
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 732ffa00a2147212e688e9add579044c570faf6c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350835"
---
# <a name="distributionlist-distributionlistcollection-node"></a>DistributionList (DistributionListCollection ノード)
バインド ファイルの DistributionList ノードには、バインド ファイルと共にエクスポートされる同報リストに関する特定の情報が含まれています。 同報リストは、送信ポート グループ、BizTalk Server 管理者と呼ばれます。  
  
## <a name="nodes-in-the-distributionlist-node"></a>DistributionList ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノードの種類**|**[データ型]**|**[説明]**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|名前|属性|xs:string|配布リストの名前を指定します。|任意|既定値: 空|  
|[SendPorts](../core/sendports-distributionlist-node.md)|レコード|ArrayOfSendPortRef (ComplexType)|送信ポートまたは同報リストに含まれる送信ポートを指定します。|任意|既定値: なし|  
|Assert|要素|xs:string|この同報リストで使用される省略可能なフィルター式の名前を指定します。|必須|既定値: 空|  
|ApplicationName|要素|xs:string|同報リストが関連付けられているアプリケーションの名前を指定します。|必須|既定値: 空|  
|説明|要素|xs:string|配布リストの説明を指定します。|必須|既定値: 空|
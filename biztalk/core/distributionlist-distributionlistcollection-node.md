---
title: "DistributionList (DistributionListCollection ノード) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: DistributionList node [binding file]
ms.assetid: 51864a5c-1697-4804-ac18-8211494f3ff0
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 931443cdca27e5c06767f075298d50ff999545a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="distributionlist-distributionlistcollection-node"></a>DistributionList (DistributionListCollection ノード)
バインド ファイルの DistributionList ノードには、バインド ファイルと共にエクスポートされる同報リストに関する特定の情報が含まれます。 同報リストは、BizTalk Server 管理者では送信ポート グループと呼ばれます。  
  
## <a name="nodes-in-the-distributionlist-node"></a>DistributionList ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノード型**|**データ型**|**Description**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|名前|属性|xs:string|同報リストの名前を指定します。|任意|既定値: 空|  
|[送信ポート](../core/sendports-distributionlist-node.md)|レコード|ArrayOfSendPortRef (ComplexType)|同報リストに含まれる送信ポートを指定します。|任意|既定値: なし|  
|[フィルター]|要素|xs:string|この同報リストで使用されるオプションのフィルター式の名前を指定します。|必須|既定値: 空|  
|ApplicationName|要素|xs:string|同報リストが関連付けられているアプリケーションの名前を指定します。|必須|既定値: 空|  
|Description|要素|xs:string|同報リストの説明を指定します。|必須|既定値: 空|
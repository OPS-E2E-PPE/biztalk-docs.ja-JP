---
title: ホスト (Service ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Host node [binding file]
ms.assetid: 597522db-0336-43b1-b464-d17cffbf25be
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a408b8f1bd269ff45881b31cd8a75d26bbc89a3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387517"
---
# <a name="host-service-node"></a>ホスト (Service ノード)
バインド ファイルのサービス ノードのホスト ノードでは、バインド ファイルと共にエクスポートされるサービスに関連付けられているホストについて説明します。  
  
## <a name="nodes-in-the-host-node"></a>ノード内のホスト ノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノードの種類**|**[データ型]**|**[説明]**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|名前|属性|xs:string|ホストの名前を指定します。|任意|既定値: 空|  
|Nt グループ名|属性|xs:string|ホストに関連付けられた Windows NT グループ名を指定します。|任意|既定値: 空|  
|型|属性|xs:int|インプロセスまたは分離ホストの種類を指定します。|必須|既定値: なし<br /><br /> 使用可能な値が記載されて、 [Microsoft.BizTalk.ExplorerOM.HostType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.hosttype.aspx)列挙体。|  
|信頼されています。|属性|xs:boolean|BizTalk ホストが認証情報を収集するために信頼できるかどうかを指定します。|必須|既定値: なし<br /><br /> 設定**true**ホストが信頼されている場合がそれ以外の場合に設定**false**します。|
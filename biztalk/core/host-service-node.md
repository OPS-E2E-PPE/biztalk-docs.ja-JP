---
title: ホスト (Service ノード) |Microsoft ドキュメント
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
ms.openlocfilehash: a9c70c23105a8d2f2ebe389b22ddf910b4166994
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="host-service-node"></a>Host (Service ノード)
バインド ファイルの Service ノードの Host ノードでは、バインド ファイルと共にエクスポートされるサービスに関連付けられているホストを記述します。  
  
## <a name="nodes-in-the-host-node"></a>Host ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノード型**|**データ型**|**Description**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|名前|属性|xs:string|ホストの名前を指定します。|任意|既定値: 空|  
|NTGroupName|属性|xs:string|ホストに関連付けられている Windows NT グループ名を指定します。|任意|既定値: 空|  
|型|属性|xs:int|ホストの種類 (インプロセスまたは分離) を指定します。|必須|既定値: なし<br /><br /> 使用可能な値に記載されて、 [Microsoft.BizTalk.ExplorerOM.HostType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.hosttype.aspx)列挙します。|  
|Trusted|属性|xs:boolean|認証情報を収集する BizTalk ホストを信頼できるかどうかを指定します。|必須|既定値: なし<br /><br /> 設定**true**ホストが信頼されている場合、それ以外の場合 'éý' **false**です。|
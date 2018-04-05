---
title: Port (Ports ノード) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Port node [binding file]
ms.assetid: 6c9a3e5f-0b3c-40f8-9a8d-5a83bd559021
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01a808f4415019ba48deb1b3b80ad8aae9e1db04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="port-ports-node"></a>Port (Ports ノード)
バインド ファイルのポート ノードには、バインド ファイルと共にエクスポートされるサービスにバインドされているポートまたは同報リストに関する特定の情報が含まれます。  
  
> [!NOTE]
>  同報リストは、BizTalk Server 管理コンソールでは送信ポート グループと呼ばれます。  
  
## <a name="nodes-in-the-port-node"></a>Port ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノード型**|**データ型**|**Description**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|名前|属性|xs:string|ポートの名前を指定します。|任意|既定値: 空|  
|Modifier|属性|xs:int|ポートの型修飾子を指定します。|必須|既定値: なし<br /><br /> 使用可能な値で使用できる、 [Microsoft.BizTalk.ExplorerOM.PortModifier](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.portmodifier.aspx)列挙します。|  
|BindingOption|属性|xs:int|ポートのバインドの種類を定義します。|必須|既定値: なし<br /><br /> 使用可能な値で使用できる、 [Microsoft.BizTalk.ExplorerOM.BindingType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.bindingtype.aspx)列挙します。|  
|[SendPortRef](../core/sendportref-port-node.md)|レコード|SendPortRef (ComplexType)|サービスによって参照される送信ポートのコンテナー ノードです。|任意|既定値: 空|  
|[DistributionListRef](../core/distributionlistref-port-node.md)|レコード|DistributionListRef (ComplexType)|サービスによって参照される同報リストのコンテナー ノードです。|任意|既定値: 空|  
|[ReceivePortRef](../core/receiveportref-port-node.md)|レコード|ReceivePortRef (ComplexType)|サービスによって参照される受信ポートのコンテナー ノードです。|任意|既定値: 空|
---
title: "Service (Services ノード) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Service node [binding file]
ms.assetid: 19e977b4-55bd-453f-9053-5590b9553b07
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 834555f43620d428d18a04938e18612793b2ab51
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="service-services-node"></a>Service (Services ノード)
バインド ファイルの Service ノードには、そのバインド ファイルに基づいてエクスポートされるサービスに関する情報が含まれます。 この Service ノードには、サービスに関連付けられているポートおよびロールを説明するノード、およびサービスに関連付けられているホストを説明するノードも含まれます。  
  
## <a name="nodes-in-the-service-node"></a>Service ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノード型**|**データ型**|**Description**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|名前|属性|xs:string|サービスの名前を指定します。|必須|既定値: 空|  
|状態|属性|ServiceRefState (SimpleType)|サービスの状態を指定します。|必須|既定値: 既定<br /><br /> 有効な値は次のとおりです。<br /><br /> -既定値します。<br />-参加解除<br />参加しています。<br />-開始|  
|TrackingOption|属性|OrchestrationTrackingTypes (SimpleType)|サービスのメッセージ追跡オプションを指定します。|必須|既定値: なし<br /><br /> 使用可能な値で使用できる、 [Microsoft.BizTalk.ExplorerOM.OrchestrationTrackingTypes](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.orchestrationtrackingtypes.aspx)列挙します。|  
|Description|属性|xs:string|サービスの説明を指定します。|任意|既定値: 空|  
|[ポート](../core/ports-service-node.md)|レコード|ArrayOfServicePortRef (ComplexType)|サービスにバインドされたポートのコンテナー ノードです。|任意|既定値: なし|  
|[Roles](../core/roles-service-node.md)|レコード|ArrayOfRoleRef (ComplexType)|サービスにバインドされたロールのコンテナー ノードです。|任意|既定値: なし|  
|[ホスト](../core/host-service-node.md)|レコード|HostRef (ComplexType)|サービスにバインドされたホストのコンテナー ノードです。|必須|既定値: なし|
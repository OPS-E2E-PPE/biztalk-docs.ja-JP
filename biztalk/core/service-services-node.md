---
title: Service (Services ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Service node [binding file]
ms.assetid: 19e977b4-55bd-453f-9053-5590b9553b07
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03a61ea635d6d781c4bf31a0e598c5d302311db6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393312"
---
# <a name="service-services-node"></a>Service (Services ノード)
バインド ファイルの Service ノードには、バインド ファイルと共にエクスポートされるサービスに関する情報が含まれています。 サービスのノードには、ポートと、サービスとサービスに関連付けられているホストを示すノードに関連付けられているロールを記述するノードも含まれています。  
  
## <a name="nodes-in-the-service-node"></a>ノード内のサービス ノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノードの種類**|**[データ型]**|**[説明]**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|名前|属性|xs:string|サービスの名前を指定します。|必須|既定値: 空|  
|状態|属性|ServiceRefState (SimpleType)|サービスの状態を指定します。|必須|既定値:既定<br /><br /> 有効な値は次のとおりです。<br /><br /> -Default します。<br />-参加解除<br />-参加しています。<br />-開始|  
|TrackingOption|属性|OrchestrationTrackingTypes (SimpleType)|メッセージ追跡用のサービスのオプションを指定します。|必須|既定値: なし<br /><br /> 使用可能な値で使用できる、 [Microsoft.BizTalk.ExplorerOM.OrchestrationTrackingTypes](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.orchestrationtrackingtypes.aspx)列挙体。|  
|説明|属性|xs:string|サービスの説明を指定します。|任意|既定値: 空|  
|[ポート](../core/ports-service-node.md)|レコード|ArrayOfServicePortRef (ComplexType)|サービスにバインドされているポートのコンテナー ノードです。|任意|既定値: なし|  
|[Roles](../core/roles-service-node.md)|レコード|ArrayOfRoleRef (ComplexType)|サービスにバインドされているロールのコンテナー ノードです。|任意|既定値: なし|  
|[ホスト](../core/host-service-node.md)|レコード|HostRef (ComplexType)|サービスにバインドされているホストのコンテナー ノードです。|必須|既定値: なし|
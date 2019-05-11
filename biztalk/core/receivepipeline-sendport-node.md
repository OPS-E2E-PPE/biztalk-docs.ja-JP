---
title: ReceivePipeline (SendPort ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ReceivePipeline node [binding file]
ms.assetid: 5305f255-e7a2-4052-bf50-4fb207cfae8d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 71c0a44ccb2d79a9fa9a5258c1d667890143dc13
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398121"
---
# <a name="receivepipeline-sendport-node"></a>ReceivePipeline (SendPort ノード)
バインド ファイルと共にエクスポートされるポートをバインド ファイルのノードには、双方向にバインドされる受信パイプラインに関する特定の情報が含まれています。 送信ポートの ReceivePipeline ノードに送信します。  
  
## <a name="nodes-in-the-receivepipeline-node"></a>ReceivePipeline ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノードの種類**|**[データ型]**|**[説明]**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|名前|属性|xs:string|送信パイプラインの名前を指定します。|任意|既定値: 空|  
|FullyQualifiedName|属性|xs:string|パイプラインがの一部としてデプロイされているアセンブリの名前を含むパイプラインの完全修飾名を指定します。|任意|既定値: 空|  
|型|属性|xs:int|パイプラインの種類を指定します。|必須|既定値: なし<br /><br /> 使用可能な値が記載されて、<br /><br /> [Microsoft.BizTalk.ExplorerOM.PipelineType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.pipelinetype.aspx)列挙体。|  
|TrackingOption|属性|PipelineTrackingTypes (SimpleType)|パイプラインの追跡オプションを指定します。|必須|既定値: なし<br /><br /> 設定可能な値は、 [Microsoft.BizTalk.ExplorerOM.PipelineTrackingTypes](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.pipelinetrackingtypes.aspx) 列挙体を参照してください。|  
|説明|属性|xs:string|送信パイプラインの説明を指定します。|任意|既定値: 空|
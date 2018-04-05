---
title: ReceivePipeline (ReceiveLocation ノード) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ReceivePipeline node [binding file]
ms.assetid: bd90ca2d-21e4-4d21-bc67-f16a150053e4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 122ffcfe7fe2d2cfc49b51c98b7251a19f5a0e31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="receivepipeline-receivelocation-node"></a>ReceivePipeline (ReceiveLocation ノード)
バインド ファイルの ReceiveLocation ノードの ReceivePipeline ノードには、バインド ファイルと共にエクスポートされる受信場所で使用される受信パイプラインに関する特定の情報が含まれます。  
  
## <a name="nodes-in-the-receivepipeline-node"></a>ReceivePipeline ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノード型**|**データ型**|**Description**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|名前|属性|xs:string|受信パイプラインの名前を指定します。|任意|既定値: 空|  
|FullyQualifiedName|属性|xs:string|パイプラインの完全修飾名を指定します。これには、パイプラインの展開先であるアセンブリの名前が含まれます。|任意|既定値: 空|  
|型|属性|xs:int|パイプラインの種類を指定します。|Required|既定値: なし<br /><br /> 指定できる値は、<br /><br /> [Microsoft.BizTalk.ExplorerOM.PipelineType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.pipelinetype.aspx)列挙します。|  
|TrackingOption|属性|PipelineTrackingTypes (SimpleType)|パイプラインの追跡オプションを指定します。|Required|既定値: なし<br /><br /> 設定可能な値は、 [Microsoft.BizTalk.ExplorerOM.PipelineTrackingTypes](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.pipelinetrackingtypes.aspx) 列挙体を参照してください。|  
|説明|属性|xs:string|受信パイプラインの説明を指定します。|任意|既定値: 空|
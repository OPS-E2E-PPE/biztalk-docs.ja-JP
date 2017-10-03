---
title: "TransmitPipeline (SendPort ノード) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: TransmitPipeline node [binding file]
ms.assetid: cee55451-6c3f-4e37-aef9-870d4b5d23aa
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4addad5ea98781865b44470f2d07b577afce6c0f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="transmitpipeline-sendport-node"></a>TransmitPipeline (SendPort ノード)
バインド ファイルの SendPort ノードの TransmitPipeline ノードでは、バインド ファイルと共にエクスポートされる送信ポートにバインドされる送信パイプラインに関する特定の情報が提供されます。  
  
## <a name="nodes-in-the-transmitpipeline-node"></a>TransmitPipeline ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノード型**|**データ型**|**Description**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|名前|属性|xs:string|送信パイプラインの名前を指定します。|任意|既定値: 空|  
|FullyQualifiedName|属性|xs:string|パイプラインの完全修飾名を指定します。これには、パイプラインの展開先であるアセンブリの名前が含まれます。|任意|既定値: 空|  
|型|属性|xs:int|パイプラインの種類を指定します。|Required|既定値: なし<br /><br /> 設定可能な値は、 [Microsoft.BizTalk.ExplorerOM.PipelineType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.pipelinetype.aspx) 列挙体を参照してください。|  
|TrackingOption|属性|PipelineTrackingTypes (SimpleType)|パイプラインの追跡オプションを指定します。|Required|既定値: なし<br /><br /> 設定可能な値は、 [Microsoft.BizTalk.ExplorerOM.PipelineTrackingTypes](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.pipelinetrackingtypes.aspx) 列挙体を参照してください。|  
|説明|属性|xs:string|送信パイプラインの説明を指定します。|任意|既定値: 空|
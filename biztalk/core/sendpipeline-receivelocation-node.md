---
title: SendPipeline (ReceiveLocation ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SendPipeline node [binding file]
ms.assetid: 7dcad2f1-b11f-4015-9067-b7ba40ee6cda
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1b6fd5239b63c71350688328b4b60d7a585abc9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398989"
---
# <a name="sendpipeline-receivelocation-node"></a>SendPipeline (ReceiveLocation ノード)
バインド ファイルの ReceiveLocation ノードの SendPipeline ノードでは、バインド ファイルと共にエクスポートされる受信場所にバインドされる送信パイプラインに関する特定の情報を提供します。  
  
## <a name="nodes-in-the-sendpipeline-node"></a>SendPipeline ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノードの種類**|**[データ型]**|**[説明]**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|名前|属性|xs:string|送信パイプラインの名前を指定します。|任意|既定値: 空|  
|FullyQualifiedName|属性|xs:string|パイプラインの完全修飾名を指定します。これには、パイプラインの展開先であるアセンブリの名前が含まれます。|任意|既定値: 空|  
|型|属性|xs:int|パイプラインの種類を指定します。|必須|既定値: なし<br /><br /> 使用可能な値が記載されて、<br /><br /> [Microsoft.BizTalk.ExplorerOM.PipelineType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.pipelinetype.aspx)列挙体。|  
|TrackingOption|属性|PipelineTrackingTypes (SimpleType)|パイプラインの追跡オプションを指定します。|必須|既定値: なし<br /><br /> 設定可能な値は、 [Microsoft.BizTalk.ExplorerOM.PipelineTrackingTypes](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.pipelinetrackingtypes.aspx) 列挙体を参照してください。|  
|説明|属性|xs:string|送信パイプラインの説明を指定します。|任意|既定値: 空|
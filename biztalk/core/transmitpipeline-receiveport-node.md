---
title: TransmitPipeline (ReceivePort ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TransmitPipeline node [binding file]
ms.assetid: 0f3b728f-1e4a-40e5-9ca9-f7dcdf995cbe
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b134d615aecac2eafc21ada63f3caa50664ca2e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243203"
---
# <a name="transmitpipeline-receiveport-node"></a>TransmitPipeline (ReceivePort ノード)
受信ポートが双方向にバインドされる送信パイプラインに関する特定の情報を提供するバインド ファイルのノードの TransmitPipeline ノードの受信ポートのバインド ファイルと共にエクスポートします。  
  
> [!NOTE]
>  送信パイプラインは双方向受信用、BizTalk Server で受信場所のレベルでバインドは、以降このノードが指定の旧バージョンと BizTalk Server 2004 との互換性。 送信パイプラインは双方向受信用、BizTalk Server 2004 での受信ポート レベルでバインドされます。 BizTalk Server 2004 からエクスポートされたバインド ファイルのこのノードに設定されているプロパティは、BizTalk Server に、バインド ファイルをインポートするときに、受信ポートによって参照される各双方向の受信場所の SendPipeline ノードに適用されます。  
  
## <a name="nodes-in-the-transmitpipeline-node"></a>TransmitPipeline ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノードの種類**|**[データ型]**|**[説明]**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|名前|属性|xs:string|送信パイプラインの名前を指定します。|任意|既定値: 空|  
|FullyQualifiedName|属性|xs:string|パイプラインがの一部としてデプロイされているアセンブリの名前を含むパイプラインの完全修飾名を指定します。|任意|既定値: 空|  
|型|属性|xs:int|パイプラインの種類を指定します。|必須|既定値: なし<br /><br /> 使用可能な値が記載されて、<br /><br /> [Microsoft.BizTalk.ExplorerOM.PipelineType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.pipelinetype.aspx)列挙体。|  
|TrackingOption|属性|PipelineTrackingTypes (SimpleType)|パイプラインの追跡オプションを指定します。|必須|既定値: なし<br /><br /> 設定可能な値は、 [Microsoft.BizTalk.ExplorerOM.PipelineTrackingTypes](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.pipelinetrackingtypes.aspx) 列挙体を参照してください。|  
|説明|属性|xs:string|送信パイプラインの説明を指定します。|任意|既定値: 空|  
  
## <a name="see-also"></a>参照  
 [送信パイプライン](../core/sendpipeline-receivelocation-node.md)   
 [ReceiveLocation](../core/receivelocation-receivelocations-node.md)
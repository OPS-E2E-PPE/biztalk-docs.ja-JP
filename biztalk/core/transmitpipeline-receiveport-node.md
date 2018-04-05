---
title: TransmitPipeline (ReceivePort ノード) |Microsoft ドキュメント
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
ms.openlocfilehash: 64b17179b7131839dc369e9bdecf5e40dd831e4d
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="transmitpipeline-receiveport-node"></a>TransmitPipeline (ReceivePort ノード)
バインド ファイルの ReceivePort ノードの TransmitPipeline ノードでは、バインド ファイルと共にエクスポートされる双方向受信ポートにバインドされている送信パイプラインに関する特定の情報が提供されます。  
  
> [!NOTE]
>  送信パイプラインは双方向受信用、BizTalk Server で受信場所のレベルでバインドは、以降このノードが指定の旧バージョンと BizTalk Server 2004 との互換性。 送信パイプラインは双方向受信用、BizTalk Server 2004 で受信ポートのレベルでバインドされます。 BizTalk Server 2004 からエクスポートされたバインド ファイルのこのノードに設定されているプロパティは、BizTalk Server に、バインド ファイルをインポートするときに、受信ポートによって参照される各双方向の受信場所の SendPipeline ノードに適用されます。  
  
## <a name="nodes-in-the-transmitpipeline-node"></a>TransmitPipeline ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノード型**|**データ型**|**Description**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|名前|属性|xs:string|送信パイプラインの名前を指定します。|任意|既定値: 空|  
|FullyQualifiedName|属性|xs:string|一部として、パイプラインが展開されたこと、アセンブリの名前を含むパイプラインの完全修飾名を指定します。|任意|既定値: 空|  
|型|属性|xs:int|パイプラインの種類を指定します。|Required|既定値: なし<br /><br /> 指定できる値は、<br /><br /> [Microsoft.BizTalk.ExplorerOM.PipelineType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.pipelinetype.aspx)列挙します。|  
|TrackingOption|属性|PipelineTrackingTypes (SimpleType)|パイプラインの追跡オプションを指定します。|Required|既定値: なし<br /><br /> 設定可能な値は、 [Microsoft.BizTalk.ExplorerOM.PipelineTrackingTypes](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.pipelinetrackingtypes.aspx) 列挙体を参照してください。|  
|説明|属性|xs:string|送信パイプラインの説明を指定します。|任意|既定値: 空|  
  
## <a name="see-also"></a>参照  
 [送信パイプライン](../core/sendpipeline-receivelocation-node.md)   
 [ReceiveLocation](../core/receivelocation-receivelocations-node.md)
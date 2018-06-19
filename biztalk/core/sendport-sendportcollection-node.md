---
title: SendPort (SendPortCollection ノード) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5cf7a6f9-9240-48b9-b196-8838afd4f41e
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43db1aa63fb828ebbc0ee6d857ce79968b846aea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22272242"
---
# <a name="sendport-sendportcollection-node"></a>SendPort (SendPortCollection ノード)
バインド ファイルの SendPort ノードには、バインド ファイルと共にエクスポートされる送信ポートに関する特定の情報が含まれます。  
  
## <a name="nodes-in-the-sendport-node"></a>SendPort ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノード型**|**データ型**|**Description**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|名前|属性|xs:string|送信ポートの名前を指定します。|任意|既定値: 空|  
|IsStatic|属性|xs:boolean|送信ポートが静的か動的かを指定します。|必須|既定値: なし|  
|IsTwoWay|属性|xs:boolean|送信ポートが一方向か送信請求 - 応答 (双方向) かを指定します。|必須|既定値: なし<br /><br /> 使用できる値は、 **MSBTS_SendPort.IsTwoWay プロパティ (WMI)** です。|  
|BindingOption|属性|xs:int|オーケストレーション ポートのバインドの種類を指定します。|必須|既定値: なし<br /><br /> 使用できる値は、 **Microsoft.BizTalk.ExplorerOM.BindingType**列挙します。|  
|Description|要素|xs:string|送信ポートの説明を指定します。|必須|既定値: 空|  
|[TransmitPipeline (SendPort ノード)](../core/transmitpipeline-sendport-node.md)|レコード|PipelineRef (ComplexType)|送信ポートに関連付けられている送信パイプラインを指定します。|任意|既定値: なし|  
|SendPipelineData|要素|xs:string|パイプラインの使用で、このインスタンスに固有のカスタム構成を指定します。|任意|既定値: 空です。|  
|[PrimaryTransport](../core/primarytransport-sendport-node.md)|レコード|TransportInfo (ComplexType)|送信ポートが使用するように構成されているプライマリ トランスポートに関する情報を指定します。|任意|既定値: なし|  
|[SecondaryTransport](../core/secondarytransport-sendport-node.md)|レコード|TransportInfo (ComplexType)|送信ポートが使用するように構成されているセカンダリ トランスポートに関する情報を指定します。|任意|既定値: なし|  
|[EncryptionCert](../core/encryptioncert-sendport-node.md)|レコード|CertificateInfo (ComplexType)|送信ポートで使用する暗号化証明書に関する情報を指定します。|任意|既定値: なし|  
|[ReceivePipeline](../core/receivepipeline-sendport-node.md)|レコード|PipelineRef (ComplexType)|送信ポートで使用する受信パイプラインに関する情報を指定します。|任意|既定値: なし|  
|ReceivePipelineData|要素|xs:string|パイプラインの使用で、このインスタンスに固有のカスタム構成を指定します。|必須|既定値: 空|  
|Tracking|要素|xs:int|送信ポートのドキュメント追跡のレベルを指定します。|必須|既定値: なし<br /><br /> 使用できる値は、 **Microsoft.BizTalk.ExplorerOM.TrackingTypes**列挙します。|  
|[フィルター]|要素|xs:string|この送信ポートに使用されるオプションのフィルター式の名前を指定します。|必須|既定値: 空<br /><br /> 使用できる値は、 **MSBTS_SendPort.Filter プロパティ (WMI)**|  
|[Transforms (SendPort ノード)](../core/transforms-sendport-node.md)|レコード|ArrayOfTransform (ComplexType)|一方向送信ポートの送信変換のコレクションを指定します。|任意|既定値: なし|  
|[InboundTransforms](../core/inboundtransforms-sendport-node.md)|レコード|ArrayOfTransform (ComplexType)|双方向の送信ポートの受信変換のコレクションを指定します。|任意|既定値: なし|  
|OrderedDelivery|要素|xs:boolean|送信ポートでメッセージを順次配送するかどうかを指定します。|必須|既定値: なし<br /><br /> 使用できる値は、 **MSBTS_SendPort.OrderedDelivery プロパティ (WMI)**|  
|[Priority]|要素|xs:int|送信ポートの優先度を指定します。|必須|既定値: 5<br /><br /> 使用できる値は、 **MSBTS_SendPort.Priority プロパティ (WMI)**|  
|StopSendingOnFailure|要素|xs:boolean|エラーが発生したときに、送信ポートがメッセージの送信を停止するかどうかを指定します。|必須|既定値: なし<br /><br /> 使用できる値は、 **MSBTS_SendPort.StopSendingOnFailure プロパティ (WMI)**|  
|RouteFailedMessage|要素|xs:boolean|失敗したメッセージを失敗したメッセージのサブスクライバーにルーティングするかどうかを指定します。|必須|既定値: なし<br /><br /> 使用できる値は、 **MSBTS_SendPort.RouteFailedMessage プロパティ (WMI)**|  
|ApplicationName|要素|xs:string|送信ポートに関連付けられているアプリケーションの名前を指定します。|必須|既定値: 空<br /><br /> 使用できる値は、 **ISSOMapping.ApplicationName プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。|

## <a name="see-also"></a>参照
詳細については、これらのプロパティ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
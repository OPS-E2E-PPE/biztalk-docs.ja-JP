---
title: SendPort (SendPortCollection ノード) |Microsoft Docs
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
ms.openlocfilehash: 3577aa70936a5a97bf91e70780911514e8b3e7b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380006"
---
# <a name="sendport-sendportcollection-node"></a>SendPort (SendPortCollection ノード)
バインド ファイルの SendPort ノードには、バインド ファイルと共にエクスポートされる送信ポートに関する特定の情報が含まれています。  

## <a name="nodes-in-the-sendport-node"></a>SendPort ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  


|                                   **名前**                                    | **ノードの種類** |         **[データ型]**          |                                       **[説明]**                                        | **制限** |                                                                                            **コメント**                                                                                             |
|-------------------------------------------------------------------------------|---------------|--------------------------------|----------------------------------------------------------------------------------------------|------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                     名前                                      |   属性   |           xs:string            |                             送信ポートの名前を指定します。                             |   任意   |                                                                                        既定値: 空                                                                                         |
|                                   IsStatic                                    |   属性   |           xs:boolean           |                    送信ポートが静的か動的かどうかを指定します。                     |     必須     |                                                                                         既定値: なし                                                                                         |
|                                   IsTwoWay                                    |   属性   |           xs:boolean           |         送信ポートが一方向か、送信請求 - 応答 (双方向) かどうかを指定します。         |     必須     |                                               既定値: なし<br /><br /> 使用できる値は、 **MSBTS_SendPort.IsTwoWay プロパティ (WMI)** します。                                                |
|                                 BindingOption                                 |   属性   |             xs:int             |                  オーケストレーション ポートのバインドの種類を指定します。                   |     必須     |                                        既定値: なし<br /><br /> 使用できる値は、 **Microsoft.BizTalk.ExplorerOM.BindingType**列挙体。                                        |
|                                  説明                                  |    要素    |           xs:string            |                          送信ポートの説明を指定します。                          |     必須     |                                                                                        既定値: 空                                                                                         |
| [TransmitPipeline (SendPort ノード)](../core/transmitpipeline-sendport-node.md) |    レコード     |   PipelineRef (ComplexType)    |                  送信ポートに関連付けられている送信パイプラインを指定します。                  |   任意   |                                                                                         既定値: なし                                                                                         |
|                               SendPipelineData                                |    要素    |           xs:string            |  パイプラインの使用率のこのインスタンスに固有、カスタム構成を指定します。  |   任意   |                                                                                        既定値: 空です。                                                                                        |
|         [PrimaryTransport](../core/primarytransport-sendport-node.md)         |    レコード     |  TransportInfo (ComplexType)   |  送信ポートが構成されているプライマリ トランスポートに関する情報を指定を使用します。  |   任意   |                                                                                         既定値: なし                                                                                         |
|       [SecondaryTransport](../core/secondarytransport-sendport-node.md)       |    レコード     |  TransportInfo (ComplexType)   | 送信ポートは次のように構成されたセカンダリ トランスポートに関する情報を指定を使用します。 |   任意   |                                                                                         既定値: なし                                                                                         |
|           [EncryptionCert](../core/encryptioncert-sendport-node.md)           |    レコード     | 証明書情報 (複合型)  |       送信ポートで使用される暗号化証明書に関する情報を指定します。        |   任意   |                                                                                         既定値: なし                                                                                         |
|          [ReceivePipeline](../core/receivepipeline-sendport-node.md)          |    レコード     |   PipelineRef (ComplexType)    |          送信ポートで使用する受信パイプラインに関する情報を指定します。          |   任意   |                                                                                         既定値: なし                                                                                         |
|                              ReceivePipelineData                              |    要素    |           xs:string            |  パイプラインの使用率のこのインスタンスに固有、カスタム構成を指定します。  |     必須     |                                                                                        既定値: 空                                                                                         |
|                                   Tracking                                    |    要素    |             xs:int             |                  送信ポートのドキュメント追跡のレベルを指定します                  |     必須     |                                       既定値: なし<br /><br /> 使用できる値は、 **Microsoft.BizTalk.ExplorerOM.TrackingTypes**列挙体。                                       |
|                                    Assert                                     |    要素    |           xs:string            |         この送信ポートで使用される省略可能なフィルター式の名前を指定します。         |     必須     |                                                既定値: 空<br /><br /> 使用できる値は、 **MSBTS_SendPort.Filter プロパティ (WMI)**                                                 |
|       [Transforms (SendPort ノード)](../core/transforms-sendport-node.md)       |    レコード     | ArrayOfTransform (ComplexType) |           送信ポートの一方向の送信変換のコレクションを指定します。            |   任意   |                                                                                         既定値: なし                                                                                         |
|        [InboundTransforms](../core/inboundtransforms-sendport-node.md)        |    レコード     | ArrayOfTransform (ComplexType) |            双方向送信ポートの受信変換のコレクションを指定します。            |   任意   |                                                                                         既定値: なし                                                                                         |
|                                OrderedDelivery                                |    要素    |           xs:boolean           |           送信ポートがメッセージの配信を注文するかどうかを指定します。            |     必須     |                                            既定値: なし<br /><br /> 使用できる値は、 **MSBTS_SendPort.OrderedDelivery プロパティ (WMI)**                                            |
|                                   [Priority]                                    |    要素    |             xs:int             |                           送信ポートの優先順位を指定します。                           |     必須     |                                                 既定値:5<br /><br /> 使用できる値は、 **MSBTS_SendPort.Priority プロパティ (WMI)**                                                  |
|                             StopSendingOnFailure                              |    要素    |           xs:boolean           |         エラー メッセージを送信する送信ポートを停止するかどうかを指定します。          |     必須     |                                          既定値: なし<br /><br /> 使用できる値は、 **MSBTS_SendPort.StopSendingOnFailure プロパティ (WMI)**                                          |
|                              RouteFailedMessage                               |    要素    |           xs:boolean           |      メッセージが失敗したメッセージのサブスクライバーにルーティングできなかったかどうかを指定します。      |     必須     |                                           既定値: なし<br /><br /> 使用できる値は、 **MSBTS_SendPort.RouteFailedMessage プロパティ (WMI)**                                           |
|                                ApplicationName                                |    要素    |           xs:string            |             送信ポートに関連付けられているアプリケーションの名前を指定します。             |     必須     | 既定値: 空<br /><br /> 使用できる値は、 **ISSOMapping.ApplicationName プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。 |

## <a name="see-also"></a>関連項目
詳細については、これらのプロパティ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
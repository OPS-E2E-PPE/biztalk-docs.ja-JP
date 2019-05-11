---
title: SecondaryTransport (SendPort ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SecondaryTransport node [binding file]
ms.assetid: e4924f63-dd5f-4437-a661-09f12c5d6da6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a4b94361e258258abd538ffeb84f7805481ddb0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251215"
---
# <a name="secondarytransport-sendport-node"></a>SecondaryTransport (SendPort ノード)
バインド ファイルの SendPort ノードの SecondaryTransport ノードは、バインド ファイルと共にエクスポートされる送信ポートにバインドされているセカンダリ トランスポートに関する特定の情報を提供します。 セカンダリ トランスポートが指定されている場合、プライマリ トランスポートですべての再試行が終了しているときに使用されます。  
  
## <a name="nodes-in-the-secondarytransport-node"></a>SecondaryTransport ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノードの種類**|**[データ型]**|**[説明]**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Address|要素|xs:string|トランスポートのアドレス (または URI) を指定します。|任意|既定値: 空|  
|[TransportType (SecondaryTransport ノード)](../core/transporttype-secondarytransport-node.md)|レコード|ProtocolType (ComplexType)|これは、このトランスポートで使用されるアダプターの名前でもトランスポートの種類を指定します。|任意|既定値: なし|  
|TransportTypeData|要素|xs:string|アダプターに固有の構成情報を指定します。|任意|既定値: 空<br /><br /> 参照してください[統合 BizTalk アダプターの構成プロパティ](../core/configuration-properties-for-integrated-biztalk-adapters.md)アダプター固有プロパティについては、この文字列に格納することができます。|  
|RetryCount|要素|xs:int|トランスポートで使用するアダプターの再試行の回数を指定します。|必須|既定値: なし|  
|RetryInterval|要素|xs:int|トランスポートで使用するアダプターを分単位での再試行間隔を指定します。|必須|既定値: なし|  
|ServiceWindowEnabled|要素|xs:boolean|トランスポートで使用するアダプターのサービス時間帯が有効になっているかどうかを指定します。|必須|既定値: なし<br /><br /> 設定**true**サービス時間帯が有効になっている場合がそれ以外の場合に設定**false**します。|  
|FromTime|要素|xs:dateTime|サービス時間帯の開始時刻を指定します。|必須|既定値: なし|  
|ToTime|要素|xs:dateTime|サービス時間帯の終了時刻を指定します。|必須|既定値: なし|  
|1 次式|要素|xs:boolean|トランスポートで使用するアダプターがプライマリかどうかを指定します。|必須|既定値: なし<br /><br /> 設定**true**トランスポートで使用するアダプターがプライマリの場合がそれ以外の場合に設定**false**します。|  
|OrderedDelivery|要素|xs:boolean|トランスポートで使用するアダプターを順番にメッセージを送信する必要があるかどうかを指定します。|必須|既定値: なし<br /><br /> 設定**true**トランスポートがメッセージの順序で送信する場合がそれ以外の場合に設定**false**します。|  
|DeliveryNotification|要素|xs:int|トランスポートで使用するアダプターが、転送が成功したかどうか、配信通知を返す必要があるかどうかを指定します。|必須|既定値: なし<br /><br /> 設定**true**配信通知では、それ以外の場合は、設定**false**します。|  
|[SendHandler](../core/sendhandler-secondarytransport-node.md)|レコード|SendHandlerRef (ComplexType)|トランスポートで使用するアダプターの送信ハンドラーを指定します。|必須|既定値: なし|
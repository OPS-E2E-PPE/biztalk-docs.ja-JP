---
title: PrimaryTransport (SendPort ノード) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PrimaryTransport node [binding file]
ms.assetid: 22b68d27-f280-4272-84b8-8a50f230228a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b2d60f3b7fbb09e2e106a4d91f1eca0385aa155
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="primarytransport-sendport-node"></a>PrimaryTransport (SendPort ノード)
バインド ファイルの SendPort ノードの PrimaryTransport ノードは、そのバインド ファイルと共にエクスポートされる送信ポートのプライマリ トランスポートに関する情報を提供します。  
  
## <a name="nodes-in-the-primarytransport-node"></a>PrimaryTransport ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノード型**|**データ型**|**Description**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Address|要素|xs:string|トランスポートのアドレス (または URI) を指定します。|任意|既定値: 空|  
|[TransportType (PrimaryTransport ノード)](../core/transporttype-primarytransport-node.md)|レコード|ProtocolType (ComplexType)|トランスポートの種類を指定します。これはこのトランスポートに使用されるアダプターの名前でもあります。|任意|既定値: なし|  
|TransportTypeData|要素|xs:string|アダプターに固有の構成情報を指定します。|任意|既定値: 空<br /><br /> 参照してください[統合 BizTalk アダプターの構成プロパティ](../core/configuration-properties-for-integrated-biztalk-adapters.md)アダプター特定プロパティについては、この文字列に格納できます。|  
|RetryCount|要素|xs:int|トランスポートで使用するアダプターの再試行回数を指定します。|必須|既定値: なし|  
|RetryInterval|要素|xs:int|トランスポートで使用するアダプターの再試行間隔 (分単位) を指定します。|必須|既定値: なし|  
|ServiceWindowEnabled|要素|xs:boolean|トランスポートで使用するアダプターでサービス時間帯が有効かどうかを指定します。|必須|既定値: なし<br /><br /> 設定**true**サービス時間帯が有効になっていると、それ以外の場合に設定**false**です。|  
|FromTime|要素|xs:dateTime|サービス時間帯の開始時刻を指定します。|必須|既定値: なし|  
|ToTime|要素|xs:dateTime|サービス時間帯の終了時刻を指定します。|必須|既定値: なし|  
|プライマリ|要素|xs:boolean|トランスポートで使用するアダプターがプライマリかどうかを指定します。|必須|既定値: なし<br /><br /> 設定**true**トランスポートで使用するアダプターがプライマリ、それ以外の場合に設定**false**です。|  
|OrderedDelivery|要素|xs:boolean|トランスポートで使用するアダプターがメッセージを順番に送信するかどうかを指定します。|必須|既定値: なし<br /><br /> 設定**true**トランスポートがメッセージを送信する順序で、それ以外の場合に設定**false**です。|  
|DeliveryNotification|要素|xs:int|トランスポートで使用するアダプターが、送信が成功したかどうかを示す配信通知を返すかどうかを指定します。|必須|既定値: なし<br /><br /> 設定**true**配信通知では、それ以外の場合は、設定**false**です。|  
|[SendHandler](../core/sendhandler-primarytransport-node.md)|レコード|SendHandlerRef (ComplexType)|トランスポートで使用するアダプターの送信ハンドラーを指定します。|必須|既定値: なし|
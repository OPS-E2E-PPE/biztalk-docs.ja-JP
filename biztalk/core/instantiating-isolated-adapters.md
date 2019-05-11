---
title: 分離アダプターをインスタンス化する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b8359a3-b098-4bb6-87b4-d3432d2671b1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89f534ab91f940a179c765fba6f109a9da6df5ae
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331840"
---
# <a name="instantiating-isolated-adapters"></a>分離アダプターをインスタンス化します。
既に説明したように、分離アダプタは BizTalk Server によってインスタンス化されません。 代わりに、インスタンス化されており、別のプロセスでホストされています。 そのトランスポート プロキシを作成するアダプターの役割は**QueryInterface**の**IBTTransportProxy**を呼び出して**IBTTransportProxy**.**RegisterIsolatedReceiver**をメッセージング エンジンに登録します。  
  
 登録するには、アダプターのパスは、いずれか、構成済みで有効になっているが、メッセージング エンジンに場所を受信する必要があります。 アダプターのホスト プロセスの資格情報は、BizTalk 分離ホスト ユーザー グループのメンバーである必要があります。 ユーザーがそのグループのメンバーでない限りは、単に権限借用を使用してここで十分です。 確実に正しいアダプターを照会するさらに、 **ClassID**がそのホスト インスタンス用に構成されたコンピューターで実行されているとします。 アダプターは、そのトランスポート プロキシで登録が正常に、その構成がの Load メソッドを呼び出すことでに送信され、 **IPersistPropertyBag**インターフェイス。  
  
 次の図は、この一連の API 呼び出しを示しています。 青で示されるインターフェイスは、アダプターによって実装されます。  
  
 ![](../core/media/isolated-adapter-init.gif "Isolated_adapter_init")  
  
 次のコード フラグメントは、登録 API の呼び出しを示しています。  
  
```  
using Microsoft.BizTalk.TransportProxy.Interop;  
using Microsoft.BizTalk.Component.Interop;  
using Microsoft.BizTalk.Message.Interop;  
  
public class MyAdapter : IBTTransport,   
 IBTTransportConfig,   
 IBTTransportControl,   
 IBaseComponent  
{  
...  
private IBTTransportProxy transportProxy;  
  
 public void Register(string uri)  
 {  
 // Create the Transport Proxy...  
 this.transportProxy =   
 (IBTTransportProxy)new BTTransportProxy();  
  
// Register on of the adapters uri’s with the TP  
 this.transportProxy.RegisterIsolatedReceiver(  
 uri,   
 (IBTTransportConfig)this );  
 }  
}  
```  
  
 **実装のヒン ト:** アダプターが進行中の作業の数を保持することをお勧めします。 アダプターをブロックする必要があります**Terminate**メッセージ数が 0 に到達するまでです。 受信側では、この作業には、BizTalk Server に発行されていないが、未処理の要求が含まれています。 応答メッセージは後に受信アダプターに配信されません**Terminate**が呼び出されました。  
  
 送信アダプターの場合は、進行中のメッセージを適切に処理する必要があります。 つまりが正常に配信されたメッセージは、メッセージが複数回送信されていることを防ぐために、アダプターのプライベート アプリケーション メッセージ キューから削除する必要があります。  
  
 後**Terminate**と呼ばれますが、メッセージング エンジンでは、送信請求-応答の組み合わせに対する応答メッセージを除き、新しいメッセージを発行する要求は受け付けられません。
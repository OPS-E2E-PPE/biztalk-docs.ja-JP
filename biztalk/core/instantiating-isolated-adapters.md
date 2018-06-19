---
title: 分離アダプターをインスタンス化 |Microsoft ドキュメント
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
ms.openlocfilehash: 9e3090252f63221547604a4fdf88388bcbf8296f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257490"
---
# <a name="instantiating-isolated-adapters"></a>分離アダプターのインスタンス化
分離アダプターは BizTalk Server によってインスタンス化されません。 代わりに、別のプロセスでインスタンス化され、ホストされます。 トランスポート プロキシを作成するアダプターの責任**QueryInterface**の**IBTTransportProxy**、およびを呼び出す**IBTTransportProxy**.**RegisterIsolatedReceiver**メッセージング エンジンに登録します。  
  
 登録には、構成済みで有効になっている受信場所の 1 つをアダプターからメッセージ エンジンに渡す必要があります。 アダプターのホスト プロセスの資格情報は、BizTalk 分離ホスト ユーザー グループのメンバーである必要があります。 ここで単に権限借用を使用しても、ユーザーがそのグループのメンバーでなければ不十分です。 アダプターのクエリが実行が正しいことを確認するさらに、 **ClassID**がそのホスト インスタンス用に構成されたコンピューターで実行されているとします。 Load メソッドを呼び出すことによりを使用してその構成が送信アダプターがそのトランスポート プロキシで正常に登録された後、 **IPersistPropertyBag**インターフェイスです。  
  
 この API 呼び出しの順序は、次の図のようになります。 アダプターは、青色で示されるインターフェイスを実装しています。  
  
 ![](../core/media/isolated-adapter-init.gif "Isolated_adapter_init")  
  
 次のコードは、登録 API の呼び出し方法を示しています。  
  
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
  
 **実装のヒン ト:** アダプターが進行中の作業の数を記録することをお勧めします。 アダプターはブロック**Terminate**メッセージの数が 0 に到達するまでです。 受信側では、BizTalk Server に対して公開されていない未処理の要求がこの作業に含まれます。 後に受信アダプターに応答メッセージは配信されません**Terminate**が呼び出されています。  
  
 送信アダプターでは、処理中のメッセージが適切に処理される必要があります。 つまり、正常に配信されたメッセージをアダプターのプライベート アプリケーション メッセージ キューから削除して、メッセージが 2 回以上送信されるのを防ぐ必要があります。  
  
 後**Terminate**と呼ばれますが、メッセージング エンジンでは、送信請求-応答の組み合わせに対する応答メッセージを除き、新しいメッセージを公開する要求は受け付けられません。
---
title: 受信アダプターの交換パターン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e505559e-66be-4c32-a2a8-a242cba10000
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 856200bbd511f580f8ef58fd0be78ee1fb6718b2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388279"
---
# <a name="exchange-patterns-for-receive-adapters"></a>受信アダプターの交換パターン
受信アダプターで「ネットワーク」からデータを受信およびにメッセージとして送信[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 この送信プロセスを一方向または双方向メッセージ交換パターンを使用できます。  
  
## <a name="one-way-submit"></a>一方向の送信  
 BizTalk メッセージング エンジンにメッセージを送信する受信アダプターの場合、新しい BizTalk メッセージの作成が必要最初です。 IBaseMessage のトピックのコード サンプルでは、これを行う方法を示します。 アダプターがメッセージの本文として設定するストリームは、メモリに読み取られていたデータをキャッシュする必要がありますので、順方向専用ストリーム通常はずです。  
  
 アダプターは、エンジンにメッセージを送信する前に書き込む必要があります、 **InboundTransportLocation**メッセージ コンテキスト プロパティを BizTalk メッセージに、system 名前空間。 これは、次のコード フラグメントに示します。  
  
 `Assembly References:`  
  
 `Microsoft.XLANGs.BaseTypes.dll`  
  
 `Microsoft.BizTalk.Pipeline.dll`  
  
 `Microsoft.BizTalk.GlobalPropertySchemas.dll`  
  
```  
using Microsoft.BizTalk.Message.Interop;  
using Microsoft.XLANGs.BaseTypes;  
  
private static readonly PropertyBase InboundTransportLocationProp =   
new BTS.InboundTransportLocation();  
  
private void StampMsgCtxProps(  
IBaseMessage msg, string uri, string adapterType)  
{  
msg.Context.Write(  
 InboundTransportLocationProp.Name.Name,   
 InboundTransportLocationProperty.Name.Namespace,   
  uri);  
}  
```  
  
 さらに、アダプターは、独自のプロパティ スキーマを定義し、メッセージを受信したことをエンドポイントに関連するメッセージ コンテキスト プロパティを書き込むことがあります。 たとえば、HTTP アダプターが HTTP ヘッダーをメッセージ コンテキストに書き込む可能性があり、SMTP レシーバーは、メッセージ コンテキストにメールの件名を書き込む可能性があります。 この情報は、パイプライン コンポーネントやオーケストレーション スケジュール、送信アダプターなどの下流コンポーネントに役立つ可能性があります。  
  
 メッセージを準備すると後、は、メッセージング エンジンに送信できます。 表示する方法を一方向の受信アダプター可能性があります、エンジンにメッセージを送信をコード サンプルを参照して[SubmitDirect (BizTalk Server サンプル)](../core/submitdirect-biztalk-server-sample.md)します。  
  
## <a name="request-response"></a>要求-応答  
 双方向受信アダプターが一方向または双方向で使用される通常の受信ポート。 アダプターでは、サービスを提供して、受信場所が一方向または双方向のポートを調べることによってがかどうかを決定、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成プロパティ バッグを指定します。 このプロセスについては、 **IBTTransportConfig.AddReceiveEndpoint メソッド (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。  
  
 次のオブジェクト相互作用の図は、要求-応答のメッセージ交換を実行するプロセスを示しています。 アダプターがトランスポート プロキシから新しいバッチを要求し、自身の参照を渡す、 **IBTTransmitter**インターフェイスを通じて、 **SubmitRequestMessage**メソッド。 メッセージング エンジンでは、このインターフェイスの応答メッセージを配信を使用して、 **TransmitMessage**メソッド。  
  
 エンジンはメッセージを非同期的に処理があるために、発生する次のことができます。  
  
- **BatchComplete**する前に発生する可能性がコールバック**完了**が返されます。  
  
- TransmitMessage の呼び出しは BatchComplete 前に行われ、実行前であってもに、可能性があります。  
  
  これら両方のシナリオはまれですが、アダプターが自身を保護これです。  
  
  非同期の非ブロッキング呼び出しを使用して、応答メッセージを送信することをお勧めします。  
  
  BaseAdapter プロジェクトには、ユーティリティ クラスが含まれる**StandardRequestResponseHandler**、このトピックで説明されている要求/応答セマンティクスをカプセル化します。  
  
## <a name="request-response-message-time-outs"></a>要求-応答メッセージのタイムアウト  
 要求メッセージのタイムアウトを指定する必要がアダプターでは、要求-応答メッセージを送信するときにある、 **IBTTransportBatch.SubmitRequestMessage メソッド (COM)** API[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。 応答メッセージは、このタイムアウト期間内でのみ、アダプターに送信されます。 タイムアウトに達すると、否定受信確認応答 (NACK) が応答メッセージではなく、アダプターに配信されます。 アダプターがタイムアウト値を指定しない場合、エンジンは 20 分の既定値を使用します。  
  
 インプロセス受信アダプター用に次のレジストリ キーを使用して、要求-応答メッセージの既定のタイムアウトを制御できます。  
  
 **DWORD**  
  
 **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc{Host Guid}\MessagingReqRespTTL**  
  
 レジストリ キーを別の場所では、分離受信アダプター。  
  
 **DWORD**  
  
 **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc.3.0\MessagingReqRespTTL**  
  
 Nack (否定受信確認応答) は SOAP エラーと、それらを処理する 2 つの方法はあります。 通常、アダプターがクライアントに NACK を返すし、クライアントで NACK を処理します。 または、マップまたはカスタム パイプライン コンポーネントを使用して、応答メッセージの内容を変更する応答メッセージを処理する送信パイプラインを構成することがあります。
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
ms.openlocfilehash: cc93f587e8d04e93e96a8e326abfcc68c51daf69
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004820"
---
# <a name="exchange-patterns-for-receive-adapters"></a>受信アダプターの交換パターン
受信アダプターは、外部からデータを受信し、これをメッセージとして [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信します。 この送信プロセスには、一方向または双方向のメッセージ交換パターンが可能です。  
  
## <a name="one-way-submit"></a>一方向の送信  
 受信アダプターから BizTalk メッセージング エンジンにメッセージを送信するには、まず受信アダプターで新しい BizTalk メッセージを作成する必要があります。 IBaseMessage のトピックのコード例では、この方法を示しています。 アダプターがメッセージ本文として設定するストリームは通常、順方向専用のストリームである必要があります。つまり、このストリームで以前メモリに読み込んだデータを、再度ストリームにキャッシュすることはできません。  
  
 アダプターは、エンジンにメッセージを送信する前に書き込む必要があります、 **InboundTransportLocation**メッセージ コンテキスト プロパティを BizTalk メッセージに、system 名前空間。 次のコードはこの処理を示すものです。  
  
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
  
 アダプターではさらに、独自のプロパティ スキーマを定義して、メッセージを受信したエンドポイントのメッセージ コンテキスト プロパティを書き込む場合もあります。 たとえば、HTTP アダプターではメッセージ コンテキストに HTTP ヘッダーを書き込む場合があり、SMTP レシーバーではメッセージ コンテキストにメールの件名を書き込む場合があります。 この情報は、パイプライン コンポーネント、オーケストレーション スケジュール、送信アダプターなどの下流コンポーネントで役立ちます。  
  
 メッセージを作成したら、メッセージング エンジンに送信できます。 表示する方法を一方向の受信アダプター可能性があります、エンジンにメッセージを送信をコード サンプルを参照して[SubmitDirect (BizTalk Server サンプル)](../core/submitdirect-biztalk-server-sample.md)します。  
  
## <a name="request-response"></a>要求-応答  
 通常、双方向の受信アダプターは、一方向または双方向の受信ポートで使用します。 このアダプターは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の構成プロパティ バッグを調べて、サービスを提供する受信場所が一方向と双方向のどちらのポートであるかを判断します。 このプロセスについては、 **IBTTransportConfig.AddReceiveEndpoint メソッド (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。  
  
 下の図に、オブジェクト間の対話処理における要求 - 応答のメッセージ交換の実行手順を示します。 アダプターがトランスポート プロキシから新しいバッチを要求し、自身の参照を渡す、 **IBTTransmitter**インターフェイスを通じて、 **SubmitRequestMessage**メソッド。 メッセージング エンジンでは、このインターフェイスの応答メッセージを配信を使用して、 **TransmitMessage**メソッド。  
  
 メッセージング エンジンはメッセージを非同期的に処理します。したがって、次の問題が発生する可能性があります。  
  
- **BatchComplete**する前に発生する可能性がコールバック**完了**が返されます。  
  
- TransmitMessage の呼び出しが、BatchComplete や、場合によっては Done より前に行われる。  
  
  どちらも発生の可能性は低いものですが、アダプターではこのような問題への対策を用意しておく必要があります。  
  
  応答メッセージは、非同期の非ブロッキング呼び出しを使用して送信することをお勧めします。  
  
  BaseAdapter プロジェクトには、ユーティリティ クラスが含まれる**StandardRequestResponseHandler**、このトピックで説明されている要求/応答セマンティクスをカプセル化します。  
  
## <a name="request-response-message-time-outs"></a>要求 - 応答メッセージのタイムアウト  
 要求メッセージのタイムアウトを指定する必要がアダプターでは、要求-応答メッセージを送信するときにある、 **IBTTransportBatch.SubmitRequestMessage メソッド (COM)** API[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。 指定したタイムアウトまでの間は応答メッセージが配信され、 タイムアウトに達すると、応答メッセージの代わりに否定受信確認応答 (NACK) がアダプターに配信されます。 アダプターでタイムアウト値を指定していない場合、エンジンでは既定値の 20 分が使用されます。  
  
 要求 - 応答メッセージのタイムアウトの既定値は、レジストリ キーを使用して設定できます。インプロセス受信アダプター用のレジストリ キーは次の場所にあります。  
  
 **DWORD**  
  
 **Hkey_local_machine \system\currentcontrolset\services\btssvc {guid} ホスト \MessagingReqRespTTL**  
  
 分離受信アダプター用のレジストリ キーは次の場所にあります。  
  
 **DWORD**  
  
 **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc.3.0\MessagingReqRespTTL**  
  
 NACK (否定受信確認応答) は SOAP エラーとなります。これは 2 つの方法で処理できます。 通常は、アダプターからクライアントに NACK を返し、クライアントで NACK を処理します。 または、応答メッセージを処理する送信パイプラインで、マップまたはカスタム パイプライン コンポーネントを使用して、応答メッセージのコンテンツを変更するよう構成することもできます。
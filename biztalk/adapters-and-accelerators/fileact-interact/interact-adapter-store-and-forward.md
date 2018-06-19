---
title: アダプター ストア アンド フォワードの対話 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d596780a-085d-48db-be44-a3ae58f591d0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c7aff0b2421a19f5fe84ee914c4f9d2bd7ef04e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963208"
---
# <a name="interact-adapter-store-and-forward"></a>アダプター ストア アンド フォワードを対話します。
ストアにし、順方向 (SnF) モードでは、メッセージは送信時にキューに配信され、変換先にキューから取得されます。 SnF を使用する場合、応答は SWIFTNet SnF 自体から取得し、応答側からフィードバックが含まれていません。  
  
 メッセージとファイルは、SnF を使用していないときに、サーバー プロセスにルーティングされたメッセージと同じような柔軟性をキューにルーティングできます。 この定義は、(SWIFTNet) の内部で MRR 内がします。 受信者キューでメッセージやファイルが配置されることが送信者によって送信された後を決定することをお勧めします。 キューにメッセージやファイルを配置することを行う SnF 配信モード (RequestControl) 内のメッセージにフラグを設定します。  
  
 キューからメッセージを取得するには、アプリケーション デザイナーによって行われた選択に基づき、2 つの異なるモードで発生します。 これらのモードは、プッシュおよびプルと呼ばれます。  
  
 プッシュ モードを使用する場合 SWIFTNet SnF メッセージを配信する取り組みが存在します。 メッセージは、「プッシュ」SWIFTNet SnF からされ、SWIFTNet リンク上のアプリケーション サーバーによって受信されます。 サーバー アプリケーションは、メッセージの受信確認で応答する前に safestored があることを確認します。 この受信確認は、メッセージを受信したどの SWIFTNet SnF ことを示します。 受信確認では、その他の追加"business"ロジックは含まれません。  
  
## <a name="queues-in-swiftnet"></a>SWIFTNet のキュー  
 キューには、メッセージと、指定した受信者に配信される、送信側から送信されたファイルが含まれます。 キューがも SWIFTNet SnF によって生成される配信通知に含まれます。  
  
 キューが定義され、受信側の組織で構成されています。 キューの実際の作成は、ユーザーの要求に SWIFT で行われます。 送信者は、キューにメッセージが最終的に配置されますに関して何も知らないです。 受信側の制御下で完全です。  
  
 キューのウィンドウ サイズ属性は、受信確認せず、キューから SWIFTNet SnF を取得するメッセージの最大数を制御します。 受信側はまだ ウィンドウで、スロットを解放する前にメッセージを確認します。  
  
### <a name="delivery-into-a-queue"></a>キューに配信  
 ストア アンド フォワードを使用してサービスの場合、受信側では、ストア アンド フォワード モードで送信されたメッセージの格納に使用するキューを決定します。  
  
 配信通知は、送信者に送信されたメッセージの配信ステータスを通知するために、送信者機関のキューに配置されています。 これは、送信アダプターのプロパティを構成できます。  
  
## <a name="sessions"></a>セッション  
 キューを取得するには、セッションが開始されます。 Sw:SnFSessionId SWIFTNet SnF によって配信されるすべてのメッセージが返されます。 Sw:SnFSessionId にはキュー名、セッション モードが含まれています: プッシュ、およびセッションの数。 すべてのセッションのセッションの数は増加します。 例を示します。  
  
 **\<Sw:SnFSessionId\>bankwxyz_applicq1:p:000458\</Sw:SnFSessionId\>**  
  
 "P"では、プッシュ セッションを示します。 セッション見なすことができますもキューの予約として、Authorizer でします。 後続のメッセージは、同じ承認者を承認する必要があります。  
  
 ストア アンド フォワードにメッセージを送信するときに、セッションは適用されません。  
  
### <a name="push-session-snf"></a>プッシュ セッション SnF  
 SnF シーケンスには、次の前提としています。  
  
-   クライアント プロセスでは、そのジョブが実行し、今すぐ終了できます。 これを行うには、オープンなセキュリティ コンテキストを SwSec:DestroyContextRequest を発行してクリーンアップする必要があります。 Sw:TermRequest 後は、プロセスには、exit() が可能性があります。  
  
-   別のクライアントが開始されます。 初期化の手順は、最初のクライアントの場合と同様です。 キューのリリースでは、SwCall 入力プリミティブとして Sw:ReleaseSnFQueueRequest でを実行することによってです。  
  
     キューのリリースが正常に処理するようになったら、SWIFTNet はキューからメッセージの配信を停止します。  
  
 サーバーは、時に 1 つの要求を処理します。 SWIFTNet SnF は、キューからの複数の要求を提供します。 これらは、サーバーが応答するか、タイムアウトが発生するまで、ネットワークと SWIFTNet リンク内でバッファリングされます。  
  
 いくつかの要求が既に配信されている、キューを解放する前にまだ確認されて、ことができます。 キューが解放されるまで、SWIFTNet SnF はこれらのメッセージの複数の受信確認を処理しません。 これらのメッセージは、後続のセッションで再配信されます。  
  
 サーバー アプリケーションがまだ後、クライアントがそのキューのリリースを発行が通常これはない場合、キューから配信される要求の肯定応答で応答するかどうか、ローカルの実装に除外されます。  
  
## <a name="see-also"></a>参照  
 [アダプターのアーキテクチャを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [InterAct アダプター コンポーネント](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [ビジネスの Exchange に対するアダプターのメッセージを相互作用します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [InterAct アダプターのクライアント アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [InterAct アダプタ サーバー アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [アダプターのセキュリティ アーキテクチャを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [アダプターのエンド ツー エンドの信頼性の高い配信を対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [アダプターの状態を操作の監視](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [InterAct アダプターの否認不可](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)
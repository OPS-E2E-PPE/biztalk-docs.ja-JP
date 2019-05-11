---
title: InterAct アダプター ストア アンド フォワード |Microsoft Docs
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
ms.openlocfilehash: 8697cd25af9622057d9bd3224fe93f26b214716d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366657"
---
# <a name="interact-adapter-store-and-forward"></a>InterAct アダプター ストア アンド フォワード
ストアにし、転送 (SnF) モードでは、メッセージが送信時に、キューに配信され、変換先にキューから取得されます。 SnF を使用して、応答は SWIFTNet SnF 自体に由来し、応答側からのフィードバックが含まれていません。  
  
 メッセージとファイルは、SnF を使用しない場合は、サーバー プロセスにルーティングされたメッセージと同様の柔軟性をキューにルーティングできます。 この定義では、(SWIFTNet) の内部で MRR 内です。 受信側キューでメッセージやファイルが配置されますは、送信側が送信後かを決定することをお勧めします。 キューにメッセージまたはファイルを配置することは SnF の配信モード (RequestControl) 内のメッセージにフラグを設定して行われます。  
  
 キューからメッセージを取得すると、アプリケーション デザイナーで行った選択によって、2 つの異なるモードでは発生します。 これらのモードは、プッシュとプルと呼ばれます。  
  
 プッシュ モードを使用する場合、メッセージを配信するため、イニシアチブは SWIFTNet SnF で存在します。 メッセージは、「プッシュ」SWIFTNet SnF からされ SWIFTNet リンクをアプリケーション サーバーを受け取ります。 サーバー アプリケーションでは、メッセージの受信確認で応答する前に safestored があることを確認します。 この受信確認は SWIFTNet SnF をどのようにメッセージを受信したことを示します。 受信確認では、その他の追加"business"のロジックは含まれません。  
  
## <a name="queues-in-swiftnet"></a>SWIFTNet のキュー  
 キューには、メッセージおよび指定された受信者に配信される、送信側から送信されたファイルが含まれます。 キューがも SWIFTNet SnF によって生成される配信通知に含まれます。  
  
 キューが定義され、受信側の組織で構成されています。 キューの実際の作成は、ユーザーの要求で SWIFT によって実行されます。 送信者は、キューでメッセージが配置最終的には何も知りません。 受信側の制御下で完全です。  
  
 キューのウィンドウ サイズ属性では、受信確認をキューから SWIFTNet SnF を取得するメッセージの最大数を制御します。 受信側はまだ ウィンドウで、スロットを解放する前にメッセージを確認します。  
  
### <a name="delivery-into-a-queue"></a>キューに配信  
 ストア アンド フォワードを使用してサービスの受信側は、ストア アンド フォワード モードで送信されたメッセージの格納に使用するキューを決定します。  
  
 配信通知は、送信者教育機関の送信者に送信されたメッセージの配信ステータスを通知するためにキューに配置されます。 これは、送信アダプターのプロパティで構成できます。  
  
## <a name="sessions"></a>セッション  
 キューを取得する際に、セッションが開始されます。 Sw:SnFSessionId SWIFTNet SnF によって配信されるすべてのメッセージが返されます。 キュー名、セッション モードを含む、Sw:SnFSessionId: プッシュ、およびセッションの数。 すべてのセッションのセッションの数は増加します。 例を示します。  
  
 **\<Sw:SnFSessionId\>bankwxyz_applicq1:p:000458\</Sw:SnFSessionId\>**  
  
 "P"では、プッシュ セッションを示します。 セッションは、権限付与者で、キューの予約としても確認できます。 後続のメッセージは、同じ承認者によって確認する必要があります。  
  
 ストア アンド フォワードにメッセージを送信するときに、セッションは適用されません。  
  
### <a name="push-session-snf"></a>プッシュ セッション SnF  
 SnF シーケンスには、次の前提としています。  
  
- クライアント プロセスでは、そのジョブで実行され、終了するようになりました。 これを行うには、オープンなセキュリティ コンテキストを SwSec:DestroyContextRequest を発行してクリーンアップする必要があります。 Sw:TermRequest 後は、プロセスには、exit() が可能性があります。  
  
- 別のクライアントが開始されます。 初期化の手順は、最初のクライアントの場合と同じです。 キューのリリースでは、SwCall 入力プリミティブとして Sw:ReleaseSnFQueueRequest でを実行することです。  
  
   SWIFTNet は、キューのリリースを正常に処理すると、すぐにキューからメッセージの配信を停止します。  
  
  サーバーは、時に 1 つの要求を処理します。 SWIFTNet SnF では、キューからの複数の要求を提供します。 これらは、サーバーが応答するか、タイムアウトが発生するまでネットワークに SWIFTNet リンク内でバッファリングされます。  
  
  一部の要求が既に配信されている、キューをリリースする前にまだ確認されたが、可能性があります。 SWIFTNet SnF は、キューが解放されるまで、これらのメッセージの複数の受信確認を処理しません。 これらのメッセージは、後続のセッションで再配信されます。  
  
  サーバー アプリケーションにも通常が表示されない場合、クライアントがそのキューでは、リリースを発行した後、キューから配信される要求の肯定応答で応答するかどうかは、ローカルの実装にままです。  
  
## <a name="see-also"></a>参照  
 [InterAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [InterAct アダプターのコンポーネント](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [業務用 Exchange 用の interAct アダプターのメッセージ](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [InterAct アダプターのクライアント アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [InterAct アダプタ サーバー アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [InterAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [アダプターのエンド ツー エンドの信頼性の高い配信を操作します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [InterAct アダプターの状態の監視](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [InterAct アダプターの否認不可](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)
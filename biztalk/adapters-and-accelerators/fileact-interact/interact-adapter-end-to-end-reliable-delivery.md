---
title: アダプターのエンド ツー エンドの信頼性の高い配信を対話 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac7c22f2-ee4a-4e9b-af40-da7eb58daf51
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90ca0fc7ae5872598ed9a61cd7541017a6a39667
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222994"
---
# <a name="interact-adapter-end-to-end-reliable-delivery"></a>アダプターのエンド ツー エンドの信頼性の高い配信を対話します。
メッセージやファイルを受信者に送信するときに、メッセージやファイルが配信される、およびビジネスをより詳細度もいいえがこれらに含まれているトランザクションで実行が予想されることを確認することをお勧めします。  
  
 両方のエンティティが相互に通信は、(たとえば、永続的なメッセージ指向ミドルウェアおよび使用するインターフェイス アプリケーションによって提供される) 永続的な記憶域を使用することができますが簡単を信頼性の高い配信を実装する場合に通信する方法、メッセージの見かけ上の状態が標準化されています。  
  
 次の図は、E2EControl の構造の例を示します。  
  
 ![End &#45; へ (& a) #45; 終了コントロール](../../adapters-and-accelerators/fileact-interact/media/63e39b43-118e-4572-9d75-21770253a1ee.gif "63e39b43-118e-4572-9d75-21770253a1ee")  
  
 図に示した例で要素が、SwInt:Request 内で送信され、受信アプリケーションに SwInt:RequestHandle 内で変更されていない配信します。 02 の行では、要求に一意の識別子を割り当てることができます。 この一意識別子は、同じ要求の後各再送信に繰り返されます。  
  
 この識別子を構築する方法は、実装者に左しますが、uuidgen() などのシステム コールに基づいている通常または要求を送信する sha-1 の計算結果がある可能性があります (プレフィックスの付いた Sw:MsgId とし、置換を使用して、base64 でエンコードされた sha-1 s単位)。 主要な要件は、(確率が非常に高い) でグローバルに一意であります。  
  
 Sw:CreationTime は、元の要求の作成の時間です。 これは、省略可能なパラメーターが、このメッセージの前の通信試行の最終的な検索を制限すると便利です。  
  
 Sw:PDIndication 要素は、2 台目またはそれ以上しようとすると、メッセージの転送は、このことを示すために存在します。 E2EControl を認識する受信側のアプリケーションは、メッセージが受信されたかどうかどうかを検索するのに、Sw:MsgId を使用できます。 省略可能な Sw:EmissionList には、前の試行の時刻が含まれています。 この時間では大文字と小文字が (世界時刻) 送信者のローカル時間 Sw:GetDateTime 関数を使用するときに、送信者によって取得したとします。 もう一度検索を制限すると便利ですが考えられます。  
  
## <a name="see-also"></a>参照  
 [アダプターのアーキテクチャを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [InterAct アダプター コンポーネント](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [ビジネスの Exchange に対するアダプターのメッセージを相互作用します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [InterAct アダプターのクライアント アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [InterAct アダプタ サーバー アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [アダプター ストア アンド フォワードを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [アダプターのセキュリティ アーキテクチャを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [アダプターの状態を操作の監視](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [アダプター否認不可を対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)
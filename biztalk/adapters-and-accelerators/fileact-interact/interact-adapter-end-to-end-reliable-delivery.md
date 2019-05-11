---
title: アダプターのエンド ツー エンドの信頼性の高い配信を対話 |Microsoft Docs
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
ms.openlocfilehash: 3b2d7ccacde04243c2635bbe5adcafad3f2b9987
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366700"
---
# <a name="interact-adapter-end-to-end-reliable-delivery"></a>アダプターのエンド ツー エンドの信頼性の高い配信を操作します。
受信者にメッセージやファイルを送信するときに、メッセージやファイルを配信できる、およびこれらに含まれているトランザクションではいいえ回を実行よりもビジネスが予想を必ず確認することをお勧めします。  
  
 簡単に場合は、信頼性の高い配信を実装できますが互いと通信する 2 つのエンティティは、(たとえば、永続的なメッセージ指向ミドルウェアおよび使用するインターフェイス アプリケーションによって提供される) 永続的なストレージを使用することができます、ときに通信する方法、メッセージの状態が認識されるを標準化します。  
  
 次の図は、E2EControl の構造の例を示します。  
  
 ![終了&#45;に&#45;コントロールの終了](../../adapters-and-accelerators/fileact-interact/media/63e39b43-118e-4572-9d75-21770253a1ee.gif "63e39b43-118e-4572-9d75-21770253a1ee")  
  
 図に示す例では、要素は、SwInt:Request 内で送信され、受信アプリケーションに SwInt:RequestHandle 内でそのまま配信。 02 の行では、要求に一意の識別子を割り当てることができます。 この一意の識別子が同じ要求の各後続の再送信に繰り返されます。  
  
 この識別子を構築する方法は、実装者は、左しますが、uuidgen() などのシステム コールに基づいて通常または送信される要求に sha-1 の計算結果がある可能性があります (プレフィックスの付いた Sw:MsgId と置き換えます、base64 でエンコードされた sha-1 s文字列の場合)。 主な要件は、(非常に高い確率) でグローバルに一意であります。  
  
 Sw:CreationTime は、元の要求の作成の時間です。 オプションのパラメーターが、このメッセージの前の通信の試行の最終的な検索を制限すると便利です。  
  
 Sw:PDIndication 要素では、2 台目またはメッセージの送信試行をさらにこれがある存在します。 E2EControl を認識する受信側アプリケーションは、メッセージが受信されたかどうかどうかを検索するのに、Sw:MsgId を使用できます。 省略可能な Sw:EmissionList には、前の試行の時間が含まれています。 この時間はローカル時刻 (世界協定時刻) の送信者の Sw:GetDateTime 関数を使用する場合は、送信側が必要があります。 もう一度これが検索の制限に役立つことでした。  
  
## <a name="see-also"></a>参照  
 [InterAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [InterAct アダプターのコンポーネント](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [業務用 Exchange 用の interAct アダプターのメッセージ](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [InterAct アダプターのクライアント アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [InterAct アダプタ サーバー アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [InterAct アダプター ストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [InterAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [InterAct アダプターの状態の監視](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [InterAct アダプターの否認不可](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)
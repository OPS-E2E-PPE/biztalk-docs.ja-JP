---
title: アダプターの否認のやり取り |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a13fb77c-b10c-4f8a-ba4b-efecc83e092c
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d9006ef82a9133884b8e1fbd1cf9caa981cf779
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366677"
---
# <a name="interact-adapter-non-repudiation"></a>アダプターの否認を対話します。
送信の InterAct メッセージの否認不可のサポートは、SwInt:NRIndicator を SwInt:RequestControl または必要に応じて、SwInt:ResponseControl で TRUE に設定して取得されます。 これは、必要なサービスが既定では、否認不可のサポートを選択していない場合にのみサービス プロファイルに従って。  
  
 否認不可は、メッセージを送信する前に、SNL によって作成された有効なシグネチャに基づいています。 そのため、送信要求メッセージを否認不可のサポートを取得するために、SwInt:RequestControl で TRUE に設定する、SwInt:RequestControl 内に含まれる、SwInt:RequestCrypto 要素の必須です。  
  
 応答メッセージの場合、要件ですが同等ですが、関連する要素は、SwInt:ResponseCrypto SwInt:ResponseControl; 内に含まれるSwInt:ResponseCrypto は TRUE に設定する必要があります。  
  
 要求時に、否認不可サポートについては、メッセージの署名、SwInt:RequestHeader、SwInt:RequestPayload、および、SwInt:RequestDescriptor の SwInt:SwiftRequestRef をカバーするために必要なは。 SwInt:SwiftRequestRef は SWIFTNet リンクによって自動的に生成されます。 SwInt:SwiftRequestRef を生成するには、関連、SNL は必要なメッセージの署名を生成するため SwSec:CryptoControl 内 SwSec:MemberRef 値も自動的に調整します。 同様に、応答で非 repudiatin サポートについては、メッセージの署名、SwInt:ResponseHeader、SwInt:ResponsePayload、および、SwInt:ResponseDescriptor の SwInt:SwiftResponseRef をカバーするために必要なは。 SwInt:SwiftResponseRef は SWIFTNet リンクによって自動的に生成されます。 SwInt:SwiftResponseRef を生成するには、関連、SNL は必要なメッセージの署名を生成するため SwSec:CryptoControl 内 SwSec:MemberRef 値も自動的に調整します。  
  
 ビジネス サービスのプロファイルは、既定では、否認不可を選択した場合に必要なメッセージの署名を選択する必要があります。 (先ほどのように、SwInt:RequestControl、または、SwInt:ResponseControl) は、メッセージを抜ける前に選択する必要があります。SNL します。  
  
 ビジネス サービス プロファイルに従って機能の選択は、メッセージを否認不可のサポートを呼び出すと、メッセージのために必要な署名が見つからなかった場合は、メッセージは、そのスイッチによって拒否されます。 状態の例外メッセージがメッセージの送信者に返されます。  
  
 ペイロードの暗号化では、否認不可のサポートと一致しません。 メッセージの否認不可のサポートが選択されているし、全体または一部のペイロードが暗号化されて、メッセージは SWIFTNet リンクによって拒否されます。  
  
 サービスには、否認不可機能、任意の要求またはコントロールでは、否認防止を示す応答があるない場合は拒否されますに注意してください。  
  
## <a name="see-also"></a>参照  
 [InterAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [InterAct アダプターのコンポーネント](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [業務用 Exchange 用の interAct アダプターのメッセージ](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [InterAct アダプターのクライアント アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [InterAct アダプタ サーバー アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [InterAct アダプター ストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [InterAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [アダプターのエンド ツー エンドの信頼性の高い配信を操作します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [InterAct アダプターの状態監視](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)
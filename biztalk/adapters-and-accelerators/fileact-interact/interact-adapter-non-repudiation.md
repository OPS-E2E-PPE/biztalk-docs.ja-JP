---
title: "アダプター否認不可を対話 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a13fb77c-b10c-4f8a-ba4b-efecc83e092c
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d7eabd7eab04c0bd64af0164b73b38af197ac9a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="interact-adapter-non-repudiation"></a>アダプター否認不可を対話します。
送信 InterAct メッセージの否認不可のサポートは、SwInt:NRIndicator を SwInt:RequestControl または必要に応じて、SwInt:ResponseControl で TRUE に設定して取得されます。 これは必要なサービスが既定では、否認不可のサポートを選択していない場合にのみに従って、サービスのプロファイルです。  
  
 否認不可は、メッセージを送信する前に、SNL によって作成された、有効な署名に基づいています。 そのため、送信要求メッセージを否認不可のサポートを取得するためには必須では、SwInt:RequestControl に TRUE を設定する、SwInt:RequestControl 内に含まれる、SwInt:RequestCrypto 要素。  
  
 応答メッセージ、要件は同等ですが、関連する要素は、SwInt:ResponseCrypto SwInt:ResponseControl; 内に含まれる点を除いてSwInt:ResponseCrypto には、TRUE を設定する必要があります。  
  
 要求時に、否認不可サポート、SwInt:RequestHeader SwInt:RequestPayload、や、SwInt:RequestDescriptor の SwInt:SwiftRequestRef に対応するメッセージの署名の必要があります。 SwInt:SwiftRequestRef は SWIFTNet リンクによって自動的に生成されます。 SwInt:SwiftRequestRef を生成すると、関連、SNL は必要なメッセージの署名を生成するため SwSec:CryptoControl 内 SwSec:MemberRef 値も自動的に調整します。 同様に、サポートについては repudiatin 以外の応答で、メッセージの署名、SwInt:ResponseHeader、SwInt:ResponsePayload、および、SwInt:ResponseDescriptor の SwInt:SwiftResponseRef をカバーするために必要です。 SwInt:SwiftResponseRef は SWIFTNet リンクによって自動的に生成されます。 SwInt:SwiftResponseRef を生成すると、関連、SNL は必要なメッセージの署名を生成するため SwSec:CryptoControl 内 SwSec:MemberRef 値も自動的に調整します。  
  
 ビジネス サービス プロファイルは、既定では、否認不可を選択した場合に必要なメッセージの署名を選択する必要 (として記載した、SwInt:RequestControl または、SwInt:ResponseControl) は、メッセージを抜ける前に選択する必要があります。SNL です。  
  
 機能の選択に従って、ビジネス サービス プロファイルには、メッセージを否認不可のサポートが呼び出される場合、およびメッセージで、必要なシグネチャが見つからない場合は、メッセージは、そのスイッチによって拒否されます。 例外のステータス メッセージがメッセージの送信者に返されます。  
  
 ペイロードの暗号化は、否認不可のサポートと一貫性がありません。 メッセージの否認不可のサポートが選択され、全体または一部にペイロードが暗号化されて、メッセージは SWIFTNet リンクによって拒否されます。  
  
 サービスには、否認不可機能、任意の要求またはコントロールでは、否認防止を示す応答があるない場合は拒否されることに注意してください。  
  
## <a name="see-also"></a>参照  
 [アダプターのアーキテクチャを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [InterAct アダプター コンポーネント](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [ビジネスの Exchange に対するアダプターのメッセージを相互作用します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [InterAct アダプターのクライアント アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [InterAct アダプタ サーバー アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [アダプター ストア アンド フォワードを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [アダプターのセキュリティ アーキテクチャを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [アダプターのエンド ツー エンドの信頼性の高い配信を対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [アダプターの状態を操作の監視](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)
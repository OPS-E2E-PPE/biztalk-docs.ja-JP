---
title: "InterAct アダプター コンポーネント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aad60b57-4cc8-44b9-98f5-e5a2ba3a41e2
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e909e49713377172d01540f4c8e660756d68ed72
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="interact-adapter-components"></a>InterAct アダプター コンポーネント
InterAct アダプターには、クライアントとサーバー コンポーネントがあります。 含まれていること、A4SWIFT の (最小) インストール SWIFT Alliance ゲートウェイ (SAG) と同じコンピューターに Windows Server が実行されている場合に注意してください。 SWIFTNet リンク (SNL) が、SAG から別のコンピューターにする可能性があるにも注意してください。 プログラミング インターフェイス (API) のホスト アダプター SWIFT によって提供されるリモート アプリケーションは、コンポーネントの場所に関係なく、SAG A4SWIFT から通信するために使用されます。  
  
 次の図は、InterAct アダプターに関連する全体のアダプターとの通信のチェーンを構成するには、コンポーネントが存在する場所を示します。  
  
 ![InterAct コンポーネント](../../adapters-and-accelerators/fileact-interact/media/cf257c5a-3668-4aff-bce9-7acc6eb672bd.gif "cf257c5a-3668-4aff-bce9-7acc6eb672bd")  
  
 次の図では、クライアント アプリケーションは、A4SWIFT および InterAct アダプターを使用します。 BizTalk Server は、ミドルウェアは、TCPIP を介してリモート API ホスト アダプターと通信する、します。  
  
 ![InterAct クライアント アプリケーション](../../adapters-and-accelerators/fileact-interact/media/7aeada39-6264-498b-92e8-303eb0cf369b.gif "7aeada39-6264-498b-92e8-303eb0cf369b")  
  
 次の図では、サーバー アプリケーションは、A4SWIFT および InterAct アダプターを使用します。 BizTalk Server は、ミドルウェアは、TCPIP を介してリモート API ホスト アダプターと通信する、します。  
  
 ![InterAct サーバー アプリケーション](../../adapters-and-accelerators/fileact-interact/media/51cbae6a-41e9-4a50-9574-5e86bc04ddba.gif "51cbae6a-41e9-4a50-9574-5e86bc04ddba")  
  
## <a name="see-also"></a>参照  
 [アダプターのアーキテクチャを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [ビジネスの Exchange に対するアダプターのメッセージを相互作用します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [InterAct アダプターのクライアント アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [InterAct アダプタ サーバー アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [アダプター ストア アンド フォワードを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [アダプターのセキュリティ アーキテクチャを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [アダプターのエンド ツー エンドの信頼性の高い配信を対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [アダプターの状態を操作の監視](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [アダプター否認不可を対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)
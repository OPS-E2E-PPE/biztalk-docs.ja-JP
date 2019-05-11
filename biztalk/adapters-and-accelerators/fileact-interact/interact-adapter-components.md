---
title: InterAct アダプターのコンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aad60b57-4cc8-44b9-98f5-e5a2ba3a41e2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28effe3955d273e3164d34eb46f8ad947e798907
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366930"
---
# <a name="interact-adapter-components"></a>InterAct アダプターのコンポーネント
InterAct アダプターには、クライアントとサーバー コンポーネントがあります。 含まれていること、A4SWIFT の (最小) インストール SWIFT Alliance ゲートウェイ (SAG) と同じコンピューターに Windows Server が実行されている場合に注意してください。 また SWIFTNet リンク (SNL) は、SAG から別のコンピューターにありますに注意してください。 プログラミング インターフェイス (API) のホスト アダプター SWIFT によって提供されるリモート アプリケーションは、A4SWIFT からコンポーネントの場所に関係なく、SAG への通信に使用されます。  
  
 InterAct アダプターに関連する全体のアダプターとの通信のチェーンを構成するコンポーネントが置かれている場所を次の図に示します。  
  
 ![InterAct コンポーネント](../../adapters-and-accelerators/fileact-interact/media/cf257c5a-3668-4aff-bce9-7acc6eb672bd.gif "cf257c5a-3668-4aff-bce9-7acc6eb672bd")  
  
 次の図では、クライアント アプリケーションは、A4SWIFT と InterAct アダプターを使用します。 BizTalk Server は、このミドルウェアは、TCPIP を介してリモート API ホスト アダプターと通信します。  
  
 ![InterAct クライアント アプリケーション](../../adapters-and-accelerators/fileact-interact/media/7aeada39-6264-498b-92e8-303eb0cf369b.gif "7aeada39-6264-498b-92e8-303eb0cf369b")  
  
 次の図では、サーバー アプリケーションは、A4SWIFT と InterAct アダプターを使用します。 BizTalk Server は、このミドルウェアは、TCPIP を介してリモート API ホスト アダプターと通信します。  
  
 ![InterAct サーバー アプリケーション](../../adapters-and-accelerators/fileact-interact/media/51cbae6a-41e9-4a50-9574-5e86bc04ddba.gif "51cbae6a-41e9-4a50-9574-5e86bc04ddba")  
  
## <a name="see-also"></a>参照  
 [InterAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [業務用 Exchange 用の interAct アダプターのメッセージ](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [InterAct アダプターのクライアント アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [InterAct アダプタ サーバー アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [InterAct アダプター ストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [InterAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [アダプターのエンド ツー エンドの信頼性の高い配信を操作します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [InterAct アダプターの状態の監視](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [InterAct アダプターの否認不可](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)
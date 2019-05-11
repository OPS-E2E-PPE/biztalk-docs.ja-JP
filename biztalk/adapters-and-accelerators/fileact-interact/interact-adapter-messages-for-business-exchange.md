---
title: 業務用 Exchange 用の interAct アダプターのメッセージ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3b443b8a-4e56-47f1-8d91-5c807fd54ccc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d97c1bd20341719440637f0fa37bd8a806a84224
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366684"
---
# <a name="interact-adapter-messages-for-business-exchange"></a>業務用 Exchange 用の interAct アダプターのメッセージ
InterAct アダプターのエンド ツー エンドのサイクルには、4 つのメッセージがあります。 これらのメッセージは SWIFTNet プリミティブです。 最初と最後のメッセージには、クライアント側のプリミティブ、SwInt:ExchangeRequest および SwInt:ExchangeResponse が構成されています。 中間の 2 つのメッセージには、サーバー側のプリミティブ、SwInt:HandleRequest および SwInt:HandleResponse が構成されています。  
  
 この簡略化のレベルでは、エンド ツー エンドのメッセージのサイクルで 6 つの手順があります。  
  
1. クライアント アプリケーションでは、要求メッセージを準備します。  
  
2. クライアント アプリケーションでは、SWIFTNet に要求メッセージを渡します。  
  
3. SWIFTNet は、要求メッセージを処理し、サーバー アプリケーションに送信します。  
  
4. サーバー アプリケーションでは、SWIFTNet から要求メッセージを受信します。  
  
5. サーバー アプリケーションでは、応答メッセージを準備します。  
  
6. サーバー アプリケーションでは、SWIFTNet に応答メッセージを渡します。  
  
7. SWIFTNet は、応答メッセージを処理し、クライアント アプリケーションに送信します。  
  
8. クライアント アプリケーションでは、SWIFTNet から応答メッセージを受信します。  
  
   InterAct メッセージ交換の図は、次のとおりです。  
  
   ![InterAct メッセージ交換](../../adapters-and-accelerators/fileact-interact/media/12fbebc6-5ab7-4d7f-9f94-4069b22161fa.gif "12fbebc6-5ab7-4d7f-9f94-4069b22161fa")  
  
## <a name="see-also"></a>参照  
 [InterAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [InterAct アダプターのコンポーネント](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [InterAct アダプターのクライアント アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [InterAct アダプタ サーバー アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [InterAct アダプター ストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [InterAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [アダプターのエンド ツー エンドの信頼性の高い配信を操作します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [InterAct アダプターの状態の監視](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [InterAct アダプターの否認不可](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)
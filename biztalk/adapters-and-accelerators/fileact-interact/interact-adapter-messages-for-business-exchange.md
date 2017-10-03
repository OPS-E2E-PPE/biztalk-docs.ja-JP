---
title: "ビジネスの Exchange に対するアダプターのメッセージを相互作用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b443b8a-4e56-47f1-8d91-5c807fd54ccc
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d19e10940e6a83c24e9397f0df94d0fc54e4da38
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="interact-adapter-messages-for-business-exchange"></a>ビジネスの Exchange に対するアダプターのメッセージを相互作用します。
InterAct アダプターのエンド ツー エンドのサイクルには、4 つのメッセージがあります。 このメッセージは SWIFTNet プリミティブです。 最初と最後のメッセージには、クライアント側のプリミティブ、SwInt:ExchangeRequest および SwInt:ExchangeResponse が構成されています。 中央の 2 つのメッセージには、サーバー側のプリミティブ、SwInt:HandleRequest および SwInt:HandleResponse が構成されています。  
  
 簡略化のレベルはこのエンド ツー エンドのメッセージのサイクルに 6 つの手順があります。  
  
1.  クライアント アプリケーションでは、要求メッセージを準備します。  
  
2.  クライアント アプリケーションは、要求メッセージを SWIFTNet に渡します。  
  
3.  SWIFTNet は要求メッセージを処理し、サーバー アプリケーションに送信します。  
  
4.  サーバー アプリケーションは、SWIFTNet から要求メッセージを受信します。  
  
5.  サーバー アプリケーションは、応答メッセージを準備します。  
  
6.  サーバー アプリケーションは、応答メッセージを SWIFTNet に渡します。  
  
7.  SWIFTNet は応答メッセージを処理し、クライアント アプリケーションに送信します。  
  
8.  クライアント アプリケーションは、SWIFTNet から応答メッセージを受信します。  
  
 次の図は、InterAct メッセージ交換を示しています。  
  
 ![InterAct メッセージ交換](../../adapters-and-accelerators/fileact-interact/media/12fbebc6-5ab7-4d7f-9f94-4069b22161fa.gif "12fbebc6-5ab7-4d7f-9f94-4069b22161fa")  
  
## <a name="see-also"></a>参照  
 [アダプターのアーキテクチャを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [InterAct アダプター コンポーネント](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [InterAct アダプターのクライアント アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [InterAct アダプタ サーバー アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [アダプター ストア アンド フォワードを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [アダプターのセキュリティ アーキテクチャを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [アダプターのエンド ツー エンドの信頼性の高い配信を対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [アダプターの状態を操作の監視](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [アダプター否認不可を対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)
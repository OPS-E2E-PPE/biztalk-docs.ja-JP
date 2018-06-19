---
title: InterAct アダプターのクライアント アプリケーション |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cdab4624-0fc2-42a3-9867-8f77e144b40c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dac8f459799f59b63976c29f4a87dfe22b56e7ac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223098"
---
# <a name="interact-adapter-client-application"></a>InterAct アダプターのクライアント アプリケーション
アダプター クライアント アプリケーションの要求メッセージは、クライアント側 SWIFTNet リンク (SNL) をクライアント アプリケーションから渡された XML ドキュメントを操作します。 この種類のメッセージは、クライアント側で実行される SWIFTNet 要求/応答プリミティブの最初の部分として発生します。  
  
 このトピックでは、SwInt:ExchangeRequest メッセージについて説明します。 SWIFTNet に「同期」のクライアント側呼び出しに使用されます。 このコンテキストでは、「同期」は意味関数呼び出しが、クライアント アプリケーションは、強制的にサーバー側のアプリケーションから応答を受信するまで待機をブロックします。 (または、代わりに、エラーが発生し、このエラーは報告をクライアントに。)  
  
 暗号ブロック (SwSec:Crypto) 存在する場合は、メッセージの署名および/または検証処理の結果を含めます。 また、特定の処理段階で、SNL によって実行される暗号化の処理を指示する命令を含めることはできます。  
  
## <a name="interact-adapter-payload-format"></a>アダプターのペイロードの形式を対話します。  
 要求ペイロードには、ビジネス メッセージの内容が含まれています。 ペイロードの構造は、整形式の XML が (単につまり、ペイロードは、XML の解析を中断されませんが、そのためがない、XML ドキュメント構造を使用する) の要件に従う必要があります。 SWIFTNet メッセージの検証が適用されている場合は、ペイロードが準拠するその他の構造要件です。 別に、ペイロードの構造と内容は、業務アプリケーションによって決まります。  
  
## <a name="see-also"></a>参照  
 [アダプターのアーキテクチャを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [InterAct アダプター コンポーネント](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [ビジネスの Exchange に対するアダプターのメッセージを相互作用します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [InterAct アダプタ サーバー アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [アダプター ストア アンド フォワードを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [アダプターのセキュリティ アーキテクチャを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [アダプターのエンド ツー エンドの信頼性の高い配信を対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [アダプターの状態を操作の監視](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [アダプター否認不可を対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)
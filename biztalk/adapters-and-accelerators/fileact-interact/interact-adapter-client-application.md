---
title: InterAct アダプターのクライアント アプリケーション |Microsoft Docs
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
ms.openlocfilehash: 935e7fd0672db3445e850ec470ed90e86ed8bfeb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366939"
---
# <a name="interact-adapter-client-application"></a>InterAct アダプターのクライアント アプリケーション
アダプター クライアントのアプリケーション要求メッセージは、クライアント側 SWIFTNet リンク (SNL) をクライアント アプリケーションから渡された XML ドキュメントを操作します。 この種類のメッセージは、クライアント側で実行される要求/応答の SWIFTNet プリミティブの最初の部分として発生します。  
  
 このトピックでは、SwInt:ExchangeRequest メッセージについて説明します。 SWIFTNet を「同期」のクライアント側の呼び出しに使用されます。 このコンテキストでは、「同期」は意味関数呼び出しが強制的に、サーバー側のアプリケーションからの応答を受信するまで待ってから、クライアント アプリケーションをブロックします。 (または、代わりに、エラーが発生し、このエラーは、クライアントに報告します。)  
  
 暗号のブロック (SwSec:Crypto) 存在する場合のメッセージの署名または検証処理結果を含めることができます。 また、特定の処理段階で、SNL によって実行される暗号化の処理を指示する命令を含めることができます、します。  
  
## <a name="interact-adapter-payload-format"></a>アダプターのペイロード形式を対話します。  
 要求ペイロードには、ビジネス メッセージの内容が含まれています。 ペイロードの構造は、整形式 XML (つまり、ペイロードは、XML の解析を中断しませんが、そのためがない、XML ドキュメント構造を使用する) の要件に従う必要があります。 SWIFTNet メッセージの検証が適用されている場合は、ペイロードが準拠するその他の構造の要件です。 別に、ペイロードの構造と内容は、業務アプリケーションによって決まります。  
  
## <a name="see-also"></a>参照  
 [InterAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [InterAct アダプターのコンポーネント](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [業務用 Exchange 用の interAct アダプターのメッセージ](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [InterAct アダプタ サーバー アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [InterAct アダプター ストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [InterAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [アダプターのエンド ツー エンドの信頼性の高い配信を操作します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [InterAct アダプターの状態の監視](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [InterAct アダプターの否認不可](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)
---
title: InterAct アダプターの状態の監視 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2bbc6a45-8d3a-444e-b760-aef0dfa7218a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 540923098d57fd508e8071daa9febc7b3eeb8c47
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366616"
---
# <a name="interact-adapter-status-monitoring"></a>InterAct アダプターの状態の監視
SWIFTNet リンク (SNL C) は、SWIFTNet ストアとその SNL に獲得前方の (SnF) セッションに関するローカルの状態を保持します。 セッションに関する情報を取得するには、次のプリミティブを SwCall() を使用します。  
  
 ![セッション情報を取得する](../../adapters-and-accelerators/fileact-interact/media/b7feb4b4-de92-4bb9-bcfe-363a127d0ed2.gif "b7feb4b4-de92-4bb9-bcfe-363a127d0ed2")  
  
 AuthorizationContext を提供する必要はないことに注意してください。 次の図に示すようにローカル SNL に表示される情報が返されます。  
  
 ![セッション状態の情報](../../adapters-and-accelerators/fileact-interact/media/afd46393-a11d-4b4a-a66b-eba5f049f306.gif "afd46393-a11d-4b4a-a66b-eba5f049f306")  
  
## <a name="see-also"></a>参照  
 [InterAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [InterAct アダプターのコンポーネント](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [業務用 Exchange 用の interAct アダプターのメッセージ](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [InterAct アダプターのクライアント アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [InterAct アダプタ サーバー アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [InterAct アダプター ストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [InterAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [アダプターのエンド ツー エンドの信頼性の高い配信を操作します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [InterAct アダプターの否認不可](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)
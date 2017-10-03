---
title: "BizTalk Adapter for TIBCO Rendezvous のアーキテクチャ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- passing messages
- architecture
- message passing
- messages, passing
ms.assetid: 174d6ceb-8e1d-4c93-827d-8155cfe47836
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 801f92453ffc85d83d57c1caa5c89ec618b96ed0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="architecture-of-biztalk-adapter-for-tibco-rendezvous"></a>BizTalk Adapter for TIBCO Rendezvous のアーキテクチャ
Microsoft BizTalk Adapter for TIBCO Rendezvous は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と TIBCO Rendezvous 間に双方向の接続を提供します。 このアダプターは、TIBCO Rendezvous API と BizTalk Adapter Framework API の両方を使用して、緊密な統合を提供します。  
  
 TIBCO Rendezvous は、エンタープライズ アプリケーション統合 (EAI) のメッセージ バスを提供するソフトウェア製品です。 TIBCO には、C、C++、Java、Visual Basic および Microsoft .NET Framework 用のメッセージング API が用意されており、Microsoft Office Excel ワークシートおよびその他の任意のアプリケーションでデータ フィードを受信できます。  
  
## <a name="message-passing"></a>メッセージ パッシング  
 メッセージを渡す概念はとても簡単です。  
  
-   メッセージには、ピリオドで区切られた要素で構成される 1 つのサブジェクトがあります。 メッセージは 1 つの Rendezous デーモンに送信されます (ただし、最終的に他の複数のデーモンに配信される場合があります)。  
  
-   リスナーは、待機しているサブジェクトを (基本的なワイルドカード機能を使用して) デーモンに通知し、2 つのデーモンが相互に "接続" されている場合または実際には同一のデーモンである場合は、一致するサブジェクトを持つメッセージがリスナーに配信されます。 詳細については、内のメッセージを参照してください。 [BizTalk Adapter for TIBCO Rendezvous のメッセージ](../core/messages-in-biztalk-adapter-for-tibco-rendezvous.md)です。  
  
 次の図は、BizTalk Adapter for TIBCO Rendezvous のアーキテクチャを示しています。  
  
 ![](../core/media/tibcorend-arch.gif "TibcoRend_Arch")  
  
## <a name="see-also"></a>参照  
 [作業の開始](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)   
 [計画とアーキテクチャ](../core/planning-and-architecture15.md)
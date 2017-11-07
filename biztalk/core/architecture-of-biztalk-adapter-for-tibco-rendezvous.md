---
title: "TIBCO Rendezvous アダプターのアーキテクチャ |Microsoft ドキュメント"
description: "BizTalk Adapter for TIBCO Rendezvous しくみ、BizTalk Server でメッセージを渡すことの詳細します。"
ms.custom: 
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 174d6ceb-8e1d-4c93-827d-8155cfe47836
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3bfee2b51df8781091ea30e512810bae21a5f2a
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="architecture-of-the-tibco-rendezvous-adapter"></a>TIBCO Rendezvous アダプターのアーキテクチャ

## <a name="overview"></a>概要
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
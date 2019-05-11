---
title: TIBCO Rendezvous アダプターのアーキテクチャ |Microsoft Docs
description: BizTalk Adapter for TIBCO Rendezvous は、BizTalk Server でメッセージを渡すなどについて説明します
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 174d6ceb-8e1d-4c93-827d-8155cfe47836
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d368e27dd0652753d223fa15b7c82d8ddbbe8b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359012"
---
# <a name="architecture-of-the-tibco-rendezvous-adapter"></a>TIBCO Rendezvous アダプターのアーキテクチャ

## <a name="overview"></a>概要
Microsoft BizTalk Adapter for TIBCO Rendezvous 間の双方向接続を提供する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と TIBCO Rendezvous します。 このアダプターは、TIBCO Rendezvous API と BizTalk Adapter Framework API の両方を使用して、緊密な統合を提供します。  
  
 TIBCO Rendezvous は、エンタープライズ アプリケーション統合 (EAI) のメッセージ バスを提供するソフトウェア製品です。 TIBCO には、C、C++、Java、Visual Basic および Microsoft .NET Framework を受信し、Microsoft Office Excel ワークシートにデータ フィードを任意の他のアプリケーションでのメッセージング Api が提供されます。  
  
## <a name="message-passing"></a>メッセージの受け渡し  
 メッセージを渡す概念はとても簡単です。  
  
- メッセージには、ピリオドで区切られた要素で構成される 1 つのサブジェクトがあります。 (ただし、最終的に他の複数のデーモンにブロードキャストする場合があります) は、1 つの Rendezvous デーモンに送信されます。  
  
- リスナーを発表しているサブジェクトを (基本的なワイルドカード機能) デーモンに関心のあるとを一致するサブジェクトを持つメッセージは、2 つのデーモン、互いに '接続' または同一のデーモンでは実際に配信されます。 詳細については、内のメッセージを参照してください。[で BizTalk Adapter for TIBCO Rendezvous メッセージ](../core/messages-in-biztalk-adapter-for-tibco-rendezvous.md)します。  
  
  次の図は、BizTalk Adapter for TIBCO Rendezvous のアーキテクチャを示します。  
  
  ![](../core/media/tibcorend-arch.gif "TibcoRend_Arch")  
  
## <a name="see-also"></a>参照  
 [作業の開始](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)  
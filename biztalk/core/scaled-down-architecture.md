---
title: 縮小されたアーキテクチャ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, small distributions
- architecture, examples
ms.assetid: e25798aa-4a1e-418c-9e0c-db964e8b5a80
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 770276aceab5c0de64615f457c20d6d1945a63b2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399976"
---
# <a name="scaled-down-architecture"></a>縮小されたアーキテクチャ
システム アーキテクチャの詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]展開を参照してください[Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)します。  
  
 次の図は、サンプル[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アーキテクチャをいくつかのドメインとサーバーの数を減らすための BizTalk Server を結合し、ファイアウォールする必要があります。 このアーキテクチャは、ほとんどの分散は、まだその機能に基づいて、BizTalk Server を区切ります。  
  
 ![縮小されたアーキテクチャ](../core/media/16ebc4ef-ff64-495b-bcac-5c1fd70ca173.gif "16ebc4ef-ff64-495b-bcac-5c1fd70ca173")  
  
        Scaled Down Architecture  
  
 前の図では、サービス インターフェイス ドメインおよびサービス ドメイン内のサーバーは、BizTalk ホスト、および物理サーバーに対応します。 追跡、ホスト インスタンスがスタンドアロン コンピューターにマスター シークレット サーバーおよび管理ツールを保持することをお勧めしますが、送信、処理、および複数のコンピューターで実行しているホストを受信します。 同様に、境界ネットワーク内のサーバーは、論理的な場所に対応します。  
  
 SMTP、メッセージ キュー、ファイル、および SQL の境界ネットワーク内のサーバーは、メール サーバー、キュー、ディレクトリ、または SQL Server、BizTalk それぞれ元の受信および送信メッセージの送受信を処理およびサービス ドメイン内のホストに対応します。  
  
## <a name="see-also"></a>参照  
 [縮小されたアーキテクチャ情報ワーカー サービスを使用](../core/scaled-down-architecture-with-information-worker-services.md)   
 [大規模な分散アーキテクチャ](../core/large-distributed-architecture.md)   
 [セキュリティで保護されたアーキテクチャの設計](../core/designing-a-secure-architecture.md)   
 [BizTalk Server のサンプル アーキテクチャ](../core/sample-biztalk-server-architectures.md)
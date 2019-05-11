---
title: 高可用性の実現 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9240e776-555c-4c38-8b59-8fef1ba6a567
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47e482709ae5a9c6b1ea67446773eaadcdc26a25
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395100"
---
# <a name="providing-high-availability"></a>高可用性の実現
高可用性を実現する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境内の各機能コンポーネントの冗長性を実装することで環境。 実行している複数のコンピューターにインストールすることで、BizTalk ホストの冗長性を実現できます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BizTalk グループで実行しているコンピューターの 1 つ以上を実行するホストのインスタンスの構成で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。 他のコンポーネントの冗長性、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]にリソースとして、コンポーネントを構成することで環境を実現できます、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]クラスター。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 内のリソースとして BizTalk ホストの構成にも対応して、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]クラスターで、特定の BizTalk アダプターの高可用性を実現するをお勧めします。  
  
 このセクションの機能コンポーネントの高可用性を実現する方法を説明します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [高 Availability2 の計画](../technical-guides/planning-for-high-availability2.md)  
  
-   [BizTalk ホストの高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)  
  
-   [データベースの高可用性](../technical-guides/high-availability-for-databases.md)  
  
-   [マスター シークレット サーバーの高可用性](../technical-guides/high-availability-for-the-master-secret-server.md)  
  
## <a name="see-also"></a>参照  
 [ディザスター リカバリー](../technical-guides/disaster-recovery.md)
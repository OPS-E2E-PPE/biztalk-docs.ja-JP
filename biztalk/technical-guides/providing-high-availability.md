---
title: 高可用性を実現して |Microsoft ドキュメント
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
ms.openlocfilehash: c4521981bc3df67553c244a55c91c1eb045c8e0d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302042"
---
# <a name="providing-high-availability"></a>高可用性を提供します。
高可用性が提供される、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境内の各機能コンポーネントの冗長性を実装することによって環境。 実行している複数のコンピューターをインストールすることで、BizTalk ホストの冗長性を実現できます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BizTalk グループとで実行しているコンピューターの 1 つ以上を実行するホストのインスタンスを構成してから、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループにします。 その他のコンポーネントの冗長性、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境でリソースとして、コンポーネントを構成することによって実現できます、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]クラスター。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]リソースとして BizTalk ホストの構成にも対応して、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]クラスターで、特定の BizTalk アダプターの高可用性を実現することをお勧めします。  
  
 このセクションの機能コンポーネントの高可用性を実現する方法について説明、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [高 Availability2 の計画](../technical-guides/planning-for-high-availability2.md)  
  
-   [BizTalk ホストの高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)  
  
-   [データベースの高可用性](../technical-guides/high-availability-for-databases.md)  
  
-   [マスター シークレット サーバーの高可用性](../technical-guides/high-availability-for-the-master-secret-server.md)  
  
## <a name="see-also"></a>参照  
 [災害復旧](../technical-guides/disaster-recovery.md)
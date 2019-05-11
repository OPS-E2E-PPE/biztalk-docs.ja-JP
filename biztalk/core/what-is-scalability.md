---
title: スケーラビリティとは何ですか。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scaling, scalability
ms.assetid: ac6acefd-864a-4f22-a136-a1951fe71e96
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46d74ed168f5dcc5a0d6d314627b6381ae5c4233
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395927"
---
# <a name="what-is-scalability"></a>スケーラビリティとは何ですか。
スケーラビリティ、ビジネス ニーズに合わせて展開するシステムの機能があります。 追加のハードウェアを追加するか、アプリケーションの大部分を変更することがなく既存のハードウェアをアップグレードすることでは、システムを拡張します。 BizTalk Server システムのコンテキストでは、スケーラビリティは、スケールとスループットのニーズの増加、待機時間の時間を短縮する必要がある場合に BizTalk の機能を指します。  
  
 BizTalk のさまざまなコンポーネントを調整して最適化した後、BizTalk コンピューター上か、メッセージ ボックス データベースのボトルネックが発生する可能性があります。 BizTalk 環境でよく発生するボトルネックの種類では、CPU、メモリ、IO、およびロックの競合のボトルネック。 ボトルネックの発生を開始するときは、ハードウェアをアップグレードするか、既存のトポロジに新しいハードウェアを追加する必要があります。 さいわい、BizTalk Server アーキテクチャを使用すると、簡単にスケール アップおよびスケール アウトできます。たとえば、グループに複数の BizTalk Server コンピューターを追加でき、余分なメッセージ ボックス データベースにも追加できます。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 層のスケール アウト](../core/scaling-out-the-biztalk-server-tier.md)   
 [SQL Server 層のスケール アウト](../core/scaling-out-the-sql-server-tier.md)   
 [BizTalk Server 層のスケール アップ](../core/scaling-up-the-biztalk-server-tier.md)   
 [SQL Server 層のスケール アップ](../core/scaling-up-the-sql-server-tier.md)   
 [受信ホスト スケール アウト](../core/scaled-out-receiving-hosts.md)   
 [スケール アウトされた処理ホスト](../core/scaled-out-processing-hosts.md)   
 [スケール アウトされた送信ホスト](../core/scaled-out-sending-hosts.md)   
 [Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)   
 [スケール アウト データベース](../core/scaled-out-databases.md)   
 [BizTalk Server データベースのクラスタリング](../core/clustering-the-biztalk-server-databases1.md)
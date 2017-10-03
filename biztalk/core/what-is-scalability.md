---
title: "スケーラビリティについて | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: scaling, scalability
ms.assetid: ac6acefd-864a-4f22-a136-a1951fe71e96
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a6208319fb8c195558101433cd1668ab0e0f064
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-scalability"></a>スケーラビリティについて
スケーラブルなシステムは必要に応じて拡張できます。 システムを拡張するということは、アプリケーションをあまり変更せずにハードウェアの追加やアップグレードを行うことです。 BizTalk Server システムでは、スケーラビリティとは、拡張によってスループットの向上や待機時間の短縮を達成できる能力を意味します。  
  
 BizTalk のさまざまなコンポーネントを調整して最適化した後でも、BizTalk コンピューターやメッセージ ボックス データベースでボトルネックが発生する可能性があります。 BizTalk 環境でよく発生するボトルネックには、CPU、メモリ、IO およびロックの競合ボトルネックがあります。 既存のトポロジでボトルネックが発生するようになったら、ハードウェアの追加やアップグレードを検討する必要があります。 さいわい、BizTalk Server はスケール アップやスケール アウトが簡単にできるアーキテクチャです。たとえば、複数の BizTalk Server コンピューターやメッセージ ボックス データベースの追加が可能です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 層のスケール アウト](../core/scaling-out-the-biztalk-server-tier.md)   
 [SQL Server 層のスケール アウト](../core/scaling-out-the-sql-server-tier.md)   
 [BizTalk Server 層のスケール アップ](../core/scaling-up-the-biztalk-server-tier.md)   
 [SQL Server 層のスケール アップ](../core/scaling-up-the-sql-server-tier.md)   
 [スケール アウト受信ホスト](../core/scaled-out-receiving-hosts.md)   
 [スケール アウトされた処理ホスト](../core/scaled-out-processing-hosts.md)   
 [スケール アウトされた送信ホスト](../core/scaled-out-sending-hosts.md)   
 [Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)   
 [スケール アウト データベース](../core/scaled-out-databases.md)   
 [BizTalk Server データベースをクラスタ リング](../core/clustering-the-biztalk-server-databases1.md)
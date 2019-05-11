---
title: エンド ツー エンドのトランザクションの追跡 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebacd2e4-6b5c-4dc4-8361-b5b77042debc
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7d19c4ce9bc30d60144ed69fc14f2323b4379d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306190"
---
# <a name="end-to-end-transaction-tracking"></a>エンド ツー エンドのトランザクション追跡
実行時環境を通過するトラフィックのフローを監視する演算子とユーザーの能力をビジネス情報の表示が関連しています。 企業は、プロセスおよび各手順を確実に収益創出に貢献するのには、再生時にシステムを流れるトランザクションを追跡できる必要があります。 AmberPoint SMS には、測定単位と Microsoft BizTalk Server でこれらのメッセージの追跡が簡単になります。 システムでは、新しいパッケージ化し、個々 のサービス コンポーネントを展開する開発者が選択した方法に準拠するように求められるのではなく、エンド ツー エンドのビジネス プロセス フローと一致する管理単位を定義することができます。 図 1 には、管理単位を定義するための画面が表示されます。  
  
 ![BizTalk の定義トランザクション](../esb-toolkit/media/ch9-biztalkdefiningtransaction.gif "Ch9 BizTalkDefiningTransaction")  
  
 **図 1**  
  
 **新しい管理単位として、トランザクションを定義します。**  
  
 トランザクションを定義した後は、ユーザーがインストルメント化でき、可視性を 1 つのサービス提供のと同じツールを使用して、各トランザクションに関連付けられているメッセージの追跡。 これらのツールでは、パフォーマンス メトリックを公開、に対するサービス レベル アグリーメント、パフォーマンスを監視、および図 2 に示すように、メッセージのログを生成できます。  
  
 ![BizTalk の監視](../esb-toolkit/media/ch9-biztalkmonitoring.gif "Ch9 BizTalkMonitoring")  
  
 **図 2**  
  
 **パイプラインのエンド ツー エンドのパフォーマンスの監視**  
  
 成功した実行時のガバナンスおよびシステムの監視の主要な要件は、例外、論理ビジネス トランザクション フローの処理が中断される可能性がありますアプリケーション エラーなどの重要なビジネス イベントの検出です。 AmberPoint SMS は、オペレーターとユーザーは、運用洞察とビジネス イベントを取得して、これらのイベントは、問題を生成したサービスに依存するすべてのコンポーネントに与える影響を監視できます。 さらに、オペレーターとユーザーことができますを迅速にトラブルシューティング システム全体の問題の根本原因を特定します。
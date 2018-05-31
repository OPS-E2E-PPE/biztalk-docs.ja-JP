---
title: エンド ツー エンドのトランザクションの追跡 |Microsoft ドキュメント
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
ms.openlocfilehash: ffa49372c54dc526f45e04317e002604ac0914d2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294114"
---
# <a name="end-to-end-transaction-tracking"></a>エンド ツー エンドのトランザクションの追跡
ビジネスの可視性は、実行時環境を通過するトラフィックのフローを監視する演算子とユーザーの機能に関連します。 企業は、プロセスと、システムを確実に収益の生成に利用できるもので自身の一部を再生するには、各ステップで経由でやり取りされるトランザクションを追跡できる必要があります。 AmberPoint SMS には、測定単位と Microsoft BizTalk Server でこれらのメッセージの追跡が簡単になります。 システムでは、新しい開発者パッケージ化し、個々 のサービス コンポーネントを展開することを選択する方法に準拠するように要求の対象ではなく、エンド ツー エンドのビジネス プロセス フローと一致する管理単位を定義することができます。 図 1 は、管理単位を定義するための画面を示しています。  
  
 ![BizTalk の定義トランザクション](../esb-toolkit/media/ch9-biztalkdefiningtransaction.gif "Ch9 BizTalkDefiningTransaction")  
  
 **図 1**  
  
 **新しい管理単位としてトランザクションを定義します。**  
  
 トランザクションを定義した後にユーザーがインストルメント化でき、可視性を 1 つのサービスを提供するのと同じツールを使用して、各トランザクションに関連付けられているメッセージの追跡します。 これらのツールでは、パフォーマンス メトリックを公開、サービス レベル契約、に対するパフォーマンスを監視、および図 2 に示すように、メッセージ ログを生成できます。  
  
 ![BizTalk の監視](../esb-toolkit/media/ch9-biztalkmonitoring.gif "Ch9 BizTalkMonitoring")  
  
 **図 2**  
  
 **パイプラインのエンド ツー エンドのパフォーマンスの監視**  
  
 正常に実行時のガバナンスおよびシステムの監視の主要な要件は、例外と、論理ビジネス トランザクション フローの処理が中断される可能性がありますアプリケーション エラーなどの重要なビジネス イベントの検出です。 AmberPoint SMS は、オペレーター、およびユーザー動作を把握し、ビジネス イベントを取得するためにし、これらのイベントが、問題を生成したサービスに依存するすべてのコンポーネントに影響を監視できます。 さらに、オペレーター、およびユーザーことができますを迅速にトラブルシューティング システム全体の問題の根本原因を特定します。
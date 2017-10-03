---
title: "SOA BizTalk の管理ポイントの概要 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d4c3a30-c50e-4c1c-9f59-d9a364078388
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60f73834a9bc02e371d4050115b1eccf5e88e02f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="overview-of-the-soa-biztalk-management-point"></a>SOA BizTalk の管理ポイントの概要
BizTalk 管理ポイントは、ネイティブ SOA サービス マネージャーとワークベンチの製品と統合されています。 一般的な Web サービスの管理ポイントとは異なりこの実装は、関連付けられている BizTalk Server として表現されている、Microsoft BizTalk Server 環境で提供されるサービスと受信場所とポートを送信します。 により、任意の性質は、受信場所と送信ポート (さまざまな BizTalk Server アダプターに対して構成されている)、これらのサービスが必ずしも、Web サービスに関連付けられていないが、それらは SOA サービス マネージャーの観点から Web サービスとして扱うことができますSOA ワークベンチです。  
  
 図 1 は、アプリケーションの例の Workbench ページを表示する SOA Service Manager の Web アプリケーションを示します。 左側のツリー ビューでは、アプリケーションと BizTalk Server 内でインストールされているサービス内を移動するユーザーと、右側のウィンドウでは、ユーザーがアプリケーションの詳細、操作、アクセス ポート、カテゴリ、ルール、および監視情報を表示します。  
  
 ![Ch9 &#45;SOAServiceManager](../esb-toolkit/media/ch9-soaservicemanager.jpg "Ch9 SOAServiceManager")  
  
 **図 1**  
  
 **ワークベンチ ページで使用可能な監視機能を示す、SOA サービス マネージャー**  
  
 すべてのアプリケーション (すべての送信ポートし、受信場所) 内の操作または特定の操作を監視します。ワークベンチの表示、選択したを通過するメッセージの一覧は、送信ポートと受信場所。 リスト内のメッセージをダブルクリックすると、ワークベンチは、(記録が有効な場合)、メッセージとそのコンテキスト プロパティの詳細を表示します。 また、そのサービスを通過リアルタイムのメッセージでは、特定のサービスとモニターを選択できます。
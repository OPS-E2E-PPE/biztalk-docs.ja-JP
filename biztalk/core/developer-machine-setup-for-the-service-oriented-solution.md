---
title: サービスの開発者のコンピューター設定指向のソリューション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- developer servers
- service solution tutorial, deployment prerequisites
- service solution tutorial, developer servers
ms.assetid: a088696f-c1ee-4578-ac02-af29b6de086b
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7a296118d9154d51ffc1dba22524a50cc7e76b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351594"
---
# <a name="developer-machine-setup-for-the-service-oriented-solution"></a>指向ソリューションのサービスの開発者のコンピュータ設定
サービス指向アーキテクチャ (SOA) は、分散システムを構築する方法です。 サービス指向ソリューションでは、クライアントが利用できる 1 つのサービスに集約できるさまざまなプロトコルを使用して複数のバックエンド システムを示します。 このソリューションでは、配信およびパフォーマンスの特性を満たすために必要なサービス レベル アグリーメントを保証するアプローチとサービスを統合します。  
  
 サービス指向ソリューションがモデルに BizTalk Server および基幹業務 (LOB) アプリケーション サーバーが接続されたサービス レベル アグリーメントによってシナリオには、サービス要求に応答する 3 秒が与えられます。 この 3 秒間のいずれかが占有されます、BizTalk Server でします。  
  
 サービス指向ソリューションの 3 つのバージョンがあります。 アダプタ、インライン、およびスタブ。 サービス指向ソリューションの 3 つのバージョンの違いの詳細については、次を参照してください。[サービス指向ソリューションを理解する](../core/understanding-the-service-oriented-solution.md)します。 開発者は、シナリオのスタブ バージョンを使用して実行中のシナリオを取得します。 このバージョンでは、実行するには、LOB バックエンド サーバーは必要ありません。 その後は、さまざまな方法のアダプターとバック エンド サーバーを統合および 1 つのサービスとして、BizTalk server を使用して応答するのにように構成シナリオのアダプター バージョンを使用できます。 BizTalk Server およびそのアダプターで誘発される待機時間を測定できます。  
  
 BizTalk server の待機時間は、そのサービスの要件を超える場合は、インストールし、SOA で行のバージョンを実行して、LOB アダプタの永続化ポイントをバイパスできます。 このバージョンは、アダプタと後続のメッセージ ボックスの永続化ポイントが原因の待機時間の投稿をバイパスします。 代わりに、インライン バージョンは、DCOM などのリモート プロシージャ コール (RPC) メカニズムによってバックエンド サーバーに直接アクセスで説明します。  
  
 メッセージ ボックスの永続化ポイントの詳細については、次を参照してください。[永続性とオーケストレーション エンジン](../core/persistence-and-the-orchestration-engine.md)します。  
  
 このデプロイ ガイドでは、インストールし、1 台のコンピューターでサービス指向ソリューションの 3 つのバージョンをテストする方法について説明します。  
  
 サービス指向ソリューションの詳細については、次を参照してください。[サービス指向ソリューションを理解する](../core/understanding-the-service-oriented-solution.md)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [サービス指向ソリューションをインストールする前に](../core/before-installing-the-service-oriented-solution.md)  
  
-   [指向ソリューションのスタブ バージョンのサービスをインストールする方法](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md)  
  
-   [指向ソリューションのインライン バージョンおよびアダプター バージョンのサービスをインストールする方法](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md)  
  
-   [指向ソリューションのサービスを実行する方法](../core/how-to-run-the-service-oriented-solution.md)
---
title: 開発者のコンピュータ設定、サービス指向ソリューション |Microsoft ドキュメント
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
ms.openlocfilehash: cb3407dbccbc4dccc902892cf04fa71991b8d93e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239458"
---
# <a name="developer-machine-setup-for-the-service-oriented-solution"></a>サービス指向ソリューションに対する開発者のコンピュータ設定
サービス指向のアーキテクチャ (SOA) は、分散システムを構築するためのアプローチです。 サービス指向ソリューションでは、クライアントで使用できる 1 つのサービスにさまざまなプロトコルを使用して複数のバックエンド システムを集計することができますを示しています。 このソリューションでは、対象となるサービス レベル契約に適した配信やパフォーマンスの特性を保証するアプローチによって、各種のサービスを統合しています。  
  
 サービス指向ソリューションは、サービス レベル契約のシナリオをモデル化しています。ソリューションに接続されている BizTalk Server および基幹業務 (LOB) アプリケーション サーバーは、3 秒以内にサービス要求に応答する必要があります。 この 3 秒間のうちの 1 秒は、BizTalk Server によって消費される場合があります。  
  
 サービス指向ソリューションの 3 つのバージョンがあります。 アダプタ、インライン、およびスタブ。 サービス指向ソリューションの 3 つのバージョンの違いの詳細については、次を参照してください。[サービス指向ソリューションを理解する](../core/understanding-the-service-oriented-solution.md)です。 開発者は、スタブ バージョンのシナリオを使用して、シナリオを実行できます。 このバージョンを実行するために LOB バックエンド サーバーは必要ありません。 このシナリオの後で、アダプタ バージョンのシナリオを利用することにより、単一のサービスである BizTalk Server から応答を行う場合、さまざまなアダプタやバックエンド サーバーをどのように統合し、構成すればよいかを学習できます。 また、BizTalk Server およびそのアダプタで発生した待機時間を測定できます。  
  
 BizTalk Server の待機時間がサービス要件を上回る場合、インライン バージョンの SOA のインストールと実行によって、LOB アダプタの永続化ポイントを無視できます。 このバージョンは、メッセージ ボックスの永続化ポイントにより、アダプタと後続の待機時間を無視します。 代わりに、このインライン バージョンは、DCOM などのリモート プロシージャ コール (RPC) を使用して、バックエンド サーバーと直接対話します。  
  
 メッセージ ボックスの永続化ポイントの詳細については、次を参照してください。[永続性と、オーケストレーション エンジン](../core/persistence-and-the-orchestration-engine.md)です。  
  
 この展開ガイドでは、単一のコンピュータにサービス指向ソリューションの 3 つのバージョンをインストールしてテストする方法について説明します。  
  
 サービス指向ソリューションの詳細については、次を参照してください。[サービス指向ソリューションを理解する](../core/understanding-the-service-oriented-solution.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [サービス指向ソリューションをインストールする前に](../core/before-installing-the-service-oriented-solution.md)  
  
-   [指向ソリューションのスタブ バージョンのサービスをインストールする方法](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md)  
  
-   [指向ソリューションのインライン バージョンおよびアダプター バージョンのサービスをインストールする方法](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md)  
  
-   [指向ソリューションのサービスを実行する方法](../core/how-to-run-the-service-oriented-solution.md)
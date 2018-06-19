---
title: 開発、サービス指向ソリューション |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tutorials, developing
- service solution tutorial, background information
- service solution tutorial, developing
- developing, tutorials
- developing, service solution tutorial
ms.assetid: 7979a05c-7fd3-4476-a623-55de8abdc493
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d8e33baa51a551d0f1f851410fda696abc96983
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239330"
---
# <a name="developing-a-service-oriented-solution"></a>指向ソリューションのサービスの開発
サービス指向ソリューションでは、Woodgrove Bank のクレジット口座残高システムを示します。 アカウントに関する情報は次の 3 つのレガシ システムから取得します。 与信限度額を提供する SAP システム、メインフレームで実行されている pending transactions システムおよび MQSeries を使用して、payment tracking システム。 残高照会の要求は、Web サービスまたは音声自動応答装置 (IVR) から取得します。 シナリオの詳細については、次を参照してください。[サービス指向ソリューションを理解する](../core/understanding-the-service-oriented-solution.md)です。  
  
 この開発者ガイドでは、Woodgrove Bank シナリオにサービス指向のアーキテクチャ ソリューションを構築するための 1 つのアプローチを提示します。 このガイドでは、業界標準のパターンで考えられるソリューションの検討から開始します。 サービス指向ソリューションのパターンについてのセクションでは、まず、パターンを BizTalk アプリケーションの適切なアイテムに変換します。 次のサービス指向ソリューションのコンポーネントについてのセクションでは、アプリケーションのさまざまな部分とその関係についてまとめます。 実装を強調表示セクションには、領域がについて説明します: など、エンタープライズ シングル サインオンを使用して — をシナリオの条件を満たすために特別な作業が必要です。 BAM の使用によるサービス指向ソリューションの監視についてのセクションでは、BAM API を使用したソリューションによる要求と結果の進行状況の追跡方法について説明します。 サービス指向ソリューションのバージョン管理についてのセクションと、サービス指向ソリューションの拡張についてのセクションでは、ソリューションの拡張および修正方法を提案します。 参照セクションでは、ソリューションのファイルとメッセージへの参照の一覧を示します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [パターンで、サービス指向ソリューション](../core/patterns-in-the-service-oriented-solution.md)  
  
-   [コンポーネントのサービス指向ソリューション](../core/components-of-the-service-oriented-solution.md)  
  
-   [指向ソリューションのサービスの実装の要点](../core/implementation-highlights-of-the-service-oriented-solution.md)  
  
-   [BAM によるソリューションを指向サービスを監視します。](../core/monitoring-the-service-oriented-solution-with-bam.md)  
  
-   [バージョン管理、サービス指向ソリューション](../core/versioning-the-service-oriented-solution.md)  
  
-   [スケーリング、サービス指向ソリューション](../core/scaling-the-service-oriented-solution.md)  
  
-   [サービス指向ソリューション リファレンス](../core/service-oriented-solution-reference.md)
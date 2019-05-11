---
title: 開発、サービス指向ソリューション |Microsoft Docs
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
ms.openlocfilehash: 62bac2f534b5f542f65b316faef7ecbad976dfee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351462"
---
# <a name="developing-a-service-oriented-solution"></a>開発、サービス指向ソリューション
サービス指向ソリューションでは、Woodgrove Bank のクレジット口座の残高システムを示します。 アカウントに関する情報は、次の 3 つのレガシ システムからは取得されます。 与信限度額を提供する SAP システム、メインフレームでは、で実行されている pending transactions システムおよび MQSeries を使用して、payment tracking システム。 残高照会の要求は、Web サービスまたは対話型音声応答 (IVR) システムによっていきます。 シナリオの詳細については、次を参照してください。[サービス指向ソリューションを理解する](../core/understanding-the-service-oriented-solution.md)します。  
  
 この開発者ガイドでは、Woodgrove bank のサービス指向アーキテクチャ ソリューションを構築するための 1 つの方法を示します。 このガイドは、業界標準のパターンで考えられるソリューションの検討から開始します。 「サービス指向ソリューションのパターン」は、そのパターンの適切な BizTalk アプリケーションのアイテムへの翻訳を開始します。 次のセクションでは、「コンポーネントのサービス指向ソリューションの」は、さまざまな部分のアプリケーションとの関係をまとめたものです。 実装が強調表示セクションには、領域がについて説明します-など、エンタープライズ シングル サインオンを使用して: シナリオの条件を満たすために特別な作業が必要です。 「BAM を使用したサービス指向ソリューションの監視」には、ソリューションで、BAM API を使用して、要求と結果の進行状況を追跡する方法について説明します。 「バージョン管理、サービス指向ソリューション」と「スケーリング サービス指向ソリューションの」セクションでは、拡張、またはソリューションを変更する方法をお勧めします。 参照セクションでは、ソリューション内のファイルを一覧表示し、メッセージへの参照を提供します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [サービス指向ソリューションのパターン](../core/patterns-in-the-service-oriented-solution.md)  
  
-   [サービス指向ソリューションのコンポーネント](../core/components-of-the-service-oriented-solution.md)  
  
-   [サービス指向ソリューションの実装の重要なポイント](../core/implementation-highlights-of-the-service-oriented-solution.md)  
  
-   [BAM によるソリューションを指向サービスを監視します。](../core/monitoring-the-service-oriented-solution-with-bam.md)  
  
-   [バージョン管理、サービス指向ソリューション](../core/versioning-the-service-oriented-solution.md)  
  
-   [スケーリング、サービス指向ソリューション](../core/scaling-the-service-oriented-solution.md)  
  
-   [サービス指向ソリューション リファレンス](../core/service-oriented-solution-reference.md)
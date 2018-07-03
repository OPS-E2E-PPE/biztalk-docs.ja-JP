---
title: BizTalk Server 2010 のパフォーマンス最適化ガイド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a56b27f-3e57-47db-a776-520f2d67d65e
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de3d6f1da478ae65d9bf7ed6862a0b13de36e288
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987051"
---
# <a name="biztalk-server-2010-performance-optimization-guide"></a>BizTalk Server 2010 のパフォーマンス最適化ガイド
Microsoft® BizTalk® Server 2010 のパフォーマンス最適化ガイドへようこそ。 BizTalk Server ソリューションのパフォーマンスを最適化するための詳細な情報を提供するには、このガイドを作成しました。 エンタープライズ アプリケーションの展開中には、完全なエンド ツー エンドのパフォーマンス テスト見過ごさします。 BizTalk Server を使用している多くの組織は、Microsoft が拡張性の高いメッセージング インフラストラクチャを構築されたことを知ることが自分のアプリケーションのパフォーマンス テストを実施ほとんどまたはまったくないの時間を費やします。 BizTalk Server アプリケーションは、カスタム ビルド コンポーネントだけでなく Microsoft によって提供される場合がありますが、多くの部分で構成されます。 Microsoft パフォーマンスにこれらのコンポーネントのあらゆる組み合わせをテストすることはできません。 したがって、完全かつ適切にアプリケーションのパフォーマンス テストを実施は、すべてのデプロイの重要なステップです。  

 このガイドでは、統合し、ベスト プラクティスと手法を BizTalk Server のパフォーマンスを最適化するために従う必要がありますの規範的なガイダンスを提供します。  

 Chm、pdf、docx フォームには、このガイドのコピーをダウンロードするには[Microsoft BizTalk Server 2010 のパフォーマンス最適化ガイド](http://go.microsoft.com/fwlink/?LinkId=210870)(http://go.microsoft.com/fwlink/?LinkId=210870)します。  

## <a name="whats-in-it"></a>これには  
 一般に、サーバーのパフォーマンスがパフォーマンスの低いコンポーネントによって決定されます-システムのボトルネック。 パフォーマンスを向上させる鍵は、ボトルネックを特定、その原因を特定し、適切な修正措置を適用できることです。  

 BizTalk Server の展開を計画するときは、このガイドを使用して、設計を支援し、環境を最適化します。 パフォーマンスの概念は、スケーラビリティの概念に関連しています。 システム コンポーネントのパフォーマンスに影響を与える要因を十分に理解した場合は、高い需要の期間をサポートするために拡大/縮小する方法でコンポーネントを配置できます。  

 このガイドでは、BizTalk Server を使用して広範なきた IT プロフェッショナルの実践的な経験に基づいて、パフォーマンスを最適化するためのガイダンスを提供します。 具体的には、このガイドには、次の 4 つの主要なセクションが含まれます。  

- **検索とボトルネックの排除**:[排除のボトルネックの検索と](../technical-guides/finding-and-eliminating-bottlenecks.md)セクションは、BizTalk Server ソリューションとする方法についての情報に関連するさまざまな種類のパフォーマンスのボトルネックをについて説明しますボトルネックを解決します。  

- **パフォーマンスを最適化する**:[のパフォーマンスの最適化](../technical-guides/optimizing-performance.md)セクションのパフォーマンスを最適化するためのガイダンスを提供する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューション。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 対象プラットフォームのパフォーマンスにパフォーマンスが密接に関連付けられている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]がインストールされています。 このセクションでは、両方のパフォーマンスを最適化するための推奨事項を提供します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プラットフォーム。  

- **BizTalk Server の運用環境をスケーリング**: [BizTalk Server の運用環境をスケーリング](../technical-guides/scaling-a-production-biztalk-server-environment.md)BizTalk 製品チームが完了した BizTalk Server のパフォーマンス テストの結果の詳細を説明します. これらのテストがスケーラビリティに重点を置いてし、追加の影響の BizTalk Server コンピューターを追加することの影響を測定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベース、および BizTalk Server コンピューターと BizTalk Server メッセージ ボックス データベースの両方をソリューションに追加することの影響同時にします。  

  - 数を増やしたときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]内のコンピューター、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ、これらのテストの 1 つだけ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベース用に構成された、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。 これらのテストを追加する影響のみに重点を置いた[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]にコンピューターを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。  

  - 数を増やしたときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]によって使用されるメッセージ ボックス データベース、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。 これらのテストを追加する影響のみに重点を置いた[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベースを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。  

  - 両方の数を増やしたときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターと[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]によって使用されるメッセージ ボックス データベース、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。 これらのテストの両方を追加する追加の影響を測定する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターと[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベースを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。  

- **BizTalk Server のパフォーマンス テスト手法**: [BizTalk Server のパフォーマンス テスト手法](../technical-guides/biztalk-server-performance-testing-methodology.md)でテストし、最適化する方法について詳細な情報を提供[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンス。 評価するときに適用される基本的なフェーズ フォーカスするパフォーマンス基準についての情報が含まれます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンス。  

## <a name="additions-to-this-version-of-the-guide"></a>このガイドのこのバージョンへの追加  
 [自動テストを容易にするために Visual Studio を使用して](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md)– Visual Studio ロード テストを実行する BizTalk Server アプリケーションのパフォーマンスを評価するの使用について説明します。  

## <a name="acknowledgments"></a>受信確認  
 ここで、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] User Education チームが BizTalk Server パフォーマンス最適化ガイドのコンテンツの適切な対処だけでなく、技術的なフィードバックを提供する次の個人の優れた貢献をいただいた確認します。  

 **作成者**  

- Tim Wieman、Microsoft  

- Paolo Salvatori、Microsoft  

- Trace Young、Microsoft  

  **レビュー担当者**  

- Tim Wieman、Microsoft  

- Paolo Salvatori、Microsoft

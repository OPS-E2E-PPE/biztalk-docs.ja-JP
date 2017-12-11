---
title: "BizTalk Server 2010 Performance Optimization Guide |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a56b27f-3e57-47db-a776-520f2d67d65e
caps.latest.revision: "31"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6a16d47f88be211b376f54d0f7116346771d136
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="biztalk-server-2010-performance-optimization-guide"></a>BizTalk Server 2010 Performance Optimization Guide
Microsoft® BizTalk® Server 2010 のパフォーマンス最適化ガイドへようこそ。 BizTalk Server ソリューションのパフォーマンスを最適化するための詳細な情報を提供するには、このガイドを作成しました。 エンタープライズ アプリケーションの展開中に頻繁に、完全エンド ツー エンドのパフォーマンスのテスト機能は見落とされがちです。 Microsoft が拡張性の高いメッセージング インフラストラクチャを構築されたことを知ること、BizTalk Server を使用している多くの組織時間をほとんどまたはまったくない独自のアプリケーションのパフォーマンスのテストを実施します。 BizTalk Server アプリケーションは、カスタム コンポーネントだけでなく Microsoft によって提供されるには、多くの部分で構成されます。 それ以外は考えられるのパフォーマンスを Microsoft がこれらのコンポーネントのあらゆる組み合わせをテストします。 そのため、完全かつ適切実施、アプリケーションのパフォーマンス テストは、任意の展開の重要な手順です。  
  
 このガイドの目的を統合し、ベスト プラクティス、および BizTalk Server のパフォーマンスを最適化するために従う必要がある手法の規範的なガイダンスを提供します。  
  
 Chm、pdf、または docx フォームでは、このガイドのコピーをダウンロードするには[Microsoft BizTalk Server 2010 Performance Optimization Guide](http://go.microsoft.com/fwlink/?LinkId=210870)(http://go.microsoft.com/fwlink/?LinkId=210870)。  
  
## <a name="whats-in-it"></a>これには  
 一般に、サーバーのパフォーマンスは、パフォーマンスの低いコンポーネントによって決定されます — ボトルネック システム内に存在します。 パフォーマンスを向上させるために、キーは、ボトルネックを特定、その原因を特定し、適切な修正措置を適用できることです。  
  
 BizTalk Server の展開を計画するときは、設計を支援し、環境を最適化するこのガイドを使用します。 パフォーマンスの概念はスケーラビリティの概念に関連しています。 システム コンポーネントのパフォーマンスに影響する要素を確実に理解した場合は、非常に混み合っての期間をサポートするために拡張できるようにコンポーネントを配置できます。  
  
 このガイドでは、BizTalk Server を使用して広範なきた IT 技術者の実践的な経験に基づいて、パフォーマンスを最適化するためのガイダンスを提供します。 具体的には、このガイドには、次の 4 つの主要なセクションが含まれています。  
  
-   **検索とボトルネックの排除**:[の検索とボトルネックの排除](../technical-guides/finding-and-eliminating-bottlenecks.md)セクションでは、BizTalk Server ソリューションとする方法についての情報に関連するさまざまな種類のパフォーマンスのボトルネックをについて説明しますボトルネックを解決します。  
  
-   **パフォーマンスを最適化する**:[のパフォーマンスの最適化](../technical-guides/optimizing-performance.md)セクションのパフォーマンスを最適化するためのガイダンスを提供する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューションです。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]基になるプラットフォームのパフォーマンスにパフォーマンスが密接[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]がインストールされています。 このセクションでは、両方のパフォーマンスを最適化するための推奨事項を説明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プラットフォームです。  
  
-   **実稼働 BizTalk Server 環境のスケーリング**:[運用 BizTalk Server 環境のスケーリング](../technical-guides/scaling-a-production-biztalk-server-environment.md)セクションでは、BizTalk 製品チームが完了した BizTalk Server のパフォーマンス テストの結果の詳細を説明します. これらのテストはスケーラビリティにフォーカスし、BizTalk Server コンピューターを追加することの影響を追加することの影響を測定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベース、および BizTalk Server コンピューターと BizTalk Server メッセージ ボックス データベースの両方をソリューションに追加することの影響同時にします。  
  
    -   数を増やすとき[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]内のコンピューター、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ、これらのテストの 1 つだけ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベース用に構成された、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。 これらのテストを追加することの影響にのみ重点を置いて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。  
  
    -   数を増やすとき[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]によって使用されるメッセージ ボックス データベース、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。 これらのテストを追加することの影響にのみ重点を置いて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベースを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。  
  
    -   両方の数を増やすとき[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターおよび[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]によって使用されるメッセージ ボックス データベース、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。 これらのテストの両方を追加する追加の影響を測定する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターおよび[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベースを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。  
  
-   **BizTalk Server のパフォーマンスのテスト方法**: [BizTalk Server のパフォーマンスのテスト方法](../technical-guides/biztalk-server-performance-testing-methodology.md)セクションでテストし、最適化する方法について詳しく説明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンス。 評価するときに適用する必要がありますのある基本的なフェーズとでフォーカスするパフォーマンスの基準に関する情報が含まれます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンス。  
  
## <a name="additions-to-this-version-of-the-guide"></a>このガイドのこのバージョンへの追加  
 [自動テストを容易にするために Visual Studio を使用して](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md)– Visual Studio ロード テストを実行する BizTalk Server アプリケーションのパフォーマンスを評価するの使用方法について説明します。  
  
## <a name="acknowledgments"></a>受信確認  
 ここで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ユーザー教育チームは、BizTalk Server Performance Optimization Guide の技術的なフィードバックとコンテンツのかなりの両方を提供する次の個人の未処理の投稿を確認する感謝します。  
  
 **作成者**  
  
-   Tim Wieman、Microsoft  
  
-   Paolo Salvatori、Microsoft  
  
-   Trace Young、Microsoft  
  
 **レビュー担当者**  
  
-   Tim Wieman、Microsoft  
  
-   Paolo Salvatori、Microsoft
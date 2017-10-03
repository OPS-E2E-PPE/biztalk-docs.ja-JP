---
title: "BAM ポータル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM portal, alerts
- activities [BAM], searching
- BAM portal
- BAM portal, features
- aggregations [BAM], BAM portal
- BAM portal, activity searches
- alerts, Alert Manager
- BAM portal, about BAM portal
- BAM, portals
- BAM portal, aggregations
ms.assetid: 593c9637-6b97-4ad8-8af7-2b49325acf10
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f86aad2a183653f00f1f7fc2533ac6956b2a85f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="bam-portal"></a>BAM ポータル
ビジネス エンド ユーザーは、BAM ポータルを使用すると、ビジネス目標に対する進捗状況を測定する主要業績評価指標 (KPI) や、ビジネス プロセスに関するその他の情報を監視できます。 また、ビジネス アナリストは、BAM ポータルを使用して監視モデルの作成を監視します。監視モデルとは、ビジネス プロセス内の表示要件の概要定義といえます。 管理者は、ビジネス プロセス管理システムの状態の監視など、さまざまな監視作業で BAM ポータルを使用します。  
  
## <a name="what-is-the-bam-portal"></a>BAM ポータルとは何ですか。  
 BAM ポータルでは、ビジネス プロセスをリアルタイムで詳しく表示できます。 これは一連の ASP.NET ページで構成される Web ベースの機能です。 BAM をカスタマイズすることにより、パフォーマンスとユーザー エクスペリエンスが向上します。  
  
## <a name="why-use-the-bam-portal"></a>BAM ポータルを使用する理由  
 BAM ポータルでは、BAM ビューに対して検索を実行したり、データを集計したり、警告を設定することができます。BAM ビューは、ビジネス データの 1 側面です。 BAM ポータルの表示により、ビジネスに必要な KPI 情報が提供されます。また、Microsoft Office Excel スプレッドシートの拡張、SQL レポートの使用、カスタム ユーザー インターフェイス (UI) の構築などの別のソリューションを実装する前に、BAM ポータルの表示を利用してビジネスの概念を実証することもできます。  
  
## <a name="bam-portal-components"></a>BAM ポータル コンポーネント  
 ここでは、BAM ポータル コンポーネントについて簡単に説明します。 より詳細な説明については、「関連項目」のトピックを参照してください。  
  
### <a name="activity-searches"></a>アクティビティの検索  
 特定の BAM アクティビティを見つけるには、BAM ポータルを使用して BAM データに対して検索を実行します。 検索句の追加や削除によって、クエリを作成します。これらの句を使用することにより、警告の通知条件に一致するアクティビティを表示することができます。  
  
 クエリは保存して再利用できます。 また、"特定の顧客からの注文書が到着したときに通知を受け取る" など、警告の基準としてクエリを使用することもできます。  
  
### <a name="aggregations"></a>集計  
 BAM ポータルでは、データのスナップショットをキャプチャし、グラフィカルなグラフや付属のピボットテーブル グラフの形式で表示できます。 このデータにより、特定のプロセスやビジネス全体の状態を確認できます。 たとえば、1 日に受け取った 1,000 件の請求書の内訳を、各請求書の現在の処理段階という観点から示す ("評価中" が 400 件、拒否が 400 件、支払済みが 100 件、"資金割当中" が 100 件など) 簡単な円グラフをユーザーが参照する場合があります。  
  
 提供されるデータを基にして、"プロセスの評価段階に達した請求書が 500 件を超えた場合に通知する" など、警告を作成する際の条件を設定することができます。  
  
### <a name="alert-manager"></a>警告マネージャー  
 BAM ポータルでは、警告の作成と既存の警告の編集用のインターフェイスを提供します。 警告では、監視する条件として、[アクティビティの検索] ページまたは [集計] ページのデータを使用します。 警告マネージャーでは、警告に関連する情報を入力できます。これらの情報には、通知先、通知方法 (電子メールなど)、他のユーザーが警告を参照およびサブスクライブできるようにするかなどの情報があります。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BAM ポータルのコンポーネント](../core/components-of-the-bam-portal.md)  
  
-   [BAM ポータルの計画](../core/planning-for-the-bam-portal.md)  
  
-   [BAM ポータルでのアクティビティの検索](../core/activity-searches-in-the-bam-portal.md)  
  
-   [BAM ポータルでの集計](../core/aggregations-in-the-bam-portal.md)  
  
-   [BAM ポータルでのアラート](../core/alerts-in-the-bam-portal.md)  
  
-   [BAM ポータルのユーザー補助機能](../core/accessibility-for-the-bam-portal.md)  
  
-   [BAM ポータルのセキュリティに関する考慮事項](../core/security-considerations-for-the-bam-portal.md)  
  
-   [BAM ポータルでの既知の問題](../core/known-issues-in-the-bam-portal.md)  
  
## <a name="see-also"></a>参照  
 [BAM ポータルにアクティビティの検索 ページ](../core/activity-search-on-the-bam-portal-page.md)   
 [BAM ポータルの集計 ページ](../core/aggregations-on-the-bam-portal-page.md)   
 [警告マネージャーで、BAM ポータル ページ](../core/alert-manager-on-the-bam-portal-page.md)
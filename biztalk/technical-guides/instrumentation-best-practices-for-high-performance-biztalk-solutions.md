---
title: "BizTalk ソリューションの高パフォーマンスのベスト プラクティスを instrumentation |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd16ea1e-055a-429b-912f-bff2b91f0fdb
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ef6f243f894071aebb0089f063ed0242ee09d9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="instrumentation-best-practices-for-high-performance-biztalk-solutions"></a>BizTalk ソリューションの高パフォーマンスのベスト プラクティスのインストルメンテーション
このホワイト ペーパーのコピーをダウンロードするには[http://go.microsoft.com/fwlink/?LinkId=205874](http://go.microsoft.com/fwlink/?LinkId=205874)です。  
  
 **公開:** 2010 年 11 月  
  
 **作成者:** Valery Mizonov、米国 Microsoft Corporation  
  
 **校閲者。**  
  
-   Mark Simms、米国 Microsoft Corporation  
  
-   Jayanthi Sampathkumar、米国 Microsoft Corporation  
  
-   Krish Srinivasan、米国 Microsoft Corporation  
  
 **適用対象:** Microsoft BizTalk Server  
  
 **概要:** BizTalk ソリューションのインストルメント化の従来の方法とは限りませんパフォーマンスの観点から最も効果的です。 一般的に使用されるインストルメンテーションとトレーシング コンポーネントのデバッグの Win32 Api を活用することは可能性があります、潜在的なボトルネックを紹介し、なるストレス条件下で実行されるマルチ スレッドの BizTalk アプリケーションのパフォーマンスの低下を担当します。  
  
 相手側からは、ソース コードのインストルメンテーションは、アプリケーションの動作に可視性のある程度の優れたは提供し、全体的なトラブルシューティングの作業の削減に役立ちます。 その結果、パフォーマンスの高い BizTalk ソリューションのインストルメント化するための根本的に新しいアプローチが重要になります重要な点を事実上オーバーヘッドなしと影響しない非割り込み型的で多機能かつ詳細な診断情報の収集を有効にするにはアプリケーションのパフォーマンスです。  
  
 [Windows Server AppFabric の Customer Advisory Team](http://blogs.msdn.com/appfabriccat) BizTalk 開発者が高パフォーマンスのインストルメンテーションとその解決策の強化に役立つ microsoft 検証済みのベスト プラクティスにコミュニティを提供する対象としています多くの Microsoft 製品によって内部的に採用します。 これらのベスト プラクティスは、BizTalk 開発者は簡単に接続して独自の実装にも適用する再利用可能なフレームワークの形式で反映されています。  
  
 完全なコピーをダウンロードする[高パフォーマンスの BizTalk ソリューションのベスト プラクティスをインストルメンテーション](http://go.microsoft.com/fwlink/?LinkId=205874)(http://go.microsoft.com/fwlink/?LinkId=205874)、Microsoft ダウンロード センターにします。
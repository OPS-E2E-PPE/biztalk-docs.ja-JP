---
title: 高パフォーマンスの BizTalk ソリューションのインストルメンテーションのベスト プラクティス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd16ea1e-055a-429b-912f-bff2b91f0fdb
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b41d67b45c8d3fa18761154e61b449fdf17df9dc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391824"
---
# <a name="instrumentation-best-practices-for-high-performance-biztalk-solutions"></a>高パフォーマンスの BizTalk ソリューションのインストルメンテーションのベスト プラクティス
このホワイト ペーパーのコピーをダウンロードするには[ http://go.microsoft.com/fwlink/?LinkId=205874](http://go.microsoft.com/fwlink/?LinkId=205874)します。  
  
 **公開日。** 2010 年 11 月  
  
 **作成者:** Valery Mizonov、Microsoft Corporation  
  
 **校閲者。**  
  
- Mark Simms、Microsoft Corporation  
  
- Jayanthi Sampathkumar、Microsoft Corporation  
  
- Krish Srinivasan、Microsoft Corporation  
  
  **適用対象します。** Microsoft BizTalk Server  
  
  **概要:** BizTalk ソリューションのインストルメント化する従来の方法常に有効ではありません、最もパフォーマンスの観点から。 一般的に使用されるインストルメンテーションとトレーシング コンポーネントのデバッグの Win32 Api を活用することは可能性があります、潜在的なボトルネックが生じるし、ストレス条件下で実行されているマルチ スレッドの BizTalk アプリケーションのパフォーマンス低下の責任になります。  
  
  相手側からソース コードのインストルメンテーションは高いアプリケーションの動作を可視化を提供し、全体的なトラブルシューティング作業を軽減します。 そのため、高パフォーマンスの BizTalk ソリューションのインストルメント化を根本的に新しいアプローチが重要な点が重要になりますほぼオーバーヘッドなしとまったく影響のない非侵入型の方法で多機能かつ詳細な診断情報の収集を有効にするにはアプリケーションのパフォーマンス。  
  
  [Windows Server AppFabric の Customer Advisory Team](http://blogs.msdn.com/appfabriccat) BizTalk 開発者の高パフォーマンスのインストルメンテーションとその解決策の強化に役立つ、検証済みのベスト プラクティスをコミュニティに提供を目的としたマイクロソフト内部的に多くの Microsoft 製品で採用しています。 BizTalk 開発者は簡単にプラグインして、独自の実装で採用する再利用可能なフレームワークのフォームには、これらのベスト プラクティスが反映されています。  
  
  完全なコピーをダウンロードする[高パフォーマンスの BizTalk ソリューションのインストルメンテーションのベスト プラクティス](http://go.microsoft.com/fwlink/?LinkId=205874)(http://go.microsoft.com/fwlink/?LinkId=205874) Microsoft ダウンロード センター。
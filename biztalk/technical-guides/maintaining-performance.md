---
title: パフォーマンスを維持する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae7e63ed-4e28-45b1-ab00-be9f9488a2e6
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da10987a6532987ff7a2ed925e717a0a713cac6e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298146"
---
# <a name="maintaining-performance"></a>パフォーマンスを維持します。
このセクションでは、定期的なメンテナンスのチェック中に検出されたパフォーマンスの問題を解決できるようにするためのものでは、情報を提供します。 ツールと重大な問題になる前に、潜在的な問題を識別する事前に、ここで説明する手法を使用することもできます。  
  
 通常、対象となる現在のシステム パフォーマンスを評価する基準としてパフォーマンス ベースラインを確立する必要があります。  
  
 このセクションのトピック、に加えては、このドキュメントでは、その他のトピックは、パフォーマンスの問題を解決します。 これらのトピックは、関連するセクションの下に表示されます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [パフォーマンスを維持するためのベスト プラクティス](../technical-guides/best-practices-for-maintaining-performance.md)  
  
-   [アダプターのパフォーマンスを向上させるためにバッチ処理の構成](../technical-guides/configuring-batching-to-improve-adapter-performance.md)  
  
-   [構成キャッシュの更新間隔を調整する方法](../technical-guides/how-to-adjust-the-configuration-cache-refresh-interval.md)  
  
-   [追跡を無効にする方法](../technical-guides/how-to-disable-tracking.md)  
  
-   [パフォーマンス Issues3 のトラブルシューティング](../technical-guides/troubleshooting-performance-issues3.md)  
  
## <a name="related-sections"></a>関連項目  
  
-   を一般に、問題のパフォーマンスの詳細についてを参照してください[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンス最適化ガイド[http://go.microsoft.com/fwlink/?LinkID=150492](http://go.microsoft.com/fwlink/?LinkID=150492)です。  
  
-   ベースラインとしきい値に対して毎週のパフォーマンス モニターのログを分析する方法については、次を参照してください[パフォーマンス分析のログ (PAL) のツールを使用して](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)、"を検索すると排除"のボトルネック、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンス。最適化ガイド[http://go.microsoft.com/fwlink/?LinkId=154675](http://go.microsoft.com/fwlink/?LinkId=154675)、および[パフォーマンス Issues3 のトラブルシューティング](../technical-guides/troubleshooting-performance-issues3.md)です。  
  
-   システムが頻繁に自動拡張の発生していないことを確認する方法についての[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを参照してください[データベースの自動拡張設定を定義する](../technical-guides/defining-auto-growth-settings-for-databases.md)、追跡データベースのサイズ変更ガイドライン」、で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]でヘルプを[http://go.microsoft.com/fwlink/?LinkId=154677](http://go.microsoft.com/fwlink/?LinkId=154677)とで「データベース層のボトルネックを識別する」、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]でヘルプを[http://go.microsoft.com/fwlink/?LinkId=154678](http://go.microsoft.com/fwlink/?LinkId=154678)です。  
  
-   SQL Server の管理に関する情報の[を実行する SQL Server のメンテナンスのプロシージャ](~/technical-guides/checklist-configuring-sql-server.md)です。  
  
-   応答時間と高いリソース使用率を確認する高負荷時に SQL Server Profiler の実行方法の詳細については、"を使用して SQL Server Profiler"SQL Server のヘルプにあるを参照してください。 [http://go.microsoft.com/fwlink/?LinkID=106720](http://go.microsoft.com/fwlink/?LinkID=106720)です。  
  
-   すべてのアダプターのメッセージのバッチ処理がリソースの消費量や待機時間の適切なことを確認する方法については、次を参照してください。[アダプターのパフォーマンスを向上させるバッチ処理構成](../technical-guides/configuring-batching-to-improve-adapter-performance.md)です。  
  
-   BizTalk Server のキャッシュ更新間隔を増やす方法については、次を参照してください。[構成キャッシュ更新間隔を調整する方法](../technical-guides/how-to-adjust-the-configuration-cache-refresh-interval.md)です。  
  
-   受信および送信ホストの制限については、「ホストの制限は何ですか?」を参照してください。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[http://go.microsoft.com/fwlink/?LinkId=154694](http://go.microsoft.com/fwlink/?LinkId=154694)です。 トリガー、アクション、および受信と送信制限の緩和方法についてを参照してください「の制限の条件の発生原因、アクション、および軽減戦略」[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[http://go.microsoft.com/fwlink/?LinkId = 154695](http://go.microsoft.com/fwlink/?LinkId=154695)です。  
  
-   パススルー送信パイプラインを使用して、既定の XML 送信パイプラインではなくを参照して「管理する送信ポートを使用して BizTalk エクスプ ローラー」[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[http://go.microsoft.com/fwlink/?LinkID=154696](http://go.microsoft.com/fwlink/?LinkID=154696)です。  
  
-   追跡データベースのサイズ変更方法の詳細については、追跡データベース サイズ ガイドライン」を参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[http://go.microsoft.com/fwlink/?LinkId=154677](http://go.microsoft.com/fwlink/?LinkId=154677)です。  
  
-   メッセージ ボックス データベース、BizTalkDTADb、BAMPrimaryImport データベースのサイズ変更方法の詳細についてを参照してください「を識別するボトルネックで、データベース層」、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[http://go.microsoft.com/fwlink/?LinkId=154678](http://go.microsoft.com/fwlink/?LinkId=154678)です。  
  
-   メッセージ ボックス データベースでの競合を回避する方法については、次を参照してください。[ディスクの競合を回避する方法](http://go.microsoft.com/fwlink/?LinkId=158809)([http://go.microsoft.com/fwlink/?LinkId=158809](http://go.microsoft.com/fwlink/?LinkId=158809)) で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンスの最適化をガイドします。
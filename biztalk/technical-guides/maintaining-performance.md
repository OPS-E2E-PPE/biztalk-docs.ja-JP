---
title: パフォーマンスの維持 |Microsoft Docs
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
ms.openlocfilehash: bdaa00ebb244db6d389393a0bbf32c0075c1f3d3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984427"
---
# <a name="maintaining-performance"></a>パフォーマンスを維持します。
このセクションでは、ものでは、定期的なメンテナンスの確認中に検出されたパフォーマンスの問題の解決に役立つ情報を提供します。 ツールとの重要な問題になる前に、潜在的な問題を識別するために事前に、ここで説明する手法を使用することもできます。  

 一般に、対象となる現在のシステムのパフォーマンスを評価するための標準としてパフォーマンス ベースラインを確立する必要があります。  

 このセクションのトピックだけでなくは、このドキュメントでその他のトピックは、パフォーマンスの問題を説明します。 これらのトピックは、関連するセクションの下に表示されます。  

## <a name="in-this-section"></a>このセクションの内容  

-   [パフォーマンスを維持するためのベスト プラクティス](../technical-guides/best-practices-for-maintaining-performance.md)  

-   [アダプターのパフォーマンスを向上するためのバッチ処理の構成](../technical-guides/configuring-batching-to-improve-adapter-performance.md)  

-   [構成キャッシュ更新間隔を調整する方法](../technical-guides/how-to-adjust-the-configuration-cache-refresh-interval.md)  

-   [追跡を無効にする方法](../technical-guides/how-to-disable-tracking.md)  

-   [パフォーマンス Issues3 のトラブルシューティング](../technical-guides/troubleshooting-performance-issues3.md)  

## <a name="related-sections"></a>関連項目  

- を一般に、問題のパフォーマンスの詳細についてを参照してください[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]でのパフォーマンス最適化ガイド[ http://go.microsoft.com/fwlink/?LinkID=150492](http://go.microsoft.com/fwlink/?LinkID=150492)します。  

- ベースラインとしきい値に対して毎週のパフォーマンス モニターのログの分析については、次を参照してください[パフォーマンス分析のログ (PAL) ツールを使用して](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)、"を検索し、を排除すること"のボトルネック、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンス。最適化ガイド[ http://go.microsoft.com/fwlink/?LinkId=154675 ](http://go.microsoft.com/fwlink/?LinkId=154675)、および[トラブルシューティング パフォーマンス Issues3](../technical-guides/troubleshooting-performance-issues3.md)します。  

- システムが頻繁に自動拡張の発生していないことを確認する方法についての[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを参照してください[データベースの自動拡張設定を定義する](../technical-guides/defining-auto-growth-settings-for-databases.md)、追跡データベースのサイズ変更ガイドライン」、で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[ http://go.microsoft.com/fwlink/?LinkId=154677](http://go.microsoft.com/fwlink/?LinkId=154677)で「データベース層のボトルネックを識別する」と、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[ http://go.microsoft.com/fwlink/?LinkId=154678](http://go.microsoft.com/fwlink/?LinkId=154678)します。  

- SQL Server の保守について[を実行する SQL Server のメンテナンスのプロシージャ](~/technical-guides/checklist-configuring-sql-server.md)します。  

- 応答時間と高いリソース使用状況を確認する高負荷時に SQL Server Profiler の実行方法の詳細については、"を使用して SQL Server Profiler"SQL Server のヘルプにあるを参照してください。 [ http://go.microsoft.com/fwlink/?LinkID=106720](http://go.microsoft.com/fwlink/?LinkID=106720)します。  

- すべてのアダプターのメッセージのバッチ処理がリソースの消費量や待機時間の適切なことを確認する方法については、次を参照してください。[アダプターのパフォーマンスを向上させるバッチ処理構成](../technical-guides/configuring-batching-to-improve-adapter-performance.md)します。  

- BizTalk Server のキャッシュ更新間隔を増やす方法については、次を参照してください。[構成キャッシュ更新間隔を調整する方法](../technical-guides/how-to-adjust-the-configuration-cache-refresh-interval.md)します。  

- 受信および送信ホストの制限については、「ホストの制限は何か」を参照してください。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[ http://go.microsoft.com/fwlink/?LinkId=154694](http://go.microsoft.com/fwlink/?LinkId=154694)します。 トリガー、アクション、および軽減戦略の受信と送信の制限についてを参照してください「の制限の条件のトリガー、アクション、および軽減戦略」[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[ http://go.microsoft.com/fwlink/?LinkId=154695](http://go.microsoft.com/fwlink/?LinkId=154695)します。  

- 既定の XML 送信パイプラインではなく、パススルー送信パイプラインを使用する「を管理する送信ポートを使用して BizTalk エクスプ ローラー」を参照してください[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[ http://go.microsoft.com/fwlink/?LinkID=154696](http://go.microsoft.com/fwlink/?LinkID=154696)します。  

- 追跡データベースのサイジングついて詳しくは、「追跡データベース サイズ変更ガイドライン」を参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[ http://go.microsoft.com/fwlink/?LinkId=154677](http://go.microsoft.com/fwlink/?LinkId=154677)します。  

- メッセージ ボックス データベース、BizTalkDTADb、BAMPrimaryImport データベースのサイジングついて詳しくは、「を識別するボトルネックで、データベース層」を参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[ http://go.microsoft.com/fwlink/?LinkId=154678](http://go.microsoft.com/fwlink/?LinkId=154678)します。  

- メッセージ ボックス データベース内での競合を避ける方法については、次を参照してください。[ディスクの競合を回避する方法](http://go.microsoft.com/fwlink/?LinkId=158809)([http://go.microsoft.com/fwlink/?LinkId=158809](http://go.microsoft.com/fwlink/?LinkId=158809)) で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンスの最適化をガイドします。

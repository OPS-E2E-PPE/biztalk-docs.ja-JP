---
title: BAM ポータルの集計ページ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], alerts
- aggregations [BAM], viewing results
- alerts, aggregations
- Aggregations page [BAM portal]
- BAM portal, aggregations
ms.assetid: 6bc1a6f2-9e9a-4db6-aaa1-188ed2f2641f
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a61df22bf5d07bd1b4d955f2baf884459de52998
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230066"
---
# <a name="aggregations-on-the-bam-portal-page"></a>BAM ポータル ページでの集計
ビジネス エンド ユーザー、開発者、およびビジネス アナリストは、集計データを提供する必要があるときに BAM ポータル ページを使用します。集計データとは、データセットを事前に計算してまとめたもので、データセットが表す特性を伝達します。 BAM ポータルの [集計] ページを使用すると、グラフィカルなグラフやピボットテーブル レポートの形式で集計データを表示できます。  
  
## <a name="the-aggregations-page"></a>[集計] ページ  
 [集計] ページでは、プロセスの状態またはビジネス全体の状態をまとめて伝達する、アクティビティの結果が表示されます。 たとえば、受け取った 1,000 件の請求書の内訳を、各請求書の処理段階という観点から示す ("評価中" が 400 件、拒否が 400 件、支払済みが 100 件、"資金割当中" が 100 件など) 簡単な円グラフをユーザーが参照する場合などに利用できます。  
  
### <a name="creating-alerts-for-aggregations"></a>集計に関する警告の作成  
 集計を基にして警告を作成できます。たとえば、プロセスの "評価" 段階に達した請求書が 500 件を超えた場合に通知するように設定できます。 これを行うには、ピボット テーブルの任意のセルを右クリックして選択**警告の設定**、セルをクリックし、をクリックするか、**警告の設定**ピボット テーブル レポートの右側にあるボタンです。 警告の作成の詳細については、次を参照してください。[警告を設定する方法](../core/how-to-set-an-alert.md)です。  
  
### <a name="viewing-individual-results-of-aggregations"></a>集計の個別の結果の表示  
 集計の数値 (たとえば、"評価中" の 400 件の請求書) を選択して、集計の個別の結果を表示することもできます。 個々 の結果にアクセスするには、ピボット テーブルの任意のセルを右クリックしを選択すると**結果の表示**です。 この操作によって、[アクティビティの検索] ページが表示されます。検索自体は自動的に構築され、その結果が表示されます (この例では、400 件の各請求書に対してレコードが 1 件ずつ表示されます)。  
  
> [!NOTE]
>  一部の BAM ビューには、集計が関連付けられていません。そのため、ビューの作成方法によっては、アクセスできる情報が存在しない場合があります。  
  
## <a name="see-also"></a>参照  
 [BAM ポータル](../core/bam-portal.md)   
 [BAM ポータルにアクティビティの検索 ページ](../core/activity-search-on-the-bam-portal-page.md)   
 [警告マネージャーで、BAM ポータル ページ](../core/alert-manager-on-the-bam-portal-page.md)
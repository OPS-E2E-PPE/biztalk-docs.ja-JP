---
title: BAM ポータルでの集計ページ |Microsoft Docs
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
ms.openlocfilehash: b5b242091e72ec4bc0ae56fdf27be5228583b7b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360157"
---
# <a name="aggregations-on-the-bam-portal-page"></a>BAM ポータルでの集計 ページ
ビジネス エンドユーザー、開発者、およびビジネス アナリストはデータ セットのデータ セットの特性を伝達事前計算済みの集計、集計のデータを提示する必要がある場合、BAM ポータル ページを使用します。 BAM ポータルの [集計] ページでは、グラフィカルなグラフとピボット テーブル レポートの形式で集計データを表示できます。  
  
## <a name="the-aggregations-page"></a>[集計] ページ  
 [集計] ページをまとめて、プロセスやビジネス全体の正常性を伝達するアクティビティの結果が表示されます。 たとえば、ユーザーは各請求書 (「評価、」400 が拒否されると、「資金割当中」で、有料と 100 の 100 件でも 400) による処理の段階に達しているの観点から受け取った 1,000 の請求書の内訳を表示する単純な円グラフを表示することがあります。  
  
### <a name="creating-alerts-for-aggregations"></a>集計に関する警告を作成します。  
 ("通知プロセスの「評価」段階に 500 件を超えた請求書がある場合)、アラートを作成するための基礎として集計を使用できます。 これを行うには、ピボット テーブルの任意のセルを右クリックして選択**警告の設定**、またはセルをクリックします をクリックして、**警告の設定**ピボット テーブル レポートの右ボタンをクリックします。 アラートの作成の詳細については、次を参照してください。[アラートを設定する方法](../core/how-to-set-an-alert.md)します。  
  
### <a name="viewing-individual-results-of-aggregations"></a>集計の個別の結果を表示します。  
 集計の数値 (「評価」の中の 400 請求など) を選択します。 また、集計の個別の結果を参照してください。 個々 の結果にアクセスするには、ピボット テーブルの任意のセルを右クリックし、選択**結果の表示**します。 この操作に応答して、アクティビティの検索ページに送信する、および検索自体は自動的に構築され、(この例では、それぞれ 400 の請求書の 1 つのレコード) では、結果が表示されます。  
  
> [!NOTE]
>  一部の BAM ビューには、それらに関連付けられている集計はありませんのでない可能性があります、ビューの作成方法によって、アクセスできる情報.  
  
## <a name="see-also"></a>参照  
 [BAM ポータル](../core/bam-portal.md)   
 [BAM ポータルのアクティビティの検索ページ](../core/activity-search-on-the-bam-portal-page.md)   
 [BAM ポータル ページの警告マネージャー](../core/alert-manager-on-the-bam-portal-page.md)
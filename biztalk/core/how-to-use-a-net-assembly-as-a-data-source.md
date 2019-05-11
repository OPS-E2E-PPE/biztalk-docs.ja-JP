---
title: データ ソースとして、.NET アセンブリを使用する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rule Composer, data sources
ms.assetid: 14dbec48-acc9-4c3c-bd7f-737dabf29543
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3308a8f292bcf28cfe9f4b6680efa9c1c7c9b595
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333611"
---
# <a name="how-to-use-a-net-assembly-as-a-data-source"></a>.NET アセンブリをデータ ソースとして使用する方法
.NET アセンブリをデータ ソースとして指定できます。 アセンブリからクラスまたはクラス メンバーを続けて選択して、ボキャブラリの定義やルール上にドラッグできます。  
  
### <a name="to-specify-a-net-assembly-as-a-data-source"></a>.NET アセンブリをデータ ソースとして指定するには  
  
1.  [ファクト エクスプ ローラー] ウィンドウ、 **.NET クラス**タブです。  
  
2.  右クリックし、**モジュール**ノード。  
  
3.  使用できるアセンブリから、.NET アセンブリを選択します。  
  
    > [!NOTE]
    >  アセンブリは、グローバル アセンブリ キャッシュ (GAC) 内に格納されている必要があります。 ビジネス ルール作成ツールは、.NET アセンブリで参照するときに .NET アセンブリを読み込みます、**ファクト エクスプ ローラー**ウィンドウまたは、 **.NET クラスまたはクラス メンバーの定義**のページ、**ボキャブラリ定義**ウィンドウです。  GAC でアセンブリを更新した場合は、ビジネス ルール作成ツールを終了してから再起動し、更新した .NET アセンブリを読み込みます。 ビジネス ルール作成ツールでは、アセンブリが自動更新されません。  
  
     ![ファクトと定義ツリー ブラウザーのスクリーン ショット。](../core/media/ebiz-netbrowse.gif "ebiz_netbrowse")
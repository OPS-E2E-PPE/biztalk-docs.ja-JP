---
title: マップの Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functoids
- functoids, about functoids
- functoid types, Record Count
- functoid types, Looping
- Looping functoids
- functoids, categories
- functoid types, Addition
- Record Count functoids
ms.assetid: 10ee8b62-cb20-4d26-9d86-b6564f30c297
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45e066b759db92db1f51db81dc98816c3f757654
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387825"
---
# <a name="functoids-in-maps"></a>マップの Functoid
BizTalk マッパーでは、レコードおよび送信先スキーマのフィールドへの送信元スキーマのレコードやフィールドから複雑な構造の変換をサポートします。 Functoid は、定義済みの数式および引数と呼ばれる特定の値を使用して計算を実行します。 これらの計算は、レコードおよびフィールドの指定された順序に基づいて実行されます。  
  
 ツールボックスから functoid を選択すると、グリッド ページにドラッグすること、および送信元スキーマおよび送信先スキーマ内のノードにリンクすることによってデータを同時に追加できる、日付または時刻の情報を変更できます。、データの連結、またはその他の操作を指定できます。実行されます。 など、**加算**functoid には、値が追加され、**レコード カウント**functoid が、インスタンス メッセージ内のループ レコードの合計数を返します。 ツールボックスで検索できる functoid のカテゴリは次のとおりです。高度な変換、累積的なデータベース、日付/時刻、数学、科学、論理と文字列します。  
  
> [!NOTE]
>  すべての functoid はインラインC#データベース functoid を除く。  
  
> [!NOTE]
>  送信先スキーマ ノードは、例外として、functoid からの入力を 1 つだけを受け入れる、**ループ**functoid。  
  
 このセクションのトピックでは、BizTalk Server の以前のバージョンから functoid を移行する方法、functoid には、実行こと、およびその使用方法について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Functoid カテゴリ](../core/functoid-categories.md)  
  
-   [Functoid 入力パラメーター](../core/functoid-input-parameters.md)  
  
-   [基本 Functoid](../core/basic-functoids.md)  
  
-   [高度な Functoid](../core/advanced-functoids.md)  
  
-   [カスケード Functoid](../core/cascading-functoids.md)  
  
-   [Functoid のプロパティ](../core/functoid-properties.md)  
  
-   [Functoid の移行](../core/migrating-functoids.md)
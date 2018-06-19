---
title: マップの Functoid |Microsoft ドキュメント
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
ms.openlocfilehash: 976af2faed27e6cae8a57d9c7c83308d0519d81d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246042"
---
# <a name="functoids-in-maps"></a>マップの Functoid
BizTalk マッパーでは、送信元スキーマのレコードやフィールドから、送信先スキーマのレコードやフィールドへの複雑な構造の変換がサポートされます。 Functoid では、定義済みの数式、および引数と呼ばれる特定の値を使用して計算を実行します。 これらの計算は、レコードおよびフィールドの指定された順序に基づいて実行されます。  
  
 ツールボックスから Functoid を選択し、グリッド ページにドラッグして、送信元スキーマや送信先スキーマのノードにリンクすると、データの統合、日付または時間情報の変更、データの連結などの操作を実行できます。 たとえば、**加算**functoid は、値を追加および**レコード カウント**functoid がインスタンス メッセージ内のループ レコードの合計数を返します。 ツールボックスに functoid のカテゴリが含まれます: 強化、変換、累積、データベース、日付/時刻、論理、数値演算、指数、および文字列。  
  
> [!NOTE]
>  データベース Functoid を除くすべての Functoid はインライン C# です。  
  
> [!NOTE]
>  送信先スキーマ ノードの例外を除いて、functoid からの入力を 1 つだけを受け入れる、**ループ**functoid です。  
  
 このセクションのトピックでは、BizTalk Server の前のバージョンから Functoid を移行する方法、Functoid の説明、Functoid で実行できること、および使用方法について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Functoid カテゴリ](../core/functoid-categories.md)  
  
-   [Functoid 入力パラメーター](../core/functoid-input-parameters.md)  
  
-   [基本 Functoid](../core/basic-functoids.md)  
  
-   [高度な Functoid](../core/advanced-functoids.md)  
  
-   [カスケード Functoid](../core/cascading-functoids.md)  
  
-   [Functoid のプロパティ](../core/functoid-properties.md)  
  
-   [Functoid の移行](../core/migrating-functoids.md)
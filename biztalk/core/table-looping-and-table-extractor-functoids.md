---
title: ループをテーブルし、テーブル抽出 Functoid |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2907aada-f11a-485c-85c8-03092803ccf7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02d4433255ac00d51c88b45bd1a2b5205bd1c735
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278362"
---
# <a name="table-looping-and-table-extractor-functoids"></a>テーブル ループ functoid とテーブル抽出 Functoid

## <a name="overview"></a>概要
マップでは、入力インスタンス メッセージの各構造に対し、通常、出力インスタンス メッセージの単一の構造を使用します。 ただし、入力インスタンス構造で複数の出力インスタンス構造を生成することが必要な場合もあります。 テーブルドリブン ループを使用すると、このような複数の構造を生成するマップを作成できます。  
  
 テーブルドリブン ループでは、**テーブル ループ**functoid および**テーブル抽出**functoid です。 **テーブル ループ**functoid が構成する内部テーブルです。 各入力レコードまたはフィールドの**テーブル ループ**functoid は一度に 1 つずつ、テーブルの行を出力します。 たとえば、入力インスタンス メッセージに 10 個のレコードと 2 つの内部テーブルの行がある場合、**テーブル ループ**functoid は、合計 2 つの 10 個のレコードのそれぞれの 20 個の行を出力します。 **テーブル抽出**functoid が行から目的の項目を抽出し、出力インスタンス メッセージに渡します。  
  
 詳細については、次を参照してください。、**テーブル ループ Functoid のリファレンス**と**テーブル抽出 Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
## <a name="next-steps"></a>次の手順
  
-   [テーブル ループ Functoid](../core/table-looping-functoid.md)  
  
-   [テーブル抽出 Functoid](../core/table-extractor-functoid.md)  
  
-   [テーブルドリブン ループの構成](../core/table-driven-looping-configuration.md)  
  
-   [テーブルドリブン ループの例](../core/table-driven-looping-example.md)
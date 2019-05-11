---
title: テーブル ループおよびテーブル抽出 Functoid |Microsoft Docs
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
ms.openlocfilehash: fe6660e5fbfb226ff49c394ee83d7205bd6e2dca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291640"
---
# <a name="table-looping-and-table-extractor-functoids"></a>テーブル ループ functoid およびテーブル抽出 Functoid

## <a name="overview"></a>概要
マップでは、一般的な入力インスタンス メッセージ内の各構造の出力インスタンス メッセージ内の 1 つの構造をあります。 ただしがあります複数の出力インスタンス構造を生成するために、入力インスタンス構造を作成する必要があります。 テーブルドリブン ループでは、このような複数の構造を生成するマップを作成することができます。  
  
 テーブル ドリブン ループでは、**テーブル ループ**functoid と**テーブル抽出**functoid。 **テーブル ループ**functoid が、内部テーブルを構成します。 各入力レコードまたはフィールドを**テーブル ループ**functoid は、一度に 1 つずつと、テーブルの行を出力します。 たとえば、入力インスタンス メッセージに 10 個のレコードと 2 つの内部テーブルの行がある場合、**テーブル ループ**functoid の出力で 2 つの 10 個のレコードごとに 20 行の合計。 **テーブル抽出**functoid が行から目的の項目を抽出し、出力インスタンス メッセージに渡します。  
  
 詳細については、次を参照してください。、**テーブル ループ Functoid のリファレンス**と**テーブル抽出 Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
  
## <a name="next-steps"></a>次のステップ
  
-   [テーブル ループ Functoid](../core/table-looping-functoid.md)  
  
-   [テーブル抽出 Functoid](../core/table-extractor-functoid.md)  
  
-   [テーブルドリブン ループの構成](../core/table-driven-looping-configuration.md)  
  
-   [テーブルドリブン ループの例](../core/table-driven-looping-example.md)
---
title: Functoid の詳細 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82bf2547-5e44-45f8-b577-97e5760a0339
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0e906b7e1c4d7ca71f952441cd22542e9637399
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360503"
---
# <a name="advanced-functoids"></a>高度な Functoid

## <a name="overview"></a>概要
高度な functoid は、使用目的に応じて、5 つのグループに分類されます。  
  
-   **ループ レコードを管理します。** **インデックス**、**イテレーション**、**ループ**、 **Nil 値**、**レコード カウント**、**テーブルエクス トラクター**、および**テーブル ループ**入力インスタンス メッセージには、予期できないいくつかのセクションが含まれている場合、さまざまな組み合わせで functoid が使用される繰り返し出現する要素、ループで表される数送信元スキーマ内のレコード。  
  
-   **条件付きのマッピング。** **値のマッピング**と**値のマッピング (フラット化)** functoid を使用して、入力インスタンス メッセージから出力インスタンス メッセージへの条件付きのマッピングを提供します。 2 番目の入力パラメーターが指定した要素または属性を出力インスタンス メッセージ内に配置されている最初の入力パラメーターが true の場合それ以外の場合、その要素または属性は、出力インスタンス メッセージでは作成されません。  
  
-   **任意のスクリプト。** **Scripting** functoid は、任意のスクリプトを実行するために使用または入力インスタンス メッセージを出力インスタンス メッセージにマップされているときにコードをコンパイルします。 送信元インスタンス メッセージの別の functoid、またはその組み合わせの出力から、構成された定数値から、入力パラメーターを受け入れるように、このようなスクリプトまたはコンパイル済みコードを作成できます。  
  
-   **単純なマッピング。** **一括コピー**出力インスタンス メッセージに入力インスタンス メッセージから任意の深さをそのサブ要素を含む要素全体をコピーする functoid を使用できます。  
  
-   **トラブルシューティング**します。 **Assert** functoid を使用して要素の値に関する仮定をテストできます。  
  
## <a name="available-functoids"></a>使用可能な functoid
  
 **詳細**functoid には。 

* アサート Functoid
* インデックス Functoid 
* 繰り返し Functoid 
* ループ Functoid 
* 一括コピー Functoid 
* Nil 値 Functoid
* レコード カウント Functoid 
* スクリプト Functoid 
* テーブル ループ functoid およびテーブル抽出 Functoid
* 値のマッピング Functoid
* 値のマッピング (フラット化) Functoid

これらの functoid について詳しくは、 **Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
  
## <a name="next-steps"></a>次のステップ
  
-   [アサート Functoid](../core/assert-functoid.md)  
  
-   [インデックス Functoid](../core/index-functoid.md)  
  
-   [繰り返し Functoid](../core/iteration-functoid.md)  
  
-   [ループ Functoid](../core/looping-functoid.md)  
  
-   [一括コピー Functoid](../core/mass-copy-functoid.md)  
  
-   [Nil 値 Functoid](../core/nil-value-functoid.md)  
  
-   [レコード カウント Functoid](../core/record-count-functoid.md)  
  
-   [テーブル ループ Functoid とテーブル抽出 Functoid](../core/table-looping-and-table-extractor-functoids.md)  
  
-   [値のマッピング Functoid](../core/value-mapping-functoid.md)  
  
-   [値のマッピング (フラット化) Functoid](../core/value-mapping-flattening-functoid.md)  
  
-   [スクリプト Functoid](../core/scripting-functoid.md)
---
title: Functoid の詳細 |Microsoft ドキュメント
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
ms.openlocfilehash: 5002b639df79ece1019c2d013c128f615517ae5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230394"
---
# <a name="advanced-functoids"></a>高度な Functoid

## <a name="overview"></a>概要
高度な Functoid は、使用目的に応じて次の 5 つのグループに分類されます。  
  
-   **ループ レコードを管理します。** **インデックス**、**イテレーション**、**ループ**、 **Nil 値**、**レコード カウント**、**テーブル抽出**、および**テーブル ループ**入力インスタンス メッセージを含むセクションが不明な場合に、さまざまな組み合わせで functoid が使用される繰り返し出現する要素、ループで表される数送信元スキーマのレコードです。  
  
-   **条件付きのマッピング。** **値のマッピング**と**値のマッピング (フラット化)** functoid は、入力インスタンス メッセージから出力インスタンス メッセージへの条件付きのマッピングを提供するために使用します。 最初の入力パラメーターが true の場合、2 番目の入力パラメーターは、出力インスタンス メッセージの指定された要素または属性に配置されます。それ以外の場合、この要素または属性は、出力インスタンス メッセージに作成されません。  
  
-   **任意のスクリプト。** **スクリプト**functoid は、任意のスクリプトを実行するために使用または入力インスタンス メッセージは、出力インスタンス メッセージにマップされているときにコードをコンパイルします。 このようなスクリプトまたはコンパイル済みコードを作成し、送信元インスタンス メッセージ、構成された定数値、別の Functoid の出力、またはこれらの組み合わせから、入力パラメーターを受け取ることができます。  
  
-   **単純なマッピング。** **一括コピー**出力インスタンス メッセージに入力インスタンス メッセージから任意の深さにサブ要素を含む、要素全体をコピーする functoid を使用できます。  
  
-   **トラブルシューティング**です。 **Assert** functoid を使用して要素の値に関する仮定をテストできます。  
  
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
* テーブル ループ functoid とテーブル抽出 Functoid
* 値のマッピング Functoid
* 値のマッピング (フラット化) Functoid

これらの functoid の詳細については、 **Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
## <a name="next-steps"></a>次の手順
  
-   [アサート Functoid](../core/assert-functoid.md)  
  
-   [インデックス Functoid](../core/index-functoid.md)  
  
-   [繰り返し Functoid](../core/iteration-functoid.md)  
  
-   [ループ Functoid](../core/looping-functoid.md)  
  
-   [一括コピー Functoid](../core/mass-copy-functoid.md)  
  
-   [Nil 値 Functoid](../core/nil-value-functoid.md)  
  
-   [レコード カウント Functoid](../core/record-count-functoid.md)  
  
-   [テーブル ループ functoid とテーブル抽出 Functoid](../core/table-looping-and-table-extractor-functoids.md)  
  
-   [値のマッピング Functoid](../core/value-mapping-functoid.md)  
  
-   [値のマッピング (フラット化) Functoid](../core/value-mapping-flattening-functoid.md)  
  
-   [スクリプト Functoid](../core/scripting-functoid.md)
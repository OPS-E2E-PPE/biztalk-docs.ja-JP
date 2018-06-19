---
title: 区切られたレコード内の最小フィールド長 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24272d0d-34c8-487a-9334-683c65c159b8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d803eb311bda7c27db5a05830f7a84f9b9857e8f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263642"
---
# <a name="minimum-field-lengths-within-delimited-records"></a>区切られたレコード内の最小フィールド長
位置指定レコードの定義では、すべてのフィールドは、特定の厳密な長さに定義されます。 区切られたレコードでは、レコードのフィールドに対して最小のフィールド長を定義できます。 この特性がによって定義された、 **[埋め込み文字を含めた最小の長さ**プロパティの**フィールド要素**と**フィールド属性**ノード。  
  
 以外の値を指定すると、**埋め込み文字を含めた最小の長さ**プロパティ、フラット ファイル アセンブラーがかどうかをフィールドに関連付けられているデータの文字の数、の設定よりも小さい**埋め込み文字を含めた最小の長さ**プロパティの違いは、構成に使用する埋め込み文字。  
  
 設定に基づいて、データ文字の前後に埋め込み文字が追加されます、 **Justification**フィールドのプロパティです。 ときに、 **Justification**プロパティに設定されている**左**を最小の長さを満たすために必要な埋め込み文字は、データ文字の後に追加されます。 ときに、 **Justification**プロパティに設定されている**右**を最小の長さを満たすために必要な埋め込み文字は、データ文字の前に追加されます。  
  
 以外の値を指定すると、**埋め込み文字を含めた最小の長さ**プロパティ、フラット ファイル逆アセンブラーは、先頭または末尾を調べます (の設定に基づいて、 **Justification**プロパティ) のフィールド値の適切な埋め込み文字の存在と存在する場合、埋め込み文字は破棄され、構築される同等の XML メッセージに表示されません。  
  
## <a name="see-also"></a>参照  
-  [フィールドに関する考慮事項](../core/field-considerations.md)   
-  **位置揃え (フラット ファイル スキーマのノード プロパティ)** と**埋め込み文字 (フラット ファイル スキーマのノード プロパティ) を含めた最小長**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
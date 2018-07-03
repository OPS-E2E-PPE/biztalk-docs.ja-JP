---
title: 区切られたレコード内の最小フィールド長 |Microsoft Docs
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
ms.openlocfilehash: 992ffbc6a2e0568bc000413bf90b3c92012d4d59
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983315"
---
# <a name="minimum-field-lengths-within-delimited-records"></a>区切られたレコード内の最小フィールド長
位置指定レコードの定義では、すべてのフィールドは、特定の厳密な長さに定義されます。 区切られたレコードでは、レコードのフィールドに対して最小のフィールド長を定義できます。 このような特性がによって定義されている、 **[埋め込み文字を含めた最小値**プロパティの**フィールド要素**と**フィールド属性**ノード。  

 0 以外の値を指定すると、**埋め込み文字を含めた最小値**プロパティ、フラット ファイル アセンブラーがかどうかをフィールドに関連付けられたデータの文字の数、の設定よりも小さい**埋め込み文字を含めた最小値**プロパティ、違いは、構成に関連する埋め込み文字が使用されます。  

 前に、または後の設定に基づいてデータの文字に埋め込み文字が追加、 **Justification**フィールドのプロパティ。 ときに、 **Justification**プロパティに設定されて**左**、最小の長さを満たすために必要な埋め込み文字は、データ文字後に追加されます。 ときに、 **Justification**プロパティに設定されて**右**、最小の長さを満たすために必要な埋め込み文字は、データ文字の前に追加されます。  

 0 以外の値を指定すると、**埋め込み文字を含めた最小値**プロパティ、フラット ファイル逆アセンブラーは、先頭または末尾が確認されます (の設定に基づいて、 **Justification**プロパティ) のフィールドの値、適切な埋め込み文字の存在と存在する場合、埋め込み文字は破棄され、構築される同等の XML メッセージに表示されません。  

## <a name="see-also"></a>参照  
- [フィールドに関する注意](../core/field-considerations.md)   
- **位置揃え (フラット ファイル スキーマのノード プロパティ)** と**埋め込み文字 (フラット ファイル スキーマのノード プロパティ) を含めた最小値** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]

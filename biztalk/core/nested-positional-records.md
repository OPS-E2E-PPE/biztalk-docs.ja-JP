---
title: 位置指定レコードを入れ子になった |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e205e9d-f740-4177-b45a-5e1baadae99a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d0eddb7925a34e79c1da45a6ec6e2670f9632695
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323623"
---
# <a name="nested-positional-records"></a>入れ子になった位置指定レコード
入れ子になった位置指定レコードは許可されている場合、 **Max Occurs**子レコードのプロパティが正の整数に設定します。 フィールドの自動計算は、新しい深さを処理できる必要があります。 ただし、この動作は方法が変更されます。 具体的には、区切り記号が null の可能性をフィールド位置の自動計算が、次の条件のいずれかが満たされた場合にのみ機能します。  
  
- 選択したノードには、区切られた挿入辞である親があります。  
  
- 選択したノードには、指定された開始位置があります。  
  
  入れ子になった位置指定レコードと位置指定レコードの親は、区切り記号が null で区切られたコンテナーとの間の違いがあることに注意してください。 構造を位置に、入れ子にする真にあってはいけません。 あいまいさの長さを決定します。 たとえば、区切られたループ ノードは、0 ~ N 個に発生する繰り返しの位置指定レコードを含めることができます。 ただし、ループ ノード自体としてフィールドを含むと位置を指定すると、ピアに繰り返しの位置指定レコード内で見つかったの繰り返しの位置指定レコードは、決定的である必要があります (正の整数)。  
  
## <a name="see-also"></a>参照  
 [位置指定レコードに関する注意](../core/positional-record-considerations.md)
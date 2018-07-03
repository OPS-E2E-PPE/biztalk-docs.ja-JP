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
ms.openlocfilehash: 618d5475842a9e5844f289a7ca77e4d9a725b130
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990219"
---
# <a name="nested-positional-records"></a>入れ子になった位置指定レコード
入れ子になった位置指定レコードは許可されている場合、 **Max Occurs**子レコードのプロパティが正の整数に設定します。 フィールドの自動計算で、新しい深さを処理できることが必要となります。 ただし、この動作が正しく行われるためには、いくつかの条件があります。 特に、区切り記号が null である可能性があるため、フィールド位置の自動計算は、次のいずれかの条件が満たされた場合にしか機能しません。  
  
- 選択されたノードに、挿入辞で区切られた親が存在する。  
  
- 選択されたノードに、開始位置が指定されている。  
  
  入れ子になった位置指定レコードは、親が null で区切られたコンテナーとなっている位置指定レコードとは異なる点に注意してください。 構造を位置に基づいて入れ子にする場合、長さを判断するときに、あいまいさは許可されません。 たとえば、区切り記号付きのループ ノードは、0 ～ N 個の連続して出現する位置指定レコードを含むことができます。 しかし、ループ ノード自体を位置指定レコードとし、連続する位置指定レコードのピアとしてフィールドを含むためには、連続する位置指定レコードの出現回数 (正の整数) が確定している必要があります。  
  
## <a name="see-also"></a>参照  
 [位置指定レコードに関する注意](../core/positional-record-considerations.md)
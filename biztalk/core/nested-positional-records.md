---
title: 位置指定レコードを入れ子になった |Microsoft ドキュメント
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
ms.openlocfilehash: c278d3ac794c560d8cd886605c1d04c097793564
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263242"
---
# <a name="nested-positional-records"></a>入れ子になった位置指定レコード
入れ子になった位置指定レコードは許可されている場合、 **Max Occurs**子レコードのプロパティは、正の整数に設定されています。 フィールドの自動計算で、新しい深さを処理できることが必要となります。 ただし、この動作が正しく行われるためには、いくつかの条件があります。 特に、区切り記号が null である可能性があるため、フィールド位置の自動計算は、次のいずれかの条件が満たされた場合にしか機能しません。  
  
-   選択されたノードに、挿入辞で区切られた親が存在する。  
  
-   選択されたノードに、開始位置が指定されている。  
  
 入れ子になった位置指定レコードは、親が null で区切られたコンテナーとなっている位置指定レコードとは異なる点に注意してください。 構造を位置に基づいて入れ子にする場合、長さを判断するときに、あいまいさは許可されません。 たとえば、区切り記号付きのループ ノードは、0 ～ N 個の連続して出現する位置指定レコードを含むことができます。 しかし、ループ ノード自体を位置指定レコードとし、連続する位置指定レコードのピアとしてフィールドを含むためには、連続する位置指定レコードの出現回数 (正の整数) が確定している必要があります。  
  
## <a name="see-also"></a>参照  
 [位置指定レコードに関する注意点](../core/positional-record-considerations.md)
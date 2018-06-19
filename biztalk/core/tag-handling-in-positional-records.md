---
title: 位置指定レコードの処理をタグ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c85d695-6dc9-4200-a453-dc576832adca
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 804647b3cf43b9b6747b2e5f50e05e38313b03d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278570"
---
# <a name="tag-handling-in-positional-records"></a>位置指定レコードのタグ処理

## <a name="overview"></a>概要
位置指定レコードには、特定のタイプのレコードを明確に区別するための、事前に定義された文字列 (タグなど) が含まれています。 これにより、適切なを正しく識別するフラット ファイル逆アセンブラー**レコード**フラット ファイル レコードを正しく解析に必要な情報を含むスキーマのノードです。  
  
 使用することができます、 **[タグ識別子**と**タグ オフセット**プロパティ、タグと位置指定レコード内の位置を指定するためにします。 これにより、タグ内に発生する任意の場所と、位置指定レコードの設定によって、ことに注意してください、**位置指定値**と**位置指定オフセット**内でさまざまなフィールドのプロパティレコードのタグは、1 つに関連付けられているデータの一部として解釈できるまたはこれらのフィールドです。  
  
 **位置指定オフセット**プロパティでは、レコード内のデータからタグを個別に処理することもできます。 たとえば、タグがレコードの先頭に、4 文字の長さの場合は、値を設定でした、**位置指定オフセット**4、これにより効率的にスキップするレコードの最初のフィールドのプロパティ、最初のフィールドの値は、レコードの同等の XML 形式に変換するときにタグを位置指定レコード。  

これらのプロパティの詳細について[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。 
  
## <a name="see-also"></a>参照  
 [位置指定レコードに関する注意点](../core/positional-record-considerations.md)   

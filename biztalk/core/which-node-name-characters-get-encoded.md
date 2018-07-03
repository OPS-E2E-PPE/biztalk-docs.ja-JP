---
title: ノード名における文字エン コードが |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48a581d2-48fa-4c36-b5c2-fe87c328a7f4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b72c7bb1eb05e8bb8ce8c0596cbacc88cb3d2f0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022072"
---
# <a name="which-node-name-characters-get-encoded"></a>ノード名における文字エンコード
XML には、XML 名の先頭文字に対する特殊な制約も含め、要素名などの XML 名に使用できる文字に制限があります。 どのような文字を使用でき、また、どのような文字を使用すべきでないかというガイドラインを次に示します。  
  
- 新しい書記体系に対応できるよう、できるだけ汎用性の高い文字 (つまり、Unicode にエンコード可能な文字) を使用する。  
  
- 区切り記号として使われる可能性のある文字は使用しない。区切り記号が使用された、XML 以外のコンテキストに XML 名が表示されることも考慮する。  
  
  次の表は、XML 名として使用できる文字を示しています。任意の位置で使用できる文字と、先頭以外のすべての位置で使用できる文字とに分類されています。 名前の先頭文字としては使用できないが、他の位置であれば使用できる文字もあるためです。 リテラル文字は引用符で囲み、文字の範囲は角かっこで示しています。  
  
|名前における位置|使用可能な文字|  
|----------------------|------------------------|  
|任意の位置|["A"-"Z"]、["a"-"z"]、"_"、[0x00C0-0x02FF]、[0x0370-0x037D]、[0x037F-0x1FFF]、[0x200C-0x200D]、[0x2070-0x218F]、[0x2C00-0x2FEF]、[0x3001-0xD7FF]、[0xF900-0xEFFF]|  
|先頭を除く任意の位置|"-"、"."、["0"-"9"]、0x00B7、[0x0300-0x036F]、[0x203F-0x2040]|  
  
 英語の要素名または属性名 (スキーマ ツリー ビューでのノード名) を使用する場合のベスト プラクティスを次に示します。  
  
-   英数字文字を使用する。ただし、先頭に数値は使用しない。  
  
-   アンダー スコア (_)、ハイフン (-)、ピリオド (.)、および中間点 (押し) を使用します。  
  
-   スペースは使用しない。  
  
-   意味を把握しやすい単語または単語の組み合わせを使用する。  
  
## <a name="see-also"></a>参照  
 [ノード名プロパティ](../core/node-name-property.md)   
 [ノード名の文字エンコードの方法](../core/how-node-name-characters-get-encoded.md)
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
ms.openlocfilehash: 810476ccd640b33ecf5996bc351947a8bceb0ad4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394791"
---
# <a name="which-node-name-characters-get-encoded"></a>ノード名における文字エン コード
XML は、いくつかの制限をいくつかの特別な XML 名の最初の文字制限など、要素名などの XML 名に使用できる文字に配置します。 どの文字を許可して有効な XML 名から除外する文字の決定に使用すべき次のとおりです。  
  
- 可能な場合は、新しい書記を確保できるように Unicode でエンコードされているように、排他的ではなく包括的に。  
  
- XML 名は、XML、以外でより簡単に表示されます。 コンテキストを区切られるようにすることがありますまたは区切り記号として使用される文字を除外します。  
  
  次の表は、どの文字を任意の位置は、名前または任意の位置、先頭以外で XML 名で使用することができます。 いくつか使用できる文字は、名前の最初の文字の中から除外されます。 リテラル文字が引用符で囲まれたと範囲は角かっこ内に表示します。  
  
|名前における位置|許可されている文字|  
|----------------------|------------------------|  
|任意の位置|["A"、"Z"]、["a"、"z"]、「_」、0x00C0-0x02FF、0x0370-0x037D、0x037F-0x1FFF、0x200C-0x200D、0x2070-0x218F、0x2C00-0x2FEF、[0x3001 0xD7FF]、[0xF900 0 xefff]|  
|先頭を除く任意の位置|"-"、"."、[「0」-「9」]、0x00B7、[0x0300-0x036F]、[0x203f-0x2040]|  
  
 として英語での要素または属性名 (スキーマ ツリー ビューでノード名) のベスト プラクティスをまとめることができます。  
  
-   点を除いては、英数字を使用していない名前に数値を開始します。  
  
-   アンダー スコア (_)、ハイフン (-)、ピリオド (.)、および中間点 (押し) を使用します。  
  
-   空白文字は使用しないでください。  
  
-   自然言語で意味のある単語または単語の組み合わせを使用します。  
  
## <a name="see-also"></a>参照  
 [ノード名プロパティ](../core/node-name-property.md)   
 [ノード名の文字エンコードの方法](../core/how-node-name-characters-get-encoded.md)
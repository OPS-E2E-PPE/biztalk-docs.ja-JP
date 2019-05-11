---
title: 位置指定レコードの処理をタグ付け |Microsoft Docs
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
ms.openlocfilehash: 8fe1ec096926dc8737c6657ca99fb3cb90b59673
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291626"
---
# <a name="tag-handling-in-positional-records"></a>タグは位置指定レコードの処理

## <a name="overview"></a>概要
位置指定レコードには、よく知られているから別のレコードの種類を 1 つのあいまいさを解消するために使用すると、タグと呼ばれる文字のシーケンスを含めることができます。 これにより、適切なを正しく識別するためにフラット ファイル逆アセンブラー**レコード**フラット ファイル レコードを正しく解析に必要な情報を含むスキーマのノード。  
  
 使用することができます、 **[タグ識別子**と**タグ オフセット**プロパティ、タグと位置指定レコード内の位置を指定するためにします。 これにより、タグの設定によって、位置指定レコードと内で発生することに注意してください、**位置指定値**と**位置指定オフセット**内のさまざまなフィールドのプロパティレコードのタグは、1 つに関連付けられているデータの一部として解釈できるまたはこれらのフィールドします。  
  
 **位置指定オフセット**プロパティでは、レコード内のデータから、タグを個別に処理することもできます。 たとえば、タグは、レコードの先頭が発生し、4 文字の長さの場合、は、値を設定できます、**位置指定オフセット**4 つ、これにより効率的にスキップするレコードの最初のフィールドのプロパティ、最初のフィールドの値がレコードの同等の XML 形式に変換するときの位置指定レコードのタグ。  

これらのプロパティについて詳しく[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。 
  
## <a name="see-also"></a>参照  
 [位置指定レコードに関する注意](../core/positional-record-considerations.md)   

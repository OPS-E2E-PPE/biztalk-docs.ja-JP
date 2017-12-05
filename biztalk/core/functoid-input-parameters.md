---
title: "Functoid 入力パラメーター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cca24f93-74a8-460c-b9ab-9aa2c767fe2f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4a430b96f7a76ad6f99a7b3f9ee151f17c7b55a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="functoid-input-parameters"></a>Functoid 入力パラメーター
Functoid をマップで使用する場合の重要な点は、Functoid に対する入力パラメーターを適切に構成することです。 入力パラメーターの順序はすべての functoid にとって重要ではありません (など、**加算**functoid は、表示されて、同じ加算から予想される 1 つのプロパティに関連付ける)、多くの functoid の入力パラメーターを持つ必要があります正しい順序で指定します。  
  
## <a name="create-input-paramaters"></a>入力パラメーターを作成します。
 Functoid の入力パラメーターを作成する 2 つの方法を次に示します。  
  
-   表示されたグリッド ページで、Functoid の左側からのリンクを作成します。 リンクを作成する順序は、関連付けられた入力パラメーターが Functoid に渡される順序です。  
  
-   開き、**構成\<Functoid\> Functoid**入力パラメーター ダイアログ ボックスを新規に追加します。 このダイアログ ボックスも重要です。ここでは、Functoid の入力パラメーターの順序を入れ替えて適切な順序にすることができるからです。 たとえば、Functoid へのリンクを間違った順序で作成した場合に、このダイアログ ボックスを開いて必要な修正を行うことができます。 Functoid の入力パラメーターの構成の詳しい手順については、「 [Functoid の入力パラメーターを構成する方法](../core/how-to-configure-functoid-input-parameters.md)です。  
  
 使用する必要があります、**構成\<Functoid\> Functoid**定数入力パラメーターを作成する ダイアログ ボックス。  
  
 使用して、リンクまたは functoid のラベルを指定すると、**ラベル**リンクまたは functoid が選択されている場合は、プロパティ ウィンドウでプロパティ、そのラベルに表示される、**構成\<Functoid\>Functoid**  ダイアログ ボックスではなく、対応するスキーマ ノードの XPath や入力パラメーターとして使用される functoid の名前。 ラベルを使用すると、各パラメーターの識別や、適切な順序での配置を容易に行うことができます。  
  
 Functoid の入力パラメーターの正しい順序に関する明確な情報は、次を参照してください。、 **Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
## <a name="see-also"></a>参照  
 [Functoid 入力パラメーターを構成します。](../core/how-to-configure-functoid-input-parameters.md)   
 [スクリプト Functoid を構成します。](../core/how-to-configure-the-scripting-functoid.md)   
 [テーブル ループ Functoid およびテーブル抽出 Functoid の構成](../core/how-to-configure-the-table-looping-and-table-extractor-functoids.md)
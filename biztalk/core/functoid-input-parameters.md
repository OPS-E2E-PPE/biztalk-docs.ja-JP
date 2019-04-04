---
title: Functoid 入力パラメーター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cca24f93-74a8-460c-b9ab-9aa2c767fe2f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a4a93d827a5f58401bb9b8fcdf9727c2a61767e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008099"
---
# <a name="functoid-input-parameters"></a>Functoid 入力パラメーター
Functoid をマップで使用する場合の重要な点は、Functoid に対する入力パラメーターを適切に構成することです。 入力パラメーターの順序はすべての functoid にとって重要ではありません (など、**加算**functoid は、同じ表示がまた 1 つが要求するプロパティを関連付ける)、多くの functoid の入力パラメーターが必要正しい順序で指定します。  
  
## <a name="create-input-paramaters"></a>入力パラメーターを作成します。
 Functoid の入力パラメーターを作成する 2 つの方法を次に示します。  
  
- 表示されたグリッド ページで、Functoid の左側からのリンクを作成します。 リンクを作成する順序は、関連付けられた入力パラメーターが Functoid に渡される順序です。  
  
- 開き、**構成\<Functoid\> Functoid**入力パラメーター ダイアログ ボックスを新規に追加します。 このダイアログ ボックスも重要です。ここでは、Functoid の入力パラメーターの順序を入れ替えて適切な順序にすることができるからです。 たとえば、Functoid へのリンクを間違った順序で作成した場合に、このダイアログ ボックスを開いて必要な修正を行うことができます。 Functoid の入力パラメーターの構成の詳しい手順については、「 [Functoid の入力パラメーターを構成する方法](../core/how-to-configure-functoid-input-parameters.md)します。  
  
  使用する必要があります、**構成\<Functoid\> Functoid**ダイアログ ボックスの定数入力パラメーターを作成します。  
  
  リンクまたは functoid を使用して、ラベルを指定すると、**ラベル**プロパティ リンクまたは functoid が選択されている場合は、プロパティ ウィンドウで、そのラベルに表示されます、**構成\<Functoid\>Functoid**  ダイアログ ボックスではなく、スキーマ ノードの対応する XPath や入力パラメーターとして使用される functoid の名前。 ラベルを使用すると、各パラメーターの識別や、適切な順序での配置を容易に行うことができます。  
  
  Functoid の入力パラメーターの適切な順序の詳細については、、 **Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]を参照してください。
  
## <a name="see-also"></a>参照  
 [Functoid 入力パラメーターを構成します。](../core/how-to-configure-functoid-input-parameters.md)   
 [スクリプト Functoid を構成します。](../core/how-to-configure-the-scripting-functoid.md)   
 [テーブル ループ Functoid およびテーブル抽出 Functoid の構成](../core/how-to-configure-the-table-looping-and-table-extractor-functoids.md)
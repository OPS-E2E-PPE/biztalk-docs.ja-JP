---
title: ソースを設定する方法は、コンパイラの値をリンク |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4edd1d73-78d1-468d-806a-3f6f258ee375
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb6d3a08cf1cc4f22ea339d74a1b7ca2de081a37
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334218"
---
# <a name="how-to-set-the-source-links-compiler-value"></a>送信元リンクのコンパイラ値を設定する方法
使用することができます、**ソース リンク**値が送信元ノードから取得され、送信先ノードに適用する方法を指定するリンクのプロパティ。 このトピックでは、使用可能な選択肢とそれらの間で選択する方法について説明します。  
  
### <a name="to-set-the-source-links-link-property"></a>送信元のリンクのリンクのプロパティを設定するには  
  
1. BizTalk マッパーのグリッド ページで、リンクをクリックして選択します。  
  
    グリッド ページ内の選択したリンクのエンドポイントが強調表示されます。  
  
2. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウで、**ソース リンク**プロパティを次の選択肢のいずれか。  
  
   -   **名前をコピーします。** 送信元スキーマ ノードの名前は、送信先スキーマのリンク先ノードの値として使用されます。  
  
   -   **テキスト値をコピーします。** (要素データまたは属性値) の送信元スキーマ内のノードに対応する値は、送信先スキーマのリンク先ノードの値として使用されます。 このオプションは、既定値です。 たとえば、 `<Node>Hello<Name>Chris</Name>Barry</Node>` 「こんにちは」になります。  
  
   -   **テキストとサブコンテンツの値をコピーします。** レコード ノードとそのすべての子ノードとその子ノードの値に対応する値をソース スキーマ (要素データおよび属性値) は、送信先スキーマのリンク先ノードの値として結合されます。 たとえば、 `<Node>Hello<Name>Chris</Name>Barry</Node>` "こんにちは Chris Barry"になります。  
  
## <a name="see-also"></a>参照  
 [リンクを使用してレコードを指定して、フィールド マッピング](../core/using-links-to-specify-record-and-field-mappings.md)   
 [コンパイラ ディレクティブおよびリンク](../core/compiler-directives-and-links.md)
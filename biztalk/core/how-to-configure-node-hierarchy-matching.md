---
title: ノード階層の照合を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5302e194-cbc7-4d26-b25b-eb4e38abfe23
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00de1b7431fd942451d99b958746d209fcdf427d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386245"
---
# <a name="how-to-configure-node-hierarchy-matching"></a>ノード階層の照合を構成する方法
マップにリンクを作成すると、BizTalk マッパーが自動的にコンパイラ リンクを作成して、描画されたリンクが実装されます。 **ターゲット リンク**リンクのプロパティは、BizTalk マッパーによるコンパイラ リンクの描画方法を制御します。 ここでは、ターゲット リンクを設定する方法を説明します。  
  
 **ソース リンク**プロパティは、値が送信元ノードから取得され、送信先ノードに適用する方法を指定します。 送信元のリンクを設定する方法については、次を参照してください。[ソース リンクのコンパイラ値を設定する方法](../core/how-to-set-the-source-links-compiler-value.md)します。  
  
> [!NOTE]
>  この操作では、BizTalk マッパーが実行されている必要があります。  
  
### <a name="to-set-the-target-links-property"></a>送信先のリンク プロパティを設定するには  
  
1. マップ グリッド ページで、送信先リンク プロパティを設定するリンクをクリックします。  
  
2. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]**プロパティ**ウィンドウで、設定、**ターゲット リンク**プロパティを次の選択肢のいずれか。  
  
   -   **リンクをフラット化します。** 送信元レコード ノードの階層がフラット化されて、送信先スキーマのリンク先レコード ノードと照合されます。  
  
       > [!NOTE]
       >  既定では、BizTalk マッパーの設定、**ターゲット リンク**プロパティを**Flatten**します。  
  
   -   **リンクを上から順に一致します。** ノードは、上のレベルから下のレベルへと順に照合されます。  
  
   -   **一致するもの下にリンクします。** ノードは、下のレベルから上のレベルへと順に照合されます。  
  
## <a name="see-also"></a>参照  
 [ノード階層レベルの照合](../core/node-hierarchy-level-matching.md)   
 [コンパイラ ディレクティブおよびリンク](../core/compiler-directives-and-links.md)   
 [リンクを使用してレコードとフィールド マッピングを指定する](../core/using-links-to-specify-record-and-field-mappings.md)
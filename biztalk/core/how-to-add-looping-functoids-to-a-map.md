---
title: ループ マップに Functoid を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b24051b7-3e79-4a49-8249-a057c048ddae
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 659b9b39beea4bf5efed4c6d1553fca173191cc5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988763"
---
# <a name="how-to-add-looping-functoids-to-a-map"></a>マップにループ Functoid を追加する方法

## <a name="overview"></a>概要
**ループ**functoid が複数のレコードまたは送信元スキーマ内のフィールドを送信先スキーマの 1 つのレコードに結合します。  

 概念情報については、**ループ**functoid を参照してください[ループ Functoid](../core/looping-functoid.md)します。  

 特定の状況では、一部の functoid が正常に動作しないと共にマップで使用している場合、**ループ**functoid。 次の条件下では、期待どおりの結果が生成されません。  

-   Functoid に複数の入力リンクが存在する。  

-   2 つまたは複数の functoid の入力リンクは、入力レコードの子フィールドにリンクされて、**ループ**functoid は、子フィールドが兄弟ではないです。  

-   Functoid の出力レコードの子フィールドにリンクされている出力リンクを持つ、**ループ**functoid。  

## <a name="add-the-looping-functoid-to-a-map-and-configure-it"></a>マップにループ functoid を追加し、構成  

1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブ。  

    選択したカテゴリに含まれる高度な Functoid の一覧が表示されます。  

2. ドラッグ、**ループ**ツールボックスから functoid をグリッド ページの適切な場所にします。  

    ![](../core/media/bts-tls-looping.gif "bts_tls_looping")  
   ループ functoid  

   > [!NOTE]
   >  Functoid は表示されているグリッド ページに配置されます。 別のグリッド ページに functoid を配置する場合は、最初にその他のグリッド ページを表示する必要があります。  
   > 
   >  複数の Functoid を同時に使用するマップを構築する場合は、相対的な位置 (左右) に注意する必要があります。 Functoids は左から順に実行されます。 1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。  

3. 入力パラメーターを確立するために、**ループ**functoid、レコードをドラッグして、入力リンクを作成またはフィールドへの送信元スキーマから、**ループ**functoid をドラッグするか、**ループ** functoid へレコードまたはフィールド、送信元スキーマにします。 すべての関連する入力レコードまたはフィールドを含める手順を繰り返して、**ループ**functoid。  

4. 出力パラメーターを使用する、**ループ**functoid をドラッグして、出力リンクを作成、**ループ**functoid、レコードまたはフィールドに、送信先スキーマでは、レコードまたはフィールドをドラッグするかを変換先スキーマ、**ループ**functoid。  

   > [!NOTE]
   >  他の functoid の出力とは異なり、**ループ**functoid は、送信先スキーマの要素にのみリンクできます。  

## <a name="see-also"></a>参照  
- [マップへの高度な Functoid の追加](../core/adding-advanced-functoids-to-a-map.md)   
- **ループ Functoid のリファレンス** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]

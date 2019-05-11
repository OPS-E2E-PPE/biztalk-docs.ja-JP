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
ms.openlocfilehash: 2621287c35a60f57c4706e0901c7f786166d6cee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343270"
---
# <a name="how-to-add-looping-functoids-to-a-map"></a>ループ マップに Functoid を追加する方法

## <a name="overview"></a>概要
**ループ**functoid が複数のレコードまたは送信元スキーマ内のフィールドを送信先スキーマの 1 つのレコードに結合します。  

 概念情報については、**ループ**functoid を参照してください[ループ Functoid](../core/looping-functoid.md)します。  

 特定の状況では、一部の functoid が正常に動作しないと共にマップで使用している場合、**ループ**functoid。 このような functoid が、次の条件を満たしている場合、期待される結果は生成されません。  

-   Functoid には、1 つ以上の入力リンクがあります。  

-   2 つまたは複数の functoid の入力リンクは、入力レコードの子フィールドにリンクされて、**ループ**functoid は、子フィールドが兄弟ではないです。  

-   Functoid の出力レコードの子フィールドにリンクされている出力リンクを持つ、**ループ**functoid。  

## <a name="add-the-looping-functoid-to-a-map-and-configure-it"></a>マップにループ functoid を追加し、構成  

1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブ。  

    選択したカテゴリでの高度な functoid の一覧が表示されます。  

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

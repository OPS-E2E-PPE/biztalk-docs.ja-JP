---
title: マップに繰り返し Functoid を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1eaea929-e352-447d-b119-bd69b6b24e6c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ed2dfe33feb7d5e0e6f43be61742bfbbddfc98c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997195"
---
# <a name="how-to-add-iteration-functoids-to-a-map"></a>マップに繰り返し Functoid を追加する方法
**イテレーション**functoid の出力、ループの現在のレコードのインデックスが構造体の最初のレコードでは、2、2 つ目のレコードを 1 から始まる具合です。  
  
 概念情報については、**イテレーション**functoid を参照してください[繰り返し Functoid](../core/iteration-functoid.md)します。  
  
### <a name="to-add-the-index-functoid-to-a-map-and-configure-it"></a>マップにインデックス Functoid を追加して構成するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブ。  
  
    選択したカテゴリに含まれる高度な Functoid の一覧が表示されます。  
  
2. ドラッグ、**インデックス**functoid (![](../core/media/bts-tls-iteration.gif "bts_tls_iteration")) ツールボックスからグリッド ページの適切な場所にします。  
  
   > [!NOTE]
   >  Functoid は表示されているグリッド ページに配置されます。 別のグリッド ページに functoid を配置する場合は、最初にその他のグリッド ページを表示する必要があります。  
  
   > [!NOTE]
   >  複数の Functoid を同時に使用するマップを構築する場合は、相対的な位置 (左右) に注意する必要があります。 Functoids は左から順に実行されます。 1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。  
  
3. ループ レコード入力パラメーターを設定する、**イテレーション**functoid、送信元スキーマからループ レコードをドラッグして、入力リンクを作成、**イテレーション**functoid、をドラッグするか**イテレーション**functoid、送信元スキーマのループ レコードを送信します。  
  
4. 出力パラメーターを使用する、**イテレーション**functoid をドラッグして、出力リンクを作成、**イテレーション**または変換先スキーマのフィールドをドラッグして、送信先スキーマのフィールドを functoid**イテレーション**functoid。  
  
   > [!NOTE]
   >  出力のデータ型に一致するように、送信先スキーマ内の関連するフィールドのデータ型が数値または数値に変換できるをある必要があります、**イテレーション**functoid。  
  
## <a name="see-also"></a>参照  
 [マップへの高度な Functoid の追加](../core/adding-advanced-functoids-to-a-map.md)
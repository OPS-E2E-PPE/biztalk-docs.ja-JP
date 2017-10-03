---
title: "論理演算 Functoid |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e37cdfc3-66de-4333-84eb-a8765afa8407
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7907d1045fde39d5ece963bd78e00d027e8a9da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="logical-functoids"></a>論理演算 Functoid

## <a name="overview"></a>概要
**論理**functoid は、次の種類の操作の実行に使用されます。  
  
-   実行時に特定の論理テストを実行します。 **論理 OR**、**論理否定**と**論理的かつ**次などの送信先インスタンス メッセージにレコードを作成するかどうかを決定する functoid を使用できます。  
  
     場合 ShipTo**または**OrderedBy が存在、BillTo address レコードを作成します。  
  
     組み合わせて、これらの functoid を使用することもできます、**ループ**functoid を何回、レコードのループを構成します。  
  
-   実行時に特定のレコードを送信先インスタンス メッセージに作成するかどうかを制御します。 Functoid などの Functoid **IsNil**、**数値検査**、**より小さい**、および**より大きい**レコードを作成するかどうか、コントロールを使用できます。  
  
     かどうか、これらの論理 functoid のいずれかの結果は**True**、送信先インスタンス メッセージに対応するレコードが生成されます。 結果は場合**False**、送信先インスタンス メッセージに対応するレコードは生成されません。  
  
 Functoid **IsNil**、**日付検査**、**論理的な実体**、**論理否定**、**数値検査**、および**文字列検査**1 つだけのパラメーターを受け取ります。 Functoid**等しい**、**より大きい**、**より大きいまたは等しい**、**より小さい**、 **小さい**、および**等しくない**2 つの入力パラメーターをそのまま使用します。 一方、**論理的かつ**と**論理 OR** functoid は 2 ~ 100 の範囲の入力パラメーターを受け取ります。  
  
 出力、**論理**functoid は、マップ内の他の functoid への入力としても使用できます。 両方の場合、**論理**functoid およびループ functoid が相互にリンクし、送信先スキーマのレコードにリンクし、ループ functoid が使用される場合にのみ、**論理**functoid の出力が**True**です。  
  
 使用することも**論理**functoid と、**値のマッピング**または**値のマッピング (フラット化)** functoid を送信先インスタンス メッセージ内のレコードかどうかを制御するには作成されます。  
  
> [!IMPORTANT]
>  2 つの異なる 2 つのレコードや送信元スキーマのフィールドをリンクする場合**論理**functoid、し、それぞれのリンク、**論理**functoid は送信先スキーマで同じレコードに最初のメッセージだけ**論理**functoid はで、生成された言語変換 XSLT (Extensible Stylesheet) を使用します。 2 番目の 2 番目のリンク**論理**functoid は無視されます。  
  
> [!NOTE]
>  論理演算 functoid は 2 つの文字列を比較するときに区別されます。 たとえば、"Abc" と "abc" は、同じではありません。 この規則の例外がいつ**論理**functoid は、ブール値を表す文字列を比較**True**と**False**です。 たとえば、"True" と "true" は同じです。  

## <a name="available-functoids"></a>使用可能な functoid  
 **論理**functoid には。 

* 等号
* より大きい
* 大きいか等しい
* IsNil
* 小さい
* 以下に
* 論理積
* 日付検査
* 論理的な実体
* 論理否定
* 数値検査
* 論理和
* 文字列検査
* 不等号

これらの関数の詳細については、[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
## <a name="see-also"></a>参照  
-  [マップに基本 Functoid を追加する方法](../core/how-to-add-basic-functoids-to-a-map.md)   
-  **論理演算 Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
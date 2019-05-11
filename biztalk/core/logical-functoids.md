---
title: 論理演算 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e37cdfc3-66de-4333-84eb-a8765afa8407
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b4fd7b2a38a5a5b4a8bbeb64ffd248502dcdb61
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65328309"
---
# <a name="logical-functoids"></a>論理演算 Functoid

## <a name="overview"></a>概要
**論理**functoid は、次の種類の操作の実行に使用されます。  

- 実行時に特定の論理テストを実行します。 **論理和**、**論理否定**と**論理的かつ**次などの送信先インスタンス メッセージにレコードを作成するかどうかを判断する functoid を使用できます。  

   場合 ShipTo**または**OrderedBy が存在する、BillTo address レコードを作成します。  

   これらの functoid と組み合わせて使用することもできます、**ループ**functoid を何回、レコードのループを構成します。  

- 実行時に、送信先インスタンス メッセージに特定のレコードが作成されたかどうかを制御します。 などの Functoid **IsNil**、**数値検査**、**未満**、および**より大きい**レコードが作成されたかどうか、コントロールを使用できます。  

   これらの論理演算 functoid のいずれかの結果が**True**、送信先インスタンス メッセージに対応するレコードが生成されます。 結果は場合**False**を送信先インスタンス メッセージに対応するレコードは生成されません。  

  Functoid **IsNil**、**論理日付**、**論理的な実体**、**論理否定**、**論理数値**、および**文字列検査**のみ 1 つのパラメーターをそのまま使用します。 Functoid**等しい**、**より大きい**、**より大きいまたは等しい**、**未満**、 **未満**、および**等しく**2 つの入力パラメーターをそのまま使用します。 一方、**論理的かつ**と**論理和**functoid は 2 ~ 100 の入力パラメーターを受け取ります。  

  出力を**論理**functoid は、マップ内の他の functoid への入力としても使用できます。 両方の場合、**論理**ループ functoid の使用、および、functoid およびループ functoid が相互にリンクし、送信先スキーマ内のレコードにリンクされている場合にのみ、**論理**functoid の出力が**True**します。  

  使用することも**論理**functoid と、**値のマッピング**または**値のマッピング (フラット化)** 送信先インスタンス メッセージ内のレコードかどうかを制御する functoid作成されます。  

> [!IMPORTANT]
>  2 つの異なる 2 つのレコードまたは送信元スキーマ内のフィールドをリンクする場合**論理**functoid、し、それぞれのリンク、**論理**functoid を送信先スキーマで同じレコード最初のみ**論理**functoid ので、生成された XSLT Extensible Stylesheet Language Transformations () を使用します。 2 番目のリンクの 2 番目の**論理**functoid は無視されます。  

> [!NOTE]
>  論理演算 functoid は、2 つの文字列を比較するときに大文字小文字を区別します。 たとえば、"Abc"と"abc"は等しくありません。 このルールの例外は**論理**functoid は、ブール値を表す文字列を比較**True**と**False**します。 たとえば、"True"と"true"は等しくなります。  

## <a name="available-functoids"></a>使用可能な functoid  
 **論理**functoid には。 

* 等号
* 大きい
* 大きいまたは等しい
* IsNil
* 小さい
* 等しいまたはそれよりも小さい
* 論理積
* 日付検査
* 論理的な実体
* 論理 NOT
* 数値検査
* 論理和
* 文字列検査
* 不等号

これらの関数の詳細については、[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。

## <a name="see-also"></a>参照  
- [マップに基本 Functoid を追加する方法](../core/how-to-add-basic-functoids-to-a-map.md)   
- **論理演算 Functoid のリファレンス** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]

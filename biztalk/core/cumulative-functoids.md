---
title: 累積 Functoid |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f0549867-e0e4-4cdb-aae0-cadc99088e03
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6ed3d5037d64cf21e1ee2676a5739f13e18da3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240066"
---
# <a name="cumulative-functoids"></a>累積 Functoid

## <a name="overview"></a>概要
**累積的な**functoid は、合計、連結された文字列の場合は、平均などの単一の値に、一連の値を削減します。  
  
 すべて**累積**functoid は、2 つの入力パラメーターを受け取ります。  
  
1.  累積する値。 この値はすべての数値**累積**functoid を除く、**累積連結**functoid は、文字列値が必要です。 値からでは、リンク、多くの場合、**フィールド属性**、**フィールド要素**、または**レコード**ノード (とその**Mixed**プロパティに設定する**True**)。  
  
    > [!NOTE]
    >  祖先にない場合**レコード**を使用して、スキーマ ツリー内のノードがループ、**累積**functoid が必要ではありません。  
  
2.  値を累積する範囲。 この引数は省略可能です。 この引数は、指定された値を累積するレベルを示します。  
  
 次の表は、スコープ パラメーターの値とその動作を示しています。  
  
|スコープ パラメーターの値|結果|  
|-----------------------------|------------|  
|0 (ゼロ)|インスタンス メッセージ全体の値を累積します。 既定値です。|  
|1 (one)|同じ親要素を持つ要素の値または属性値を累積します。|  
|2|同じ祖父要素を持つ要素の値または属性値を累積します。|  
|3 以上|上記のパターンよりもさらに幅の広い範囲 (祖父の親要素、祖父の祖父要素など) の要素の値または属性値を累積します。|  

## <a name="example"></a>例  
 使用例、**累積**functoid がコストを合計する注文全体でします。 次のコードは、注文書の例です。  
  
```  
<ns0:PurchaseOrder xmlns:ns0="http://CumulativeFunctoid.PurchaseOrder">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <LineItems>  
        <Item>  
            <Product>Laptop Computer</Product>  
            <Description>Thin profile laptop</Description>  
            <Price>1999.95</Price>  
            <Quantity>1</Quantity>  
        </Item>  
        <Item>  
            <Product>Monitor Swipes</Product>  
            <Description>Disposable monitor swipes</Description>  
            <Price>3.95</Price>  
            <Quantity>10</Quantity>  
        </Item>  
    </LineItems>  
</ns0:PurchaseOrder>  
```  
  
 **Max Occurs**プロパティを**項目**レコードはありますが、もちろん、 **unbounded**です。 これは、Item レコードがループすることを示しています。BizTalk マッパーは、このレコードをループとしてコンパイルします。  
  
 次の図を使用して、マップ、**乗算**functoid と**累積合計**item レコードを集計で functoid の入力方向の発注書とで結果を出力、 **POTotal**フィールド。  
  
 ![累積合計 functoid の使用方法を示すマップ。] (../core/media/cumulativefunctoids.gif "cumulativefunctoids")  

  
 このマップでは、前のデータと既定のスコープ パラメーターの値 0 (ゼロ) を使用して、次の出力結果を生成しています。  
  
```  
<ns0:SummedPO xmlns:ns0="http://CumulativeFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <POTotal>2039.45</POTotal>  
</ns0:SummedPO>  
```  
  
 この例ではすべて、**項目**レコードに属する、 **LineItems**レコードが蓄積されるに参加: スコープ パラメーターの既定値は、メッセージ全体の値が累積されることを示します。 **価格**と**数量**フィールドに送信される、**乗算**functoid です。 出力、**乗算**functoid への入力になります、**累積合計**functoid です。 出力、**累積合計**functoid は、累積された値として、**項目**入力注文書のレコードを走査します。  
  
> [!NOTE]
>  入力の累積集計は、入力リンクの発生元の親レコードに対して行われます。 場合でも、**累積**functoid が別の functoid から入力を取得、累積的な集計にわたって実行入力リンクの親レコードへの入力として機能する functoid を**累積**functoid です。  
  
 スコープ パラメーターを 1 (one) に変更し、出力スキーマに若干の変更を加えると、出力結果は次のようになります。  
  
```  
<ns0:SummedPO xmlns:ns0="http://CumulativeFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <ItemTotal>1999.95</ItemTotal>  
    <ItemTotal>39.5</ItemTotal>  
</ns0:SummedPO>  
```  
  
 スコープ パラメーターを 1 (one) に設定すると、同じ親を持つ要素または属性の累積値が示されます。 ここで、**価格**と**数量**フィールドである**項目**親として functoid ごとに値の合計を計算できるように**項目**です。  
  
 スコープ パラメーターを 2 に設定すると、この Functoid は、同じ祖父を持つ要素または属性の値を累積します。 親の親、**価格**と**数量**フィールドは、 **LineItems**レコード。 1 つだけを使用する必要があるため**LineItems**インスタンス メッセージのレコードを結果と同じ既定値を使用します。  
  
```  
<ns0:SummedPO xmlns:ns0="http://CumulativeFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <POTotal>2039.45</POTotal>  
</ns0:SummedPO>  
```  
  
> [!NOTE]
>  累積 functoid (を除き、**累積文字列**functoid) 数値以外の入力を無視します。 たとえば、"three" という入力値は無視されます。  
  
 **累積平均**、**累積最小値**、および**累積最大値**functoid の動作と同じように、**累積合計**functoid です。 **累積文字列**数値を集計するのではなく、文字列を連結します。  

## <a name="available-functoids"></a>使用可能な functoid
  
 **累積**functoid には。 

* 累積平均
* 累積連結
* 累積最大値
* 累積最小値
* 累積合計

これらの functoid の詳細については、[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
## <a name="see-also"></a>参照  
-  [マップに基本 Functoid を追加する方法](../core/how-to-add-basic-functoids-to-a-map.md)   
-  **累積 Functoid のリファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
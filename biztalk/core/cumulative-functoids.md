---
title: 累積 Functoid |Microsoft Docs
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
ms.openlocfilehash: c3f2b9a53a41072dd98edf486ce1b8abcedfbae2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353428"
---
# <a name="cumulative-functoids"></a>累積 Functoid

## <a name="overview"></a>概要
**累積的な**functoid は、合計、連結された文字列の場合は、平均などの 1 つの値を一連の値を削減します。  

 すべて**累積**functoid は 2 つの入力パラメーターを受け取ります。  

1. 累積する値。 この値はすべての数値**累積**functoid を除く、**累積連結**functoid は文字列値が必要です。 値からでは、リンク、多くの場合、**フィールド属性**、**フィールド要素**、または**レコード**ノード (とその**Mixed** に設定するプロパティ**True**)。  

   > [!NOTE]
   >  祖先にない場合**レコード**を使用して、スキーマ ツリー内のノードがループを**累積**functoid が必要ではありません。  

2. 値を累積する範囲。 この引数は省略可能です。 引数がどの程度近いかを示す関連の指定した値が累積する必要があります。  

   次の表は、スコープのパラメーターとその効果の値を示しています。  

|スコープ パラメーターの値|効果|  
|-----------------------------|------------|  
|0 (ゼロ)|インスタンス メッセージ全体では、値を累積します。 これが既定値です。|  
|1 (1 つ)|同じ親要素を持つ要素または属性の値の値を累積します。|  
|2|同じ祖父要素を持つ要素または属性の値の値を累積します。|  
|3 以上|(祖父母、優れた-祖父母など) は、上記のパターン、段階的により広いスコープの値を要素または属性の値を累積します。|  

## <a name="example"></a>例  
 使用する例を**累積**functoid 可能性があるコストを合計注文書。 次のコードは、注文書の例です。  

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

 **Max Occurs**プロパティを**項目**レコードがある場合は、もちろん、 **unbounded**します。 これは、item レコードがループ、および BizTalk マッパーがこのレコードをループとしてコンパイルされることを示します。  

 次の図を使用して、マップ、**乗算**functoid と**累積合計**item レコードを集計で functoid の入力方向の発注書とで結果を出力、 **書**フィールド。  

 ![累積合計 functoid の使用方法を示すマップ。](../core/media/cumulativefunctoids.gif "cumulativefunctoids")  


 マップには、前のデータと、既定スコープ パラメーター値は 0 (ゼロ) は、次の出力が生成されます。  

```  
<ns0:SummedPO xmlns:ns0="http://CumulativeFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <POTotal>2039.45</POTotal>  
</ns0:SummedPO>  
```  

 この例では、すべて、**項目**レコードに属する、 **LineItems**レコードが蓄積されるに参加 — スコープのパラメーターの既定値は、メッセージ全体の値を累積することを示します。 **価格**と**数量**フィールドに送信される、**乗算**functoid。 出力、**乗算**functoid への入力になります、**累積合計**functoid。 出力、**累積合計**functoid は、累積した値、**項目**入力発注書のレコードが走査されます。  

> [!NOTE]
>  入力の累積集計は、入力リンクが元の親レコードに対して行われます。 場合でも、**累積**functoid 別の functoid からの入力を取得すると、累積的な集計が場所入力リンクの親レコードへの入力として機能する functoid へ、**累積**functoid。  

 スコープを 1 (one) パラメーターと出力スキーマを少し変更を変更するには、次のような出力が得られます。  

```  
<ns0:SummedPO xmlns:ns0="http://CumulativeFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <ItemTotal>1999.95</ItemTotal>  
    <ItemTotal>39.5</ItemTotal>  
</ns0:SummedPO>  
```  

 スコープのパラメーターを 1 (1) に設定すると、同じ親を持つ要素または属性の累積値を示します。 ここで、**価格**と**数量**フィールドが**項目**親として、functoid ごとに値を合計するように**項目**します。  

 スコープのパラメーターが 2 の場合、functoid は、同じ祖父を持つ要素または属性の値を累積します。 親の親、**価格**と**数量**フィールドは、 **LineItems**レコード。 1 つしかないため、 **LineItems**既定値と同じインスタンス メッセージ内のレコードの結果のです。  

```  
<ns0:SummedPO xmlns:ns0="http://CumulativeFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <POTotal>2039.45</POTotal>  
</ns0:SummedPO>  
```  

> [!NOTE]
>  累積 functoid (を除き、**累積文字列**functoid) 数値以外の入力を無視します。 たとえば、入力値を「3」は無視されます。  

 **累積平均**、**累積最小値**、および**累積最大値**functoid の動作と同様に、**累積合計**functoid。 **累積文字列**数値を集計するのではなく、文字列を連結します。  

## <a name="available-functoids"></a>使用可能な functoid

 **累積**functoid には。 

* 累積平均
* 累積連結
* 累積最大値
* 累積最小値
* 累積合計

これらの functoid の詳細については、[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。

## <a name="see-also"></a>参照  
- [マップに基本 Functoid を追加する方法](../core/how-to-add-basic-functoids-to-a-map.md)   
- **累積 Functoid のリファレンス** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]

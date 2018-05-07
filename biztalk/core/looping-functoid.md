---
title: ループ Functoid |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 19886ccb-4642-48a4-b93e-563640ea828b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ce2b66fd796708a0e8b24ee05e3a0b043af6808
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="looping-functoid"></a>ループ Functoid

## <a name="overview--example"></a>概要 & の使用例
**ループ** functoid が複数のレコードまたは送信元スキーマ内のフィールドを送信先スキーマの 1 つのレコードに結合します。  
  
 次に示します、 **ループ**単一のマスター住所リストに 2 つの異なる調査から収集された functoid のマップ内でアドレスを結合するために使用します。  
  
> [!NOTE]
>  **ループ** と **値のマッピング (フラット化)** functoid をまとめて使用しない必要があります。 送信元の下にある対象ノードの依存関係のループがないと見なさコンパイル済みのマップの結果、両方をまとめて使用する場合、 **ループ** functoid です。  
  
 ![ループ functoid の使用方法を示すマップです。] (../core/media/loopingfunctoid.gif "loopingfunctoid")  
  
 **FoodSurvey** と **FlowerSurvey** 、送信元スキーマのループ レコードは、ループにマップされる **アドレス** 、送信先スキーマのレコードです。 3 つの入力インスタンス メッセージがある場合 **FoodSurvey** レコードと 2 つ **FlowerSurvey** 、レコード、 **ループ**functoid では、これらの 5 つを作成する結合 **アドレス** 出力インスタンス メッセージ内のレコードです。  
  
 次のコードは、入力インスタンス メッセージのサンプルです。  
  
```  
<ns0:Surveys xmlns:ns0="http://LoopingFunctoid.Surveys">  
    <FoodSurvey Name="Karin Zimprich" Address="345 N 63rd St" City="Boston" State="MA" PostalCode="07485" />  
    <FoodSurvey Name="Wendy Wheeler" Address="7890 Broadway" City="Columbus" State="OH" PostalCode="46290" />  
    <FoodSurvey Name="Florian Voss" Address="1234 Main St" City="Denver" State="CO" PostalCode="97402" />  
    <FlowerSurvey Name="Kelly Focht" Address="456 1st Ave" City="Miami" State="FL" PostalCode="81406" />  
    <FlowerSurvey Name="Jim Kim" Address="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103" />  
</ns0:Surveys>  
```  
  
 この入力インスタンス メッセージを上の図に示したマップで処理すると、次の出力インスタンス メッセージが生成されます。  
  
```  
<ns0:MasterAddresses xmlns:ns0="http://LoopingFunctoid.MasterAddresses">  
    <Address Name="Karin Zimprich" Street="345 N 63rd St" City="Boston" State="MA" PostalCode="07458"/>  
    <Address Name="Wendy Wheeler" Street="7890 Broadway" City="Columbus" State="OH" PostalCode="46290"/>  
    <Address Name="Florian Voss" Street="1234 Main St" City="Denver" State="CO" PostalCode="97402"/>  
    <Address Name="Kelly Focht" Street="456 1st Ave" City="Miami" State="FL" PostalCode="81406"/>  
    <Address Name="Jim Kim" Street="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103"/>  
</ns0:MasterAddresses>  
```  
  
 **FoodSurvey** と **FlowerSurvey** メッセージのアドレスがまとめられます。 まとめられたメッセージでは、各アドレスの送信元は示されません。 元を追跡する場合は、追加、 **ソース** 属性を **アドレス** のレコード、 **MasterAddress** スキーマとマップを定数値です。 この値を設定するには、接続、 **FoodSurvey** フィールドを新しい **ソース** フィールドです。 コネクタ線上では、変更、 **リンク プロパティ** &#124; **コンパイラ** &#124; **リンクのソース** を「名前のコピー」プロパティです。 に対して、このプロセスを繰り返して、 **FlowerSurvey** フィールドです。 ここから入力メッセージを再処理すると、次の出力が得られます。  
  
```  
<ns0:MasterAddresses xmlns:ns0="http://LoopingFunctoid.MasterAddresses">  
    <Address Name="Karin Zimprich" Street="345 N 63rd St" City="Boston" State="MA" PostalCode="07458" Source="FoodSurvey"/>  
    <Address Name="Wendy Wheeler" Street="7890 Broadway" City="Columbus" State="OH" PostalCode="46290" Source="FoodSurvey"/>  
    <Address Name="Florian Voss" Street="1234 Main St" City="Denver" State="CO" PostalCode="97402" Source="FoodSurvey"/>  
    <Address Name="Kelly Focht" Street="456 1st Ave" City="Miami" State="FL" PostalCode="81406" Source="FlowerSurvey"/>  
    <Address Name="Jim Kim" Street="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103" Source="FlowerSurvey"/>  
</ns0:MasterAddresses>  
```  

## <a name="relationships-with-nodes"></a>ノードとの関係

 ノード間のリレーションシップの動作に影響する、 **ループ** functoid です。 たとえば、子ノードと、ソース スキーマ内の親の両方のリンク、 **ループ** functoid により、宛先ノードが作成されます。  
  
 Functoid は、送信元ノード間のリレーションシップにも影響を受けます。 ソース ノードの兄弟ではない子フィールドに、functoid を接続する、 **ループ** functoid が予期しない結果を生成します。 使用例を **文字列連結** を組み合わせる functoid、 **FoodSurvey** 名 フィールドと **FlowerSurvey** Address フィールドのアドレス フィールドに **MasterAddress** と次の出力インスタンス メッセージが生成します。  
  
```  
<ns0:MasterAddresses xmlns:ns0="http://LoopingFunctoid.MasterAddresses">  
    <Address Street="345 N 63rd St" City="Boston" State="MA" PostalCode="07458"/>  
    <Address Street="7890 Broadway" City="Columbus" State="OH" PostalCode="46290"/>  
    <Address Street="1234 Main St" City="Denver" State="CO" PostalCode="97402"/>  
    <Address Name="Kelly Focht" Street="456 1st Ave" City="Miami" State="FL" PostalCode="81406"/>  
    <Address Name="Jim Kim" Street="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103"/>  
</ns0:MasterAddresses>  
```  
  
 注意してください方法 **名前** フィールドが **FoodSurvey** ソース メッセージになくがの存在 **FlowerSurvey** メッセージのソースします。  
  
> [!IMPORTANT]
>  ソース ノードの子フィールドに、functoid を接続する、 **ループ** functoid は、送信元ノードは兄弟ではない場合に、予期しない結果になる可能性があります。  
  
 **ループ** functoid は、条件付きループを作成し、カタログにスキーマのマップに使用できる強力な構造です。 重複するいくつかの影響もあります **ループ** functoid のパスを考慮する必要があります。  
  
## <a name="next-steps"></a>次の手順
  
-   [条件付きループ](../core/conditional-looping.md)  
  
-   [カタログに対するフラット スキーマ](../core/flat-schema-to-catalog.md)  
  
-   [ループ パス](../core/loop-paths.md)  
  
## <a name="see-also"></a>参照  
 **テーブル ループ Functoid リファレンス** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
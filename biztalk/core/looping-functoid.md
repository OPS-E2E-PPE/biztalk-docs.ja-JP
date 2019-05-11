---
title: ループ Functoid |Microsoft Docs
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
ms.openlocfilehash: ed86e27ebb2ff9a2eace4801906d61ed677c85af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380460"
---
# <a name="looping-functoid"></a>ループ Functoid

## <a name="overview--example"></a>概要と例
**ループ**functoid が複数のレコードまたは送信元スキーマ内のフィールドを送信先スキーマの 1 つのレコードに結合します。  
  
 次に示します、**ループ**を 1 つのマスター住所リストに 2 つの異なる調査から functoid をマップ内でアドレスを結合するために使用を収集します。  
  
> [!NOTE]
>  **ループ**と**値のマッピング (フラット化)** functoid は一緒使用できません。 元のループの下にあるターゲット ノードの依存関係がないと見なされます。 コンパイル済みのマップの両方をまとめて使用する場合になります、**ループ**functoid。  
  
 ![ループ functoid の使用方法を示すマップです。](../core/media/loopingfunctoid.gif "loopingfunctoid")  
  
 **FoodSurvey**と**FlowerSurvey** 、送信元スキーマのループ レコードは、ループにマップされます**アドレス**送信先スキーマのレコード。 入力インスタンス メッセージを 3 つ**FoodSurvey**レコードと 2 つ**FlowerSurvey** 、レコード、**ループ**functoid では、これらの 5 つを作成する結合**アドレス**出力インスタンス メッセージ内のレコード。  
  
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
  
 この入力インスタンス メッセージでは、前の図に、マップによって処理されるときに次の出力インスタンス メッセージを生成します。  
  
```  
<ns0:MasterAddresses xmlns:ns0="http://LoopingFunctoid.MasterAddresses">  
    <Address Name="Karin Zimprich" Street="345 N 63rd St" City="Boston" State="MA" PostalCode="07458"/>  
    <Address Name="Wendy Wheeler" Street="7890 Broadway" City="Columbus" State="OH" PostalCode="46290"/>  
    <Address Name="Florian Voss" Street="1234 Main St" City="Denver" State="CO" PostalCode="97402"/>  
    <Address Name="Kelly Focht" Street="456 1st Ave" City="Miami" State="FL" PostalCode="81406"/>  
    <Address Name="Jim Kim" Street="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103"/>  
</ns0:MasterAddresses>  
```  
  
 **FoodSurvey**と**FlowerSurvey**メッセージのアドレスが統合されました。 結合されたメッセージには、各アドレスのソースは示しません。 元を追跡する場合は、追加、**ソース**属性を**アドレス**のレコード、 **MasterAddress**スキーマおよびマップ定数値。 この値を設定するには、接続、 **FoodSurvey**フィールドを新しい**ソース**フィールド。 コネクタ線上では、変更、 **リンク プロパティ** &#124; **コンパイラ** &#124; **リンクのソース** を「名前のコピー」プロパティです。 この手順を繰り返します、 **FlowerSurvey**フィールド。 上記の入力メッセージを再処理には、次の出力が得られます。  
  
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

 ノード間のリレーションシップの動作に影響を与える、**ループ**functoid。 たとえば、子ノードとその親に送信元スキーマの両方のリンク、**ループ**functoid は、移行先ノードが作成されないようにためです。  
  
 Functoid は、ソース ノード間のリレーションシップの影響を受けます。 Functoid のソース ノードの兄弟ではない子フィールドに接続する、**ループ**functoid は、予期しない結果を生成可能性があります。 を使用するなど、**文字列連結**functoid、 **FoodSurvey**名フィールドと**FlowerSurvey** のアドレスの名前フィールドに、アドレスフィールド**MasterAddress**次の出力インスタンス メッセージが生成されます。  
  
```  
<ns0:MasterAddresses xmlns:ns0="http://LoopingFunctoid.MasterAddresses">  
    <Address Street="345 N 63rd St" City="Boston" State="MA" PostalCode="07458"/>  
    <Address Street="7890 Broadway" City="Columbus" State="OH" PostalCode="46290"/>  
    <Address Street="1234 Main St" City="Denver" State="CO" PostalCode="97402"/>  
    <Address Name="Kelly Focht" Street="456 1st Ave" City="Miami" State="FL" PostalCode="81406"/>  
    <Address Name="Jim Kim" Street="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103"/>  
</ns0:MasterAddresses>  
```  
  
 注意してください方法、**名前**フィールドが**FoodSurvey**ソース メッセージには、存在なく**FlowerSurvey**メッセージのソースします。  
  
> [!IMPORTANT]
>  Functoid のソース ノードの子フィールドに接続する、**ループ**ソース ノードは兄弟ではない場合、functoid が予期しない結果を生成可能性があります。  
  
 **ループ**functoid は、条件付きループを作成して、カタログにスキーマのマップに使用できる強力な構造です。 重複のいくつかの効果もあります**ループ**functoid のパスを考慮する必要があります。  
  
## <a name="next-steps"></a>次のステップ
  
-   [条件付きループ](../core/conditional-looping.md)  
  
-   [カタログに対するフラット スキーマ](../core/flat-schema-to-catalog.md)  
  
-   [ループ パス](../core/loop-paths.md)  
  
## <a name="see-also"></a>参照  
 **テーブル ループ Functoid のリファレンス** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
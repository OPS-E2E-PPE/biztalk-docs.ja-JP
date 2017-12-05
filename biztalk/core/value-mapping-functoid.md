---
title: "値のマッピング Functoid |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Value Mapping functoids
- functoids, empty tags
- Concatenate functoids
ms.assetid: 3dd626fb-3bf6-4ede-9fd2-ddae5a54d178
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 038d59827a62c9f4e83879ec7cf2e0b47fd738f4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="value-mapping-functoid"></a>値のマッピング Functoid
**値のマッピング**functoid は、最初のパラメーターが true の場合に、2 番目のパラメーターの値を返します。 この Functoid は、主にフィールドの属性をレコードの属性に変更する場合に使用します。 入力メッセージの一部を平坦化する複数のレコードを 1 つのレコードに変換することによって、使用、[値のマッピング (フラット化) Functoid](../core/value-mapping-flattening-functoid.md)です。  
  
 次の図は、map、**値のマッピング**functoid、レコードの属性にフィールドの属性を変更するために使用します。  
  
 ![](../core/media/valuemappingfunctoid.gif "valuemappingfunctoid")  
値のマッピング Functoid を含むマップ  
  
 次のコードは、名前のペアで、入力インスタンス メッセージを示し、値が割り当てられます**名前**と**値**属性。  
  
```  
<ns0:Root xmlns:ns0="http://ValueMapping.WeatherIn">  
    <Record>  
        <Field Name="WindSpeed" Value="5"/>   
        <Field Name="Temperature" Value="20" />  
    </Record>  
    <Record>  
        <Field Name="WindSpeed" Value="15" />  
        <Field Name="Temperature" Value="18" />  
    </Record>  
</ns0:Root>  
```  
  
 このメッセージに対して、前述のマップを適用して変換すると、レコードごとに値が対応する名前の属性に割り当てられます。  
  
```  
<ns0:Root xmlns:ns0="http://ValueMapping.WeatherOut">  
    <Record WindSpeed="5"/>  
    <Record Temperature="20"/>  
    <Record WindSpeed="15"/>  
    <Record Temperature="18"/>  
</ns0:Root>  
```  
  
 **等しい**functoid の値がテスト、**名前**属性。 最初の**等しい**の値のテストの functoid**名前**"windspeed"。 ときに、**名前**が"WindSpeed、"最初**等しい**functoid を返します**True**です。 、これにより、さらに、**値のマッピング**の値を設定する functoid、 **WindSpeed** 、出力インスタンス メッセージ内の属性です。  
  
## <a name="suppressing-the-creation-of-empty-tags"></a>空のタグを作成しないようにする  
 空のタグを作成しないようにするには、値のマッピング Functoid を使用して、タグを作成するかどうかを制御します。 値が True の場合は目的のフィールドが作成され、True でない場合は作成されません。 ループ シナリオでは論理 Functoid を使用し、論理 Functoid を目的のレコードまたはフィールドに接続します。 条件が False と評価された場合、タグは作成されません。 例については、次を参照してください。[条件付きループ](../core/conditional-looping.md)です。  
  
## <a name="forcing-the-creation-of-empty-tags"></a>空のタグを強制的に作成する  
 空のタグを作成するのには、目的のフィールドまたはリンクの Value プロパティに値を追加することができます、 **Concatenate** functoid を目的のフィールドです。  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を選択すると、空のタグの生成を強制することは、"\<空\>"、目的のフィールドの値プロパティ内の値。 この場合、空の値のフィールドが作成されます。  
  
## <a name="see-also"></a>参照  
 [値のマッピング (フラット化) Functoid](../core/value-mapping-flattening-functoid.md)   
 [値のマッピング Functoid をマップに追加する方法](../core/how-to-add-value-mapping-functoids-to-a-map.md)   
 [高度な Functoid](../core/advanced-functoids.md)
---
title: 値のマッピング Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Value Mapping functoids
- functoids, empty tags
- Concatenate functoids
ms.assetid: 3dd626fb-3bf6-4ede-9fd2-ddae5a54d178
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ca60ff3024eb1b4cadc42e42c65a0c44c82ef5d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292612"
---
# <a name="value-mapping-functoid"></a>値のマッピング Functoid
**値のマッピング**functoid は、最初のパラメーターが true の場合に 2 番目のパラメーターの値を返します。 Functoid の一般的な用途は、フィールドの属性をレコードの属性に変更するのにです。 入力メッセージの一部を統合すると、複数のレコードを 1 つのレコードに変換することを使用して、[値のマッピング (フラット化) Functoid](../core/value-mapping-flattening-functoid.md)します。  
  
 次の図は、map、**値のマッピング**functoid、レコードの属性にフィールドの属性を変更するために使用します。  
  
 ![](../core/media/valuemappingfunctoid.gif "valuemappingfunctoid")  
値のマッピング Functoid マップ  
  
 次のコードは、名前のペアで、入力インスタンス メッセージし、に値が割り当てられている**名前**と**値**属性。  
  
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
  
 図に示したマップでは、値が別個のレコードに対応する名前を持つ属性に割り当てられているいずれかに、このメッセージを変換できます。  
  
```  
<ns0:Root xmlns:ns0="http://ValueMapping.WeatherOut">  
    <Record WindSpeed="5"/>  
    <Record Temperature="20"/>  
    <Record WindSpeed="15"/>  
    <Record Temperature="18"/>  
</ns0:Root>  
```  
  
 **等しい**functoid の値のテスト、**名前**属性。 最初の**等しい**の値のテストの functoid**名前**"windspeed"。 ときに、**名前**"WindSpeed、"は、最初の**等しい**functoid を返します**True**します。 これにより、有効、**値のマッピング**functoid の値を設定する、 **WindSpeed**出力インスタンス メッセージ内の属性。  
  
## <a name="suppressing-the-creation-of-empty-tags"></a>空のタグの作成を抑制します。  
 空のタグを抑制するには、タグを作成するかどうか場合、コントロールに値のマッピング functoid を使用します。 値が評価される場合は true、先にフィールドが作成されます。それ以外の場合、目的のフィールドは作成されません。 ループでは、論理演算 functoid を使用し、送信先レコードまたはフィールドに接続します。 条件が false に評価される場合、タグは作成されません。 例については、次を参照してください。[条件付きループ](../core/conditional-looping.md)します。  
  
## <a name="forcing-the-creation-of-empty-tags"></a>空のタグの作成を強制  
 作成される空のタグを強制的には、[destination] フィールドまたはリンクの Value プロパティに値を追加することができます、 **Concatenate** functoid を目的のフィールド。  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を選択して空のタグの生成を強制することは、"\<空\>"目的のフィールドの値プロパティの値。 この場合、フィールド、空の値が作成されます。  
  
## <a name="see-also"></a>参照  
 [値のマッピング (フラット化) Functoid](../core/value-mapping-flattening-functoid.md)   
 [値のマッピングをマップに Functoid を追加する方法](../core/how-to-add-value-mapping-functoids-to-a-map.md)   
 [高度な Functoid](../core/advanced-functoids.md)
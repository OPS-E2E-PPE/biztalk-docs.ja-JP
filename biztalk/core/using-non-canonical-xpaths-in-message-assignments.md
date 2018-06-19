---
title: メッセージ割り当てにおける非正規 Xpath の使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 052d1d72-43ce-4654-bf29-86f82ad65e91
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 201d6f8b6bc910faf79b64ac0b4617530b20608a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287626"
---
# <a name="using-non-canonical-xpaths-in-message-assignments"></a>メッセージ割り当てにおける非正規 XPath の使用
.Net メッセージの部分を使用すると、XML シリアル化属性によってコードに注釈を付けることができますが、識別フィールドやプロパティ注釈も伴う場合、非常に複雑な XPath 式になります。 これらの複雑な XPath 式は非正規にすることができます。 非正規 XPath は、直接バインドされたオーケストレーションでのみ使用する必要があります。論理的または物理的にバインドされたオーケストレーションでは失敗する可能性があります。 直接バインドされたオーケストレーションは、XML ドキュメントの処理用のパイプラインに依存しないため、処理前に XML ドキュメント全体がメモリに読み込まれます。  
  
## <a name="canonical-and-non-canonical-xpath"></a>正規 XPath と非正規 XPath  
 標準または XPath の省略形は、XPath 仕様から省略構文を使用して ([http://www.w3.org/TR/xpath](http://go.microsoft.com/fwlink/?LinkId=119567)) の場所のパスを指定します。 正規 XPath 式の一部の識別に役立つプロパティは次のとおりです。  
  
-   `child::` 軸は、既定では式の各ステップに使用されます。  
  
-   `@` は、`attribute::` の短縮形です。  
  
-   `//` は、`/descendant-or-self::node()/` の短縮形です。  
  
-   `.` は、`self::node()` の短縮形です。  
  
-   `..` は、`parent::node()` の短縮形です。  
  
 正規 XPath 式は、`/*[local-name()='element-name' and namespaceURI()='http://MyUri.org']/*[local-name()='element-name']/@*[local-name='attribute-name']` のような単純式です。  
  
 正規 XPath 式は XPath の非正規形と対比できます。 正規 XPath 式は、"一般形式" または "任意の XPath" とも呼ばれ、任意の複雑な式および複数の軸を組み合わせる式 (`//element-name//*[local-name()='element-name' and position()=2]` など) とは区別されます。  
  
## <a name="example"></a>例  
 次のプログラムを考慮してください。  
  
```  
using System;  
using System.IO;  
using System.Xml.Serialization;  
using Microsoft.XLANGs.BaseTypes;  
  
namespace ComplexNetXPath  
{  
    public class Animal  
    {  
        [Property( typeof(BTS.RetryCount) )]  
        public int NumberOfLegs;  
    }   
    public class Snake : Animal  
    {  
        public Snake()  
        {  
            NumberOfLegs = 0;  
        }  
    }   
    public class Dog : Animal  
    {  
        public Dog()  
        {  
            NumberOfLegs = 4;  
        }  
    }   
    public class Zoo  
    {  
        //  
        // Dogs and snakes are the possible animals of  
        // the week.  
        //  
        [XmlElement(typeof(Snake))]  
        [XmlElement(typeof(Dog))]  
        public Animal AnimalOfTheWeek;  
    }  
    class Class1  
    {  
        static void Main(string[] args)  
        {  
            XmlSerializer ser = new XmlSerializer(typeof(Zoo));  
            Stream s = Console.OpenStandardOutput();  
            Zoo z = new Zoo();  
            z.AnimalOfTheWeek = new Dog();  
            ser.Serialize( s, z );  
            s.Flush();  
            Console.WriteLine("------------------");  
            z.AnimalOfTheWeek = new Snake();  
            ser.Serialize( s, z );  
            s.Flush();  
        }  
    }  
}   
```  
  
 Zoo 型には、Snake または Dog の場合がある Animal フィールドが含まれます。 Animal インスタンスには、NumberOfLegs フィールド に BTS.RetryCount プロパティを割り当てる PropertyAttribute によって注釈が付けられた、NumberOfLegs フィールドがあります。  
  
> [!NOTE]
>  実際のアプリケーションでは、独自のプロパティを定義します。  
  
 ある週の動物 (AnimalOfTheWeek) が犬 (Dog) である場合、シリアル化された Zoo インスタンスは次のようになります。  
  
```  
<Zoo>  
  <Dog>  
    <NumberOfLegs>4</NumberOfLegs>  
  </Dog>  
</Zoo>   
```  
  
 ある週の動物 (AnimalOfTheWeek) がヘビ (Snake) である場合、シリアル化された Zoo インスタンスは次のようになります。  
  
```  
<Zoo>  
  <Snake>  
    <NumberOfLegs>0</NumberOfLegs>  
  </Snake>  
</Zoo>  
```  
  
 .Net の Zoo クラスと同等の XML スキーマを考えると、RetryCount プロパティを選択するための XPath 式で、Snake ステップまたは Dog ステップをプロパティへのパスに示すことができます。  
  
```  
/*[local-name()='Zoo' and namespace-uri()='']/*[(local-name()='Dog' and namespace-uri()='') or (local-name()='Snake' and namespace-uri()='')]/*[local-name()='NumberOfLegs' and namespace-uri()='']  
```  
  
 XML パイプライン コンポーネントでは、この非正規 XPath 式を処理できません。 このような状況を回避するには、複数の選択肢がある XML シリアル化属性を XML パイプラインと共に使用しないでください。次の XML シリアル化属性を使用するときには注意が必要です。  
  
-   XmlElementAttribute  
  
-   XmlAttributeAttribute  
  
-   XmlArrayItemAttribute
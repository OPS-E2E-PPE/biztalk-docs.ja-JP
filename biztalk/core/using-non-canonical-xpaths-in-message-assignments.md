---
title: メッセージ割り当てにおける非正規 Xpath の使用 |Microsoft Docs
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
ms.openlocfilehash: 2402b3b95e9eb12d3362f018a197dc6cbc602020
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395410"
---
# <a name="using-non-canonical-xpaths-in-message-assignments"></a>メッセージ割り当てにおける非正規 Xpath の使用
場合も、XML シリアル化属性の使用によるコードの注釈を設定することは .Net メッセージの部分を使用する場合は、識別フィールドやプロパティ注釈と共に、非常に複雑な XPath 式で結果ことができます。 これらの複雑な XPath 式になるは非正規ことができます。 非正規 XPath は、直接バインドされたオーケストレーションでのみ使用する必要があり、論理的または物理的にバインドされたオーケストレーションで失敗する可能性があります。 直接バインドされたオーケストレーションは、XML ドキュメントを処理するためのパイプラインには依存しません。その結果、XML ドキュメント全体が処理する前にメモリに読み込まれます。  
  
## <a name="canonical-and-non-canonical-xpath"></a>標準および非正規 XPath  
 または正規 XPath の短い形式は、XPath 仕様から省略構文を使用して ([http://www.w3.org/TR/xpath](http://go.microsoft.com/fwlink/?LinkId=119567)) の場所のパスを指定します。 正規 XPath 式の一部の特徴的なプロパティは次のとおりです。  
  
- `child::`軸は既定では、式の各ステップと見なされます。  
  
- `@` 省略形は`attribute::`します。  
  
- `//` 省略形は`/descendant-or-self::node()/`します。  
  
- `.` 省略形は`self::node()`します。  
  
- `..` 省略形は`parent::node()`します。  
  
  正規 XPath 式の単純な式として`/*[local-name()='element-name' and namespaceURI()='http://MyUri.org']/*[local-name()='element-name']/@*[local-name='attribute-name']`します。  
  
  これは、XPath の非正規の形式と対照的ことができます。 このフォームは、「一般形式」または"任意の XPath"とも呼ばれます、式を任意に複雑で、複数の軸を組み合わせることもできますは区別:`//element-name//*[local-name()='element-name' and position()=2]`します。  
  
## <a name="example"></a>例  
 次のプログラムを検討してください。  
  
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
  
 Zoo 型には、Snake または Dog、可能性のある Animal フィールドが含まれています。 Animal インスタンスには、BTS 割り当てる propertyattribute によって注釈が付けられた、NumberOfLegs フィールドがあります。このフィールドに RetryCount プロパティです。  
  
> [!NOTE]
>  実際のアプリケーションは、独自のプロパティを定義します。  
  
 週の動物には、犬が、シリアル化された Zoo インスタンスはようになります。  
  
```  
<Zoo>  
  <Dog>  
    <NumberOfLegs>4</NumberOfLegs>  
  </Dog>  
</Zoo>   
```  
  
 週の動物がヘビの場合は、シリアル化された Zoo インスタンスはようになります。  
  
```  
<Zoo>  
  <Snake>  
    <NumberOfLegs>0</NumberOfLegs>  
  </Snake>  
</Zoo>  
```  
  
 .Net と同じ Xml スキーマを検討して Zoo クラス、RetryCount プロパティを選択するための XPath 式により、Snake または Dog ステップのプロパティへのパスに表示します。  
  
```  
/*[local-name()='Zoo' and namespace-uri()='']/*[(local-name()='Dog' and namespace-uri()='') or (local-name()='Snake' and namespace-uri()='')]/*[local-name()='NumberOfLegs' and namespace-uri()='']  
```  
  
 XML パイプライン コンポーネントは、この非正規 XPath 式を処理できません。 このような状況を避けるためには、複数選択の属性の Xml シリアル化する必要がありますいない使用 XML パイプラインと共にと次の xml シリアル化属性を使用するときに、注意を実行する必要があります。  
  
-   XmlElementAttribute  
  
-   XmlAttributeAttribute  
  
-   XmlArrayItemAttribute
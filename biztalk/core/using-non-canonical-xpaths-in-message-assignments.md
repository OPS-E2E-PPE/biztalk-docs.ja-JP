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
# <a name="using-non-canonical-xpaths-in-message-assignments"></a><span data-ttu-id="2a68e-102">メッセージ割り当てにおける非正規 Xpath の使用</span><span class="sxs-lookup"><span data-stu-id="2a68e-102">Using Non-Canonical XPaths in Message Assignments</span></span>
<span data-ttu-id="2a68e-103">場合も、XML シリアル化属性の使用によるコードの注釈を設定することは .Net メッセージの部分を使用する場合は、識別フィールドやプロパティ注釈と共に、非常に複雑な XPath 式で結果ことができます。</span><span class="sxs-lookup"><span data-stu-id="2a68e-103">If you use .Net message parts, it is possible to annotate your code with the XML serialization attribute that, when also accompanied by distinguished fields and/or property annotations, can result in fairly complex XPath expressions.</span></span> <span data-ttu-id="2a68e-104">これらの複雑な XPath 式になるは非正規ことができます。</span><span class="sxs-lookup"><span data-stu-id="2a68e-104">It is possible that these complex XPath expressions will be non-canonical.</span></span> <span data-ttu-id="2a68e-105">非正規 XPath は、直接バインドされたオーケストレーションでのみ使用する必要があり、論理的または物理的にバインドされたオーケストレーションで失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2a68e-105">Non-canonical XPath should only be used in direct bound orchestrations and may fail with logically or physically bound orchestrations.</span></span> <span data-ttu-id="2a68e-106">直接バインドされたオーケストレーションは、XML ドキュメントを処理するためのパイプラインには依存しません。その結果、XML ドキュメント全体が処理する前にメモリに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="2a68e-106">Direct bound orchestrations do not rely on a pipeline for processing the XML document; as a result, the entire XML document is loaded in memory prior to processing.</span></span>  
  
## <a name="canonical-and-non-canonical-xpath"></a><span data-ttu-id="2a68e-107">標準および非正規 XPath</span><span class="sxs-lookup"><span data-stu-id="2a68e-107">Canonical and Non-Canonical XPath</span></span>  
 <span data-ttu-id="2a68e-108">または正規 XPath の短い形式は、XPath 仕様から省略構文を使用して ([http://www.w3.org/TR/xpath](http://go.microsoft.com/fwlink/?LinkId=119567)) の場所のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="2a68e-108">The canonical or short-form of XPath uses the abbreviated syntax from the XPath specification ([http://www.w3.org/TR/xpath](http://go.microsoft.com/fwlink/?LinkId=119567)) to specify a location path.</span></span> <span data-ttu-id="2a68e-109">正規 XPath 式の一部の特徴的なプロパティは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2a68e-109">Some distinguishing properties of canonical XPath expressions include:</span></span>  
  
- <span data-ttu-id="2a68e-110">`child::`軸は既定では、式の各ステップと見なされます。</span><span class="sxs-lookup"><span data-stu-id="2a68e-110">The `child::` axis is assumed by default for each step of the expression</span></span>  
  
- <span data-ttu-id="2a68e-111">`@` 省略形は`attribute::`します。</span><span class="sxs-lookup"><span data-stu-id="2a68e-111">`@` is short for `attribute::`.</span></span>  
  
- <span data-ttu-id="2a68e-112">`//` 省略形は`/descendant-or-self::node()/`します。</span><span class="sxs-lookup"><span data-stu-id="2a68e-112">`//` is short for `/descendant-or-self::node()/`.</span></span>  
  
- <span data-ttu-id="2a68e-113">`.` 省略形は`self::node()`します。</span><span class="sxs-lookup"><span data-stu-id="2a68e-113">`.` is short for `self::node()`.</span></span>  
  
- <span data-ttu-id="2a68e-114">`..` 省略形は`parent::node()`します。</span><span class="sxs-lookup"><span data-stu-id="2a68e-114">`..` is short for `parent::node()`.</span></span>  
  
  <span data-ttu-id="2a68e-115">正規 XPath 式の単純な式として`/*[local-name()='element-name' and namespaceURI()='http://MyUri.org']/*[local-name()='element-name']/@*[local-name='attribute-name']`します。</span><span class="sxs-lookup"><span data-stu-id="2a68e-115">Canonical XPath expressions are simple expressions such as `/*[local-name()='element-name' and namespaceURI()='http://MyUri.org']/*[local-name()='element-name']/@*[local-name='attribute-name']`.</span></span>  
  
  <span data-ttu-id="2a68e-116">これは、XPath の非正規の形式と対照的ことができます。</span><span class="sxs-lookup"><span data-stu-id="2a68e-116">This can be contrasted with the non-canonical form of XPath.</span></span> <span data-ttu-id="2a68e-117">このフォームは、「一般形式」または"任意の XPath"とも呼ばれます、式を任意に複雑で、複数の軸を組み合わせることもできますは区別:`//element-name//*[local-name()='element-name' and position()=2]`します。</span><span class="sxs-lookup"><span data-stu-id="2a68e-117">This form is also known as the "general form" or "arbitrary XPath" and is distinguished by expressions that are arbitrarily complex and may combine multiple axes: `//element-name//*[local-name()='element-name' and position()=2]`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a68e-118">例</span><span class="sxs-lookup"><span data-stu-id="2a68e-118">Example</span></span>  
 <span data-ttu-id="2a68e-119">次のプログラムを検討してください。</span><span class="sxs-lookup"><span data-stu-id="2a68e-119">Consider the following program:</span></span>  
  
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
  
 <span data-ttu-id="2a68e-120">Zoo 型には、Snake または Dog、可能性のある Animal フィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2a68e-120">The Zoo type contains an Animal field that may be either a Snake or a Dog.</span></span> <span data-ttu-id="2a68e-121">Animal インスタンスには、BTS 割り当てる propertyattribute によって注釈が付けられた、NumberOfLegs フィールドがあります。このフィールドに RetryCount プロパティです。</span><span class="sxs-lookup"><span data-stu-id="2a68e-121">The Animal instance has a NumberOfLegs field that is annotated with the PropertyAttribute which assigns the BTS.RetryCount property to this field.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a68e-122">実際のアプリケーションは、独自のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="2a68e-122">A real application would define its own properties.</span></span>  
  
 <span data-ttu-id="2a68e-123">週の動物には、犬が、シリアル化された Zoo インスタンスはようになります。</span><span class="sxs-lookup"><span data-stu-id="2a68e-123">When the animal of the week is a dog, the serialized Zoo instance looks like this:</span></span>  
  
```  
<Zoo>  
  <Dog>  
    <NumberOfLegs>4</NumberOfLegs>  
  </Dog>  
</Zoo>   
```  
  
 <span data-ttu-id="2a68e-124">週の動物がヘビの場合は、シリアル化された Zoo インスタンスはようになります。</span><span class="sxs-lookup"><span data-stu-id="2a68e-124">When the animal of the week is a snake, the serialized Zoo instance looks like this:</span></span>  
  
```  
<Zoo>  
  <Snake>  
    <NumberOfLegs>0</NumberOfLegs>  
  </Snake>  
</Zoo>  
```  
  
 <span data-ttu-id="2a68e-125">.Net と同じ Xml スキーマを検討して Zoo クラス、RetryCount プロパティを選択するための XPath 式により、Snake または Dog ステップのプロパティへのパスに表示します。</span><span class="sxs-lookup"><span data-stu-id="2a68e-125">Considering the Xml schema equivalent to the .Net Zoo class, the XPath expression for selecting the RetryCount property would allow for either a Snake or a Dog step to appear on the path to the property:</span></span>  
  
```  
/*[local-name()='Zoo' and namespace-uri()='']/*[(local-name()='Dog' and namespace-uri()='') or (local-name()='Snake' and namespace-uri()='')]/*[local-name()='NumberOfLegs' and namespace-uri()='']  
```  
  
 <span data-ttu-id="2a68e-126">XML パイプライン コンポーネントは、この非正規 XPath 式を処理できません。</span><span class="sxs-lookup"><span data-stu-id="2a68e-126">The XML pipeline components cannot handle this non-canonical XPath expression.</span></span> <span data-ttu-id="2a68e-127">このような状況を避けるためには、複数選択の属性の Xml シリアル化する必要がありますいない使用 XML パイプラインと共にと次の xml シリアル化属性を使用するときに、注意を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a68e-127">To avoid this situation, multiple-choice Xml serialization attributes should not be used in conjunction with the XML pipelines and care should be taken when using the following xml serialization attributes:</span></span>  
  
-   <span data-ttu-id="2a68e-128">XmlElementAttribute</span><span class="sxs-lookup"><span data-stu-id="2a68e-128">XmlElementAttribute</span></span>  
  
-   <span data-ttu-id="2a68e-129">XmlAttributeAttribute</span><span class="sxs-lookup"><span data-stu-id="2a68e-129">XmlAttributeAttribute</span></span>  
  
-   <span data-ttu-id="2a68e-130">XmlArrayItemAttribute</span><span class="sxs-lookup"><span data-stu-id="2a68e-130">XmlArrayItemAttribute</span></span>
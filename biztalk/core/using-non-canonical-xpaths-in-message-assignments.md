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
ms.openlocfilehash: f35d946ff595fa4d85427c7b3d6be81247cedf68
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977861"
---
# <a name="using-non-canonical-xpaths-in-message-assignments"></a><span data-ttu-id="b494f-102">メッセージ割り当てにおける非正規 XPath の使用</span><span class="sxs-lookup"><span data-stu-id="b494f-102">Using Non-Canonical XPaths in Message Assignments</span></span>
<span data-ttu-id="b494f-103">.Net メッセージの部分を使用すると、XML シリアル化属性によってコードに注釈を付けることができますが、識別フィールドやプロパティ注釈も伴う場合、非常に複雑な XPath 式になります。</span><span class="sxs-lookup"><span data-stu-id="b494f-103">If you use .Net message parts, it is possible to annotate your code with the XML serialization attribute that, when also accompanied by distinguished fields and/or property annotations, can result in fairly complex XPath expressions.</span></span> <span data-ttu-id="b494f-104">これらの複雑な XPath 式は非正規にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b494f-104">It is possible that these complex XPath expressions will be non-canonical.</span></span> <span data-ttu-id="b494f-105">非正規 XPath は、直接バインドされたオーケストレーションでのみ使用する必要があります。論理的または物理的にバインドされたオーケストレーションでは失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b494f-105">Non-canonical XPath should only be used in direct bound orchestrations and may fail with logically or physically bound orchestrations.</span></span> <span data-ttu-id="b494f-106">直接バインドされたオーケストレーションは、XML ドキュメントの処理用のパイプラインに依存しないため、処理前に XML ドキュメント全体がメモリに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="b494f-106">Direct bound orchestrations do not rely on a pipeline for processing the XML document; as a result, the entire XML document is loaded in memory prior to processing.</span></span>  
  
## <a name="canonical-and-non-canonical-xpath"></a><span data-ttu-id="b494f-107">正規 XPath と非正規 XPath</span><span class="sxs-lookup"><span data-stu-id="b494f-107">Canonical and Non-Canonical XPath</span></span>  
 <span data-ttu-id="b494f-108">または正規 XPath の短い形式は、XPath 仕様から省略構文を使用して ([http://www.w3.org/TR/xpath](http://go.microsoft.com/fwlink/?LinkId=119567)) の場所のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b494f-108">The canonical or short-form of XPath uses the abbreviated syntax from the XPath specification ([http://www.w3.org/TR/xpath](http://go.microsoft.com/fwlink/?LinkId=119567)) to specify a location path.</span></span> <span data-ttu-id="b494f-109">正規 XPath 式の一部の特徴的なプロパティは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b494f-109">Some distinguishing properties of canonical XPath expressions include:</span></span>  
  
- <span data-ttu-id="b494f-110">`child::` 軸は、既定では式の各ステップに使用されます。</span><span class="sxs-lookup"><span data-stu-id="b494f-110">The `child::` axis is assumed by default for each step of the expression</span></span>  
  
- <span data-ttu-id="b494f-111">`@` は、`attribute::` の短縮形です。</span><span class="sxs-lookup"><span data-stu-id="b494f-111">`@` is short for `attribute::`.</span></span>  
  
- <span data-ttu-id="b494f-112">`//` は、`/descendant-or-self::node()/` の短縮形です。</span><span class="sxs-lookup"><span data-stu-id="b494f-112">`//` is short for `/descendant-or-self::node()/`.</span></span>  
  
- <span data-ttu-id="b494f-113">`.` は、`self::node()` の短縮形です。</span><span class="sxs-lookup"><span data-stu-id="b494f-113">`.` is short for `self::node()`.</span></span>  
  
- <span data-ttu-id="b494f-114">`..` は、`parent::node()` の短縮形です。</span><span class="sxs-lookup"><span data-stu-id="b494f-114">`..` is short for `parent::node()`.</span></span>  
  
  <span data-ttu-id="b494f-115">正規 XPath 式は、`/*[local-name()='element-name' and namespaceURI()='http://MyUri.org']/*[local-name()='element-name']/@*[local-name='attribute-name']` のような単純式です。</span><span class="sxs-lookup"><span data-stu-id="b494f-115">Canonical XPath expressions are simple expressions such as `/*[local-name()='element-name' and namespaceURI()='http://MyUri.org']/*[local-name()='element-name']/@*[local-name='attribute-name']`.</span></span>  
  
  <span data-ttu-id="b494f-116">正規 XPath 式は XPath の非正規形と対比できます。</span><span class="sxs-lookup"><span data-stu-id="b494f-116">This can be contrasted with the non-canonical form of XPath.</span></span> <span data-ttu-id="b494f-117">正規 XPath 式は、"一般形式" または "任意の XPath" とも呼ばれ、任意の複雑な式および複数の軸を組み合わせる式 (`//element-name//*[local-name()='element-name' and position()=2]` など) とは区別されます。</span><span class="sxs-lookup"><span data-stu-id="b494f-117">This form is also known as the "general form" or "arbitrary XPath" and is distinguished by expressions that are arbitrarily complex and may combine multiple axes: `//element-name//*[local-name()='element-name' and position()=2]`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b494f-118">例</span><span class="sxs-lookup"><span data-stu-id="b494f-118">Example</span></span>  
 <span data-ttu-id="b494f-119">次のプログラムを検討してください。</span><span class="sxs-lookup"><span data-stu-id="b494f-119">Consider the following program:</span></span>  
  
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
  
 <span data-ttu-id="b494f-120">Zoo 型には、Snake または Dog の場合がある Animal フィールドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b494f-120">The Zoo type contains an Animal field that may be either a Snake or a Dog.</span></span> <span data-ttu-id="b494f-121">Animal インスタンスには、NumberOfLegs フィールド に BTS.RetryCount プロパティを割り当てる PropertyAttribute によって注釈が付けられた、NumberOfLegs フィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="b494f-121">The Animal instance has a NumberOfLegs field that is annotated with the PropertyAttribute which assigns the BTS.RetryCount property to this field.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b494f-122">実際のアプリケーションでは、独自のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="b494f-122">A real application would define its own properties.</span></span>  
  
 <span data-ttu-id="b494f-123">ある週の動物 (AnimalOfTheWeek) が犬 (Dog) である場合、シリアル化された Zoo インスタンスは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b494f-123">When the animal of the week is a dog, the serialized Zoo instance looks like this:</span></span>  
  
```  
<Zoo>  
  <Dog>  
    <NumberOfLegs>4</NumberOfLegs>  
  </Dog>  
</Zoo>   
```  
  
 <span data-ttu-id="b494f-124">ある週の動物 (AnimalOfTheWeek) がヘビ (Snake) である場合、シリアル化された Zoo インスタンスは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b494f-124">When the animal of the week is a snake, the serialized Zoo instance looks like this:</span></span>  
  
```  
<Zoo>  
  <Snake>  
    <NumberOfLegs>0</NumberOfLegs>  
  </Snake>  
</Zoo>  
```  
  
 <span data-ttu-id="b494f-125">.Net の Zoo クラスと同等の XML スキーマを考えると、RetryCount プロパティを選択するための XPath 式で、Snake ステップまたは Dog ステップをプロパティへのパスに示すことができます。</span><span class="sxs-lookup"><span data-stu-id="b494f-125">Considering the Xml schema equivalent to the .Net Zoo class, the XPath expression for selecting the RetryCount property would allow for either a Snake or a Dog step to appear on the path to the property:</span></span>  
  
```  
/*[local-name()='Zoo' and namespace-uri()='']/*[(local-name()='Dog' and namespace-uri()='') or (local-name()='Snake' and namespace-uri()='')]/*[local-name()='NumberOfLegs' and namespace-uri()='']  
```  
  
 <span data-ttu-id="b494f-126">XML パイプライン コンポーネントでは、この非正規 XPath 式を処理できません。</span><span class="sxs-lookup"><span data-stu-id="b494f-126">The XML pipeline components cannot handle this non-canonical XPath expression.</span></span> <span data-ttu-id="b494f-127">このような状況を回避するには、複数の選択肢がある XML シリアル化属性を XML パイプラインと共に使用しないでください。次の XML シリアル化属性を使用するときには注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="b494f-127">To avoid this situation, multiple-choice Xml serialization attributes should not be used in conjunction with the XML pipelines and care should be taken when using the following xml serialization attributes:</span></span>  
  
-   <span data-ttu-id="b494f-128">XmlElementAttribute</span><span class="sxs-lookup"><span data-stu-id="b494f-128">XmlElementAttribute</span></span>  
  
-   <span data-ttu-id="b494f-129">XmlAttributeAttribute</span><span class="sxs-lookup"><span data-stu-id="b494f-129">XmlAttributeAttribute</span></span>  
  
-   <span data-ttu-id="b494f-130">XmlArrayItemAttribute</span><span class="sxs-lookup"><span data-stu-id="b494f-130">XmlArrayItemAttribute</span></span>
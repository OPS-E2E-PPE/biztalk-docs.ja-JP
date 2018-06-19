---
title: メッセージ割り当てにおける Xpath の使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XPaths, XPath function
- XPaths, messages
- code samples, XPaths
- messages, XPaths
- XPath function
- XPaths, code samples
- XPaths, nodes
ms.assetid: f2e12409-bb77-4315-b03b-5c7736ae51d5
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9ec1e5b56f382601c79324df8651c91c483cb4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288114"
---
# <a name="using-xpaths-in-message-assignments"></a><span data-ttu-id="3e132-102">メッセージ割り当てにおける Xpath の使用</span><span class="sxs-lookup"><span data-stu-id="3e132-102">Using XPaths in Message Assignments</span></span>
<span data-ttu-id="3e132-103">使用することができます、 **xpath** XPath 値をメッセージ部分に割り当てるか、メッセージ部分を参照する XPath に値を代入する関数。</span><span class="sxs-lookup"><span data-stu-id="3e132-103">You can use the **xpath** function to assign an XPath value to a message part, or to assign a value to an XPath that refers to a message part.</span></span> <span data-ttu-id="3e132-104">メッセージおよびメッセージ部分に割り当てる方法に関する詳細については、次を参照してください。[メッセージの構築](../core/constructing-messages.md)です。</span><span class="sxs-lookup"><span data-stu-id="3e132-104">For more information on assigning to messages and message parts, see [Constructing Messages](../core/constructing-messages.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3e132-105">xpath 関数の詳細については、XML パス言語 (XPath) についてのサード パーティのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e132-105">For more information on the xpath function, see third-party documentation on the XML Path Language (XPath).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3e132-106">使用、 **xpath**関数は、メッセージの割り当てに制限することはありません。</span><span class="sxs-lookup"><span data-stu-id="3e132-106">The use of the **xpath** function is not limited to message assignment.</span></span> <span data-ttu-id="3e132-107">たとえば、次のように、任意の式で使用することができます。</span><span class="sxs-lookup"><span data-stu-id="3e132-107">You can also use it in any expression, for example:</span></span>  
  
```  
If ((System.Double) xpath(_RequestMessage.part, "number(//book[last()]/price)") == 75.00 && (System.Boolean) xpath(msgBoolean, "string(//boolean)") == false)...  
```  
  
> [!NOTE]
>  <span data-ttu-id="3e132-108">値を文字列に割り当てる場合は、XPath string() 関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="3e132-108">If you want to assign a value to a string, use the XPath string() function.</span></span> <span data-ttu-id="3e132-109">例:</span><span class="sxs-lookup"><span data-stu-id="3e132-109">For example:</span></span>  
  
```  
myString = xpath(msg, "string(/*/book[1]/title)");  
```  
  
> [!NOTE]
>  <span data-ttu-id="3e132-110">エンジンではスキーマが認識されないため、メッセージ内に含まれるノード (完全パスが必要) に対する値の読み取りまたは書き込み操作のみを行うことができます。それ以外の場合は、エンジンで例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="3e132-110">The engine is not schema-aware, so you can only read values from or write values to a node that exists in the containing message (the complete path must exist), or the engine will raise an exception.</span></span> <span data-ttu-id="3e132-111">これは、既定値を指定した場合にも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="3e132-111">This is true even if you supply a default value.</span></span>  
  
## <a name="assigning-to-an-xpath-in-a-message-part"></a><span data-ttu-id="3e132-112">メッセージ部分の XPath への割り当て</span><span class="sxs-lookup"><span data-stu-id="3e132-112">Assigning to an XPath in a message part</span></span>  
 <span data-ttu-id="3e132-113">次のスキーマを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="3e132-113">Consider the following schema:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:b="http://schemas.microsoft.com/BizTalk/2003" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="catalog">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element minOccurs="1" maxOccurs="unbounded" name="book">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="title" type="xs:string" />  
              <xs:element name="author">  
                <xs:complexType>  
                  <xs:sequence>  
                    <xs:element name="FirstName" type="xs:string" />  
                    <xs:element name="LastName" type="xs:string" />  
                  </xs:sequence>  
                </xs:complexType>  
              </xs:element>  
              <xs:element name="price" type="xs:string" />  
            </xs:sequence>  
            <xs:attribute name="country" type="xs:string" />  
          </xs:complexType>  
        </xs:element>  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="3e132-114">次のようにして関数を使用すると、このスキーマの種類のドキュメント インスタンスに値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="3e132-114">You can use the  function as follows to set values on a document instance of that schema type:</span></span>  
  
```  
//assumes that a message named _ResponseMessage is already constructed  
_ResponseMessage.part = _RequestMessage.part;  
xpath(_ResponseMessage.part, "/*/book[1]/@country") = "USA";  
xpath(_ResponseMessage.part, "/*/book[1]/title") = "Legends";  
xpath(_ResponseMessage.part, "/*/book[1]/author/FirstName") = "A";  
xpath(_ResponseMessage.part, "/*/book[1]/author/LastName") = "B";  
xpath(_ResponseMessage.part, "/*/book[1]/price") = 50;  
```  
  
## <a name="assigning-to-a-message-part-from-an-xpath"></a><span data-ttu-id="3e132-115">XPath からメッセージ部分への割り当て</span><span class="sxs-lookup"><span data-stu-id="3e132-115">Assigning to a message part from an XPath</span></span>  
  
```  
//assumes that a message named objMessage is already constructed  
objMessage.BooleanPart = xpath("false()");  
objMessage.IntPart = xpath("100");  
objMessage.StringPart = xpath("'Hello'");  
objMessage.StringPart2 = xpath("'World'");  
```  
  
## <a name="using-xpath-to-assign-from-nodes-and-node-sets"></a><span data-ttu-id="3e132-116">XPath を使用したノードおよびノード セットからの割り当て</span><span class="sxs-lookup"><span data-stu-id="3e132-116">Using XPath to assign from nodes and node sets</span></span>  
 <span data-ttu-id="3e132-117">XPath を使用して、XML ノードおよびノード セットを XML 要素、クラス、あるいはスキーマ ベースまたはクラス ベースのメッセージに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="3e132-117">You can also use XPath to assign XML nodes and node sets to an XML element, a class, or a schema-based or class-based message.</span></span>  
  
 <span data-ttu-id="3e132-118">Book という名前の XML シリアル化可能なクラスを使用して、次の例について考えてみます。</span><span class="sxs-lookup"><span data-stu-id="3e132-118">Suppose you have an XML-serializable class called Book, and consider the following examples:</span></span>  
  
```  
[Serializable]  
Class Book {...}  
```  
  
 <span data-ttu-id="3e132-119">例 1 — カタログから 4 番目の book 要素を選択し、XML 要素変数に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3e132-119">Example One — select the fourth book element from the catalog, and assign it to an XML element variable:</span></span>  
  
```  
myXmlElement = xpath(myMsg, "/catalog/book[3]");  
```  
  
 <span data-ttu-id="3e132-120">例 2 — カタログから 4 番目の book 要素を選択し、XML 逆シリアル化を使用して Book クラス インスタンスに変換します。</span><span class="sxs-lookup"><span data-stu-id="3e132-120">Example Two — select the fourth book element from the catalog, and convert it using XML deserialization into a Book class instance:</span></span>  
  
```  
myBook = xpath(myMsg, "/catalog/book[3]");  
```  
  
 <span data-ttu-id="3e132-121">例 3 — カタログから 4 番目の book 要素を選択し、Book という種類のメッセージに変換します。</span><span class="sxs-lookup"><span data-stu-id="3e132-121">Example Three — select the fourth book element from the catalog, and convert it a message of type Book:</span></span>  
  
```  
myBookMsg = xpath(myMsg, "/catalog/book[3]");  
```  
  
 <span data-ttu-id="3e132-122">例 4 — カタログのすべての book 要素を選択します。MyMethod は XmlNodeSet をパラメーターとして受け取ります。</span><span class="sxs-lookup"><span data-stu-id="3e132-122">Example Four — select all book elements in the catalog, where MyMethod takes an XmlNodeSet as a parameter:</span></span>  
  
```  
MyMethod(xpath(myMsg, "/catalog/book"));  
```  
  
 <span data-ttu-id="3e132-123">例 5 — "BookOfTheMonth" コンテナーに book 要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="3e132-123">Example Five — add a book element to the "BookOfTheMonth" container:</span></span>  
  
```  
xpath(MyMsg2, "/RecommendedBooks/BookOfTheMonth") = myBook;  
```  
  
 <span data-ttu-id="3e132-124">例 6 — 価格が 20 以下に設定されているすべての本をお勧めの本のセットに追加します。</span><span class="sxs-lookup"><span data-stu-id="3e132-124">Example Six — add all books that are priced at twenty or less to a set of recommended books:</span></span>  
  
```  
xpath(MyMsg2, "/RecommendedBooks/BestPriceBooks") = xpath(MyMsg, "/catalog/book[@price <= 20]");  
```  
  
 <span data-ttu-id="3e132-125">例 7 — XML 要素を返すユーザー コードを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3e132-125">Example Seven — call user code that returns an XML element:</span></span>  
  
```  
xpath(MyMsg2, "/RecommendedBooks/AdvertisedByPartner") = GetPartnerAdvertisedBook();  
```  
  
 <span data-ttu-id="3e132-126">例 5 および 7 を適用する前は、次のようになっています。</span><span class="sxs-lookup"><span data-stu-id="3e132-126">Before applying examples five and seven:</span></span>  
  
```  
<RecommendedBooks>  
       <BookOfTheMonth/>  
       <BestPriceBooks/>  
       <AdvertisedByPartner/>  
</RecommendedBooks>  
```  
  
 <span data-ttu-id="3e132-127">例 5 および 7 を適用した後は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3e132-127">After applying examples five and seven:</span></span>  
  
```  
<RecommendedBooks>  
       <BookOfTheMonth>  
              <Book country="USA">  
                     <title>McSharry</title>  
                     <author>  
                            <FirstName>Nancy</FirstName>  
                            <LastName>Jensen</LastName>  
                     </author>  
              </Book>  
       </BookOfTheMonth>  
       <BestPriceBooks/>  
       <AdvertisedByPartner>  
              <Book country="USA">  
                     <title>The Rooster</title>  
                     <author>  
                            <FirstName>Mindy</FirstName>  
                            <LastName>Martin</LastName>  
                     </author>  
              </Book>  
       </AdvertisedByPartner>  
</RecommendedBooks>  
```
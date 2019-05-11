---
title: メッセージ割り当てにおける Xpath の使用 |Microsoft Docs
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
ms.openlocfilehash: 18968936cc1271d42fdf490ce2395c437b3ecfd7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396726"
---
# <a name="using-xpaths-in-message-assignments"></a><span data-ttu-id="a51f5-102">メッセージ割り当てにおける Xpath の使用</span><span class="sxs-lookup"><span data-stu-id="a51f5-102">Using XPaths in Message Assignments</span></span>
<span data-ttu-id="a51f5-103">使用することができます、 **xpath**関数、メッセージ部分の XPath 値を割り当てる、またはメッセージ部分を参照する XPath に値を代入します。</span><span class="sxs-lookup"><span data-stu-id="a51f5-103">You can use the **xpath** function to assign an XPath value to a message part, or to assign a value to an XPath that refers to a message part.</span></span> <span data-ttu-id="a51f5-104">メッセージおよびメッセージ部分に割り当てる方法に関する詳細については、次を参照してください。[メッセージの構築](../core/constructing-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="a51f5-104">For more information on assigning to messages and message parts, see [Constructing Messages](../core/constructing-messages.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a51f5-105">Xpath 関数の詳細については、XML Path Language (XPath) でサード パーティのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a51f5-105">For more information on the xpath function, see third-party documentation on the XML Path Language (XPath).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a51f5-106">使用、 **xpath**関数は、メッセージの割り当てに制限することはありません。</span><span class="sxs-lookup"><span data-stu-id="a51f5-106">The use of the **xpath** function is not limited to message assignment.</span></span> <span data-ttu-id="a51f5-107">使える、任意の式の例。</span><span class="sxs-lookup"><span data-stu-id="a51f5-107">You can also use it in any expression, for example:</span></span>  
  
```  
If ((System.Double) xpath(_RequestMessage.part, "number(//book[last()]/price)") == 75.00 && (System.Boolean) xpath(msgBoolean, "string(//boolean)") == false)...  
```  
  
> [!NOTE]
>  <span data-ttu-id="a51f5-108">文字列に値を代入する場合は、XPath string() 関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="a51f5-108">If you want to assign a value to a string, use the XPath string() function.</span></span> <span data-ttu-id="a51f5-109">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a51f5-109">For example:</span></span>  
  
```  
myString = xpath(msg, "string(/*/book[1]/title)");  
```  
  
> [!NOTE]
>  <span data-ttu-id="a51f5-110">エンジンはスキーマに対応していない、メッセージが (完全なパスが存在する必要があります)、または、エンジンによって、例外が発生のみから値を読み取るか、格納先に存在するノードに値を書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="a51f5-110">The engine is not schema-aware, so you can only read values from or write values to a node that exists in the containing message (the complete path must exist), or the engine will raise an exception.</span></span> <span data-ttu-id="a51f5-111">これは、既定値を指定する場合でも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="a51f5-111">This is true even if you supply a default value.</span></span>  
  
## <a name="assigning-to-an-xpath-in-a-message-part"></a><span data-ttu-id="a51f5-112">メッセージ部分の XPath への割り当てください。</span><span class="sxs-lookup"><span data-stu-id="a51f5-112">Assigning to an XPath in a message part</span></span>  
 <span data-ttu-id="a51f5-113">次のスキーマを検討してください。</span><span class="sxs-lookup"><span data-stu-id="a51f5-113">Consider the following schema:</span></span>  
  
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
  
 <span data-ttu-id="a51f5-114">スキーマの種類のドキュメント インスタンスの値を設定するのにには、次のように、関数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a51f5-114">You can use the  function as follows to set values on a document instance of that schema type:</span></span>  
  
```  
//assumes that a message named _ResponseMessage is already constructed  
_ResponseMessage.part = _RequestMessage.part;  
xpath(_ResponseMessage.part, "/*/book[1]/@country") = "USA";  
xpath(_ResponseMessage.part, "/*/book[1]/title") = "Legends";  
xpath(_ResponseMessage.part, "/*/book[1]/author/FirstName") = "A";  
xpath(_ResponseMessage.part, "/*/book[1]/author/LastName") = "B";  
xpath(_ResponseMessage.part, "/*/book[1]/price") = 50;  
```  
  
## <a name="assigning-to-a-message-part-from-an-xpath"></a><span data-ttu-id="a51f5-115">XPath からメッセージ部分への割り当てください。</span><span class="sxs-lookup"><span data-stu-id="a51f5-115">Assigning to a message part from an XPath</span></span>  
  
```  
//assumes that a message named objMessage is already constructed  
objMessage.BooleanPart = xpath("false()");  
objMessage.IntPart = xpath("100");  
objMessage.StringPart = xpath("'Hello'");  
objMessage.StringPart2 = xpath("'World'");  
```  
  
## <a name="using-xpath-to-assign-from-nodes-and-node-sets"></a><span data-ttu-id="a51f5-116">XPath ノードとノードからの割り当てを使用して設定します。</span><span class="sxs-lookup"><span data-stu-id="a51f5-116">Using XPath to assign from nodes and node sets</span></span>  
 <span data-ttu-id="a51f5-117">XML ノードの割り当てを XPath を使用することもでき、ノードが XML 要素、クラス、またはスキーマ ベースまたはクラス ベースのメッセージに設定します。</span><span class="sxs-lookup"><span data-stu-id="a51f5-117">You can also use XPath to assign XML nodes and node sets to an XML element, a class, or a schema-based or class-based message.</span></span>  
  
 <span data-ttu-id="a51f5-118">Book という名前を XML にシリアル化できるクラスがあると仮定して、次の例を検討してください。</span><span class="sxs-lookup"><span data-stu-id="a51f5-118">Suppose you have an XML-serializable class called Book, and consider the following examples:</span></span>  
  
```  
[Serializable]  
Class Book {...}  
```  
  
 <span data-ttu-id="a51f5-119">例 1 — カタログから 4 番目の book 要素を選択し、XML 要素変数に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a51f5-119">Example One — select the fourth book element from the catalog, and assign it to an XML element variable:</span></span>  
  
```  
myXmlElement = xpath(myMsg, "/catalog/book[3]");  
```  
  
 <span data-ttu-id="a51f5-120">例 2 — カタログから 4 番目の book 要素を選択し、Book クラス インスタンスに XML 逆シリアル化を使用して変換します。</span><span class="sxs-lookup"><span data-stu-id="a51f5-120">Example Two — select the fourth book element from the catalog, and convert it using XML deserialization into a Book class instance:</span></span>  
  
```  
myBook = xpath(myMsg, "/catalog/book[3]");  
```  
  
 <span data-ttu-id="a51f5-121">例 3 — カタログから 4 番目の book 要素を選択し、book という種類のメッセージを変換します。</span><span class="sxs-lookup"><span data-stu-id="a51f5-121">Example Three — select the fourth book element from the catalog, and convert it a message of type Book:</span></span>  
  
```  
myBookMsg = xpath(myMsg, "/catalog/book[3]");  
```  
  
 <span data-ttu-id="a51f5-122">例 4 — MyMethod、XmlNodeSet をパラメーターとしては、場所、カタログのすべての book 要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="a51f5-122">Example Four — select all book elements in the catalog, where MyMethod takes an XmlNodeSet as a parameter:</span></span>  
  
```  
MyMethod(xpath(myMsg, "/catalog/book"));  
```  
  
 <span data-ttu-id="a51f5-123">例 5 —"BookOfTheMonth"コンテナーに book 要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="a51f5-123">Example Five — add a book element to the "BookOfTheMonth" container:</span></span>  
  
```  
xpath(MyMsg2, "/RecommendedBooks/BookOfTheMonth") = myBook;  
```  
  
 <span data-ttu-id="a51f5-124">例 6 — 価格の 20 個推奨ブック セットを以下であるすべての書籍を追加します。</span><span class="sxs-lookup"><span data-stu-id="a51f5-124">Example Six — add all books that are priced at twenty or less to a set of recommended books:</span></span>  
  
```  
xpath(MyMsg2, "/RecommendedBooks/BestPriceBooks") = xpath(MyMsg, "/catalog/book[@price <= 20]");  
```  
  
 <span data-ttu-id="a51f5-125">例 7 — XML 要素を返すユーザー コードを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a51f5-125">Example Seven — call user code that returns an XML element:</span></span>  
  
```  
xpath(MyMsg2, "/RecommendedBooks/AdvertisedByPartner") = GetPartnerAdvertisedBook();  
```  
  
 <span data-ttu-id="a51f5-126">例 5 および 7 を適用するには。</span><span class="sxs-lookup"><span data-stu-id="a51f5-126">Before applying examples five and seven:</span></span>  
  
```  
<RecommendedBooks>  
       <BookOfTheMonth/>  
       <BestPriceBooks/>  
       <AdvertisedByPartner/>  
</RecommendedBooks>  
```  
  
 <span data-ttu-id="a51f5-127">例 5 および 7 を適用するには: した後</span><span class="sxs-lookup"><span data-stu-id="a51f5-127">After applying examples five and seven:</span></span>  
  
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
---
title: "メッセージ割り当てにおける Xpath の使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9ec1e5b56f382601c79324df8651c91c483cb4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-xpaths-in-message-assignments"></a>メッセージ割り当てにおける Xpath の使用
使用することができます、 **xpath** XPath 値をメッセージ部分に割り当てるか、メッセージ部分を参照する XPath に値を代入する関数。 メッセージおよびメッセージ部分に割り当てる方法に関する詳細については、次を参照してください。[メッセージの構築](../core/constructing-messages.md)です。  
  
> [!NOTE]
>  xpath 関数の詳細については、XML パス言語 (XPath) についてのサード パーティのドキュメントを参照してください。  
  
> [!NOTE]
>  使用、 **xpath**関数は、メッセージの割り当てに制限することはありません。 たとえば、次のように、任意の式で使用することができます。  
  
```  
If ((System.Double) xpath(_RequestMessage.part, "number(//book[last()]/price)") == 75.00 && (System.Boolean) xpath(msgBoolean, "string(//boolean)") == false)...  
```  
  
> [!NOTE]
>  値を文字列に割り当てる場合は、XPath string() 関数を使用します。 例:  
  
```  
myString = xpath(msg, "string(/*/book[1]/title)");  
```  
  
> [!NOTE]
>  エンジンではスキーマが認識されないため、メッセージ内に含まれるノード (完全パスが必要) に対する値の読み取りまたは書き込み操作のみを行うことができます。それ以外の場合は、エンジンで例外が発生します。 これは、既定値を指定した場合にも当てはまります。  
  
## <a name="assigning-to-an-xpath-in-a-message-part"></a>メッセージ部分の XPath への割り当て  
 次のスキーマを考えてみます。  
  
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
  
 次のようにして関数を使用すると、このスキーマの種類のドキュメント インスタンスに値を設定できます。  
  
```  
//assumes that a message named _ResponseMessage is already constructed  
_ResponseMessage.part = _RequestMessage.part;  
xpath(_ResponseMessage.part, "/*/book[1]/@country") = "USA";  
xpath(_ResponseMessage.part, "/*/book[1]/title") = "Legends";  
xpath(_ResponseMessage.part, "/*/book[1]/author/FirstName") = "A";  
xpath(_ResponseMessage.part, "/*/book[1]/author/LastName") = "B";  
xpath(_ResponseMessage.part, "/*/book[1]/price") = 50;  
```  
  
## <a name="assigning-to-a-message-part-from-an-xpath"></a>XPath からメッセージ部分への割り当て  
  
```  
//assumes that a message named objMessage is already constructed  
objMessage.BooleanPart = xpath("false()");  
objMessage.IntPart = xpath("100");  
objMessage.StringPart = xpath("'Hello'");  
objMessage.StringPart2 = xpath("'World'");  
```  
  
## <a name="using-xpath-to-assign-from-nodes-and-node-sets"></a>XPath を使用したノードおよびノード セットからの割り当て  
 XPath を使用して、XML ノードおよびノード セットを XML 要素、クラス、あるいはスキーマ ベースまたはクラス ベースのメッセージに割り当てることもできます。  
  
 Book という名前の XML シリアル化可能なクラスを使用して、次の例について考えてみます。  
  
```  
[Serializable]  
Class Book {...}  
```  
  
 例 1 — カタログから 4 番目の book 要素を選択し、XML 要素変数に割り当てます。  
  
```  
myXmlElement = xpath(myMsg, "/catalog/book[3]");  
```  
  
 例 2 — カタログから 4 番目の book 要素を選択し、XML 逆シリアル化を使用して Book クラス インスタンスに変換します。  
  
```  
myBook = xpath(myMsg, "/catalog/book[3]");  
```  
  
 例 3 — カタログから 4 番目の book 要素を選択し、Book という種類のメッセージに変換します。  
  
```  
myBookMsg = xpath(myMsg, "/catalog/book[3]");  
```  
  
 例 4 — カタログのすべての book 要素を選択します。MyMethod は XmlNodeSet をパラメーターとして受け取ります。  
  
```  
MyMethod(xpath(myMsg, "/catalog/book"));  
```  
  
 例 5 — "BookOfTheMonth" コンテナーに book 要素を追加します。  
  
```  
xpath(MyMsg2, "/RecommendedBooks/BookOfTheMonth") = myBook;  
```  
  
 例 6 — 価格が 20 以下に設定されているすべての本をお勧めの本のセットに追加します。  
  
```  
xpath(MyMsg2, "/RecommendedBooks/BestPriceBooks") = xpath(MyMsg, "/catalog/book[@price <= 20]");  
```  
  
 例 7 — XML 要素を返すユーザー コードを呼び出します。  
  
```  
xpath(MyMsg2, "/RecommendedBooks/AdvertisedByPartner") = GetPartnerAdvertisedBook();  
```  
  
 例 5 および 7 を適用する前は、次のようになっています。  
  
```  
<RecommendedBooks>  
       <BookOfTheMonth/>  
       <BestPriceBooks/>  
       <AdvertisedByPartner/>  
</RecommendedBooks>  
```  
  
 例 5 および 7 を適用した後は、次のようになります。  
  
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
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
# <a name="using-xpaths-in-message-assignments"></a>メッセージ割り当てにおける Xpath の使用
使用することができます、 **xpath**関数、メッセージ部分の XPath 値を割り当てる、またはメッセージ部分を参照する XPath に値を代入します。 メッセージおよびメッセージ部分に割り当てる方法に関する詳細については、次を参照してください。[メッセージの構築](../core/constructing-messages.md)します。  
  
> [!NOTE]
>  Xpath 関数の詳細については、XML Path Language (XPath) でサード パーティのドキュメントを参照してください。  
  
> [!NOTE]
>  使用、 **xpath**関数は、メッセージの割り当てに制限することはありません。 使える、任意の式の例。  
  
```  
If ((System.Double) xpath(_RequestMessage.part, "number(//book[last()]/price)") == 75.00 && (System.Boolean) xpath(msgBoolean, "string(//boolean)") == false)...  
```  
  
> [!NOTE]
>  文字列に値を代入する場合は、XPath string() 関数を使用します。 以下に例を示します。  
  
```  
myString = xpath(msg, "string(/*/book[1]/title)");  
```  
  
> [!NOTE]
>  エンジンはスキーマに対応していない、メッセージが (完全なパスが存在する必要があります)、または、エンジンによって、例外が発生のみから値を読み取るか、格納先に存在するノードに値を書き込むことができます。 これは、既定値を指定する場合でも当てはまります。  
  
## <a name="assigning-to-an-xpath-in-a-message-part"></a>メッセージ部分の XPath への割り当てください。  
 次のスキーマを検討してください。  
  
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
  
 スキーマの種類のドキュメント インスタンスの値を設定するのにには、次のように、関数を使用できます。  
  
```  
//assumes that a message named _ResponseMessage is already constructed  
_ResponseMessage.part = _RequestMessage.part;  
xpath(_ResponseMessage.part, "/*/book[1]/@country") = "USA";  
xpath(_ResponseMessage.part, "/*/book[1]/title") = "Legends";  
xpath(_ResponseMessage.part, "/*/book[1]/author/FirstName") = "A";  
xpath(_ResponseMessage.part, "/*/book[1]/author/LastName") = "B";  
xpath(_ResponseMessage.part, "/*/book[1]/price") = 50;  
```  
  
## <a name="assigning-to-a-message-part-from-an-xpath"></a>XPath からメッセージ部分への割り当てください。  
  
```  
//assumes that a message named objMessage is already constructed  
objMessage.BooleanPart = xpath("false()");  
objMessage.IntPart = xpath("100");  
objMessage.StringPart = xpath("'Hello'");  
objMessage.StringPart2 = xpath("'World'");  
```  
  
## <a name="using-xpath-to-assign-from-nodes-and-node-sets"></a>XPath ノードとノードからの割り当てを使用して設定します。  
 XML ノードの割り当てを XPath を使用することもでき、ノードが XML 要素、クラス、またはスキーマ ベースまたはクラス ベースのメッセージに設定します。  
  
 Book という名前を XML にシリアル化できるクラスがあると仮定して、次の例を検討してください。  
  
```  
[Serializable]  
Class Book {...}  
```  
  
 例 1 — カタログから 4 番目の book 要素を選択し、XML 要素変数に割り当てます。  
  
```  
myXmlElement = xpath(myMsg, "/catalog/book[3]");  
```  
  
 例 2 — カタログから 4 番目の book 要素を選択し、Book クラス インスタンスに XML 逆シリアル化を使用して変換します。  
  
```  
myBook = xpath(myMsg, "/catalog/book[3]");  
```  
  
 例 3 — カタログから 4 番目の book 要素を選択し、book という種類のメッセージを変換します。  
  
```  
myBookMsg = xpath(myMsg, "/catalog/book[3]");  
```  
  
 例 4 — MyMethod、XmlNodeSet をパラメーターとしては、場所、カタログのすべての book 要素を選択します。  
  
```  
MyMethod(xpath(myMsg, "/catalog/book"));  
```  
  
 例 5 —"BookOfTheMonth"コンテナーに book 要素を追加します。  
  
```  
xpath(MyMsg2, "/RecommendedBooks/BookOfTheMonth") = myBook;  
```  
  
 例 6 — 価格の 20 個推奨ブック セットを以下であるすべての書籍を追加します。  
  
```  
xpath(MyMsg2, "/RecommendedBooks/BestPriceBooks") = xpath(MyMsg, "/catalog/book[@price <= 20]");  
```  
  
 例 7 — XML 要素を返すユーザー コードを呼び出します。  
  
```  
xpath(MyMsg2, "/RecommendedBooks/AdvertisedByPartner") = GetPartnerAdvertisedBook();  
```  
  
 例 5 および 7 を適用するには。  
  
```  
<RecommendedBooks>  
       <BookOfTheMonth/>  
       <BestPriceBooks/>  
       <AdvertisedByPartner/>  
</RecommendedBooks>  
```  
  
 例 5 および 7 を適用するには: した後  
  
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
---
title: メッセージは、XSD スキーマとして表される |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Message Assignment shape [Orchestration Designer], maps
- maps, transforms
- Expression Editor, assigning maps
ms.assetid: 646e84d4-1dcc-4f92-9205-84cb6c7df297
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37c15de5c7bbf4c5d8639c1d05a427d48686b58b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324961"
---
# <a name="messages-represented-as-xsd-schemas"></a>XSD スキーマとして表されるメッセージ
XSD メッセージの種類のテンプレート XML インスタンスがデザイン時に定義されているし、ディスクに格納されます。 実行時に、.NET コンポーネントはディスクから XML を取得し、XmlDocument として返されます。 オーケストレーション コードでは、オーケストレーションで宣言されているメッセージ インスタンスにこの XmlDocument 結果を割り当てることができます。  
  
 **メッセージの割り当て**形状に 1 行のコードがあります。  
  
```  
MsgOut = CreateMsgHelper.Helper.GetXmlDocumentTemplate();  
```  
  
 XmlDocument を作成するヘルパー コンポーネントには、1 つの静的メソッドがあります。  
  
```  
private static XmlDocument _template = null;  
private static object _sync = new object();  
private static String LOCATION = @"C:\MyTemplateLocation\MyMsgTemplate.xml";  
  
public static XmlDocument GetXmlDocumentTemplate()  
{  
   XmlDocument doc = _template;  
   if (doc == null)  
   {  
      // Load the doc template from disk.  
      doc = new XmlDocument();  
      XmlTextReader reader = new XmlTextReader(LOCATION);  
      doc.Load(reader);  
  
      // Synchronize assignment to _template.  
      lock (_sync)  
      {  
         XmlDocument doc2 = _template;  
         if (doc2 == null)  
         {  
            _template = doc;  
         }  
         else  
         {  
            // Another thread beat us to it.  
            doc = doc2;  
         }  
      }  
   }  
  
   // Need to explicitly create a clone so that we are not  
   // referencing the same object statically held by this class.  
   doc = (XmlDocument) doc.CloneNode(true);  
   return doc;  
}  
```  
  
## <a name="see-also"></a>参照  
 [.NET クラスとして表されるメッセージ](../core/messages-represented-as-net-classes.md)   
 [XLANGMessage として表されるメッセージ](../core/messages-represented-as-xlangmessage.md)   
 [ユーザー コードでのメッセージの構築](../core/constructing-messages-in-user-code.md)
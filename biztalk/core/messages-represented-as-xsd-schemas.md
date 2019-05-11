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
# <a name="messages-represented-as-xsd-schemas"></a><span data-ttu-id="8ddfe-102">XSD スキーマとして表されるメッセージ</span><span class="sxs-lookup"><span data-stu-id="8ddfe-102">Messages Represented as XSD Schemas</span></span>
<span data-ttu-id="8ddfe-103">XSD メッセージの種類のテンプレート XML インスタンスがデザイン時に定義されているし、ディスクに格納されます。</span><span class="sxs-lookup"><span data-stu-id="8ddfe-103">A template XML instance of the XSD message type is defined at design time and then stored on disk.</span></span> <span data-ttu-id="8ddfe-104">実行時に、.NET コンポーネントはディスクから XML を取得し、XmlDocument として返されます。</span><span class="sxs-lookup"><span data-stu-id="8ddfe-104">At run time, a .NET component picks up the XML from disk and returns it as an XmlDocument.</span></span> <span data-ttu-id="8ddfe-105">オーケストレーション コードでは、オーケストレーションで宣言されているメッセージ インスタンスにこの XmlDocument 結果を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8ddfe-105">The orchestration code can assign this XmlDocument result to the message instance declared in the orchestration.</span></span>  
  
 <span data-ttu-id="8ddfe-106">**メッセージの割り当て**形状に 1 行のコードがあります。</span><span class="sxs-lookup"><span data-stu-id="8ddfe-106">The **Message Assignment** shape has a single line of code:</span></span>  
  
```  
MsgOut = CreateMsgHelper.Helper.GetXmlDocumentTemplate();  
```  
  
 <span data-ttu-id="8ddfe-107">XmlDocument を作成するヘルパー コンポーネントには、1 つの静的メソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="8ddfe-107">The Helper Component that creates the XmlDocument has a single static method:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8ddfe-108">参照</span><span class="sxs-lookup"><span data-stu-id="8ddfe-108">See Also</span></span>  
 <span data-ttu-id="8ddfe-109">[.NET クラスとして表されるメッセージ](../core/messages-represented-as-net-classes.md) </span><span class="sxs-lookup"><span data-stu-id="8ddfe-109">[Messages Represented as .NET Classes](../core/messages-represented-as-net-classes.md) </span></span>  
 <span data-ttu-id="8ddfe-110">[XLANGMessage として表されるメッセージ](../core/messages-represented-as-xlangmessage.md) </span><span class="sxs-lookup"><span data-stu-id="8ddfe-110">[Messages Represented as XLANGMessage](../core/messages-represented-as-xlangmessage.md) </span></span>  
 [<span data-ttu-id="8ddfe-111">ユーザー コードでのメッセージの構築</span><span class="sxs-lookup"><span data-stu-id="8ddfe-111">Constructing Messages in User Code</span></span>](../core/constructing-messages-in-user-code.md)
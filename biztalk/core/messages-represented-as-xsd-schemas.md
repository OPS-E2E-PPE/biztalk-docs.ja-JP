---
title: XSD スキーマとして表されるメッセージ |Microsoft ドキュメント
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
ms.openlocfilehash: 47242dc01ed05ca2ab3c2cb71daffc5a81f9462c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262970"
---
# <a name="messages-represented-as-xsd-schemas"></a><span data-ttu-id="6c5b8-102">XSD スキーマとして表されるメッセージ</span><span class="sxs-lookup"><span data-stu-id="6c5b8-102">Messages Represented as XSD Schemas</span></span>
<span data-ttu-id="6c5b8-103">XSD メッセージの種類のテンプレート XML インスタンスは、デザイン時に定義されてディスクに格納されます。</span><span class="sxs-lookup"><span data-stu-id="6c5b8-103">A template XML instance of the XSD message type is defined at design time and then stored on disk.</span></span> <span data-ttu-id="6c5b8-104">実行時には、XML は .NET コンポーネントによってディスクから取得され、XmlDocument として返されます。</span><span class="sxs-lookup"><span data-stu-id="6c5b8-104">At run time, a .NET component picks up the XML from disk and returns it as an XmlDocument.</span></span> <span data-ttu-id="6c5b8-105">オーケストレーション コードでは、オーケストレーションで宣言されているメッセージ インスタンスに、この XmlDocument 結果を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6c5b8-105">The orchestration code can assign this XmlDocument result to the message instance declared in the orchestration.</span></span>  
  
 <span data-ttu-id="6c5b8-106">**メッセージの割り当て**形状に 1 行のコードがあります。</span><span class="sxs-lookup"><span data-stu-id="6c5b8-106">The **Message Assignment** shape has a single line of code:</span></span>  
  
```  
MsgOut = CreateMsgHelper.Helper.GetXmlDocumentTemplate();  
```  
  
 <span data-ttu-id="6c5b8-107">XmlDocument を作成するヘルパー コンポーネントには、次に示す単一の静的メソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6c5b8-107">The Helper Component that creates the XmlDocument has a single static method:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6c5b8-108">参照</span><span class="sxs-lookup"><span data-stu-id="6c5b8-108">See Also</span></span>  
 <span data-ttu-id="6c5b8-109">[.NET クラスとして表されるメッセージ](../core/messages-represented-as-net-classes.md) </span><span class="sxs-lookup"><span data-stu-id="6c5b8-109">[Messages Represented as .NET Classes](../core/messages-represented-as-net-classes.md) </span></span>  
 <span data-ttu-id="6c5b8-110">[XLANGMessage として表されるメッセージ](../core/messages-represented-as-xlangmessage.md) </span><span class="sxs-lookup"><span data-stu-id="6c5b8-110">[Messages Represented as XLANGMessage](../core/messages-represented-as-xlangmessage.md) </span></span>  
 [<span data-ttu-id="6c5b8-111">ユーザー コードでメッセージの構築</span><span class="sxs-lookup"><span data-stu-id="6c5b8-111">Constructing Messages in User Code</span></span>](../core/constructing-messages-in-user-code.md)
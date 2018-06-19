---
title: .NET クラスとして表されるメッセージ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, expressions
- orchestrations, filters
ms.assetid: cdbea200-552e-4734-a370-2f93da07ea81
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16f0ea95f02de6e9fda411fa0183569dc0779033
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263394"
---
# <a name="messages-represented-as-net-classes"></a><span data-ttu-id="74cc1-102">.NET クラスとして表されるメッセージ</span><span class="sxs-lookup"><span data-stu-id="74cc1-102">Messages Represented as .NET Classes</span></span>
<span data-ttu-id="74cc1-103">この方法ではまず、メッセージの種類を定義する .NET クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="74cc1-103">This approach first involves creating a .NET class that defines your message type.</span></span> <span data-ttu-id="74cc1-104">このクラスには、既定のコンストラクターを指定する必要があります。指定しなかった場合、それを使用するオーケストレーションがコンパイルされません。</span><span class="sxs-lookup"><span data-stu-id="74cc1-104">The class must have a default constructor or the orchestration using it will not compile.</span></span> <span data-ttu-id="74cc1-105">このようなクラスの簡単な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="74cc1-105">A simple example of such a class is shown here.</span></span>  
  
```  
using System;  
using Microsoft.XLANGs.BaseTypes;  
Using PropertyNamespace;  
  
namespace NetClass  
{  
   [Serializable]  
   public class MsgClass  
   {  
      public MsgClass()  
      {  
         StrField = "OK";  
         IntField = 1;  
         ShortField = 1;  
      }  
  
      [PropertyNamespace.ShortPropertyName]  
      public Int16 ShortField;  
  
      [PropertyAttribute(typeof(PropertyNamespace.StringPropertyName)]  
      [DistinguishedFieldAttribute()]  
      public String StrField;  
  
      [DistinguishedFieldAttribute()]  
      public int IntField;  
   }  
}  
```  
  
 <span data-ttu-id="74cc1-106">上の例の ShortField は PropertyNamespace.ShortPropertyName 型のプロパティとなります。このプロパティの基になる型は、ShortField と同じ Int16 型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="74cc1-106">In the above example, ShortField would be a property of type PropertyNamespace.ShortPropertyName and the underlying type of the property would have to be Int16 which is the type of ShortField.</span></span> <span data-ttu-id="74cc1-107">StrField は、識別フィールド、および PropertyNamespace.StringPropertyName 型のプロパティとなります。このプロパティの基になる型は、StrField と同じ String 型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="74cc1-107">StrField would be both a distinguished field and a property of type PropertyNamespace.StringPropertyName and the underlying type of the property would have to be type of String which is the type of StrField.</span></span> <span data-ttu-id="74cc1-108">通常、PropertyNamespace.StringPropertyName と PropertyNamespace.ShortPropertyName は、BizTalk スキーマ エディターを使用してスキーマ プロパティとして作成されます。C# プロジェクトでは、これらのスキーマ プロパティが含まれているアセンブリを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74cc1-108">Normally both PropertyNamespace.StringPropertyName and PropertyNamespace.ShortPropertyName would be created through the BizTalk Schema Editor as schema properties, and you need to reference the assembly which contains the schema properties in your C# project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="74cc1-109">C# プログラミング言語では、属性名の末尾の "Attribute" は省略可能です。したがって、末尾の "Attribute" を省略した "DistinguishedField" や "Property" を代わりに使用できます。</span><span class="sxs-lookup"><span data-stu-id="74cc1-109">In C# programming language, the Attribute ending of an attribute name is optional, so you can omit the Attribute ending and use DistinguishedField or Property instead.</span></span> <span data-ttu-id="74cc1-110">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="74cc1-110">For example,</span></span>  
  
```  
[Property(typeof(PropertyNamespace.StringPropertyName))]  
[DistinguishedField]  
public string StrField;  
```  
  
 <span data-ttu-id="74cc1-111">メッセージの種類をいったん定義したら、この種類のメッセージを新規作成するコードをオーケストレーションに記述するのは非常に簡単です。</span><span class="sxs-lookup"><span data-stu-id="74cc1-111">Once the message type is defined, it is very easy to write code in the orchestration that will create a new message of this type.</span></span> <span data-ttu-id="74cc1-112">内で、**メッセージの構築**図形、単純な式を記述するの新しいメッセージを作成、 **MsgClass** 、上記のように入力し、Distinguished となるフィールドに値を割り当てます(既定値をオーバーライドする場合) のフィールドです。</span><span class="sxs-lookup"><span data-stu-id="74cc1-112">Within a **Construct Message** shape, you write simple expressions to create a new message of the **MsgClass** type shown above, and then assign values to the fields which are attributed as Distinguished Fields (if you wish to override the default values).</span></span> <span data-ttu-id="74cc1-113">MyMsg はオーケストレーション メッセージ変数で、種類は NetClass.MsgClass です。</span><span class="sxs-lookup"><span data-stu-id="74cc1-113">Note that MyMsg is an orchestration message variable whose type is NetClass.MsgClass.</span></span>  
  
```  
MyMsg = new NetClass.MsgClass();  
MyMsg.StrField = "Changed Value";  
MyMsg.IntField = 15;  
```  
  
## <a name="see-also"></a><span data-ttu-id="74cc1-114">参照</span><span class="sxs-lookup"><span data-stu-id="74cc1-114">See Also</span></span>  
 <span data-ttu-id="74cc1-115">[XSD スキーマとして表されるメッセージ](../core/messages-represented-as-xsd-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="74cc1-115">[Messages Represented as XSD Schemas](../core/messages-represented-as-xsd-schemas.md) </span></span>  
 <span data-ttu-id="74cc1-116">[XLANGMessage として表されるメッセージ](../core/messages-represented-as-xlangmessage.md) </span><span class="sxs-lookup"><span data-stu-id="74cc1-116">[Messages Represented as XLANGMessage](../core/messages-represented-as-xlangmessage.md) </span></span>  
 [<span data-ttu-id="74cc1-117">ユーザー コードでメッセージの構築</span><span class="sxs-lookup"><span data-stu-id="74cc1-117">Constructing Messages in User Code</span></span>](../core/constructing-messages-in-user-code.md)
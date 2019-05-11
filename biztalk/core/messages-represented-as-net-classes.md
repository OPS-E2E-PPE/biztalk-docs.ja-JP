---
title: メッセージは、.NET クラスとして表される |Microsoft Docs
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
ms.openlocfilehash: a01e0c5834e117a16541f8dee45218285f05e0f4
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531183"
---
# <a name="messages-represented-as-net-classes"></a><span data-ttu-id="bd2dd-102">.NET クラスとして表されるメッセージ</span><span class="sxs-lookup"><span data-stu-id="bd2dd-102">Messages Represented as .NET Classes</span></span>
<span data-ttu-id="bd2dd-103">このアプローチでは、最初、メッセージの種類を定義する .NET クラスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd2dd-103">This approach first involves creating a .NET class that defines your message type.</span></span> <span data-ttu-id="bd2dd-104">クラスに既定のコンス トラクターが必要か、それを使用して、オーケストレーションはコンパイルされません。</span><span class="sxs-lookup"><span data-stu-id="bd2dd-104">The class must have a default constructor or the orchestration using it will not compile.</span></span> <span data-ttu-id="bd2dd-105">このようなクラスの単純な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bd2dd-105">A simple example of such a class is shown here.</span></span>  
  
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
  
 <span data-ttu-id="bd2dd-106">上記の例では、shortfield と同じになります PropertyNamespace.ShortPropertyName 型のプロパティとプロパティの基になる型が型である Int16 する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd2dd-106">In the above example, ShortField would be a property of type PropertyNamespace.ShortPropertyName and the underlying type of the property would have to be Int16 which is the type of ShortField.</span></span> <span data-ttu-id="bd2dd-107">StrField は、識別フィールドおよび PropertyNamespace.StringPropertyName 型のプロパティの両方には、プロパティの基になる型が文字列、StrField の型の型を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd2dd-107">StrField would be both a distinguished field and a property of type PropertyNamespace.StringPropertyName and the underlying type of the property would have to be type of String which is the type of StrField.</span></span> <span data-ttu-id="bd2dd-108">通常 PropertyNamespace.StringPropertyName と PropertyNamespace.ShortPropertyName は BizTalk スキーマ エディターを使用として作成、スキーマのプロパティと、C#プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="bd2dd-108">Normally both PropertyNamespace.StringPropertyName and PropertyNamespace.ShortPropertyName would be created through the BizTalk Schema Editor as schema properties, and you need to reference the assembly which contains the schema properties in your C# project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bd2dd-109">C#プログラミング言語、属性名の属性の終了は省略可能で、属性の終わりを省略して DistinguishedField"や"プロパティの代わりに使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="bd2dd-109">In C# programming language, the Attribute ending of an attribute name is optional, so you can omit the Attribute ending and use DistinguishedField or Property instead.</span></span> <span data-ttu-id="bd2dd-110">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bd2dd-110">For example,</span></span>  
  
```  
[Property(typeof(PropertyNamespace.StringPropertyName))]  
[DistinguishedField]  
public string StrField;  
```  
  
 <span data-ttu-id="bd2dd-111">メッセージの種類を定義すると後、は、非常に簡単にこの型の新しいメッセージを作成するオーケストレーションでコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="bd2dd-111">Once the message type is defined, it is very easy to write code in the orchestration that will create a new message of this type.</span></span> <span data-ttu-id="bd2dd-112">内で、**メッセージの構築**図形、単純な式を記述するは新しいメッセージを作成する、 **MsgClass** 、上記の種類し、Distinguished となるフィールドに値を割り当てるフィールド (既定値を上書きする場合)。</span><span class="sxs-lookup"><span data-stu-id="bd2dd-112">Within a **Construct Message** shape, you write simple expressions to create a new message of the **MsgClass** type shown above, and then assign values to the fields which are attributed as Distinguished Fields (if you wish to override the default values).</span></span> <span data-ttu-id="bd2dd-113">MyMsg はオーケストレーション メッセージ変数の種類は NetClass.MsgClass であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bd2dd-113">Note that MyMsg is an orchestration message variable whose type is NetClass.MsgClass.</span></span>  
  
```  
MyMsg = new NetClass.MsgClass();  
MyMsg.StrField = "Changed Value";  
MyMsg.IntField = 15;  
```  
  
## <a name="see-also"></a><span data-ttu-id="bd2dd-114">参照</span><span class="sxs-lookup"><span data-stu-id="bd2dd-114">See Also</span></span>  
 <span data-ttu-id="bd2dd-115">[XSD スキーマとして表されるメッセージ](../core/messages-represented-as-xsd-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="bd2dd-115">[Messages Represented as XSD Schemas](../core/messages-represented-as-xsd-schemas.md) </span></span>  
 <span data-ttu-id="bd2dd-116">[XLANGMessage として表されるメッセージ](../core/messages-represented-as-xlangmessage.md) </span><span class="sxs-lookup"><span data-stu-id="bd2dd-116">[Messages Represented as XLANGMessage](../core/messages-represented-as-xlangmessage.md) </span></span>  
 [<span data-ttu-id="bd2dd-117">ユーザー コードでのメッセージの構築</span><span class="sxs-lookup"><span data-stu-id="bd2dd-117">Constructing Messages in User Code</span></span>](../core/constructing-messages-in-user-code.md)
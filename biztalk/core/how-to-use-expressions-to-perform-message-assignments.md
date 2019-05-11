---
title: 式を使用して、メッセージの割り当てを実行する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, distinquished fields
- orchestrations, expressions
- messages, manipulating
- messages, assigning messages
- messages, expressions
- messages, message parts
- orchestrations, messages
- messages, components
ms.assetid: 9989caf5-012c-4fc4-b5d8-981ca9a69f43
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: acadf37a102cedb9ddc902b4ca854d5e8458fa7c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333445"
---
# <a name="how-to-use-expressions-to-perform-message-assignments"></a><span data-ttu-id="6d784-102">式を使用して、メッセージの割り当てを実行する方法</span><span class="sxs-lookup"><span data-stu-id="6d784-102">How to Use Expressions to Perform Message Assignments</span></span>
<span data-ttu-id="6d784-103">式を使用して、オーケストレーションでさまざまな方法でメッセージを操作することができます。</span><span class="sxs-lookup"><span data-stu-id="6d784-103">You can use expressions to manipulate messages in various ways in your orchestration.</span></span>  
  
## <a name="referring-to-message-fields"></a><span data-ttu-id="6d784-104">メッセージのフィールドを参照します。</span><span class="sxs-lookup"><span data-stu-id="6d784-104">Referring to message fields</span></span>  
 <span data-ttu-id="6d784-105">メッセージ名に次のように、フィールド名を追加して、メッセージの識別フィールドを参照することができます。</span><span class="sxs-lookup"><span data-stu-id="6d784-105">You can refer to a distinguished field in a message by appending the field name to the message name as follows:</span></span>  
  
```  
MyMsg.Amount  
```  
  
 <span data-ttu-id="6d784-106">この例で MyMsg はメッセージと基になる、メッセージの種類を識別フィールドとして識別されているフィールドになります。</span><span class="sxs-lookup"><span data-stu-id="6d784-106">In this example, MyMsg is the message, and Amount is a field that has been identified as a distinguished field for the message type that MyMsg is based on.</span></span>  
  
## <a name="assigning-to-messages-and-message-parts"></a><span data-ttu-id="6d784-107">メッセージおよびメッセージ部分への割り当てください。</span><span class="sxs-lookup"><span data-stu-id="6d784-107">Assigning to messages and message parts</span></span>  
 <span data-ttu-id="6d784-108">別のメッセージまたはメッセージ部分のメッセージ部分に直接メッセージを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6d784-108">You can assign a message directly to another message, or a message part to a message part:</span></span>  
  
```  
MyMsg=IncomingMsg;  
MyMsg.Invoice=IncomingMsg.Invoice;  
```  
  
 <span data-ttu-id="6d784-109">この例では、請求書は、スキーマに基づくメッセージ部分です。</span><span class="sxs-lookup"><span data-stu-id="6d784-109">In this example, Invoice is a message part based on a schema.</span></span>  
  
 <span data-ttu-id="6d784-110">既に構築されたメッセージ プロパティを変更する場合: が受信されたメッセージなど、メッセージの構築図形では、2 番目の 1 つ目を割り当てることで新しいメッセージの構築および内で新しいメッセージのプロパティを変更する必要があります同じメッセージの構築図形。</span><span class="sxs-lookup"><span data-stu-id="6d784-110">If you want to modify a property on a message that has already been constructed—such as a message that has been received—you must construct a new message by assigning the first to the second in a Construct Message shape, and modify the property on the new message within the same Construct Message shape.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d784-111">参照するか、昇格された; 場合を除き、MyMsg.Invoice.MyField などのメッセージ フィールドに割り当てることはできません。のみ、参照するか、メッセージ全体、メッセージ部分、昇格させたメッセージ プロパティ、または識別フィールドに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6d784-111">You cannot refer or assign to message fields, such as MyMsg.Invoice.MyField, unless they have been promoted; you can only refer or assign to entire messages, message parts, promoted message properties, or distinguished fields.</span></span>  
  
## <a name="adding-message-parts"></a><span data-ttu-id="6d784-112">メッセージ部分の追加</span><span class="sxs-lookup"><span data-stu-id="6d784-112">Adding message parts</span></span>  
 <span data-ttu-id="6d784-113">既存のマルチパート メッセージに追加のパーツを追加するにを使用して、 **XLANGs.BaseTypes.XLANGMessage.AddPart**メソッド。</span><span class="sxs-lookup"><span data-stu-id="6d784-113">You can add additional parts to an existing multipart message by using the **XLANGs.BaseTypes.XLANGMessage.AddPart** method.</span></span> <span data-ttu-id="6d784-114">これを行うには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6d784-114">To do so, do the following:</span></span>  
  
-   <span data-ttu-id="6d784-115">作成、C#プロジェクトに参照を追加して**Microsoft.XLANGs.BaseTypes**します。</span><span class="sxs-lookup"><span data-stu-id="6d784-115">Create a C# project and add a reference to **Microsoft.XLANGs.BaseTypes**.</span></span>  
  
-   <span data-ttu-id="6d784-116">次のようなパブリック クラスを実装します。</span><span class="sxs-lookup"><span data-stu-id="6d784-116">Implement a public class similar to the following:</span></span>  
  
    ```  
    public class MyAddPartHelper  
    {  
         public static void AddPart(XLANGMessage msg, object part, String partName)  
         {  
              msg.AddPart(part, partName);  
         }  
    }  
    ```  
  
     <span data-ttu-id="6d784-117">3 つのオーバー ロードされたメソッドがある**Microsoft.XLANGs.BaseTypes.AddPart**:</span><span class="sxs-lookup"><span data-stu-id="6d784-117">There are three overloaded methods for **Microsoft.XLANGs.BaseTypes.AddPart**:</span></span>  
  
    ```  
    public void AddPart(object part, String partName);  
    public void AddPart(XLANGPart part);  
    public void AddPart(XLANGPart part, String partName);  
    ```  
  
-   <span data-ttu-id="6d784-118">BizTalk プロジェクトで、パブリック クラスと呼び出しへの参照を追加、 **AddPart**からメソッド、**式**図形の次のように、オーケストレーションで。</span><span class="sxs-lookup"><span data-stu-id="6d784-118">In your BizTalk project, add a reference to the public class and call the **AddPart** method from the **Expression** shape in your orchestration as follows:</span></span>  
  
    ```  
    MyAddPartHelper.AddPart(myMessage, myStringObject, “StringObject1”);  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="6d784-119">メッセージ部分としてシリアル化できないオブジェクト、またはカスタムの書式設定されたオブジェクトを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="6d784-119">You cannot add non-serializable objects or custom formatted objects as message parts.</span></span> <span data-ttu-id="6d784-120">使用したその他のパーツを追加する前にすべての静的部分を初期化する必要があります、 **AddPart**メソッド。</span><span class="sxs-lookup"><span data-stu-id="6d784-120">All static parts must be initialized before adding additional parts using the **AddPart** method.</span></span> <span data-ttu-id="6d784-121">ステートメントを作成、メッセージの内部でのみ、メッセージに任意の部分を追加できます。</span><span class="sxs-lookup"><span data-stu-id="6d784-121">You can add arbitrary parts to a message only inside its message construct statement.</span></span> <span data-ttu-id="6d784-122">ステートメントを作成、メッセージの外部で他のパーツを追加することはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="6d784-122">Adding additional parts outside of the message construct statement is not supported.</span></span>  
  
## <a name="retrieving-message-parts"></a><span data-ttu-id="6d784-123">メッセージ部分の取得</span><span class="sxs-lookup"><span data-stu-id="6d784-123">Retrieving message parts</span></span>  
 <span data-ttu-id="6d784-124">使用して既存のマルチパート メッセージからメッセージ部分を取得することができます、 **RetrieveAs**メソッドから**Microsoft.XLANGs.BaseTypes**します。</span><span class="sxs-lookup"><span data-stu-id="6d784-124">You can retrieve a message part from an existing multipart message by using the **RetrieveAs** method from **Microsoft.XLANGs.BaseTypes**.</span></span> <span data-ttu-id="6d784-125">これを行うには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6d784-125">To do so, do the following:</span></span>  
  
-   <span data-ttu-id="6d784-126">作成、C#プロジェクトに参照を追加して**Microsoft.XLANGs.BaseTypes**します。</span><span class="sxs-lookup"><span data-stu-id="6d784-126">Create a C# project and add a reference to **Microsoft.XLANGs.BaseTypes**.</span></span>  
  
-   <span data-ttu-id="6d784-127">次のようなパブリック クラスを実装します。</span><span class="sxs-lookup"><span data-stu-id="6d784-127">Implement a public class similar to the following:</span></span>  
  
    ```  
    Public class MyAddPartHelper  
    {  
         public static Object GetPart(XLANGMessage msg, string sName, Type t)  
         {  
              XLANGPart p =  msg[sName];  
              return p.RetrieveAs(t);  
         }  
         public static Object GetPart(XLANGMessage msg, int partIndex, Type t)  
         {  
               XLANGPart p = msg[partIndex];  
               return p.RetrieveAs(t);  
          }  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="6d784-128">**RetrieveAs**メソッドは、名、インデックスを使用してメッセージ部分の取得をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6d784-128">The **RetrieveAs** method supports retrieving message parts by name and by index.</span></span>  
  
-   <span data-ttu-id="6d784-129">BizTalk プロジェクトで、パブリック クラスと呼び出しへの参照を追加、 **GetPart**からメソッド、**式**図形の次のように、オーケストレーションで。</span><span class="sxs-lookup"><span data-stu-id="6d784-129">In your BizTalk project, add a reference to the public class and call the **GetPart** method from the **Expression** shape in your orchestration as follows:</span></span>  
  
    ```  
    sPart = (System.String) MyAddPartHelper.GetPart(msg, "StringObject1" , typeof(System.String));  
    //sPart is a type of System.String  
    sPart = (System.String) MyAddPartHelper.GetPart(msg, 1, typeof(System.String));  
    //Retriving the message part with index = 1  
    ```  
  
## <a name="message-part-context-property-access"></a><span data-ttu-id="6d784-130">メッセージ部分コンテキスト プロパティのアクセス</span><span class="sxs-lookup"><span data-stu-id="6d784-130">Message part context property access</span></span>  
 <span data-ttu-id="6d784-131">メッセージ部分には、メッセージ コンテキストから別のコンテキストがあります。</span><span class="sxs-lookup"><span data-stu-id="6d784-131">A message part has context separate from the message context.</span></span> <span data-ttu-id="6d784-132">設定すると、スキーマ エディターでのメッセージ部分のコンテキスト プロパティを構築することができます、 **Property Schema Base**プロパティに関連付けられている要素を**PartContextPropertyBase します。**</span><span class="sxs-lookup"><span data-stu-id="6d784-132">You can construct message part context properties through the schema editor when you set the **Property Schema Base** property for the associated element to **PartContextPropertyBase.**</span></span>  
  
 <span data-ttu-id="6d784-133">アクセスは、ような式からのメッセージ プロパティと同様です。</span><span class="sxs-lookup"><span data-stu-id="6d784-133">The access is similar to message properties, through an expression like:</span></span>  
  
```  
Msg.PartName(myPartContextProperty)  
```  
  
 <span data-ttu-id="6d784-134">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6d784-134">For example:</span></span>  
  
```  
Str=Msg.PartName(myPartContextProperty); //assumes myPartContextProperty is of type string  
```  
  
## <a name="xlangmessage-context-property-access"></a><span data-ttu-id="6d784-135">XLANGMessage のコンテキスト プロパティのアクセス</span><span class="sxs-lookup"><span data-stu-id="6d784-135">XLANGMessage context property access</span></span>  
 <span data-ttu-id="6d784-136">メッセージ プロパティにアクセスしたい場合、 **XLANGMessage**インターフェイス、コードでは、型のパラメーターとして、メッセージを渡すことができます**Microsoft.XLANGs.BaseTypes.XLANGMessage**メソッド使用して、式図形から、 **Microsoft.XLANGs.BaseTypes.XLANGMessage**メソッド**SetPropertyValue**と**GetPropertyValue**を実現するにはこれ。</span><span class="sxs-lookup"><span data-stu-id="6d784-136">If you would like to access message properties from the **XLANGMessage** interface from your code, you can pass the message as a parameter of type **Microsoft.XLANGs.BaseTypes.XLANGMessage** to a method from an Expression shape, and then use the **Microsoft.XLANGs.BaseTypes.XLANGMessage** methods **SetPropertyValue** and **GetPropertyValue** to achieve this.</span></span> <span data-ttu-id="6d784-137">これを行うには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6d784-137">To do so, do the following:</span></span>  
  
-   <span data-ttu-id="6d784-138">作成、C#プロジェクトに参照を追加して**Microsoft.XLANGs.BaseTypes**と**Microsoft.BizTalk.GlobalPropertySchemas**します。</span><span class="sxs-lookup"><span data-stu-id="6d784-138">Create a C# project and add a reference to **Microsoft.XLANGs.BaseTypes** and **Microsoft.BizTalk.GlobalPropertySchemas**.</span></span>  
  
-   <span data-ttu-id="6d784-139">ようなコードを使用してコンテキスト プロパティへのアクセスの下。</span><span class="sxs-lookup"><span data-stu-id="6d784-139">Access the context property using the code similar to the below:</span></span>  
  
    ```  
    MyMsg.GetPropertyValue(typeof(BTS.MessageID));  
    MyMsg.SetPropertyValue(typeof(MIME.IsMultipartRelated), true);  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="6d784-140">取得または、独自のカスタム コンテキスト プロパティを設定する場合は、アセンブリへの参照には、プロパティ スキーマが含まれていますを追加するか、プロパティ スキーマ プロジェクトへの参照を追加する必要があります、C#プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="6d784-140">If you would like to get or set your own custom context properties, you need to add a reference to your property schema project or add a reference to the assembly contains the property schemas in your C# project.</span></span>  
  
## <a name="assigning-to-message-properties"></a><span data-ttu-id="6d784-141">メッセージのプロパティへの割り当てください。</span><span class="sxs-lookup"><span data-stu-id="6d784-141">Assigning to message properties</span></span>  
 <span data-ttu-id="6d784-142">メッセージ プロパティに値を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6d784-142">You can assign a value to a message property:</span></span>  
  
```  
MyMessage(MySchemaNamespace.MyProperty)=True;  
```  
  
 <span data-ttu-id="6d784-143">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してくださいし、MIME マルチパート メッセージのプロパティに値を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6d784-143">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] you can refer to and assign values to the MIME properties of a multi-part message:</span></span>  
  
```  
Message_Out.MessagePart_1(MIME.FileName)="document.doc";  
```  
  
> [!NOTE]
>  <span data-ttu-id="6d784-144">BizTalk メッセージは、メッセージのコンテキストとメッセージ部分で構成されます。</span><span class="sxs-lookup"><span data-stu-id="6d784-144">A BizTalk message consists of message context and message parts.</span></span> <span data-ttu-id="6d784-145">取得したり、メッセージ コンテキスト プロパティを設定する前にまずメッセージ部分を初期化する必要があります。それ以外の場合、XLANG コンパイル中にエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d784-145">You must first initialize the message parts before you can get or set any message context property; otherwise, you will receive error during the XLANG compile time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d784-146">参照</span><span class="sxs-lookup"><span data-stu-id="6d784-146">See Also</span></span>  
 <span data-ttu-id="6d784-147">[オーケストレーションでメッセージの使用](../core/using-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="6d784-147">[Using Messages in Orchestrations](../core/using-messages-in-orchestrations.md) </span></span>  
 [<span data-ttu-id="6d784-148">ユーザー コードでのメッセージの構築</span><span class="sxs-lookup"><span data-stu-id="6d784-148">Constructing Messages in User Code</span></span>](../core/constructing-messages-in-user-code.md)   
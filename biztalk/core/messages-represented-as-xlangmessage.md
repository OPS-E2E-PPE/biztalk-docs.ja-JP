---
title: "XLANGMessage として表されるメッセージ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aadca870-2f93-4be3-8733-a0cd3815add7
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 996c88ca73fcc8abc450159e1cf26cd24b7aa241
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="messages-represented-as-xlangmessage"></a><span data-ttu-id="faed8-102">XLANGMessage として表されるメッセージ</span><span class="sxs-lookup"><span data-stu-id="faed8-102">Messages Represented as XLANGMessage</span></span>
<span data-ttu-id="faed8-103">**XLANGMessage**オブジェクト、XLANG サービスで宣言されたメッセージ インスタンスを表します。</span><span class="sxs-lookup"><span data-stu-id="faed8-103">An **XLANGMessage** object represents a message instance declared with an XLANG service.</span></span> <span data-ttu-id="faed8-104">このオブジェクトを取得するには、メソッド呼び出しのパラメーターとしてメッセージに参照を渡します。</span><span class="sxs-lookup"><span data-stu-id="faed8-104">This object is obtained by passing a reference to a message as a parameter in a method invocation.</span></span> <span data-ttu-id="faed8-105">**XLANGPart**オブジェクトは、XLANG サービス内のメッセージ インスタンスに含まれるメッセージ部分を表します。</span><span class="sxs-lookup"><span data-stu-id="faed8-105">An **XLANGPart** object represents a message part contained in a message instance within an XLANG service.</span></span> <span data-ttu-id="faed8-106">このオブジェクトは取得を受信側のパラメーター型がメソッドの呼び出しで一部の参照を渡すか**XLANGPart**の渡された参照を列挙することによって、または**XLANGMessage**です。</span><span class="sxs-lookup"><span data-stu-id="faed8-106">This object is obtained either by passing a part reference in a method invocation where the receiving parameter type is **XLANGPart** or by enumerating on a passed reference of **XLANGMessage**.</span></span>  
  
 <span data-ttu-id="faed8-107">オーケストレーション メッセージ変数をユーザー コンポーネントに渡され、として受信した可能性があります、 **XLANGMessage**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="faed8-107">An orchestration message variable may be passed to a user component and received as an **XLANGMessage** object.</span></span> <span data-ttu-id="faed8-108">**XLANGMessage**オブジェクトは、部分やメッセージ プロパティへのアクセスを許可します。ユーザーが「保持」、 **XLANGMessage**し、それによって、宣言されたスコープの有効期間を拡張します。</span><span class="sxs-lookup"><span data-stu-id="faed8-108">The **XLANGMessage** object allows accessing the parts and accessing message properties.The user may "hold on" to an **XLANGMessage** and thereby extend its lifetime beyond the declared scope.</span></span> <span data-ttu-id="faed8-109">その後、 **XLANGMessage**メソッドから返され、オーケストレーション内のメッセージ変数に割り当てられている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="faed8-109">Subsequently, an **XLANGMessage** may be retuned from a method and assigned to a message variable in an orchestration.</span></span>  
  
## <a name="constructing-an-xlangmessage"></a><span data-ttu-id="faed8-110">XLANGMessage の作成</span><span class="sxs-lookup"><span data-stu-id="faed8-110">Constructing an XLANGMessage</span></span>  
 <span data-ttu-id="faed8-111">構築するときに、 **XLANGMessage**ストリームの種類と、ストリームにはいずれかを実装する必要があります**IStreamFactory**するか、 **MemoryStream**です。</span><span class="sxs-lookup"><span data-stu-id="faed8-111">When constructing an **XLANGMessage** with a stream, the stream type must either implement **IStreamFactory** or be a **MemoryStream**.</span></span> <span data-ttu-id="faed8-112">次のコード サンプルを構築する方法を示しています、 **XLANGMessage**:</span><span class="sxs-lookup"><span data-stu-id="faed8-112">The following code sample shows how to construct an **XLANGMessage**:</span></span>  
  
```  
public class FileStreamFactory : IStreamFactory  
{  
    string _fname;  
  
    public FileStreamFactory(string fname)  
    {  
        _fname = fname;  
    }  
  
    public Stream CreateStream()  
    {  
        return new FileStream  
        (  
            _fname,  
            FileMode.Open,  
            FileAccess.Read,  
            FileShare.Read  
        );  
    }  
}  
  
public static void AssignStreamFactoryToPart(XLANGMessage msg)  
{  
    IStreamFactory sf = new FileStreamFactory( @”c:\data.xml” );  
    msg[0].LoadFrom( sf );  
}  
```  
  
 <span data-ttu-id="faed8-113">送信元メッセージを変換しないで新しいメッセージを作成することが必要な場合もあります。</span><span class="sxs-lookup"><span data-stu-id="faed8-113">There may be times when you want to create a new message without transforming a source message.</span></span> <span data-ttu-id="faed8-114">型の変数を使用してこれを行う**System.Xml.XmlDocument**読み込みや、それ以外の場合に適切なコンテンツを構築します。</span><span class="sxs-lookup"><span data-stu-id="faed8-114">You can do this by using a variable of type **System.Xml.XmlDocument** and loading or otherwise constructing appropriate content.</span></span> <span data-ttu-id="faed8-115">次の例では、文字列から XML を読み込むを使用して、 **LoadXml**メソッドの**XmlDocument**:</span><span class="sxs-lookup"><span data-stu-id="faed8-115">In the following example, XML is loaded from a string by using the **LoadXml** method of **XmlDocument**:</span></span>  
  
```  
XmlVariable.LoadXml("\<ns0:Root PONumber=\"047745351122111\" xmlns:ns0=\"http://BTSHTTPSend.SimpleSchema\">\<MyChildRecord SubAttr1=\"Simple Attribute \" />\</ns0:Root>");  
XLANGMessage XmlMsg = XmlVariable;  
  
```  
  
 <span data-ttu-id="faed8-116">次の例を使用して、ファイルから XML を読み込んで、**ロード**メソッドの**XmlDocument**:</span><span class="sxs-lookup"><span data-stu-id="faed8-116">The following example loads XML from a file by using the **Load** method of **XmlDocument**:</span></span>  
  
```  
XmlVariable.Load("C:\MyData.xml");  
XLANGMessage XmlMsg = XmlVariable;  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="faed8-117">サイズの大きいメッセージを構築する場合は、前のセクションで示したストリーミング メソッドのいずれかを使用または使用を検討して、**変換**オーケストレーション デザイナーでの図形です。</span><span class="sxs-lookup"><span data-stu-id="faed8-117">If you want to construct larger messages, use one of the streaming methods demonstrated in the previous section or consider using the **Transform** shape in Orchestration Designer.</span></span>  
  
## <a name="considerations-when-using-xlangmessage-and-xlangpart"></a><span data-ttu-id="faed8-118">XLANGMessage および XLANGPart を使用する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="faed8-118">Considerations When Using XLANGMessage and XLANGPart</span></span>  
 <span data-ttu-id="faed8-119">使用する場合**XLANGMessage**と**XLANGPart**ユーザー コードでは、次を検討してください。</span><span class="sxs-lookup"><span data-stu-id="faed8-119">When using **XLANGMessage** and **XLANGPart** in user code, consider the following:</span></span>  
  
-   <span data-ttu-id="faed8-120">メッセージの一部としては渡さないように、 **XLANGPart**引数または戻り値の型の値**XLANGPart**です。</span><span class="sxs-lookup"><span data-stu-id="faed8-120">Do not pass a message part as an **XLANGPart** argument or return a value of type **XLANGPart**.</span></span> <span data-ttu-id="faed8-121">渡す必要があります**XLANGPart**部分の型として。</span><span class="sxs-lookup"><span data-stu-id="faed8-121">You should pass **XLANGPart** as the type of the part.</span></span> <span data-ttu-id="faed8-122">例:</span><span class="sxs-lookup"><span data-stu-id="faed8-122">For example:</span></span>  
  
    ```  
    Message String msg;  
    Class.Test(msg);  
    // or you can do the following  
    Messagetype mt  
    {  
         String part;  
    };  
    Message mt msg;  
    Class.Test(msg,part);  
  
    ```  
  
     <span data-ttu-id="faed8-123">メッセージ自体を渡すこともできますとして、 **XLANGMessage**を使用して、 **XLANGMessage**添字演算子、関数呼び出しの内部で部分にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="faed8-123">You can also pass the message itself as an **XLANGMessage** and use the **XLANGMessage** subscript operators to access the part inside the function call.</span></span> <span data-ttu-id="faed8-124">ただし、移動しないようにすれば、 **XLANGPart**関数呼び出しの有効期間を超えて拡張してその有効期間、コレクション内です。</span><span class="sxs-lookup"><span data-stu-id="faed8-124">However, you should not put an **XLANGPart** in a collection whose lifetime extends past the lifetime of the function call.</span></span> <span data-ttu-id="faed8-125">代わりに、配置する必要があります、 **XLANGMessage**コレクション内で。</span><span class="sxs-lookup"><span data-stu-id="faed8-125">Instead, you should put the **XLANGMessage** in the collection.</span></span> <span data-ttu-id="faed8-126">例:</span><span class="sxs-lookup"><span data-stu-id="faed8-126">For example:</span></span>  
  
    ```  
    Void Test(XLANGMessage xlm)  
    {  
         try  
         {  
          XLANGPart xlp = xlm[0];  
          String sval = (String) xlp.RetrieveAs(typeof(string));  
         }  
         finally  
         {  
          Xlm.Dispose();  
         }  
    }  
    ```  
  
-   <span data-ttu-id="faed8-127">オーケストレーション パラメーターとして定義していない**XLANGMessage**または**XLANGPart**です。</span><span class="sxs-lookup"><span data-stu-id="faed8-127">Do not define an orchestration parameter as **XLANGMessage** or **XLANGPart**.</span></span> <span data-ttu-id="faed8-128">メッセージを渡す必要がある場合は、メッセージの型のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="faed8-128">If you want to pass a message, then use a message type parameter to pass the message.</span></span> <span data-ttu-id="faed8-129">部分を渡す必要がある場合は、代わりにメッセージを渡してから、部分を使用します。</span><span class="sxs-lookup"><span data-stu-id="faed8-129">If you want to pass a part, then pass the message instead and then use the part.</span></span> <span data-ttu-id="faed8-130">部分の値だけが必要な場合は、部分の型を使用して部分を渡します。</span><span class="sxs-lookup"><span data-stu-id="faed8-130">If you only want the part value, then use the part type to pass the part.</span></span>  
  
-   <span data-ttu-id="faed8-131">戻ることはありません、 **XLANGMessage**メソッド呼び出しのパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="faed8-131">Do not return an **XLANGMessage** parameter for a method call.</span></span> <span data-ttu-id="faed8-132">返す場合、 **XLANGMessage**に渡されるパラメーターとしを呼び出すことはできません、 **Dispose**メソッドで、パラメーター、メソッドの呼び出しの内部では、直感的に違反している有効期間の前提条件とそのも例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="faed8-132">If you return an **XLANGMessage** parameter that is passed in, and then you cannot call the **Dispose** method on the parameter inside the method call, it intuitively violates lifetime assumptions and it also throws an exception.</span></span> <span data-ttu-id="faed8-133">メッセージを渡すときに、 **XLANGMessage**パラメーターをユーザー コードは、メッセージを正常に参照されているメッセージがない特殊なコンテキストを参照します。</span><span class="sxs-lookup"><span data-stu-id="faed8-133">When passing a message through an **XLANGMessage** parameter to user code, you reference the message to a special context that does not normally have messages referenced to it.</span></span> <span data-ttu-id="faed8-134">このコンテキストの有効期間は、オーケストレーション インスタンスの有効期間です。</span><span class="sxs-lookup"><span data-stu-id="faed8-134">The lifetime of this context is the lifetime of the orchestration instance.</span></span> <span data-ttu-id="faed8-135">これは、BizTalk Server からは、ユーザー コードがメッセージを保持しているかどうかがわからないためです。</span><span class="sxs-lookup"><span data-stu-id="faed8-135">This is because BizTalk Server does not know whether the user code will hold onto the message.</span></span>  
  
     <span data-ttu-id="faed8-136">オーケストレーション インスタンスが存在する場合、そのインスタンスで作成されたメッセージは有効ではないので、そのようなコレクションの有効期間は、インスタンスの有効期間以下でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="faed8-136">When an orchestration instance exits, any messages created in that instance are no longer valid, so the lifetime of such a collection should be less than or equal to that of the instance lifetime.</span></span> <span data-ttu-id="faed8-137">ただし、を介して、メッセージが渡されるときに、ループ内でメッセージ参照を解放する場合、 **XLANGMessage**を呼び出すことができますし、オーケストレーション インスタンスと同じ有効期間を持つ引数**XLANGMessage.Dispose**参照を解放します。</span><span class="sxs-lookup"><span data-stu-id="faed8-137">However, if you want to release a message reference in a loop when the message was passed through an **XLANGMessage** argument that has the same lifetime as the orchestration instance, then you can call **XLANGMessage.Dispose** to free up the reference.</span></span> <span data-ttu-id="faed8-138">さらに、ユーザー コード メソッドの内部場合は、 **XLANGMessage**パラメーターはローカルでのみ使用され、パラメーターの有効期間に含まれる関数呼び出しの呼び出すこともできます**XLANGMessage.Dispose**ルート コンテキストへの参照を解放しをもたらすため、対応するメッセージに、通常の有効期間動作します。</span><span class="sxs-lookup"><span data-stu-id="faed8-138">Moreover, if inside the user code method, the **XLANGMessage** parameter is only used locally and the lifetime of the parameter is contained in that of the function call, you can also call **XLANGMessage.Dispose** to free up the reference to the root context and give the corresponding message back the normal lifetime behavior.</span></span> <span data-ttu-id="faed8-139">例:</span><span class="sxs-lookup"><span data-stu-id="faed8-139">For example:</span></span>  
  
    ```  
    void Test(XLANGMessage xlm)  
    {  
         try  
         {  
          //XLANGMessage is only used locally  
         }  
         finally  
         {  
          xlm.Dispose();  
         }  
    }  
    ```  
  
     <span data-ttu-id="faed8-140">コレクションでは、xlm を配置するかどうかは、クラス自体がいる必要があります、 **Dispose**クリーンアップの方法です。</span><span class="sxs-lookup"><span data-stu-id="faed8-140">If you place the xlm in a collection, then the class itself must have a **Dispose** method for cleanup.</span></span> <span data-ttu-id="faed8-141">例:</span><span class="sxs-lookup"><span data-stu-id="faed8-141">For example:</span></span>  
  
    ```  
    Public class A  
    {  
         Hashtable h = new Hashtable();  
         Public Test(XLANGMessage xlm)  
         {  
          h[xlm] = 1;  
         }  
         //You can have more methods here  
         Public Dispose()  
         {  
          foreach (XLANGMessage xlm in h.Keys)  
           Xlm.Dispose();  
         }  
    }  
    ```  
  
     <span data-ttu-id="faed8-142">呼び出して**A.Dispose**のコレクションを使用が終了したら**XLANGMessages**です。</span><span class="sxs-lookup"><span data-stu-id="faed8-142">You would call **A.Dispose** when you are finished with the collection of **XLANGMessages**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faed8-143">参照</span><span class="sxs-lookup"><span data-stu-id="faed8-143">See Also</span></span>  
 <span data-ttu-id="faed8-144">[XSD スキーマとして表されるメッセージ](../core/messages-represented-as-xsd-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="faed8-144">[Messages Represented as XSD Schemas](../core/messages-represented-as-xsd-schemas.md) </span></span>  
 <span data-ttu-id="faed8-145">[.NET クラスとして表されるメッセージ](../core/messages-represented-as-net-classes.md) </span><span class="sxs-lookup"><span data-stu-id="faed8-145">[Messages Represented as .NET Classes](../core/messages-represented-as-net-classes.md) </span></span>  
 [<span data-ttu-id="faed8-146">ユーザー コードでメッセージの構築</span><span class="sxs-lookup"><span data-stu-id="faed8-146">Constructing Messages in User Code</span></span>](../core/constructing-messages-in-user-code.md)
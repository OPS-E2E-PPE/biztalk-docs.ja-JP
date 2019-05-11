---
title: ファイル送信ポート経由で AS2 メッセージの送信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8c5ce9ff-fd73-4d5f-9b16-387c1e520c3a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 184a6a1b6a0111dffaf9096e23e60945d8310ecf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399064"
---
# <a name="sending-an-as2-message-over-a-file-send-port"></a><span data-ttu-id="fe0f2-102">ファイル送信ポート経由で AS2 メッセージの送信</span><span class="sxs-lookup"><span data-stu-id="fe0f2-102">Sending an AS2 Message over a FILE Send Port</span></span>
<span data-ttu-id="fe0f2-103">通常、AS2 メッセージは HTTP アダプターを介して送信されます。</span><span class="sxs-lookup"><span data-stu-id="fe0f2-103">AS2 messages are normally sent over an HTTP adapter.</span></span> <span data-ttu-id="fe0f2-104">ただし、カスタム コンポーネントを作成する場合は、AS2 メッセージを FILE アダプター経由で送信できます。</span><span class="sxs-lookup"><span data-stu-id="fe0f2-104">You can, however, send AS2 messages over a FILE adapter if you create custom components.</span></span> <span data-ttu-id="fe0f2-105">このトピックでは、このようなソリューションのしくみについて説明し、ソリューションのサンプル コードを示します。</span><span class="sxs-lookup"><span data-stu-id="fe0f2-105">This topic describes how such a solution would work and provides sample code for the solution.</span></span>  
  
 <span data-ttu-id="fe0f2-106">AS2 メッセージが HTTP 経由で送信されると、送信パイプラインの AS2 エンコーダーは、メッセージの送信に必要な HTTP (および AS2) ヘッダーを `HTTP.UserHttpHeaders` コンテキスト プロパティに挿入します。</span><span class="sxs-lookup"><span data-stu-id="fe0f2-106">When AS2 messages are sent over HTTP, the AS2 Encoder in the send pipeline populates the `HTTP.UserHttpHeaders` context property with the HTTP (and AS2) headers required for sending the message.</span></span> <span data-ttu-id="fe0f2-107">これらのヘッダーは、既存の `HTTP.UserHttpHeaders` コンテキスト プロパティ、別のコンテキスト プロパティ、またはアグリーメント プロパティから (この優先順位で) 取得されます。</span><span class="sxs-lookup"><span data-stu-id="fe0f2-107">It takes these headers either from the existing `HTTP.UserHttpHeaders` context property, from separate context properties, or from agreement properties (in that order of precedence).</span></span> <span data-ttu-id="fe0f2-108">送信ポートの HTTP アダプターは、これらのヘッダーをメッセージに書き込み、HTTP 経由でメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="fe0f2-108">The HTTP adapter in the send port will write the headers to the message, and send the message over HTTP.</span></span>  
  
 <span data-ttu-id="fe0f2-109">送信ポートの HTTP アダプターの代わりに FILE アダプターを使用する場合、`HTTP.UserHttpHeaders` コンテキスト プロパティのヘッダー値は、メッセージに書き込まれません。</span><span class="sxs-lookup"><span data-stu-id="fe0f2-109">If you use a FILE adapter instead of an HTTP adapter in the send port, the header values in the `HTTP.UserHttpHeaders` context property will not be written to the message.</span></span> <span data-ttu-id="fe0f2-110">`HTTP.UserHttpHeaders` のヘッダーをメッセージの前に付けるためのカスタム パイプライン コンポーネントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe0f2-110">You have to create a custom pipeline component to prepend the headers in `HTTP.UserHttpHeaders` to the message.</span></span> <span data-ttu-id="fe0f2-111">こうすることにより、メッセージは FILE アダプターによってフォルダーに追加でき、必要な HTTP ヘッダーが含まれた AS2 メッセージになります。</span><span class="sxs-lookup"><span data-stu-id="fe0f2-111">The message can then be dropped into a folder by the FILE adapter, and will be an AS2 message that includes the required HTTP headers.</span></span>  
  
 <span data-ttu-id="fe0f2-112">すべての AS2 ヘッダーが `HTTP.UserHttpHeaders` コンテキスト プロパティに含まれるようにするためにも、カスタム コンポーネントの作成が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fe0f2-112">You may also need to create a custom component to ensure that all the AS2 headers are included in the `HTTP.UserHttpHeaders` context property.</span></span> <span data-ttu-id="fe0f2-113">カスタム オーケストレーションまたはカスタム パイプライン コンポーネントを AS2Encoder の前に作成すると、AS2 エンコーダーによって `HTTP.UserHttpHeaders` を構築するために使用されるコンテキスト プロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="fe0f2-113">You can create either a custom orchestration, or a custom pipeline component before the AS2Encoder, to set the context properties that the AS2 Encoder uses to build `HTTP.UserHttpHeaders`.</span></span>  
  
## <a name="writing-headers-to-an-as2-message"></a><span data-ttu-id="fe0f2-114">AS2 メッセージへのヘッダーの書き込み</span><span class="sxs-lookup"><span data-stu-id="fe0f2-114">Writing Headers to an AS2 Message</span></span>  
 <span data-ttu-id="fe0f2-115">HTTP アダプターではなく FILE アダプターを使用して AS2 メッセージを生成するには、カスタムの AS2 送信パイプラインで AS2 エンコーダーの後にカスタム パイプライン コンポーネントを追加します。</span><span class="sxs-lookup"><span data-stu-id="fe0f2-115">To generate an AS2 message using a FILE adapter, rather than an HTTP adapter, add a custom pipeline component after the AS2 Encoder in a custom AS2 send pipeline.</span></span> <span data-ttu-id="fe0f2-116">`HTTP.UserHttpHeaders` コンテキスト プロパティのヘッダーをメッセージに書き込むコードを、このカスタム パイプライン コンポーネントに追加します。</span><span class="sxs-lookup"><span data-stu-id="fe0f2-116">Include code in the custom pipeline component that writes the headers from the `HTTP.UserHttpHeaders` context property into the message.</span></span> <span data-ttu-id="fe0f2-117">サンプル コードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fe0f2-117">An example is the following sample code:</span></span>  
  
```  
public IBaseMessage Execute(IPipelineContext pContext, IBaseMessage pInMsg)  
        {  
            IPipelineContext pipelineContext = pContext;  
            IBaseMessage baseMessage = pInMsg;  
  
            //Prepend Headers  
            MemoryStream ms = new MemoryStream();  
            string strName = "UserHttpHeaders";  
            string strValue = (string)baseMessage.Context.Read(strName,  
              "http://schemas.microsoft.com/BizTalk/2003/  
              http-properties");  
  
            //Leave an empty line between the headers and the body  
            strValue += "\r\n";  
            ms.Write(Encoding.ASCII.GetBytes(strValue), 0,   
               Encoding.ASCII.GetByteCount(strValue));  
  
            //Append Body  
            Stream sr = baseMessage.BodyPart.Data;  
  
            //Read the body of the message and append it to the memory   
              stream containing the headers  
            int size = 1024;  
            byte[] buffer = new byte[size];  
            while (0 != (size = sr.Read(buffer, 0, buffer.Length)))  
            {  
                ms.Write(buffer, 0, size);  
            }  
  
            //Set the body of the message to the new memory stream  
            baseMessage.BodyPart.Data = ms;  
  
            //Rewind the stream  
            ms.Seek(0, SeekOrigin.Begin);  
  
            return baseMessage;  
        }  
```  
  
## <a name="promoting-as2-header-context-properties"></a><span data-ttu-id="fe0f2-118">AS2 ヘッダー コンテキスト プロパティの昇格</span><span class="sxs-lookup"><span data-stu-id="fe0f2-118">Promoting AS2 Header Context Properties</span></span>  
 <span data-ttu-id="fe0f2-119">カスタム オーケストレーションまたはカスタム パイプライン コンポーネントを使用すると、AS2 ヘッダーのプロパティをメッセージのコンテキストに昇格できます。</span><span class="sxs-lookup"><span data-stu-id="fe0f2-119">You can promote AS2 header properties into the context of a message using either a custom orchestration or a custom pipeline component.</span></span>  
  
 <span data-ttu-id="fe0f2-120">カスタム パイプライン コンポーネントを使用して AS2 ヘッダー プロパティを昇格するには、カスタムの AS2 送信パイプラインで AS2 エンコーダーの前にカスタム パイプライン コンポーネントを追加します。</span><span class="sxs-lookup"><span data-stu-id="fe0f2-120">To promote AS2 header properties using a custom pipeline component, add a custom pipeline component before the AS2 Encoder in a custom AS2 send pipeline.</span></span> <span data-ttu-id="fe0f2-121">`HTTP.UserHttpHeaders` からメッセージにヘッダーを書き込むには、上記のサンプル コードを使用できます。ただし、Read メソッドを Promote メソッドで置き換えて、昇格するコンテキスト プロパティの名前、値、および名前空間を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe0f2-121">You can use code from the sample code shown above for writing headers from `HTTP.UserHttpHeaders` into the message, with the exception that you would replace the Read method with a Promote method, providing the name, value, and namespace of the context property to be promoted.</span></span>  
  
 <span data-ttu-id="fe0f2-122">カスタム オーケストレーションを使用して AS2 ヘッダー プロパティを昇格するには、FILE 受信ポート、メッセージの構築図形、および FILE 送信ポートを使用してオーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="fe0f2-122">To promote AS2 header properties using a custom orchestration, create an orchestration with a FILE receive port, a Construct Message shape, and a FILE send port.</span></span> <span data-ttu-id="fe0f2-123">メッセージの構築図形には、AS2 ヘッダーが含まれた昇格対象プロパティを設定するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="fe0f2-123">To the Construct Message shape, add code setting the promoted properties that contain the AS2 headers.</span></span> <span data-ttu-id="fe0f2-124">カスタム オーケストレーションに `Microsoft.BizTalk.HttpTransport.dll` への参照を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe0f2-124">You must add a reference to `Microsoft.BizTalk.HttpTransport.dll` in the custom orchestration.</span></span>  
  
 <span data-ttu-id="fe0f2-125">HTTP ヘッダーの名前空間は非 AS2 HTTP ヘッダーの場合は `http://schemas.microsoft.com/BizTalk/2003/http-properties` であり、AS2 ヘッダーの場合は `http://schemas.microsoft.com/BizTalk/2003/as2-properties` です。</span><span class="sxs-lookup"><span data-stu-id="fe0f2-125">The namespaces for HTTP headers is `http://schemas.microsoft.com/BizTalk/2003/http-properties` for non-AS2 HTTP headers and `http://schemas.microsoft.com/BizTalk/2003/as2-properties` for AS2 headers.</span></span>  
  
 <span data-ttu-id="fe0f2-126">次のサンプル コードに、オーケストレーションのメッセージの構築図形で AS2 ヘッダー プロパティを昇格する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="fe0f2-126">The following sample code shows how to promote AS2 header properties in the Construct Message shape of an orchestration.</span></span> <span data-ttu-id="fe0f2-127">このコードでは、MDN の AS2 ヘッダーが昇格されます。</span><span class="sxs-lookup"><span data-stu-id="fe0f2-127">This code promotes AS2 headers for an MDN.</span></span>  
  
```  
Message_2=new System.Xml.XmlDocument();  
Message_2=Message_1;  
Message_2(EdiIntAS.IsAS2PayloadMessage)=false;  
Message_2(EdiIntAS.IsAS2AsynchronousMdn)=true;  
Message_2(EdiIntAS.IsAS2MdnResponseMessage)=true;  
Message_2(EdiIntAS.SendMDN)=true;  
Message_2(EdiIntAS.IsAS2MessageSigned)=false;  
Message_2(EdiIntAS.AS2To)="Party1";  
Message_2(EdiIntAS.AS2From)="Home";  
Message_2(EdiIntAS.MessageId)="123456";  
Message_2(EdiIntAS.OriginalMessageId)="2123456";  
Message_2(HTTP.UserHttpHeaders)="Message1-Id: xyz\r\nMyHeader: MyValue";  
```  
  
## <a name="see-also"></a><span data-ttu-id="fe0f2-128">参照</span><span class="sxs-lookup"><span data-stu-id="fe0f2-128">See Also</span></span>  
 [<span data-ttu-id="fe0f2-129">BizTalk Server AS2 ソリューションの開発と構成</span><span class="sxs-lookup"><span data-stu-id="fe0f2-129">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)
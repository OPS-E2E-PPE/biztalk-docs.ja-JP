---
title: オーケストレーションで SOAP ヘッダーへのアクセス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP headers, orchestrations
- SOAP headers, properties
- orchestrations, SOAP headers
ms.assetid: 91fe053a-3f16-497c-b4bb-5fb54bec62e5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01260e95c6e4bb1676c2bca589660e21812f2d9a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361931"
---
# <a name="accessing-soap-headers-in-orchestrations"></a><span data-ttu-id="3ab71-102">オーケストレーションで SOAP ヘッダーへのアクセス</span><span class="sxs-lookup"><span data-stu-id="3ab71-102">Accessing SOAP Headers in Orchestrations</span></span>
<span data-ttu-id="3ab71-103">定義されていると、不明な SOAP ヘッダーのオーケストレーションで SOAP ヘッダー コンテキスト プロパティにアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="3ab71-103">You can access the SOAP header context properties in orchestrations for defined and unknown SOAP headers.</span></span> <span data-ttu-id="3ab71-104">プロパティ スキーマおよびコンテキスト プロパティの詳細については、次を参照してください。[プロパティ スキーマ](../core/property-schemas.md)します。</span><span class="sxs-lookup"><span data-stu-id="3ab71-104">For more information about property schemas and context properties, see [Property Schemas](../core/property-schemas.md).</span></span>  
  
## <a name="defined-soap-header-context-properties"></a><span data-ttu-id="3ab71-105">定義済みの SOAP ヘッダー コンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="3ab71-105">Defined SOAP header context properties</span></span>  
 <span data-ttu-id="3ab71-106">オーケストレーションで定義されている SOAP ヘッダー コンテキスト プロパティには、プロパティ スキーマが必要です。</span><span class="sxs-lookup"><span data-stu-id="3ab71-106">The defined SOAP header context properties in orchestrations require a property schema.</span></span> <span data-ttu-id="3ab71-107">プロパティ スキーマは、ターゲットの名前空間をいる必要があります**http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**、および**Property Schema Base**プロパティに設定**MessageContextPropertyBase**します。</span><span class="sxs-lookup"><span data-stu-id="3ab71-107">The property schema must have the target namespace **http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**, and the **Property Schema Base** property set to **MessageContextPropertyBase**.</span></span> <span data-ttu-id="3ab71-108">プロパティ スキーマ内の各ルート要素名は、定義済みの SOAP ヘッダーのルート要素名と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ab71-108">Each root element name in the property schema must match the root element name of the defined SOAP header.</span></span> <span data-ttu-id="3ab71-109">プロパティ スキーマおよびプロパティ名の名前空間を使用して、コンテキスト プロパティの値を表示できます。</span><span class="sxs-lookup"><span data-stu-id="3ab71-109">You can then access the values of the context properties using the namespace of the property schema and the property name.</span></span> <span data-ttu-id="3ab71-110">プロパティ スキーマの名前空間は、上に示したターゲットの名前空間と異なります。</span><span class="sxs-lookup"><span data-stu-id="3ab71-110">The namespace of the property schema is different from the target namespace listed above.</span></span> <span data-ttu-id="3ab71-111">プロパティ スキーマの名前空間には、任意の文字列できますが、通常、プロジェクトの名前を既定になります。</span><span class="sxs-lookup"><span data-stu-id="3ab71-111">Although the namespace of the property schema can be any string, it usually defaults to the name of the project.</span></span>  
  
 <span data-ttu-id="3ab71-112">次の例は、プロパティ スキーマの名前空間、SOAP ヘッダー コンテキスト プロパティにアクセスする**SOAPHeader**、およびプロパティ名**OrigDest**:</span><span class="sxs-lookup"><span data-stu-id="3ab71-112">The following example shows accessing the SOAP header context property for a property schema namespace, **SOAPHeader**, and the property name **OrigDest**:</span></span>  
  
```  
stringVar = requestMessageInstance(SOAPHeader.OrigDest);  
```  
  
> [!NOTE]
>  <span data-ttu-id="3ab71-113">定義済みの SOAP ヘッダーは、"in"または"out"ヘッダーに扱われます。</span><span class="sxs-lookup"><span data-stu-id="3ab71-113">Defined SOAP headers are treated either as "in" or "out" headers.</span></span> <span data-ttu-id="3ab71-114">ウィザードでは、要求と応答メッセージの同じ SOAP ヘッダーが定義されている場合、ウィザードでは、応答の受信値は自動的に返されません。</span><span class="sxs-lookup"><span data-stu-id="3ab71-114">If the wizard defines the same SOAP header for the request and response message, the wizard does not automatically return the incoming value in the response.</span></span> <span data-ttu-id="3ab71-115">応答メッセージの SOAP ヘッダー コンテキスト プロパティに要求メッセージの SOAP ヘッダー コンテキスト プロパティに明示的にコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ab71-115">You must explicity copy the SOAP header context property of the request message to the SOAP header context property of the response message.</span></span>  
  
## <a name="copying-soap-header-context-property-of-incoming-message"></a><span data-ttu-id="3ab71-116">受信メッセージの SOAP ヘッダー コンテキスト プロパティのコピー</span><span class="sxs-lookup"><span data-stu-id="3ab71-116">Copying SOAP header context property of incoming message</span></span>  
 <span data-ttu-id="3ab71-117">応答メッセージの同じ SOAP ヘッダー コンテキスト プロパティには、受信メッセージの SOAP ヘッダー コンテキスト プロパティをコピーできます。</span><span class="sxs-lookup"><span data-stu-id="3ab71-117">You can copy the SOAP header context property of an incoming message to the same SOAP header context property of the response message.</span></span>  
  
 <span data-ttu-id="3ab71-118">次の例では、SOAP ヘッダー コンテキスト プロパティのコピーを示しています。</span><span class="sxs-lookup"><span data-stu-id="3ab71-118">The following example shows copying the SOAP header context property:</span></span>  
  
```  
ResponseMessageInstance(SOAPHeader.OrigDest) = RequestMessageInstance(SOAPHeader.OrigDest);  
```  
  
 <span data-ttu-id="3ab71-119">SOAP 応答の SOAP ヘッダーを作成するときに、SOAP ヘッダーを正しく作成することを確認します。</span><span class="sxs-lookup"><span data-stu-id="3ab71-119">When you create SOAP headers for the SOAP response, you ensure that you create your SOAP headers correctly.</span></span> <span data-ttu-id="3ab71-120">SOAP アダプターでは、SOAP ヘッダー コンテキスト プロパティの内容を検証しません。</span><span class="sxs-lookup"><span data-stu-id="3ab71-120">The SOAP adapter does not verify the contents of the SOAP header context properties.</span></span> <span data-ttu-id="3ab71-121">応答 SOAP ヘッダーの値が正しくない場合、SOAP アダプターは、Web サービスのコンシューマーに応答メッセージを送信することはできません。</span><span class="sxs-lookup"><span data-stu-id="3ab71-121">If the values of the response SOAP headers are incorrect, the SOAP adapter cannot send the response message to the consumer of your Web service.</span></span>  
  
## <a name="unknown-soap-header-context-property"></a><span data-ttu-id="3ab71-122">不明な SOAP ヘッダー コンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="3ab71-122">Unknown SOAP header context property</span></span>  
 <span data-ttu-id="3ab71-123">不明な SOAP ヘッダー コンテキスト プロパティでは、プロパティ スキーマは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="3ab71-123">The unknown SOAP header context property does not require a property schema.</span></span> <span data-ttu-id="3ab71-124">このグローバル コンテキスト プロパティにアクセスすることができます**SOAP します。UnknownHeaders**します。</span><span class="sxs-lookup"><span data-stu-id="3ab71-124">You can access this global context property **SOAP.UnknownHeaders**.</span></span>  
  
 <span data-ttu-id="3ab71-125">次の例は、不明な SOAP ヘッダー コンテキスト プロパティにアクセスする**SOAP します。UnknownHeaders**:</span><span class="sxs-lookup"><span data-stu-id="3ab71-125">The following example shows accessing the unknown SOAP header context property **SOAP.UnknownHeaders**:</span></span>  
  
```  
stringVar = RequestMessageInstance(SOAP.UnknownHeaders);  
```  
  
 <span data-ttu-id="3ab71-126">コンテキスト プロパティに含まれる値は、XML データを含む文字列です。</span><span class="sxs-lookup"><span data-stu-id="3ab71-126">The values contained in the context properties are strings containing XML data.</span></span> <span data-ttu-id="3ab71-127">このデータにアクセスする最も簡単な方法は、BizTalk 式エディターを使用する、**メッセージの割り当て**または**式**図形および内の文字列を読み込み、 **XmlDocument**および使用特定のフィールドにアクセスする XPATH クエリです。</span><span class="sxs-lookup"><span data-stu-id="3ab71-127">The simplest way to access this data is to use the BizTalk Expression Editor in a **Message Assignment** or **Expression** shape and load the string in an **XmlDocument** and use XPATH queries to access specific fields.</span></span> <span data-ttu-id="3ab71-128">BizTalk 式エディターで XML ドキュメントの作成の詳細については、次を参照してください。 [xlang-s 言語](../core/xlang-s-language.md)します。</span><span class="sxs-lookup"><span data-stu-id="3ab71-128">For more information creating XML documents in the BizTalk Expression Editor, see [XLANG-s Language](../core/xlang-s-language.md).</span></span>  
  
 <span data-ttu-id="3ab71-129">コンテキスト プロパティは、特定のメッセージに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="3ab71-129">Context properties are associated with a particular message.</span></span> <span data-ttu-id="3ab71-130">メッセージング エンジンは、応答メッセージに要求メッセージからの既知の SOAP ヘッダーの値を自動的にマップしません。</span><span class="sxs-lookup"><span data-stu-id="3ab71-130">The Messaging Engine does not automatically map the values of known SOAP headers from the request message to the response message.</span></span> <span data-ttu-id="3ab71-131">Web サービスの応答メッセージを作成するときに具体的には、SOAP ヘッダーの値を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ab71-131">When creating the response message for a Web service, you must specifically set the SOAP header values.</span></span> <span data-ttu-id="3ab71-132">次のコマンドは、SOAP ヘッダー コンテキスト プロパティの設定の最も簡単なメソッドを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab71-132">The following command is the simplest method of setting a SOAP header context property:</span></span>  
  
```  
ResponseMessageInstance(SOAPHeader.OrigDest) = "<?xml version="1.0" encoding="utf-16"?><OrigDest xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\"><Origination xmlns=\"\">Home</Origination><Destination xmlns=\"\">Work</Destination> </OrigDest>"  
```  
  
 <span data-ttu-id="3ab71-133">作成してこれも実現できる、 **XmlDocument**の文字列値の書き込みと、 **XmlDocument**をコンテキスト プロパティ。</span><span class="sxs-lookup"><span data-stu-id="3ab71-133">You can also achieve this by creating an **XmlDocument** and writing the string value of the **XmlDocument** to the context property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ab71-134">場合、 **SOAP します。UnknownHeaders**プロパティが null で、BizTalk は自動的に SOAP 要求を SOAP 応答で受信した不明なヘッダーを返します。</span><span class="sxs-lookup"><span data-stu-id="3ab71-134">If the **SOAP.UnknownHeaders** property is null, BizTalk automatically returns the unknown headers received in the SOAP request to the SOAP response.</span></span> <span data-ttu-id="3ab71-135">場合、 **SOAP します。UnknownHeaders**応答メッセージのコンテキスト プロパティが null でないし、BizTalk は、SOAP 応答にその値を返します。</span><span class="sxs-lookup"><span data-stu-id="3ab71-135">If the **SOAP.UnknownHeaders** context property on the response message is not null, then BizTalk returns that value to the SOAP response.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ab71-136">参照</span><span class="sxs-lookup"><span data-stu-id="3ab71-136">See Also</span></span>  
 [<span data-ttu-id="3ab71-137">公開済み Web サービスでの SOAP ヘッダー</span><span class="sxs-lookup"><span data-stu-id="3ab71-137">SOAP Headers with Published Web Services</span></span>](../core/soap-headers-with-published-web-services.md)
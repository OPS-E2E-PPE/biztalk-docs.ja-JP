---
title: オーケストレーションで SOAP ヘッダーの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP headers, orchestrations
- SOAP headers, code samples
- SOAP headers, creating
- SOAP headers, properties
- Web services, SOAP headers
- orchestrations, SOAP headers
- creating, SOAP headers
ms.assetid: 4754dd23-386b-4093-8ea4-4da6b4d9279c
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cce21530c975356b811378f437cddaf8eb64612d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65321768"
---
# <a name="using-soap-headers-in-orchestrations"></a><span data-ttu-id="30dae-102">オーケストレーションで SOAP ヘッダーの使用</span><span class="sxs-lookup"><span data-stu-id="30dae-102">Using SOAP Headers in Orchestrations</span></span>
<span data-ttu-id="30dae-103">オーケストレーションでは、プロパティ スキーマを使用して、SOAP ヘッダー コンテキスト プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="30dae-103">Orchestrations use property schemas to define SOAP header context properties.</span></span> <span data-ttu-id="30dae-104">SOAP ヘッダー コンテキスト プロパティを設定するのにには、BizTalk エディターを使用します。</span><span class="sxs-lookup"><span data-stu-id="30dae-104">You use the BizTalk Editor to set SOAP header context properties.</span></span>  
  
## <a name="defining-soap-header-context-properties-with-property-schemas"></a><span data-ttu-id="30dae-105">プロパティ スキーマを使用した SOAP ヘッダー コンテキスト プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="30dae-105">Defining SOAP header context properties with property schemas</span></span>  
 <span data-ttu-id="30dae-106">プロパティ スキーマをオーケストレーションで定義済みの SOAP ヘッダー コンテキスト プロパティを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30dae-106">You need a property schema to use defined SOAP header context properties in orchestrations.</span></span> <span data-ttu-id="30dae-107">プロパティ スキーマのターゲットの名前空間をいる必要があります**http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**、および**Property Schema Base**プロパティに設定**MessageContextPropertyBase**します。</span><span class="sxs-lookup"><span data-stu-id="30dae-107">The property schema must have the target namespace of **http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**, and the **Property Schema Base** property set to **MessageContextPropertyBase**.</span></span> <span data-ttu-id="30dae-108">プロパティ スキーマ内の各ルート要素名は、定義済みの SOAP ヘッダー内のルート要素名と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30dae-108">Each root element name in the property schema must match the root element name in the defined SOAP header.</span></span> <span data-ttu-id="30dae-109">プロパティ スキーマおよびプロパティ名の名前空間を使用して、コンテキスト プロパティの値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="30dae-109">You can then set values for the context properties using the namespace of the property schema and the property name.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30dae-110">プロパティ スキーマの名前空間は、ターゲット スキーマの名前空間と異なる (**http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**)。</span><span class="sxs-lookup"><span data-stu-id="30dae-110">The namespace of the property schema is different from the namespace of the target schema (**http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**).</span></span> <span data-ttu-id="30dae-111">名前空間は、任意の文字列。ただし、通常、プロジェクトの名前を既定になります。</span><span class="sxs-lookup"><span data-stu-id="30dae-111">Your namespace can be any string; however, it usually defaults to the name of the project.</span></span>  
  
 <span data-ttu-id="30dae-112">次のコードは、プロパティ スキーマ名前空間は、SOAP ヘッダー コンテキスト プロパティを割り当てる**SOAPHeader**プロパティ名を持つ**OrigDest**:</span><span class="sxs-lookup"><span data-stu-id="30dae-112">The following code shows assigning a SOAP header context property where the property schema namespace is **SOAPHeader** with a property name of **OrigDest**:</span></span>  
  
```  
requestMessageInstance(SOAPHeader.OrigDest) = stringVar;  
```  
  
 <span data-ttu-id="30dae-113">プロパティ スキーマおよびコンテキスト プロパティの詳細については、次を参照してください。[プロパティ スキーマ](../core/property-schemas.md)します。</span><span class="sxs-lookup"><span data-stu-id="30dae-113">For more information about property schemas and context properties, see [Property Schemas](../core/property-schemas.md).</span></span>  
  
## <a name="using-biztalk-editor-to-set-soap-header-context-properties"></a><span data-ttu-id="30dae-114">BizTalk エディターを使用して、SOAP ヘッダー コンテキスト プロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="30dae-114">Using BizTalk Editor to set SOAP header context properties</span></span>  
 <span data-ttu-id="30dae-115">オーケストレーションで SOAP ヘッダー コンテキスト プロパティは、XML データを含む文字列に設定されます。</span><span class="sxs-lookup"><span data-stu-id="30dae-115">For orchestrations, the SOAP header context properties are set to strings that contain XML data.</span></span> <span data-ttu-id="30dae-116">BizTalk 式エディタを使用してこれらの文字列を設定する、**メッセージの割り当て**または**式**図形。</span><span class="sxs-lookup"><span data-stu-id="30dae-116">You set these strings using the BizTalk Expression Editor in a **Message Assignment** or **Expression** shape.</span></span>  
  
 <span data-ttu-id="30dae-117">次の例は、コンテキスト プロパティを設定する文字列を示しています。</span><span class="sxs-lookup"><span data-stu-id="30dae-117">The following example shows the string setting the context property:</span></span>  
  
```  
RequestMessageInstance(SOAPHeader.OrigDest) = "<?xml version=\"1.0\"?>  
<OrigDest xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\">  
<Origination>Home</Origination>  
<Destination>Work</Destination>  
</OrigDest>"  
```  
  
## <a name="using-biztalk-editor-to-create-an-instance-of-a-soap-header-root-element"></a><span data-ttu-id="30dae-118">BizTalk エディターを使用して、SOAP ヘッダー ルート要素のインスタンスを作成するには</span><span class="sxs-lookup"><span data-stu-id="30dae-118">Using BizTalk Editor to create an instance of a SOAP header root element</span></span>  
 <span data-ttu-id="30dae-119">SOAP ヘッダーを正しい文字列に設定すると、困難なことができます。</span><span class="sxs-lookup"><span data-stu-id="30dae-119">Setting the SOAP header to the correct string can be difficult.</span></span> <span data-ttu-id="30dae-120">BizTalk プロジェクトに Web 参照を追加するには、すべての複合 Web メッセージ部分は、ルート要素として Reference.xsd に追加されます。</span><span class="sxs-lookup"><span data-stu-id="30dae-120">When adding a Web reference to a BizTalk project, all complex Web message parts are added to Reference.xsd as root elements.</span></span> <span data-ttu-id="30dae-121">Reference.xsd には、各定義済みの SOAP ヘッダーのルート要素も含まれています。</span><span class="sxs-lookup"><span data-stu-id="30dae-121">Reference.xsd also contains root elements for each defined SOAP header.</span></span> <span data-ttu-id="30dae-122">SOAP ヘッダーを正しい文字列を設定するためには、BizTalk エディターを使用して Reference.xsd の SOAP ヘッダー ルート要素のインスタンスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30dae-122">To ensure that you set the SOAP header with the correct string, you should use BizTalk Editor to create an instance of the SOAP header root element for Reference.xsd.</span></span> <span data-ttu-id="30dae-123">実際のデータを格納するのに、生成されたインスタンス データを直接またはインスタンス データを使用できます。</span><span class="sxs-lookup"><span data-stu-id="30dae-123">You can use the generated instance data directly or the instance data to contain your real data.</span></span>  
  
 <span data-ttu-id="30dae-124">BizTalk エディターを使用してインスタンス データを生成する方法の詳細については、次を参照してください。[インスタンス メッセージの生成方法](../core/how-to-generate-instance-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="30dae-124">For more information about using the BizTalk Editor to generate instance data, see [How to Generate Instance Messages](../core/how-to-generate-instance-messages.md).</span></span>  
  
## <a name="creating-an-xmldocument-to-set-context-properties"></a><span data-ttu-id="30dae-125">コンテキスト プロパティを設定する XmlDocument の作成</span><span class="sxs-lookup"><span data-stu-id="30dae-125">Creating an XmlDocument to set context properties</span></span>  
 <span data-ttu-id="30dae-126">コンテキスト プロパティを設定するには、作成を**XmlDocument**との文字列値を書き込み、 **XmlDocument**をコンテキスト プロパティ。</span><span class="sxs-lookup"><span data-stu-id="30dae-126">You can set context properties by creating an **XmlDocument** and writing the string value of the **XmlDocument** to the context property.</span></span> <span data-ttu-id="30dae-127">型の変数を宣言する**XMLDocument**し、XML データを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="30dae-127">You declare a variable of type **XMLDocument** and assign the XML data.</span></span>  
  
 <span data-ttu-id="30dae-128">次の例では、宣言型の変数を設定**XMLDocument**し、XML データを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="30dae-128">The following example shows setting a declaring a variable of type **XMLDocument** and assign the XML data:</span></span>  
  
```  
xmlDoc.LoadXml("<?xml version=\"1.0\"?><OrigDest xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\"><Origination>Home</Origination><Destination>Work</Destination></OrigDest>");  
```  
  
 <span data-ttu-id="30dae-129">次の例では、コンテキスト プロパティの設定を示しています。</span><span class="sxs-lookup"><span data-stu-id="30dae-129">The following example shows setting the context property:</span></span>  
  
```  
RequestMessageInstance(SOAPHeader.OrigDest) = xmlDoc.OuterXml;  
```  
  
 <span data-ttu-id="30dae-130">詳細については、BizTalk 式エディターを使用して、次を参照してください。[式の要件と制限](../core/requirements-and-limitations-for-expressions.md)します。</span><span class="sxs-lookup"><span data-stu-id="30dae-130">For more information about using BizTalk Expression Editor, see [Requirements and Limitations for Expressions](../core/requirements-and-limitations-for-expressions.md).</span></span> <span data-ttu-id="30dae-131">.NET クラスを呼び出すことの詳細については、次を参照してください。[ユーザー コードでのメッセージの構築](../core/constructing-messages-in-user-code.md)します。</span><span class="sxs-lookup"><span data-stu-id="30dae-131">For more information about calling .NET classes, see [Constructing Messages in User Code](../core/constructing-messages-in-user-code.md).</span></span>  
  
## <a name="creating-soap-headers-for-a-soap-request"></a><span data-ttu-id="30dae-132">SOAP 要求の SOAP ヘッダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="30dae-132">Creating SOAP headers for a SOAP request</span></span>  
 <span data-ttu-id="30dae-133">SOAP 要求の SOAP ヘッダーを作成するときに、SOAP ヘッダーを正しく作成されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30dae-133">When you create SOAP headers for the SOAP request, you must ensure that you have correctly created the SOAP headers.</span></span> <span data-ttu-id="30dae-134">SOAP アダプターでは、SOAP ヘッダー コンテキスト プロパティの内容を検証しません。</span><span class="sxs-lookup"><span data-stu-id="30dae-134">The SOAP adapter does not verify the contents of the SOAP header context properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30dae-135">SOAP ヘッダーが正しくない場合、BizTalk は、Web サービスに SOAP 要求を送信することはできません。</span><span class="sxs-lookup"><span data-stu-id="30dae-135">If the SOAP header is incorrect, BizTalk cannot send the SOAP request to the Web service.</span></span>  
  
 <span data-ttu-id="30dae-136">BizTalk を返す Web サービスに SOAP 応答は、SOAP ヘッダーを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="30dae-136">The SOAP response that BizTalk returns to the Web service may also contain SOAP headers.</span></span> <span data-ttu-id="30dae-137">定義済みの SOAP ヘッダーがある場合は、これらの SOAP ヘッダーのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="30dae-137">You can only access these SOAP headers if they are defined SOAP headers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30dae-138">消費済み Web サービスのサポートは、SOAP ヘッダーを定義するだけです。</span><span class="sxs-lookup"><span data-stu-id="30dae-138">Consumed Web services support only defined SOAP headers.</span></span>  
  
 <span data-ttu-id="30dae-139">定義済みの SOAP ヘッダーの詳細については、次を参照してください。[を使用して SOAP ヘッダー](../core/using-soap-headers.md)します。</span><span class="sxs-lookup"><span data-stu-id="30dae-139">For more information about defined SOAP headers, see [Using SOAP Headers](../core/using-soap-headers.md).</span></span> <span data-ttu-id="30dae-140">応答 SOAP ヘッダーは、要求 SOAP ヘッダーと同じ構文を使用するコンテキスト プロパティに設定されます。</span><span class="sxs-lookup"><span data-stu-id="30dae-140">The response SOAP headers are set to context properties using the same syntax as the request SOAP headers.</span></span>  
  
 <span data-ttu-id="30dae-141">次のコードでは、応答 SOAP ヘッダーにアクセスする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="30dae-141">The following code shows how to access the response SOAP headers:</span></span>  
  
```  
stringVar = ResponseMessageInstance(SOAPHeader.OrigDest);  
```  
  
 <span data-ttu-id="30dae-142">コンテキスト プロパティに含まれる値は、XML データを含む文字列です。</span><span class="sxs-lookup"><span data-stu-id="30dae-142">The values contained in the context properties are strings containing XML data.</span></span> <span data-ttu-id="30dae-143">BizTalk 式エディタを使用してこれらの文字列を設定する、**メッセージの割り当て**または**式**図形。</span><span class="sxs-lookup"><span data-stu-id="30dae-143">You set these strings using BizTalk Expression Editor in a **Message Assignment** or **Expression** shape.</span></span> <span data-ttu-id="30dae-144">内の文字列を読み込み、 **XmlDocument** XPath クエリを使用して、特定のフィールドにアクセスするとします。</span><span class="sxs-lookup"><span data-stu-id="30dae-144">You load the string in an **XmlDocument** and use XPath queries to access specific fields.</span></span>  
  
 <span data-ttu-id="30dae-145">BizTalk 式エディターで XML ドキュメントの作成の詳細については、次を参照してください。 [xlang-s 言語](../core/xlang-s-language.md)します。</span><span class="sxs-lookup"><span data-stu-id="30dae-145">For more information about creating XML documents in BizTalk Expression Editor, see [XLANG-s Language](../core/xlang-s-language.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30dae-146">参照</span><span class="sxs-lookup"><span data-stu-id="30dae-146">See Also</span></span>  
 <span data-ttu-id="30dae-147">[Xlang-s 言語](../core/xlang-s-language.md) </span><span class="sxs-lookup"><span data-stu-id="30dae-147">[XLANG-s Language](../core/xlang-s-language.md) </span></span>  
 [<span data-ttu-id="30dae-148">使用する Web サービスでの SOAP ヘッダー</span><span class="sxs-lookup"><span data-stu-id="30dae-148">SOAP Headers with Consumed Web Services</span></span>](../core/soap-headers-with-consumed-web-services.md)
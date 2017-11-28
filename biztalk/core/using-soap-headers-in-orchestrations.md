---
title: "オーケストレーションで SOAP ヘッダーの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faae7013c824926adea67feab296e1993f93e326
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-soap-headers-in-orchestrations"></a><span data-ttu-id="f79fd-102">オーケストレーションで SOAP ヘッダーの使用</span><span class="sxs-lookup"><span data-stu-id="f79fd-102">Using SOAP Headers in Orchestrations</span></span>
<span data-ttu-id="f79fd-103">オーケストレーションは、プロパティ スキーマを使用して SOAP ヘッダー コンテキスト プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="f79fd-103">Orchestrations use property schemas to define SOAP header context properties.</span></span> <span data-ttu-id="f79fd-104">SOAP ヘッダー コンテキスト プロパティを設定するのにには、BizTalk エディターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f79fd-104">You use the BizTalk Editor to set SOAP header context properties.</span></span>  
  
## <a name="defining-soap-header-context-properties-with-property-schemas"></a><span data-ttu-id="f79fd-105">プロパティ スキーマを使用した SOAP ヘッダー コンテキスト プロパティの定義</span><span class="sxs-lookup"><span data-stu-id="f79fd-105">Defining SOAP header context properties with property schemas</span></span>  
 <span data-ttu-id="f79fd-106">オーケストレーション内に定義されている SOAP ヘッダー コンテキスト プロパティを使用するには、プロパティ スキーマが必要です。</span><span class="sxs-lookup"><span data-stu-id="f79fd-106">You need a property schema to use defined SOAP header context properties in orchestrations.</span></span> <span data-ttu-id="f79fd-107">プロパティ スキーマのターゲットの名前空間を持つ必要があります**http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**、および**Property Schema Base**プロパティに設定**MessageContextPropertyBase**です。</span><span class="sxs-lookup"><span data-stu-id="f79fd-107">The property schema must have the target namespace of **http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**, and the **Property Schema Base** property set to **MessageContextPropertyBase**.</span></span> <span data-ttu-id="f79fd-108">プロパティ スキーマ内の各ルート要素名は、定義されている SOAP ヘッダーのルート要素名に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f79fd-108">Each root element name in the property schema must match the root element name in the defined SOAP header.</span></span> <span data-ttu-id="f79fd-109">これにより、プロパティ スキーマの名前空間とプロパティ名を使用してコンテキスト プロパティの値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="f79fd-109">You can then set values for the context properties using the namespace of the property schema and the property name.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f79fd-110">プロパティ スキーマの名前空間は、ターゲット スキーマの名前空間と異なる (**http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**)。</span><span class="sxs-lookup"><span data-stu-id="f79fd-110">The namespace of the property schema is different from the namespace of the target schema (**http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**).</span></span> <span data-ttu-id="f79fd-111">名前空間には任意の文字列を指定できますが、通常は既定によりプロジェクト名が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f79fd-111">Your namespace can be any string; however, it usually defaults to the name of the project.</span></span>  
  
 <span data-ttu-id="f79fd-112">次のコードは、プロパティ スキーマの名前空間がここでは、SOAP ヘッダー コンテキスト プロパティを割り当てる**SOAPHeader**というプロパティ名を持つ**OrigDest**:</span><span class="sxs-lookup"><span data-stu-id="f79fd-112">The following code shows assigning a SOAP header context property where the property schema namespace is **SOAPHeader** with a property name of **OrigDest**:</span></span>  
  
```  
requestMessageInstance(SOAPHeader.OrigDest) = stringVar;  
```  
  
 <span data-ttu-id="f79fd-113">プロパティ スキーマおよびコンテキスト プロパティの詳細については、次を参照してください。[プロパティ スキーマ](../core/property-schemas.md)です。</span><span class="sxs-lookup"><span data-stu-id="f79fd-113">For more information about property schemas and context properties, see [Property Schemas](../core/property-schemas.md).</span></span>  
  
## <a name="using-biztalk-editor-to-set-soap-header-context-properties"></a><span data-ttu-id="f79fd-114">BizTalk エディタでの SOAP ヘッダー コンテキスト プロパティの設定</span><span class="sxs-lookup"><span data-stu-id="f79fd-114">Using BizTalk Editor to set SOAP header context properties</span></span>  
 <span data-ttu-id="f79fd-115">オーケストレーションでは、SOAP ヘッダーのコンテキスト プロパティは、XML データを含む文字列に設定されます。</span><span class="sxs-lookup"><span data-stu-id="f79fd-115">For orchestrations, the SOAP header context properties are set to strings that contain XML data.</span></span> <span data-ttu-id="f79fd-116">BizTalk 式エディタを使用してこれらの文字列を設定する、**メッセージの割り当て**または**式**図形です。</span><span class="sxs-lookup"><span data-stu-id="f79fd-116">You set these strings using the BizTalk Expression Editor in a **Message Assignment** or **Expression** shape.</span></span>  
  
 <span data-ttu-id="f79fd-117">次の例は、コンテキスト プロパティを設定する文字列を示しています。</span><span class="sxs-lookup"><span data-stu-id="f79fd-117">The following example shows the string setting the context property:</span></span>  
  
```  
RequestMessageInstance(SOAPHeader.OrigDest) = "<?xml version=\"1.0\"?>  
<OrigDest xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\">  
<Origination>Home</Origination>  
<Destination>Work</Destination>  
</OrigDest>"  
```  
  
## <a name="using-biztalk-editor-to-create-an-instance-of-a-soap-header-root-element"></a><span data-ttu-id="f79fd-118">BizTalk エディタでの SOAP ヘッダー ルート要素のインスタンスの作成</span><span class="sxs-lookup"><span data-stu-id="f79fd-118">Using BizTalk Editor to create an instance of a SOAP header root element</span></span>  
 <span data-ttu-id="f79fd-119">SOAP ヘッダーを正しい文字列に設定することが困難な場合もあります。</span><span class="sxs-lookup"><span data-stu-id="f79fd-119">Setting the SOAP header to the correct string can be difficult.</span></span> <span data-ttu-id="f79fd-120">BizTalk プロジェクトに Web 参照を追加するときに、すべての複雑な Web メッセージ部分がルート要素として Reference.xsd に追加されます。</span><span class="sxs-lookup"><span data-stu-id="f79fd-120">When adding a Web reference to a BizTalk project, all complex Web message parts are added to Reference.xsd as root elements.</span></span> <span data-ttu-id="f79fd-121">Reference.xsd には、定義されている各 SOAP ヘッダーのルート要素も含まれます。</span><span class="sxs-lookup"><span data-stu-id="f79fd-121">Reference.xsd also contains root elements for each defined SOAP header.</span></span> <span data-ttu-id="f79fd-122">SOAP ヘッダーを正しい文字列に設定するためには、BizTalk エディタを使用して Reference.xsd の SOAP ヘッダー ルート要素のインスタンスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f79fd-122">To ensure that you set the SOAP header with the correct string, you should use BizTalk Editor to create an instance of the SOAP header root element for Reference.xsd.</span></span> <span data-ttu-id="f79fd-123">生成されたインスタンス データを直接使用することも、インスタンス データに実際のデータを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="f79fd-123">You can use the generated instance data directly or the instance data to contain your real data.</span></span>  
  
 <span data-ttu-id="f79fd-124">BizTalk エディターを使用してインスタンス データを生成する方法の詳細については、次を参照してください。[インスタンス メッセージの生成方法](../core/how-to-generate-instance-messages.md)です。</span><span class="sxs-lookup"><span data-stu-id="f79fd-124">For more information about using the BizTalk Editor to generate instance data, see [How to Generate Instance Messages](../core/how-to-generate-instance-messages.md).</span></span>  
  
## <a name="creating-an-xmldocument-to-set-context-properties"></a><span data-ttu-id="f79fd-125">XmlDocument の作成によるコンテキスト プロパティの設定</span><span class="sxs-lookup"><span data-stu-id="f79fd-125">Creating an XmlDocument to set context properties</span></span>  
 <span data-ttu-id="f79fd-126">コンテキスト プロパティを設定するには作成することで、 **XmlDocument**と書き込みの文字列値、 **XmlDocument**をコンテキスト プロパティです。</span><span class="sxs-lookup"><span data-stu-id="f79fd-126">You can set context properties by creating an **XmlDocument** and writing the string value of the **XmlDocument** to the context property.</span></span> <span data-ttu-id="f79fd-127">型の変数を宣言する**XMLDocument**し、XML データを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f79fd-127">You declare a variable of type **XMLDocument** and assign the XML data.</span></span>  
  
 <span data-ttu-id="f79fd-128">次の例では宣言型の変数を設定**XMLDocument**し、XML データを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f79fd-128">The following example shows setting a declaring a variable of type **XMLDocument** and assign the XML data:</span></span>  
  
```  
xmlDoc.LoadXml("<?xml version=\"1.0\"?><OrigDest xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\"><Origination>Home</Origination><Destination>Work</Destination></OrigDest>");  
```  
  
 <span data-ttu-id="f79fd-129">次の例は、コンテキスト プロパティの設定方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f79fd-129">The following example shows setting the context property:</span></span>  
  
```  
RequestMessageInstance(SOAPHeader.OrigDest) = xmlDoc.OuterXml;  
```  
  
 <span data-ttu-id="f79fd-130">詳細については、BizTalk 式エディターを使用して、次を参照してください。[式の要件と制限](../core/requirements-and-limitations-for-expressions.md)です。</span><span class="sxs-lookup"><span data-stu-id="f79fd-130">For more information about using BizTalk Expression Editor, see [Requirements and Limitations for Expressions](../core/requirements-and-limitations-for-expressions.md).</span></span> <span data-ttu-id="f79fd-131">.NET クラスを呼び出すことの詳細については、次を参照してください。[ユーザー コードでメッセージを構築する](../core/constructing-messages-in-user-code.md)です。</span><span class="sxs-lookup"><span data-stu-id="f79fd-131">For more information about calling .NET classes, see [Constructing Messages in User Code](../core/constructing-messages-in-user-code.md).</span></span>  
  
## <a name="creating-soap-headers-for-a-soap-request"></a><span data-ttu-id="f79fd-132">SOAP 要求の SOAP ヘッダーの作成</span><span class="sxs-lookup"><span data-stu-id="f79fd-132">Creating SOAP headers for a SOAP request</span></span>  
 <span data-ttu-id="f79fd-133">SOAP 要求の SOAP ヘッダーを作成するときは、SOAP ヘッダーが正しく作成されたことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f79fd-133">When you create SOAP headers for the SOAP request, you must ensure that you have correctly created the SOAP headers.</span></span> <span data-ttu-id="f79fd-134">SOAP アダプタでは SOAP ヘッダー コンテキスト プロパティの内容を検証しません。</span><span class="sxs-lookup"><span data-stu-id="f79fd-134">The SOAP adapter does not verify the contents of the SOAP header context properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f79fd-135">SOAP ヘッダーが正しくなければ、BizTalk は Web サービスに SOAP 要求を送信できません。</span><span class="sxs-lookup"><span data-stu-id="f79fd-135">If the SOAP header is incorrect, BizTalk cannot send the SOAP request to the Web service.</span></span>  
  
 <span data-ttu-id="f79fd-136">BizTalk から Web サービスに返される SOAP 応答にも SOAP ヘッダーが含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="f79fd-136">The SOAP response that BizTalk returns to the Web service may also contain SOAP headers.</span></span> <span data-ttu-id="f79fd-137">これらの SOAP ヘッダーには、定義されている SOAP ヘッダーである場合にのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f79fd-137">You can only access these SOAP headers if they are defined SOAP headers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f79fd-138">使用される Web サービスは、定義されている SOAP ヘッダーのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="f79fd-138">Consumed Web services support only defined SOAP headers.</span></span>  
  
 <span data-ttu-id="f79fd-139">定義済み SOAP ヘッダーの詳細については、次を参照してください。[を使用して SOAP ヘッダー](../core/using-soap-headers.md)です。</span><span class="sxs-lookup"><span data-stu-id="f79fd-139">For more information about defined SOAP headers, see [Using SOAP Headers](../core/using-soap-headers.md).</span></span> <span data-ttu-id="f79fd-140">応答 SOAP ヘッダーは、要求 SOAP ヘッダーと同じ構文を使用してコンテキスト プロパティに設定されます。</span><span class="sxs-lookup"><span data-stu-id="f79fd-140">The response SOAP headers are set to context properties using the same syntax as the request SOAP headers.</span></span>  
  
 <span data-ttu-id="f79fd-141">次のコードは、応答 SOAP ヘッダーへのアクセス方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f79fd-141">The following code shows how to access the response SOAP headers:</span></span>  
  
```  
stringVar = ResponseMessageInstance(SOAPHeader.OrigDest);  
```  
  
 <span data-ttu-id="f79fd-142">コンテキスト プロパティに含まれている値は、XML データを含む文字列です。</span><span class="sxs-lookup"><span data-stu-id="f79fd-142">The values contained in the context properties are strings containing XML data.</span></span> <span data-ttu-id="f79fd-143">BizTalk 式エディタを使用してこれらの文字列を設定する、**メッセージの割り当て**または**式**図形です。</span><span class="sxs-lookup"><span data-stu-id="f79fd-143">You set these strings using BizTalk Expression Editor in a **Message Assignment** or **Expression** shape.</span></span> <span data-ttu-id="f79fd-144">内の文字列を読み込み、 **XmlDocument**を使用して XPath クエリを特定のフィールドにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="f79fd-144">You load the string in an **XmlDocument** and use XPath queries to access specific fields.</span></span>  
  
 <span data-ttu-id="f79fd-145">BizTalk 式エディターで XML ドキュメントの作成の詳細については、次を参照してください。 [XLANG-s 言語](../core/xlang-s-language.md)します。</span><span class="sxs-lookup"><span data-stu-id="f79fd-145">For more information about creating XML documents in BizTalk Expression Editor, see [XLANG-s Language](../core/xlang-s-language.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f79fd-146">参照</span><span class="sxs-lookup"><span data-stu-id="f79fd-146">See Also</span></span>  
 <span data-ttu-id="f79fd-147">[XLANG の言語](../core/xlang-s-language.md) </span><span class="sxs-lookup"><span data-stu-id="f79fd-147">[XLANG-s Language](../core/xlang-s-language.md) </span></span>  
 [<span data-ttu-id="f79fd-148">使用する Web サービスでの SOAP ヘッダー</span><span class="sxs-lookup"><span data-stu-id="f79fd-148">SOAP Headers with Consumed Web Services</span></span>](../core/soap-headers-with-consumed-web-services.md)
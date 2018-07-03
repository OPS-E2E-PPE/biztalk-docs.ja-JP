---
title: Web サービスを使用するための計画 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24863069-929b-4b0b-9643-073965fb5532
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d8373ffa078b0138979e34a154330b429a73664
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986075"
---
# <a name="planning-for-consuming-web-services"></a><span data-ttu-id="80515-102">Web サービスを使用の計画</span><span class="sxs-lookup"><span data-stu-id="80515-102">Planning for Consuming Web Services</span></span>
<span data-ttu-id="80515-103">Web サービスの計画は、Web サービスを公開し、Web サービスを使用するための計画の計画、2 つのカテゴリに分けることができます。</span><span class="sxs-lookup"><span data-stu-id="80515-103">Planning for Web services can be divided into two categories, planning for publishing Web services and planning for consuming Web services.</span></span> <span data-ttu-id="80515-104">このトピックでは、Web サービスの使用に関する考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="80515-104">This topic describes the considerations for consuming Web services.</span></span> <span data-ttu-id="80515-105">Web サービスを公開する方法については、次を参照してください。 [Planning for Web の発行 Services1](../technical-guides/planning-for-publishing-web-services1.md)します。</span><span class="sxs-lookup"><span data-stu-id="80515-105">For information about publishing Web services, see [Planning for Publishing Web Services1](../technical-guides/planning-for-publishing-web-services1.md).</span></span>  
  
 <span data-ttu-id="80515-106">計画を作成するには、次を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="80515-106">Keep the following in mind as you create your plan:</span></span>  
  
- <span data-ttu-id="80515-107">**パラメーター名に 2 つのアンダー スコア文字を使用**</span><span class="sxs-lookup"><span data-stu-id="80515-107">**Using Two Underscore Characters in a Parameter Name**</span></span>  
  
   <span data-ttu-id="80515-108">Web メソッドのパラメータ名を "__" (2 つのアンダースコア文字) で始めることはできません。</span><span class="sxs-lookup"><span data-stu-id="80515-108">Parameter names for Web methods cannot begin with "__" (two underscore characters).</span></span> <span data-ttu-id="80515-109">2 つのアンダースコア文字で始まる名前を使用すると、XLANG/s でサポートされない (使用できない) Web メッセージ部分が作成される場合があります。</span><span class="sxs-lookup"><span data-stu-id="80515-109">Names that begin with two underscore characters may create Web message parts that are unsupported (unusable) by XLANG/s.</span></span>  
  
- <span data-ttu-id="80515-110">**すべての要素と anyAttribute の Web メソッドでは、属性はサポートされていません**</span><span class="sxs-lookup"><span data-stu-id="80515-110">**The Any Element and the anyAttribute Attributes Are Not Supported in Web Methods**</span></span>  
  
   <span data-ttu-id="80515-111">使用することはできません、**任意**要素または**anyAttribute** Web メソッドのスキーマ内の属性。</span><span class="sxs-lookup"><span data-stu-id="80515-111">You cannot use the **any** element or **anyAttribute** attribute in the schema for a Web method.</span></span>  
  
- <span data-ttu-id="80515-112">**Xlang/s キーワードの使用**</span><span class="sxs-lookup"><span data-stu-id="80515-112">**Using XLANG/s Keywords**</span></span>  
  
   <span data-ttu-id="80515-113">Web サービス名または Web メソッド名に XLANG/s のキーワードを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="80515-113">A Web service name or a Web method name cannot be a keyword in an XLANG/s.</span></span> <span data-ttu-id="80515-114">Web サービス名または Web メソッド名で XLANG/s のキーワードを使用すると、Web サービスを追加するときにコンパイル エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="80515-114">If you use an XLANG/s keyword in the Web service name or Web method name, you will get a compilation error when you add the Web service.</span></span> <span data-ttu-id="80515-115">Xlang/s 言語の予約語の一覧は、次を参照してください。、 [xlang/s の予約語](http://go.microsoft.com/fwlink/?LinkId=155765)(http://go.microsoft.com/fwlink/?LinkId=155765)します。</span><span class="sxs-lookup"><span data-stu-id="80515-115">For a list of reserved words for the XLANG/s language, see the [XLANG/s Reserved Words](http://go.microsoft.com/fwlink/?LinkId=155765) (http://go.microsoft.com/fwlink/?LinkId=155765).</span></span>  
  
- <span data-ttu-id="80515-116">**パラメーターの型のサポートを必要な xlang/s**</span><span class="sxs-lookup"><span data-stu-id="80515-116">**Required XLANG/s Support for Parameter Types**</span></span>  
  
   <span data-ttu-id="80515-117">非 xlang/s サポートされている Web メソッドのパラメーター型を使用すると、コンパイル エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="80515-117">Using non-XLANG/s supported Web method parameter types will cause compilation errors.</span></span> <span data-ttu-id="80515-118">たとえば、BizTalk Server では 1 次元配列のスキーマの種類で構成されるパラメータはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="80515-118">For example, BizTalk Server does not support a parameter that consists of a single dimensional array of schema types.</span></span> <span data-ttu-id="80515-119">さらに、BizTalk Server では、多次元配列はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="80515-119">In addition, BizTalk Server does not support multidimensional arrays.</span></span> <span data-ttu-id="80515-120">Xlang/s 言語は、BizTalk server によって予約されている単語の一覧は、次を参照してください。 [xlang/s の予約語](http://go.microsoft.com/fwlink/?LinkId=155765)(http://go.microsoft.com/fwlink/?LinkId=155765)します。</span><span class="sxs-lookup"><span data-stu-id="80515-120">For a list of words that XLANG/s language reserves in BizTalk Server, see [XLANG/s Reserved Words](http://go.microsoft.com/fwlink/?LinkId=155765) (http://go.microsoft.com/fwlink/?LinkId=155765).</span></span>  
  
- <span data-ttu-id="80515-121">**Web 参照を含む c# のキーワードまたは識別子を追加することでコンパイル エラーが生じないように**</span><span class="sxs-lookup"><span data-stu-id="80515-121">**Avoiding Compilation Errors Caused by Adding Web References Containing C# Keywords or Identifiers**</span></span>  
  
   <span data-ttu-id="80515-122">使用すると、 **Web 参照の追加**BizTalk Server を BizTalk プロジェクトに Web 参照を追加するにはスキーマに対して各 Web メソッドを呼び出すために必要なスキーマ型に変換します。</span><span class="sxs-lookup"><span data-stu-id="80515-122">When you use the **Add Web Reference**to add Web references to BizTalk projects, BizTalk Server converts the schema types that are required to call each Web method to schemas.</span></span> <span data-ttu-id="80515-123">変換後のスキーマは Reference.xsd に追加されます。</span><span class="sxs-lookup"><span data-stu-id="80515-123">BizTalk Server adds these schemas to Reference.xsd.</span></span> <span data-ttu-id="80515-124">スキーマに C# のキーワードと同じ要素名や C# の識別子として有効でない要素名が含まれる場合は、ランタイム エラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="80515-124">If your schemas contain element names that are C# keywords or the element name is not valid as a C# identifier, you may get a run-time error.</span></span> <span data-ttu-id="80515-125">ランタイム エラーを回避するには、使用する Web サービスに C# のキーワードと同じ要素名や C# の識別子として無効な要素名を含めないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="80515-125">To avoid run-time errors, ensure that the Web service you consume does not contain element names that are C# keywords or invalid C# identifiers.</span></span>  
  
- <span data-ttu-id="80515-126">**複数のサービス/ポートの種類の定義はサポートされていません**</span><span class="sxs-lookup"><span data-stu-id="80515-126">**Multiple Service/Port Type Definitions Are Unsupported**</span></span>  
  
   <span data-ttu-id="80515-127">BizTalk Server では、単一のサービスおよびポートの種類の定義を含む Web サービス ファイルを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="80515-127">BizTalk Server supports adding a Web service file with a single service and port type definition.</span></span> <span data-ttu-id="80515-128">複数のサービスまたはポートの種類の定義を含む WSDL ファイルを追加すると、次のエラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="80515-128">If you add a WSDL file with multiple service or port type definitions, you may receive the following error:</span></span>  
  
   `Could not generate BizTalk files. Object reference not set to an instance of an object.`  
  
- <span data-ttu-id="80515-129">**Web サービスによって公開される配列を使用するためのサポート**</span><span class="sxs-lookup"><span data-stu-id="80515-129">**Support for Consuming Arrays Exposed by Web Services**</span></span>  
  
   <span data-ttu-id="80515-130">BizTalk Server では、BizTalk Server Web サービスではない Web サービスによって公開される 1 次元配列およびジャグ配列を使用できます。</span><span class="sxs-lookup"><span data-stu-id="80515-130">BizTalk Server can consume one dimensional and jagged arrays exposed by Web services that are not BizTalk Server Web services.</span></span> <span data-ttu-id="80515-131">Web サービスの配列を使用する方法の詳細については、次を参照してください。 [Web サービスの配列を使用する方法](http://go.microsoft.com/fwlink/?LinkId=155766)(http://go.microsoft.com/fwlink/?LinkId=155766)します。</span><span class="sxs-lookup"><span data-stu-id="80515-131">For more information about how to consume Web service arrays, see [How to Consume Web Service Arrays](http://go.microsoft.com/fwlink/?LinkId=155766) (http://go.microsoft.com/fwlink/?LinkId=155766).</span></span>  
  
  > [!NOTE]  
  >  <span data-ttu-id="80515-132">多次元配列の構文はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="80515-132">Multi dimensional array syntax is not supported.</span></span> <span data-ttu-id="80515-133">たとえば、 *MyArray [「1, 5]* します。</span><span class="sxs-lookup"><span data-stu-id="80515-133">For example, *MyArray[1,5]*.</span></span>  
  
  > [!NOTE]  
  >  <span data-ttu-id="80515-134">BizTalk Server がの配列の使用をサポートしていません**データセット**Web サービスによって公開されているオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="80515-134">BizTalk Server does not support consuming an array of **DataSet** objects exposed by a Web service.</span></span> <span data-ttu-id="80515-135">Xlang/s サブサービスは、.NET DataSet クラスをサポートしてネイティブがプロジェクトをコンパイルしようとしたときにエラーが発生する、.NET DataSet オブジェクトの配列を公開する Web サービスへの Web 参照を含む BizTalk プロジェクトを作成する場合。</span><span class="sxs-lookup"><span data-stu-id="80515-135">The XLANG/s subservice does natively support the .NET DataSet class, but if you create a BizTalk project that contains a Web reference to a Web service that exposes an array of .NET DataSet objects you will get errors when you attempt to compile the project.</span></span>  
  
- <span data-ttu-id="80515-136">**Xml シリアル化可能な web メソッドのパラメーターが必要があります。**</span><span class="sxs-lookup"><span data-stu-id="80515-136">**Web Method Parameters Must be Xml Serializable**</span></span>  
  
   <span data-ttu-id="80515-137">使用する Web サービスのパラメータはすべて、XML シリアル化可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="80515-137">All parameters in a consumed Web service must be Xml Serializable.</span></span> <span data-ttu-id="80515-138">XML シリアル化可能でないパラメータを含む Web メソッドを追加すると、次のエラー メッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="80515-138">If you add a Web method that contains a parameter that is not Xml Serializable, you may receive the following error message:</span></span>  
  
   <span data-ttu-id="80515-139">"System.Xml.Element はメッセージ部分の型になるように、XML にシリアル化可能である必要があります。"</span><span class="sxs-lookup"><span data-stu-id="80515-139">System.Xml.Element must be Xml Seralizeable to be a message part type.</span></span>  
  
  > [!NOTE]  
  >  <span data-ttu-id="80515-140">データ型、 **XmlDocument**と**データセット**、サポートされていない Xml シリアル化可能な中にします。</span><span class="sxs-lookup"><span data-stu-id="80515-140">The data types, **XmlDocument** and **DataSet**, while not Xml Serializable, are supported.</span></span>  
  
- <span data-ttu-id="80515-141">**メッセージングのみの Web サービスの使用**</span><span class="sxs-lookup"><span data-stu-id="80515-141">**Consuming Messaging-Only Web Services**</span></span>  
  
   <span data-ttu-id="80515-142">メッセージングのみの Web サービスを利用する場合、すべて BizTalk Server メッセージ ボディ部分の名前は、Web メソッドのパラメーター名と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80515-142">When consuming messaging-only Web services, all BizTalk Server message body part names must match the Web method parameter names.</span></span> <span data-ttu-id="80515-143">たとえば、Web サービスの署名が `WebMethod(MyType1 type1, MyType2 type2)` である場合、ボディ部分の名前は type1 および type2 である必要があります。それ以外の場合は、次の実行時エラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="80515-143">For example, if the signature of the Web service is `WebMethod(MyType1 type1, MyType2 type2)`, the part name must be type1 and type2, you may get the following runtime error:</span></span>  
  
   `Failed to retrieve the message part for parameter %1`  
  
   <span data-ttu-id="80515-144">詳細については、次を参照してください。 [Messaging-Only シナリオで Web サービスを使用する方法](http://go.microsoft.com/fwlink/?LinkId=155767)(http://go.microsoft.com/fwlink/?LinkId=155767)します。</span><span class="sxs-lookup"><span data-stu-id="80515-144">For more information, see [How to Consume Web Services in a Messaging-Only Scenario](http://go.microsoft.com/fwlink/?LinkId=155767) (http://go.microsoft.com/fwlink/?LinkId=155767).</span></span>  
  
- <span data-ttu-id="80515-145">**プログラムによる SOAP 送信ポートの構成**</span><span class="sxs-lookup"><span data-stu-id="80515-145">**Configuring a SOAP Send Port Programmatically**</span></span>  
  
   <span data-ttu-id="80515-146">プログラムを使って、構成プロパティをメッセージ コンテキストに設定できます。</span><span class="sxs-lookup"><span data-stu-id="80515-146">It is possible to set configuration properties programmatically on the message context.</span></span> <span data-ttu-id="80515-147">送信ポートが静的または動的かどうかは、オーケストレーションまたはカスタム パイプライン コンポーネントでこれらのプロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="80515-147">You can set these properties in an orchestration or a custom pipeline component whether the send port is static or dynamic.</span></span>  
  
  > [!NOTE]  
  >  <span data-ttu-id="80515-148">構成する、 **MethodName**プロパティ、静的 soap 送信ポートをプログラムで、設定する必要がある**メソッド名**に **[後で指定]** で、 **Webサービス**のタブ、 **SOAP トランスポートのプロパティ** ダイアログ ボックスで、BizTalk Server 管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="80515-148">To configure the **MethodName** property for the static SOAP send port programmatically, you need to set **Method name** to **[Specify Later]** in the **Web Service** tab of the **SOAP Transport Properties** dialog box in the BizTalk Server Administration console.</span></span>  
  
   <span data-ttu-id="80515-149">詳細については、 **MethodName**プロパティを参照してください[消費する Web サービスの URI を動的に設定する方法](http://go.microsoft.com/fwlink/?LinkID=155768)(http://go.microsoft.com/fwlink/?LinkID=155768)します。</span><span class="sxs-lookup"><span data-stu-id="80515-149">For more information about the **MethodName** property, see [How to Dynamically Set the URI of a Consumed Web Service](http://go.microsoft.com/fwlink/?LinkID=155768) (http://go.microsoft.com/fwlink/?LinkID=155768).</span></span>  
  
- <span data-ttu-id="80515-150">**プロパティの規則**</span><span class="sxs-lookup"><span data-stu-id="80515-150">**Property Rules**</span></span>  
  
   <span data-ttu-id="80515-151">構成プロパティがオーケストレーション、または受信パイプラインのカスタム パイプライン コンポーネントで設定されている場合は、次のルールが適用されます。</span><span class="sxs-lookup"><span data-stu-id="80515-151">If the configuration property is set in an orchestration or in a custom pipeline component in a receive pipeline, then the following rules are applied:</span></span>  
  
  - <span data-ttu-id="80515-152">メッセージを送信する場合は、静的な送信ポート、プロパティの値は、その送信ポート用に構成された値で上書きされます。</span><span class="sxs-lookup"><span data-stu-id="80515-152">If a message is sent to a static send port, the property value will be overwritten with the value configured for that send port.</span></span>  
  
  - <span data-ttu-id="80515-153">動的送信ポートにメッセージを送信する場合、プロパティの値は上書きされません。</span><span class="sxs-lookup"><span data-stu-id="80515-153">If a message is sent to a dynamic send port, the property value will not be overwritten.</span></span>  
  
    <span data-ttu-id="80515-154">構成プロパティが送信パイプラインのカスタム パイプライン コンポーネントで設定されている場合は、次のルールが適用されます。</span><span class="sxs-lookup"><span data-stu-id="80515-154">If a configuration property is set in a custom pipeline component in a send pipeline, then the following rule is applied:</span></span>  
  
  - <span data-ttu-id="80515-155">メッセージを送信する送信ポートが静的か動的かにかかわらず、プロパティ値は上書きされません。</span><span class="sxs-lookup"><span data-stu-id="80515-155">The value will not be overwritten regardless of whether the message is sent to a static or dynamic send port.</span></span> <span data-ttu-id="80515-156">つまり、送信パイプライン コンポーネントは、設定されているかどうかにかかわらず、構成プロパティを上書きします。</span><span class="sxs-lookup"><span data-stu-id="80515-156">In other words, send pipeline components overwrite the configuration property no matter where it was set.</span></span>  
  
  - <span data-ttu-id="80515-157">カスタム パイプライン コンポーネントの詳細については、次を参照してください。[カスタム パイプライン コンポーネントの開発](http://go.microsoft.com/fwlink/?LinkId=155769)(http://go.microsoft.com/fwlink/?LinkId=155769)します。</span><span class="sxs-lookup"><span data-stu-id="80515-157">For more information about custom pipeline components, see [Developing Custom Pipeline Components](http://go.microsoft.com/fwlink/?LinkId=155769) (http://go.microsoft.com/fwlink/?LinkId=155769).</span></span>  
  
  - <span data-ttu-id="80515-158">SOAP 送信アダプタの構成プロパティの詳細については、次を参照してください。[消費する Web サービスの URI を動的に設定する方法](http://go.microsoft.com/fwlink/?LinkID=155768)(http://go.microsoft.com/fwlink/?LinkID=155768)します。</span><span class="sxs-lookup"><span data-stu-id="80515-158">For more information about the configuration properties of the SOAP send adapter, see [How to Dynamically Set the URI of a Consumed Web Service](http://go.microsoft.com/fwlink/?LinkID=155768) (http://go.microsoft.com/fwlink/?LinkID=155768).</span></span>  
  
- <span data-ttu-id="80515-159">**使用する Web サービスを複数ルートのスキーマと、コンパイル エラーを含む Web 参照を追加します。**</span><span class="sxs-lookup"><span data-stu-id="80515-159">**Adding a Web Reference to a Consumed Web Service That Contains a Multi-Rooted Schema Will Cause a Compilation Error**</span></span>  
  
   <span data-ttu-id="80515-160">公開済みの BizTalk オーケストレーションから派生した Web サービス プロジェクトに Web 参照を追加して、オーケストレーションに複数のルートを持つスキーマが含まれています、し、エラーが発生、プロジェクトのコンパイル時にします。</span><span class="sxs-lookup"><span data-stu-id="80515-160">If you add a Web reference to your project for a Web service that was derived from a published BizTalk orchestration and the orchestration contains a schema with multiple roots, then an error will occur when the project is compiled.</span></span> <span data-ttu-id="80515-161">公開済みの BizTalk オーケストレーションから派生した Web 参照をプロジェクトに追加する場合は、オーケストレーションに複数ルートのスキーマが含まれていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="80515-161">If you add a Web reference to your project that was derived from a published BizTalk orchestration, ensure that the orchestration does not contain any multi-rooted schemas.</span></span>  
  
- <span data-ttu-id="80515-162">**Web メソッドのパラメータとして TypedDataSets の使用**</span><span class="sxs-lookup"><span data-stu-id="80515-162">**Using TypedDataSets as Parameters to Web Methods**</span></span>  
  
   <span data-ttu-id="80515-163">Web メソッドのパラメータとして TypedDataSets を使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="80515-163">The following is what you need to do to support using TypedDataSets as parameters to Web methods:</span></span>  
  
  1.  <span data-ttu-id="80515-164">Web 参照を C# プロジェクトに追加し、プロキシを生成します。</span><span class="sxs-lookup"><span data-stu-id="80515-164">Add the Web reference to a C# project and then generate the proxy.</span></span>  
  
  2.  <span data-ttu-id="80515-165">SOAP 送信ポートを作成し、送信ポートにプロキシを指定して、メソッドを選択します。</span><span class="sxs-lookup"><span data-stu-id="80515-165">Create a SOAP send port and specify the proxy on the send port and choose the method.</span></span>  
  
  3.  <span data-ttu-id="80515-166">オーケストレーションで、遅延バインディング ポートとメッセージの種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="80515-166">In the orchestration, define a late bound port and define the message types.</span></span> <span data-ttu-id="80515-167">ほとんどの場合は、プロパティの昇格や識別フィールドへのアクセスは必要ありません、として、型を定義できます**XMLDocument**します。</span><span class="sxs-lookup"><span data-stu-id="80515-167">For most cases where no property promotion or distinguished field access is needed, the type can be defined as **XMLDocument**.</span></span> <span data-ttu-id="80515-168">この種類に対応したパススルー パイプラインを選択してください。</span><span class="sxs-lookup"><span data-stu-id="80515-168">Select PassThrough pipelines with this type.</span></span>  
  
  4.  <span data-ttu-id="80515-169">BizTalk Server 管理コンソールで、 **Web サービス** タブで、 **SOAP トランスポートのプロパティ**SOAP のダイアログ ボックスで送信ポート、その作成したプロキシを使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="80515-169">In the BizTalk Server Administration console, in the **Web Service** tab in the **SOAP Transport Properties** dialog box of the SOAP send port, specify that you want to use that proxy that you created.</span></span> <span data-ttu-id="80515-170">アセンブリ、型、メソッドも指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80515-170">You will also need to specify assembly, type, and method.</span></span>  
  
- <span data-ttu-id="80515-171">**ジェネリック パラメーターと、コンパイル エラーを想定した Web メソッドを含む使用する Web サービスに Web 参照を追加します。**</span><span class="sxs-lookup"><span data-stu-id="80515-171">**Adding a Web Reference to a Consumed Web Service that Contains a Web Method Expecting Generic-Based Parameters Will Cause a Compilation Error**</span></span>  
  
   <span data-ttu-id="80515-172">Null 許容パラメーターなどのジェネリック パラメーターを想定した Web メソッドを含む Web サービス プロジェクトに Web 参照を追加すると、プロジェクトのコンパイル時にエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="80515-172">If you add a Web reference to your project for a Web service that contains a Web method expecting generic-based parameters such as nullable parameters, an error will occur when the project is compiled.</span></span> <span data-ttu-id="80515-173">これはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="80515-173">This is not supported.</span></span> <span data-ttu-id="80515-174">ジェネリック クラスは XLANG/s から明示的な特殊化によって呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="80515-174">You must use explicit specialization to call the generic class from XLANG/s.</span></span>  
  
- <span data-ttu-id="80515-175">**Web 参照の追加を使用して BizTalk スキーマの生成**</span><span class="sxs-lookup"><span data-stu-id="80515-175">**BizTalk Schema Generation Using the Add Web Reference**</span></span>  
  
   <span data-ttu-id="80515-176">使用すると、 **Web 参照の追加**BizTalk Server を BizTalk プロジェクトに Web 参照を追加するにはスキーマに対して各 Web メソッドを呼び出すために必要なスキーマ型に変換します。</span><span class="sxs-lookup"><span data-stu-id="80515-176">When you use the **Add Web Reference**to add Web references to BizTalk projects, BizTalk Server converts the schema types that are required to call each Web method to schemas.</span></span> <span data-ttu-id="80515-177">変換後のスキーマは Reference.xsd に追加されます。</span><span class="sxs-lookup"><span data-stu-id="80515-177">BizTalk Server adds these schemas to Reference.xsd.</span></span> <span data-ttu-id="80515-178">いることを確認する、 **Web 参照の追加**BizTalk スキーマを生成します。 正しく、Web サービスは、次のガイドラインに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="80515-178">To ensure that the **Add Web Reference** generates the BizTalk schemas correctly, the Web services must conform to the following guidelines:</span></span>  
  
  -   <span data-ttu-id="80515-179">Web メソッド**SoapDocumentMethodAttribute**の代わりに**SoapRpcMethodAttribute**します。</span><span class="sxs-lookup"><span data-stu-id="80515-179">Web methods should have **SoapDocumentMethodAttribute** instead of **SoapRpcMethodAttribute**.</span></span>  
  
  -   <span data-ttu-id="80515-180">Web サービスおよびメソッドを使用する必要があります、**リテラル**の代わりにバインド**Encoded**など **[SoapDocumentMethod(Use=SoapBindingUse.Literal)]** します。</span><span class="sxs-lookup"><span data-stu-id="80515-180">Web services and methods must use the **Literal** binding instead of **Encoded** such as **[SoapDocumentMethod(Use=SoapBindingUse.Literal)]**.</span></span>  
  
  -   <span data-ttu-id="80515-181">Web メソッドのパラメーターと戻り値の型**XmlRootAttribute**有効な**Namespace**プロパティ ネイティブ XSD 型、および XmlNode 型でない限り、します。</span><span class="sxs-lookup"><span data-stu-id="80515-181">Web method parameters and return types must have **XmlRootAttribute** with a valid **Namespace** property unless they are native XSD types and the XmlNode type.</span></span>  
  
  -   <span data-ttu-id="80515-182">Web メソッドが使用する必要があります、 **RequestNamespace**と**ResponseNamespace**プロパティ**SoapDocumentMethodAttribute**します。</span><span class="sxs-lookup"><span data-stu-id="80515-182">Web methods must not use the **RequestNamespace** and **ResponseNamespace** properties in **SoapDocumentMethodAttribute**.</span></span>  
  
  -   <span data-ttu-id="80515-183">Web サービスは、Web Services Interoperability (WSI) Basic Profile バージョン 1.1 に準拠する。</span><span class="sxs-lookup"><span data-stu-id="80515-183">Web services must be compliant with the Web services interoperability (WSI) Basic Profile version 1.1.</span></span>  
  
- <span data-ttu-id="80515-184">**Web 参照の追加は、Web Services Description Language (WSDL) インポート要素をサポートしていません**</span><span class="sxs-lookup"><span data-stu-id="80515-184">**The Add Web Reference Does Not Support the Web Services Description Language (WSDL) Import Element**</span></span>  
  
   <span data-ttu-id="80515-185">インポート要素を使用して WSDL ファイルの Web 参照を追加すると、[Web 参照の追加] は失敗します。</span><span class="sxs-lookup"><span data-stu-id="80515-185">The Add Web Reference fails when you add Web references for the WSDL file with the import element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80515-186">参照</span><span class="sxs-lookup"><span data-stu-id="80515-186">See Also</span></span>  
 [<span data-ttu-id="80515-187">BizTalk Server 層の計画</span><span class="sxs-lookup"><span data-stu-id="80515-187">Planning the BizTalk Server Tier</span></span>](../technical-guides/planning-the-biztalk-server-tier.md)
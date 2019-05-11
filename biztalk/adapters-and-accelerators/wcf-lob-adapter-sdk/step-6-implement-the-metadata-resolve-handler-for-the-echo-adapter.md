---
title: 手順 6:エコー アダプターのメタデータ解決ハンドラーの実装 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0105d1b0-efbd-457b-af0d-08e29408a318
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98171f958a1e16b5078fb570b107ffcf93cd5954
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363131"
---
# <a name="step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter"></a><span data-ttu-id="61120-102">手順 6:エコー アダプターのメタデータ解決ハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="61120-102">Step 6: Implement the Metadata Resolve Handler for the Echo Adapter</span></span>
<span data-ttu-id="61120-103">![手順 9 の 6](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-6of9.gif "Step_6of9")</span><span class="sxs-lookup"><span data-stu-id="61120-103">![Step 6 of 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-6of9.gif "Step_6of9")</span></span>  
  
 <span data-ttu-id="61120-104">**所要時間:** 45 分</span><span class="sxs-lookup"><span data-stu-id="61120-104">**Time to complete:** 45 minutes</span></span>  
  
 <span data-ttu-id="61120-105">実装するこの手順で、`Microsoft.ServiceModel.Channels.Common.IMetadataResolverHandler`インターフェイス操作を解決するには、エコー アダプターのメタデータを入力します。</span><span class="sxs-lookup"><span data-stu-id="61120-105">In this step, you implement the `Microsoft.ServiceModel.Channels.Common.IMetadataResolverHandler` interface to resolve operation and type metadata for the echo adapter.</span></span> <span data-ttu-id="61120-106">アダプターの機能に関係なく、このインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61120-106">Regardless of your adapter's capability, you must implement this interface.</span></span> <span data-ttu-id="61120-107">[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] EchoAdapterMetadataResolverHandler を要求する派生クラスが自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="61120-107">The [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] automatically generates the derived class called EchoAdapterMetadataResolverHandler for you.</span></span>  
  
 <span data-ttu-id="61120-108">次のセクションでは、このインターフェイスを実装する方法について理解を深めるために EchoAdapterMetadataResolverHandler クラスを更新します。</span><span class="sxs-lookup"><span data-stu-id="61120-108">In the following section, you update the EchoAdapterMetadataResolverHandler class to get a better understanding on how to implement this interface.</span></span> <span data-ttu-id="61120-109">この手順を完了すると、エコー アダプターのハンドラーを解決する作業のメタデータがあります。</span><span class="sxs-lookup"><span data-stu-id="61120-109">When you complete this step, you have a working metadata resolve handler for the echo adapter.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="61120-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="61120-110">Prerequisites</span></span>  
 <span data-ttu-id="61120-111">この手順を開始する前にする必要がありますが正常に完了して[手順 5。エコー アダプターのメタデータ検索ハンドラーの実装](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="61120-111">Before you begin this step, you must have successfully completed [Step 5: Implement the Metadata Search Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md).</span></span> <span data-ttu-id="61120-112">次の操作と種類のクラスを理解することも必要があります。</span><span class="sxs-lookup"><span data-stu-id="61120-112">You must also understand the following operation and type classes:</span></span>  
  
-   `Microsoft.ServiceModel.Channels.Common.ParameterizedOperationMetadata`  
  
-   `Microsoft.ServiceModel.Channels.Common.OperationMetadata`  
  
-   `Microsoft.ServiceModel.Channels.Common.OperationParameter`  
  
-   `Microsoft.ServiceModel.Channels.Common.OperationResult`  
  
-   `Microsoft.ServiceModel.Channels.Common.TypeMetadata`  
  
-   `Microsoft.ServiceModel.Channels.Common.StructuredTypeMetadata`  
  
-   `Microsoft.ServiceModel.Channels.Common.TypeMember`  
  
-   `Microsoft.ServiceModel.Channels.Common.SimpleQualifiedType`  
  
-   `Microsoft.ServiceModel.Channels.Common.ComplexQualifiedType`  
  
## <a name="the-imetadataresolverhandler-interface"></a><span data-ttu-id="61120-113">IMetadataResolverHandler インターフェイス</span><span class="sxs-lookup"><span data-stu-id="61120-113">The IMetadataResolverHandler Interface</span></span>  
  
```  
public interface IMetadataResolverHandler : IConnectionHandler, IDisposable  
  {  
      bool IsOperationMetadataValid(string operationId, DateTime lastUpdatedTimestamp, TimeSpan timeout);        
      bool IsTypeMetadataValid(string typeId, DateTime lastUpdatedTimestamp, TimeSpan timeout);  
      OperationMetadata ResolveOperationMetadata(string operationId, TimeSpan timeout, out TypeMetadataCollection extraTypeMetadataResolved);  
      TypeMetadata ResolveTypeMetadata(string typeId, TimeSpan timeout, out TypeMetadataCollection extraTypeMetadataResolved);  
  }  
```  
  
 <span data-ttu-id="61120-114">次の表では、各メソッドの動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="61120-114">The following table describes what each method does:</span></span>  
  
|<span data-ttu-id="61120-115">**メソッド名**</span><span class="sxs-lookup"><span data-stu-id="61120-115">**Method Name**</span></span>|<span data-ttu-id="61120-116">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="61120-116">**Description**</span></span>|  
|---------------------|---------------------|  
|<span data-ttu-id="61120-117">IsOperationMetadataValid</span><span class="sxs-lookup"><span data-stu-id="61120-117">IsOperationMetadataValid</span></span>|<span data-ttu-id="61120-118">型のメタデータが指定された日時以降に変更されていない場合、true を返します</span><span class="sxs-lookup"><span data-stu-id="61120-118">Returns a true if the type metadata has not changed since the date and time specified</span></span>|  
|<span data-ttu-id="61120-119">IsTypeMetadataValid</span><span class="sxs-lookup"><span data-stu-id="61120-119">IsTypeMetadataValid</span></span>|<span data-ttu-id="61120-120">指定した型のメタデータが有効かどうかを示すブール値を返します。</span><span class="sxs-lookup"><span data-stu-id="61120-120">Returns a Boolean value that indicates whether the specified type metadata is valid.</span></span>|  
|<span data-ttu-id="61120-121">ResolveOperationMetadata</span><span class="sxs-lookup"><span data-stu-id="61120-121">ResolveOperationMetadata</span></span>|<span data-ttu-id="61120-122">対応する、操作 ID を解決します。 `Microsoft.ServiceModel.Channels.Common.OperationMetadata`</span><span class="sxs-lookup"><span data-stu-id="61120-122">Resolves an operation ID to corresponding `Microsoft.ServiceModel.Channels.Common.OperationMetadata`</span></span>|  
|<span data-ttu-id="61120-123">ResolveTypeMetadata</span><span class="sxs-lookup"><span data-stu-id="61120-123">ResolveTypeMetadata</span></span>|<span data-ttu-id="61120-124">指定されたメタデータ typeId に、対応する解決`Microsoft.ServiceModel.Channels.Common.TypeMetadata`します。</span><span class="sxs-lookup"><span data-stu-id="61120-124">Resolves a supplied metadata typeId to a corresponding `Microsoft.ServiceModel.Channels.Common.TypeMetadata`.</span></span>|  
  
### <a name="to-implement-the-isoperationmetadatavalid-method"></a><span data-ttu-id="61120-125">IsOperationMetadataValid メソッドを実装するには</span><span class="sxs-lookup"><span data-stu-id="61120-125">To implement the IsOperationMetadataValid method</span></span>  
  
1.  <span data-ttu-id="61120-126">ソリューション エクスプ ローラーで、 **EchoAdapterMetadataResolverHandler.cs**ファイル。</span><span class="sxs-lookup"><span data-stu-id="61120-126">In Solution Explorer, double-click the **EchoAdapterMetadataResolverHandler.cs** file.</span></span>  
  
2.  <span data-ttu-id="61120-127">Visual Studio エディターで、任意の場所を右クリック コンテキスト メニューで、エディター内をポイント**アウトライン**、 をクリックし、**アウトラインの中止**します。</span><span class="sxs-lookup"><span data-stu-id="61120-127">In the Visual Studio editor, right-click anywhere within the editor, in the context menu, point to **Outlining**, and then click **Stop Outlining**.</span></span>  
  
3.  <span data-ttu-id="61120-128">Visual Studio エディターで検索、 **IsOperationMetadataValid**メソッドは、このメソッド内では、既存のすべてのメタデータを指定した操作が有効であることを示す次の 1 つのステートメントでを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="61120-128">In the Visual Studio editor, find the **IsOperationMetadataValid** method, inside this method, replace the existing with the following single statement to indicate that every specified operation metadata is valid.</span></span>  
  
    ```csharp  
    return true;  
    ```  
  
### <a name="to-implement-the-istypemetadatavalid-method"></a><span data-ttu-id="61120-129">IsTypeMetadataValid メソッドを実装するには</span><span class="sxs-lookup"><span data-stu-id="61120-129">To implement the IsTypeMetadataValid method</span></span>  
  
-   <span data-ttu-id="61120-130">Visual Studio エディターで検索、 **IsTypeMetadataValid**メソッドは、このメソッド内では、既存のすべての指定した型のメタデータが有効であることを示す次の 1 つのステートメントでを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="61120-130">In the Visual Studio editor, find the **IsTypeMetadataValid** method, inside this method, replace the existing with the following single statement to indicate that every specified type metadata is valid.</span></span>  
  
    ```csharp  
    return true;  
    ```  
  
### <a name="to-implement-the-resolveoperationmetadata-method"></a><span data-ttu-id="61120-131">ResolveOperationMetadata メソッドを実装するには</span><span class="sxs-lookup"><span data-stu-id="61120-131">To implement the ResolveOperationMetadata method</span></span>  
  
1.  <span data-ttu-id="61120-132">Visual Studio エディターで検索、 **ResolveOperationMetadata** OnReceiveEcho 操作、void OnReceiveEcho (Uri のパス、長い fileLength) を解決するには、次のように既存のメソッドは、このメソッド内での置換します。</span><span class="sxs-lookup"><span data-stu-id="61120-132">In the Visual Studio editor, find the **ResolveOperationMetadata** method, inside this method, replace the existing with the following to resolve the OnReceiveEcho operation, void OnReceiveEcho(Uri path, long fileLength).</span></span>  
  
    ```csharp  
    extraTypeMetadataResolved = null;  
    switch( operationId )  
    {  
        case "Echo/OnReceiveEcho":  
            ParameterizedOperationMetadata om = new ParameterizedOperationMetadata(operationId, "OnReceiveEcho");  
            om.OriginalName = "lobNotification";  
            om.Description = "This operation echoes the location and length of a file dropped in the specified file system.";  
            om.OperationGroup = "EchoInboundContract";  
            om.OperationNamespace = EchoAdapter.SERVICENAMESPACE;  
            // syntax: void OnReceiveEcho(Uri path, long fileLength)  
            OperationParameter parmPath = new OperationParameter("path", OperationParameterDirection.In, QualifiedType.UriType, false);  
            parmPath.Description = "Absolute path of the file";  
            OperationParameter parmLength = new OperationParameter("length", OperationParameterDirection.In, QualifiedType.LongType, false);  
            parmLength.Description = "Length of the file received in this location.";  
            om.Parameters.Add(parmPath);  
            om.Parameters.Add(parmLength);  
            om.OperationResult = OperationResult.Empty;  
            return om;  
    ```  
  
2.  <span data-ttu-id="61120-133">エコー/EchoStrings 操作、string[] EchoStrings(string data) を解決するのには、次の追加を続行します。</span><span class="sxs-lookup"><span data-stu-id="61120-133">Continue adding the following to resolve the Echo/EchoStrings operation, string[] EchoStrings(string data).</span></span>  
  
    ```csharp  
    case "Echo/EchoStrings":  
        om = new ParameterizedOperationMetadata(operationId, "EchoStrings");  
        om.OriginalName = "lobEchoStrings";  
        om.Description = "This operation echoes the incoming string COUNT number of times in a string array.";  
        om.OperationGroup = "EchoOutboundContract";  
        om.OperationNamespace = EchoAdapter.SERVICENAMESPACE;  
        // syntax: string[] EchoStrings(string data)  
        OperationParameter parmData = new OperationParameter("data", OperationParameterDirection.In, QualifiedType.StringType, false);  
        parmData.Description = "Input string";  
        om.Parameters.Add(parmData);  
        om.OperationResult = new OperationResult(QualifiedType.StringType, true);  
        return om;  
    ```  
  
3.  <span data-ttu-id="61120-134">エコー/EchoStrings 操作、string[] EchoStrings(string data) を解決するのには、次のロジックの追加を続行します。</span><span class="sxs-lookup"><span data-stu-id="61120-134">Continue adding the following logic to resolve the Echo/EchoStrings operation, string[] EchoStrings(string data).</span></span>  
  
    ```csharp  
    case "Echo/EchoGreetings":  
        om = new ParameterizedOperationMetadata(operationId, "EchoGreetings");  
        om.OriginalName = "lobEchoGreetings";  
        om.Description = "This operation echoes the incoming Greeting object COUNT number of times in an array of type Greeting.";  
        om.OperationGroup = "EchoOutboundContract";  
        om.OperationNamespace = EchoAdapter.SERVICENAMESPACE;  
        // syntax: Greeting[] EchoGreetings(Greeting greeting)  
        ComplexQualifiedType cqtGreeting = new ComplexQualifiedType("Types/GreetingType");  
        OperationParameter parmGreeting = new OperationParameter("greeting", OperationParameterDirection.In, cqtGreeting, false);  
        parmGreeting.Description = "Input greeting";  
        om.Parameters.Add(parmGreeting);  
        om.OperationResult = new OperationResult(cqtGreeting, true);  
        return om;  
    ```  
  
4.  <span data-ttu-id="61120-135">CustomGreeting EchoCustomGreetingFromFile(Uri greetingInstancePath) 操作を解決するのには、次のロジックの追加を続行します。</span><span class="sxs-lookup"><span data-stu-id="61120-135">Continue adding the following logic to resolve the CustomGreeting EchoCustomGreetingFromFile(Uri greetingInstancePath) operation.</span></span>  
  
    ```csharp  
    case "Echo/EchoCustomGreetingFromFile":  
        om = new ParameterizedOperationMetadata(operationId, "EchoCustomGreetingFromFile");  
        om.OriginalName = "lobEchoGreetingUsePredefinedMetadata";  
        om.Description = "This operation echoes the incoming Greeting object COUNT number of times in an array of type Greeting.  The Greeting type metadata is created using predefined XSD file.";  
        om.OperationGroup = "EchoOutboundContract";  
        om.OperationNamespace = EchoAdapter.SERVICENAMESPACE;  
        OperationParameter parmGreetingInstancePath = new OperationParameter("greetingInstancePath", OperationParameterDirection.In, QualifiedType.UriType, false);  
        om.Parameters.Add(parmGreetingInstancePath);  
        ComplexQualifiedType cqtGreetingXsd = new ComplexQualifiedType("Types/CustomGreetingFromXsdType");  
        om.OperationResult = new OperationResult(cqtGreetingXsd, false);  
  
        // resolve extra typemetadata here  
        extraTypeMetadataResolved = new TypeMetadataCollection();  
  
        // use a predefined schema to generate metadata for this type  
        CustomGreetingTypeMetadata tmGreetingXsd = new CustomGreetingTypeMetadata("Types/CustomGreetingFromXsdType", "CustomGreeting");  
        extraTypeMetadataResolved.Add(tmGreetingXsd);                   
        return om;  
  
    ```  
  
5.  <span data-ttu-id="61120-136">既定のケースを処理するために、次の追加を続行します。</span><span class="sxs-lookup"><span data-stu-id="61120-136">Continue adding the following to handle default case.</span></span>  
  
    ```csharp  
        default:  
            throw new AdapterException("Cannot resolve metadata for operation identifier " + operationId);  
    }  
    ```  
  
### <a name="to-implement-the-resolvetypemetadata-method"></a><span data-ttu-id="61120-137">ResolveTypeMetadata メソッドを実装するには</span><span class="sxs-lookup"><span data-stu-id="61120-137">To implement the ResolveTypeMetadata method</span></span>  
  
-   <span data-ttu-id="61120-138">Visual Studio エディターで検索、 **ResolveTypeMetadata**メソッドは、このメソッド内で置換を返すには、次のように、既存の`Microsoft.ServiceModel.Channels.Common.TypeMetadata`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="61120-138">In the Visual Studio editor, find the **ResolveTypeMetadata** method, inside this method, replace the existing with the following to return a `Microsoft.ServiceModel.Channels.Common.TypeMetadata` object.</span></span>  
  
    ```csharp  
    extraTypeMetadataResolved = null;  
    string typeNamespaceForGreeting = EchoAdapter.SERVICENAMESPACE + "/Types";  
    switch (typeId)  
    {  
        case "Types/GreetingType":  
            StructuredTypeMetadata tmGreeting = new StructuredTypeMetadata(typeId, "Greeting");  
            tmGreeting.TypeNamespace = typeNamespaceForGreeting;  
            tmGreeting.Members.Add(new TypeMember("id", QualifiedType.GuidType, false));  
            tmGreeting.Members.Add(new TypeMember("sentDateTime", QualifiedType.DateTimeType, false));  
            ComplexQualifiedType cqtName = new ComplexQualifiedType("Types/NameType");  
            tmGreeting.Members.Add(new TypeMember("name", cqtName, false));  
            tmGreeting.Members.Add(new TypeMember("greetingText", QualifiedType.StringType, false));  
            return tmGreeting;  
  
        case "Types/NameType":  
            StructuredTypeMetadata tmName = new StructuredTypeMetadata(typeId, "Name");  
            tmName.TypeNamespace = typeNamespaceForGreeting;  
            ComplexQualifiedType cqtSalutation = new ComplexQualifiedType("Types/SalutationType");  
            tmName.Members.Add(new TypeMember("salutation", cqtSalutation, false));  
            tmName.Members.Add(new TypeMember("firstName", QualifiedType.StringType, false));  
            tmName.Members.Add(new TypeMember("middleName", QualifiedType.StringType, false));  
            tmName.Members.Add(new TypeMember("lastName", QualifiedType.StringType, false));  
            return tmName;  
  
        case "Types/SalutationType":  
            EnumTypeMetadata tmSalutation = new EnumTypeMetadata(typeId, "Salutation", new string[] { "Mr.", "Mrs.", "Dr.", "Ms.", "Miss" });  
            tmSalutation.TypeNamespace = typeNamespaceForGreeting;  
            return tmSalutation;  
  
        default:  
            throw new AdapterException("Cannot resolve metadata for type identifier " + typeId);  
    }  
  
    ```  
  
### <a name="to-define-the-custom-greeting-type-metadata-class"></a><span data-ttu-id="61120-139">カスタムの案内応答型のメタデータ クラスを定義するには</span><span class="sxs-lookup"><span data-stu-id="61120-139">To define the custom greeting type metadata class</span></span>  
  
1.  <span data-ttu-id="61120-140">ソリューション エクスプ ローラーで右クリックし、**エコー アダプター**プロジェクトをポイントして、**追加**、 をクリックし、**新しい項目の**。</span><span class="sxs-lookup"><span data-stu-id="61120-140">In Solution Explorer, right-click the **Echo Adapter** project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="61120-141">**新しい項目の追加**ダイアログ ボックスで、**テンプレート**、 をクリックして**クラス**します。</span><span class="sxs-lookup"><span data-stu-id="61120-141">In the **Add New Item** dialog box, under **Templates**, click **Class**.</span></span>  
  
3.  <span data-ttu-id="61120-142">**名前**テキスト ボックスに「 **CustomGreetingTypeMetadata**します。</span><span class="sxs-lookup"><span data-stu-id="61120-142">In the **Name** text box, type **CustomGreetingTypeMetadata**.</span></span>  
  
4.  <span data-ttu-id="61120-143">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="61120-143">Click **Add**.</span></span>  
  
5.  <span data-ttu-id="61120-144">Visual Studio エディターでは、次のように、既存のコードを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="61120-144">In the Visual Studio editor, replace the existing code with the following:</span></span>  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
    using Microsoft.ServiceModel.Channels.Common;  
    using System.Xml;  
    using System.Xml.Schema;  
    using System.IO;  
  
    namespace Microsoft.Adapters.Samples.EchoV2  
    {  
        public class CustomGreetingTypeMetadata : TypeMetadata  
        {  
            private const string CONST_METADATA_FILE_NAME = "Microsoft.Adapters.Samples.EchoV2.CustomGreeting.xsd";  
  
            public CustomGreetingTypeMetadata(string typeId, string typeName)  
                : base(typeId, typeName)  
            {  
                this.TypeNamespace = EchoAdapter.SERVICENAMESPACE + "/PreDefinedTypes";  
                this.Description = " ";  
                this.CanUseCommonCache = true;  
                // if the nillable is not set to true, the generated proxy wraps the operation  
                // with request and response objects  
                this.IsNillable = true;  
            }  
  
            /// <summary>  
            /// Override the base ExportXmlSchema to provide own   
            /// custom XML Schema  
            /// </summary>  
            /// <param name="schemaExportContext"></param>  
            /// <param name="metadataLookup"></param>  
            /// <param name="timeout"></param>  
            public override void ExportXmlSchema(XmlSchemaExportContext schemaExportContext, MetadataLookup metadataLookup, TimeSpan timeout)  
            {  
                if (schemaExportContext == null)  
                {  
                    throw new AdapterException("Schema export context is null.");  
                }  
                // Read in XML Schema file or create XmlSchema object yourself  
                Stream predefinedXsdFile = System.Reflection.Assembly.GetExecutingAssembly().GetManifestResourceStream(CONST_METADATA_FILE_NAME);  
                XmlReader reader = XmlReader.Create(predefinedXsdFile);  
                XmlSchema schema = XmlSchema.Read(reader, null);  
                if (!IsComplexTypeAlreadyDefined(schemaExportContext.SchemaSet, schema))  
                {  
                    schemaExportContext.SchemaSet.Add(schema);  
                    if (!schemaExportContext.NamespacePrefixSet.ContainsKey(this.TypeNamespace))  
                    {  
                        schemaExportContext.NamespacePrefixSet.Add(this.TypeNamespace, getUniqueNamespacePrefix(schemaExportContext, 0));  
                    }  
                }  
                reader.Close();  
            }  
  
            /// <summary>  
            /// A default value cannot be set for this type metadata.  
            /// </summary>  
            public override bool CanSetDefaultValue  
            {  
                get { return false; }  
            }  
  
            /// <summary>  
            /// Helper function to see if the schema is already defined in the   
            /// XmlSchemaSet.  
            /// </summary>  
            /// <param name="oldschemaset"></param>  
            /// <param name="newschema"></param>  
            /// <returns></returns>  
            public static bool IsComplexTypeAlreadyDefined(XmlSchemaSet oldschemaset, XmlSchema newschema)  
            {  
                // ensure correct namespace was defined in the passed-in schema  
                foreach (XmlSchema schema in oldschemaset.Schemas(newschema.TargetNamespace))  
                {  
                    foreach (XmlSchemaObject newschemaObject in newschema.Items)  
                    {  
                        if (newschemaObject is XmlSchemaComplexType)  
                        {  
                            //check for the definition of complex type in the schemaset             
                            foreach (XmlSchemaObject schemaObject in schema.Items)  
                            {  
                                XmlSchemaComplexType complexType = schemaObject as XmlSchemaComplexType;  
                                // Definition of this Complex Type already exists  
                                if (complexType != null && String.Compare(complexType.Name, ((XmlSchemaComplexType)newschemaObject).Name, false, System.Globalization.CultureInfo.InvariantCulture) == 0)  
                                    return true;  
                            }  
                        }  
                    }  
                }  
                return false;  
            }  
  
            /// <summary>  
            /// Helper function to generate a unique namespace prefix  
            /// </summary>  
            /// <param name="schemaExportContext"></param>  
            /// <param name="startSuffix"></param>  
            /// <returns></returns>  
            private string getUniqueNamespacePrefix(XmlSchemaExportContext schemaExportContext, int startSuffix)  
            {  
                string defaultPrefix = "ns";  
                string val = defaultPrefix + startSuffix;  
                if (schemaExportContext.NamespacePrefixSet.ContainsValue(val))  
                {  
                    return getUniqueNamespacePrefix(schemaExportContext, ++startSuffix);  
                }  
                else  
                {  
                    return val;  
                }  
            }  
        }  
    }  
    ```  
  
6.  <span data-ttu-id="61120-145">Visual Studio から、**ファイル** メニューのをクリックして**すべて保存**します。</span><span class="sxs-lookup"><span data-stu-id="61120-145">In Visual Studio, from the **File** menu, click **Save All**.</span></span>  
  
### <a name="to-create-the-custom-greeting-xml-schema-definition"></a><span data-ttu-id="61120-146">XML スキーマ定義のカスタムあいさつ文を作成するには</span><span class="sxs-lookup"><span data-stu-id="61120-146">To create the custom greeting XML schema definition</span></span>  
  
1.  <span data-ttu-id="61120-147">ソリューション エクスプ ローラーで右クリックし、**エコー アダプター**プロジェクトをポイントして、**追加**、 をクリックし、**新しい項目の**。</span><span class="sxs-lookup"><span data-stu-id="61120-147">In Solution Explorer, right-click the **Echo Adapter** project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="61120-148">**新しい項目の追加**ダイアログ ボックスで、**テンプレート**、 をクリックして**XML スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="61120-148">In the **Add New Item** dialog box, under **Templates**, click **XML Schema**.</span></span>  
  
3.  <span data-ttu-id="61120-149">**名前**テキスト ボックスに「 **CustomGreeting**します。</span><span class="sxs-lookup"><span data-stu-id="61120-149">In the **Name** text box, type **CustomGreeting**.</span></span>  
  
4.  <span data-ttu-id="61120-150">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="61120-150">Click **Add**.</span></span>  
  
5.  <span data-ttu-id="61120-151">ソリューション エクスプ ローラーで右クリックし、 **CustomGreeting.xsd**ファイル**コードの表示**します。</span><span class="sxs-lookup"><span data-stu-id="61120-151">In Solution Explorer, right-click the **CustomGreeting.xsd** file and choose **View Code**.</span></span>  
  
6.  <span data-ttu-id="61120-152">Visual Studio エディターで、既存のコードを CustomGreeting スキーマの定義を開始する次のコードに置き換えることにより開始します。</span><span class="sxs-lookup"><span data-stu-id="61120-152">In the Visual Studio editor, begin by replacing the existing code with the following code that begins the definition of the CustomGreeting schema:</span></span>  
  
    ```csharp  
    <?xml version="1.0" encoding="utf-8" ?>   
    <xs:schema id="XMLSchema1"   
                      targetNamespace="http://tempuri.org/XMLSchema1.xsd"  
                      elementFormDefault="qualified"  
                      xmlns="http://tempuri.org/XMLSchema1.xsd"  
                      xmlns:mstns="http://tempuri.org/XMLSchema1.xsd"  
                      xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    </xs:schema>  
    ```  
  
     <span data-ttu-id="61120-153">次のコードでは、CustomGreeting スキーマの定義を開始します。</span><span class="sxs-lookup"><span data-stu-id="61120-153">with the following code that begins the definition of the CustomGreeting schema:</span></span>  
  
    ```csharp  
    <?xml version="1.0" encoding="utf-16"?>  
    <xsd:schema xmlns:b="http://schemas.microsoft.com/BizTalk/2003" xmlns="echov2://microsoft.adapters.samples.echov2/PreDefinedTypes" elementFormDefault="qualified" targetNamespace="echov2://microsoft.adapters.samples.echov2/PreDefinedTypes" xmlns:xsd ="http://www.w3.org/2001/XMLSchema">  
    ```  
  
7.  <span data-ttu-id="61120-154">CustomGreeting 要素を定義するには、次を追加します。</span><span class="sxs-lookup"><span data-stu-id="61120-154">Add the following to define the CustomGreeting element:</span></span>  
  
    ```csharp  
    <xsd:element name="greeting" type="CustomGreeting" />  
    ```  
  
8.  <span data-ttu-id="61120-155">CustomGreeting 複合型の定義を追加します。</span><span class="sxs-lookup"><span data-stu-id="61120-155">Now add the definition of the CustomGreeting complex type:</span></span>  
  
    ```csharp  
    <xsd:complexType name="CustomGreeting">  
      <xsd:sequence>  
        <xsd:element name="address" type="UsAddress" />  
        <xsd:element name="greetingText" type="xsd:string" />  
      </xsd:sequence>  
    </xsd:complexType>  
    ```  
  
9. <span data-ttu-id="61120-156">UsAddress 複合型を追加することで、CustomGreeting スキーマ定義を続行します。</span><span class="sxs-lookup"><span data-stu-id="61120-156">Continue the CustomGreeting schema definition by adding the  UsAddress complex type:</span></span>  
  
    ```csharp  
    <xsd:complexType name="UsAddress">  
      <xsd:sequence>  
        <xsd:element minOccurs="1" maxOccurs="1" name="street1" nillable="true" type="xsd:string" />  
        <xsd:element minOccurs="0" maxOccurs="1" name="street2" type="xsd:string" />  
        <xsd:element minOccurs="1" maxOccurs="1" name="city" type="xsd:string" />  
        <xsd:element minOccurs="1" maxOccurs="1" name="state" type="xsd:string" />  
        <xsd:element name="zip" type="PostalCode" />  
      </xsd:sequence>  
    </xsd:complexType>  
    ```  
  
10. <span data-ttu-id="61120-157">PostalCode 単純型とスキーマの終了タグを追加して CustomGreeting スキーマの定義が完了します。</span><span class="sxs-lookup"><span data-stu-id="61120-157">Complete the definition of the CustomGreeting schema by adding the PostalCode simple type and the closing tag for the schema:</span></span>  
  
    ```csharp  
      <xsd:simpleType name="PostalCode">  
        <xsd:restriction base="xsd:positiveInteger">  
          <xsd:pattern value="\d{5}" />  
        </xsd:restriction>  
      </xsd:simpleType>  
    </xsd:schema>  
    ```  
  
11. <span data-ttu-id="61120-158">埋め込みリソースとして扱われるために、このファイルのビルド アクションを今すぐ更新します。</span><span class="sxs-lookup"><span data-stu-id="61120-158">Now update the build action for this file so it is treated as an embedded resource.</span></span> <span data-ttu-id="61120-159">Visual Studio ソリューション ウィンドウで、ファイルを右クリックし、選択**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="61120-159">To do this, in the Visual Studio solution pane, right-click the file and choose **Properties**.</span></span> <span data-ttu-id="61120-160">ビルド アクションを変更する**None**に**埋め込みリソース**します。</span><span class="sxs-lookup"><span data-stu-id="61120-160">Change Build Action from **None** to **Embedded Resource**.</span></span>  
  
12. <span data-ttu-id="61120-161">Visual Studio から、**ファイル** メニューのをクリックして**すべて保存**します。</span><span class="sxs-lookup"><span data-stu-id="61120-161">In Visual Studio, from the **File** menu, click **Save All**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61120-162">これで作業が保存されました。</span><span class="sxs-lookup"><span data-stu-id="61120-162">You saved your work.</span></span> <span data-ttu-id="61120-163">安全にこの時点で Visual Studio を閉じて、次の手順に進むまたは[手順 7。エコー アダプターの同期送信ハンドラーを実装する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="61120-163">You can safely close Visual Studio at this time or go to the next step, [Step 7: Implement the Synchronous Outbound Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md).</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="61120-164">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="61120-164">What Did I Just Do?</span></span>  
 <span data-ttu-id="61120-165">エコー アダプターの機能を解決するメタデータを実装するだけです。</span><span class="sxs-lookup"><span data-stu-id="61120-165">You just implemented the metadata resolving capability for the echo adapter.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="61120-166">次の手順</span><span class="sxs-lookup"><span data-stu-id="61120-166">Next Steps</span></span>  
 <span data-ttu-id="61120-167">次の手順では、エコー アダプターの同期送信ハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="61120-167">In the next step, you implement the synchronous outbound handler for the Echo Adapter.</span></span> <span data-ttu-id="61120-168">ビルドし、同期受信ハンドラーを実装し、エコー アダプターの展開します。</span><span class="sxs-lookup"><span data-stu-id="61120-168">You then implement the synchronous inbound handler and then build and deploy the Echo Adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61120-169">参照</span><span class="sxs-lookup"><span data-stu-id="61120-169">See Also</span></span>  
 <span data-ttu-id="61120-170">[手順 5:エコー アダプターのメタデータ検索ハンドラーを実装します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="61120-170">[Step 5: Implement the Metadata Search Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md) </span></span>  
 <span data-ttu-id="61120-171">[手順 7:エコー アダプターの同期送信ハンドラーを実装します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="61120-171">[Step 7: Implement the Synchronous Outbound Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md) </span></span>  
 [<span data-ttu-id="61120-172">チュートリアル 1:エコー アダプターを開発する</span><span class="sxs-lookup"><span data-stu-id="61120-172">Tutorial 1: Develop the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)
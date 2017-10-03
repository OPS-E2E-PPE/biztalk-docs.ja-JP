---
title: "手順 6: エコー アダプター メタデータの解決ハンドラーを実装する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0105d1b0-efbd-457b-af0d-08e29408a318
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 022da31cacedaa59c9e5821fb049165f463c7f06
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter"></a>手順 6: エコー アダプター メタデータの解決ハンドラーを実装します。
![手順 9 の 6](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-6of9.gif "Step_6of9")  
  
 **所要時間:** 45 分  
  
 実装するこの手順で、`Microsoft.ServiceModel.Channels.Common.IMetadataResolverHandler`インターフェイスに操作を解決するには、エコー アダプターのメタデータを入力します。 アダプターの機能に関係なく、このインターフェイスを実装する必要があります。 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] EchoAdapterMetadataResolverHandler を要求する派生クラスが自動的に生成されます。  
  
 次のセクションでは、このインターフェイスを実装する方法について理解を深めるために EchoAdapterMetadataResolverHandler クラスを更新します。 この手順を完了したときに、エコー アダプターのハンドラーを解決する作業のメタデータがあります。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を開始する前にする必要がありますが正常に完了しました[手順 5: エコー アダプターのメタデータの検索ハンドラーの実装](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md)です。 次の操作と種類のクラスを理解する必要があります。  
  
-   `Microsoft.ServiceModel.Channels.Common.ParameterizedOperationMetadata`  
  
-   `Microsoft.ServiceModel.Channels.Common.OperationMetadata`  
  
-   `Microsoft.ServiceModel.Channels.Common.OperationParameter`  
  
-   `Microsoft.ServiceModel.Channels.Common.OperationResult`  
  
-   `Microsoft.ServiceModel.Channels.Common.TypeMetadata`  
  
-   `Microsoft.ServiceModel.Channels.Common.StructuredTypeMetadata`  
  
-   `Microsoft.ServiceModel.Channels.Common.TypeMember`  
  
-   `Microsoft.ServiceModel.Channels.Common.SimpleQualifiedType`  
  
-   `Microsoft.ServiceModel.Channels.Common.ComplexQualifiedType`  
  
## <a name="the-imetadataresolverhandler-interface"></a>IMetadataResolverHandler インターフェイス  
  
```  
public interface IMetadataResolverHandler : IConnectionHandler, IDisposable  
  {  
      bool IsOperationMetadataValid(string operationId, DateTime lastUpdatedTimestamp, TimeSpan timeout);        
      bool IsTypeMetadataValid(string typeId, DateTime lastUpdatedTimestamp, TimeSpan timeout);  
      OperationMetadata ResolveOperationMetadata(string operationId, TimeSpan timeout, out TypeMetadataCollection extraTypeMetadataResolved);  
      TypeMetadata ResolveTypeMetadata(string typeId, TimeSpan timeout, out TypeMetadataCollection extraTypeMetadataResolved);  
  }  
```  
  
 次の表では、各メソッドの実行内容について説明します。  
  
|**メソッド名**|**Description**|  
|---------------------|---------------------|  
|IsOperationMetadataValid|型のメタデータが指定した日時以降に変更されていない場合、true を返します|  
|IsTypeMetadataValid|指定した型のメタデータが有効かどうかを示すブール値を返します。|  
|ResolveOperationMetadata|対応する操作 ID を解決します。`Microsoft.ServiceModel.Channels.Common.OperationMetadata`|  
|ResolveTypeMetadata|な typeId で指定されたメタデータを対応する解決`Microsoft.ServiceModel.Channels.Common.TypeMetadata`です。|  
  
### <a name="to-implement-the-isoperationmetadatavalid-method"></a>IsOperationMetadataValid メソッドを実装するには  
  
1.  ソリューション エクスプ ローラーで、 **EchoAdapterMetadataResolverHandler.cs**ファイル。  
  
2.  Visual Studio エディターで、任意の場所を右クリック コンテキスト メニューで、エディター内のをポイント**アウトライン**、クリックして**アウトラインの中止**です。  
  
3.  Visual Studio エディターで、検索、 **IsOperationMetadataValid**このメソッド内のメソッドは、既存のすべてのメタデータを指定した操作が有効であることを示す次の 1 つのステートメントでを置換します。  
  
    ```csharp  
    return true;  
    ```  
  
### <a name="to-implement-the-istypemetadatavalid-method"></a>IsTypeMetadataValid メソッドを実装するには  
  
-   Visual Studio エディターで、検索、 **IsTypeMetadataValid**このメソッド内のメソッドは、既存のすべての指定した型のメタデータが無効であることを示す次の 1 つのステートメントでを置換します。  
  
    ```csharp  
    return true;  
    ```  
  
### <a name="to-implement-the-resolveoperationmetadata-method"></a>ResolveOperationMetadata メソッドを実装するには  
  
1.  Visual Studio エディターで、検索、 **ResolveOperationMetadata** OnReceiveEcho 操作、void OnReceiveEcho (Uri パス、長い fileLength) を解決するのには次のように、既存の代わりにこのメソッド内のメソッドです。  
  
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
  
2.  エコー/EchoStrings 操作、string[] EchoStrings(string data) を解決するのには、次の追加を続行します。  
  
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
  
3.  エコー/EchoStrings 操作、string[] EchoStrings(string data) を解決するのには、次のロジックを追加していきます。  
  
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
  
4.  続けて、CustomGreeting EchoCustomGreetingFromFile(Uri greetingInstancePath) 操作を解決するのには、次のロジックを追加します。  
  
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
  
5.  既定のケースを処理するには、次の追加を続行します。  
  
    ```csharp  
        default:  
            throw new AdapterException("Cannot resolve metadata for operation identifier " + operationId);  
    }  
    ```  
  
### <a name="to-implement-the-resolvetypemetadata-method"></a>ResolveTypeMetadata メソッドを実装するには  
  
-   Visual Studio エディターで、検索、 **ResolveTypeMetadata**を返すには、次のように、既存の代わりにこのメソッド内のメソッド、`Microsoft.ServiceModel.Channels.Common.TypeMetadata`オブジェクト。  
  
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
  
### <a name="to-define-the-custom-greeting-type-metadata-class"></a>カスタムの案内応答型のメタデータ クラスを定義するには  
  
1.  ソリューション エクスプ ローラーで右クリックし、**エコー アダプター**プロジェクトをポイントし、**追加**、順にクリック**新しい項目の**します。  
  
2.  **新しい項目の追加**ダイアログ ボックスで、**テンプレート**をクリックして**クラス**です。  
  
3.  **名前**テキスト ボックスで、「 **CustomGreetingTypeMetadata**です。  
  
4.  **[追加]**をクリックします。  
  
5.  Visual Studio エディターでは、次のように、既存のコードを置き換えます。  
  
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
  
6.  Visual Studio から、**ファイル** メニューのをクリックして**すべて保存**です。  
  
### <a name="to-create-the-custom-greeting-xml-schema-definition"></a>カスタムの案内応答 XML スキーマ定義を作成するには  
  
1.  ソリューション エクスプ ローラーで右クリックし、**エコー アダプター**プロジェクトをポイントし、**追加**、順にクリック**新しい項目の**します。  
  
2.  **新しい項目の追加**ダイアログ ボックスで、**テンプレート**をクリックして**XML スキーマ**です。  
  
3.  **名前**テキスト ボックスで、「 **CustomGreeting**です。  
  
4.  **[追加]**をクリックします。  
  
5.  ソリューション エクスプ ローラーで右クリックし、 **CustomGreeting.xsd**ファイルして選択**コードの表示**です。  
  
6.  Visual Studio エディターで CustomGreeting スキーマの定義を開始する次のコードを既存のコードを置き換えることで開始します。  
  
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
  
     次のコードでは、CustomGreeting スキーマの定義を開始します。  
  
    ```csharp  
    <?xml version="1.0" encoding="utf-16"?>  
    <xsd:schema xmlns:b="http://schemas.microsoft.com/BizTalk/2003" xmlns="echov2://microsoft.adapters.samples.echov2/PreDefinedTypes" elementFormDefault="qualified" targetNamespace="echov2://microsoft.adapters.samples.echov2/PreDefinedTypes" xmlns:xsd ="http://www.w3.org/2001/XMLSchema">  
    ```  
  
7.  CustomGreeting 要素を定義するには、次を追加します。  
  
    ```csharp  
    <xsd:element name="greeting" type="CustomGreeting" />  
    ```  
  
8.  CustomGreeting 複合型の定義を追加します。  
  
    ```csharp  
    <xsd:complexType name="CustomGreeting">  
      <xsd:sequence>  
        <xsd:element name="address" type="UsAddress" />  
        <xsd:element name="greetingText" type="xsd:string" />  
      </xsd:sequence>  
    </xsd:complexType>  
    ```  
  
9. UsAddress 複合型を追加することによって、CustomGreeting スキーマ定義を続行します。  
  
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
  
10. PostalCode 単純型とスキーマの終了タグの追加、CustomGreeting スキーマの定義を完了します。  
  
    ```csharp  
      <xsd:simpleType name="PostalCode">  
        <xsd:restriction base="xsd:positiveInteger">  
          <xsd:pattern value="\d{5}" />  
        </xsd:restriction>  
      </xsd:simpleType>  
    </xsd:schema>  
    ```  
  
11. 埋め込みリソースとして扱われるために、このファイルのビルド アクションを今すぐ更新します。 Visual Studio ソリューション ウィンドウで、これには、ファイルを右クリックして、**プロパティ**です。 ビルド アクションを変更する**None**に**埋め込みリソース**です。  
  
12. Visual Studio から、**ファイル** メニューのをクリックして**すべて保存**です。  
  
> [!NOTE]
>  これで作業が保存されました。 安全にこの時点で Visual Studio を終了したり、次の手順に進みます[手順 7: エコー アダプターの同期送信ハンドラーの実装](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md)です。  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 エコー アダプターの機能を解決するメタデータを実装されているだけです。  
  
## <a name="next-steps"></a>次の手順  
 次の手順では、エコー アダプターの同期送信ハンドラーを実装します。 ビルドし、同期受信ハンドラーを実装し、エコー アダプターを展開します。  
  
## <a name="see-also"></a>参照  
 [手順 5: エコー アダプターのメタデータの検索ハンドラーを実装します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md)   
 [手順 7: エコー アダプターの同期送信ハンドラーを実装します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md)   
 [チュートリアル 1: エコー アダプターを開発します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)
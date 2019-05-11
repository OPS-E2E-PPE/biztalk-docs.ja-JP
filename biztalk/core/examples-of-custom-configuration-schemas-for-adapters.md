---
title: アダプターのカスタム構成スキーマの例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 31b188de-9363-4f4c-b40a-149ff59ddf8d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 101a7a38ef9dbebc7829281bb1bfb6d547ef2f2b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346085"
---
# <a name="examples-of-custom-configuration-schemas-for-adapters"></a><span data-ttu-id="47ec2-102">アダプターのカスタム構成スキーマの例</span><span class="sxs-lookup"><span data-stu-id="47ec2-102">Examples of Custom Configuration Schemas for Adapters</span></span>
<span data-ttu-id="47ec2-103">ここでは、アダプター構成スキーマをカスタマイズする方法については、次の例を示します。</span><span class="sxs-lookup"><span data-stu-id="47ec2-103">This section provides the following examples for how to customize configuration schemas for adapters:</span></span>  
  
-   <span data-ttu-id="47ec2-104">**例 1** baf:designer 拡張と baf:description 拡張を使用してアダプターのプロパティ ページを表す完全なカスタム XSD スキーマ ファイルを示しています。</span><span class="sxs-lookup"><span data-stu-id="47ec2-104">**Example 1** shows a complete custom XSD schema file representing an adapter property page using the baf:designer and baf:description extensions.</span></span>  
  
-   <span data-ttu-id="47ec2-105">**例 2**のカスタム プロパティ値ウィンドウを作成する方法について説明、baf:designer 拡張と baf:description 拡張を使用しても、 **BatchSize** 1 と 99 の間の値のみを受け入れるプロパティ。</span><span class="sxs-lookup"><span data-stu-id="47ec2-105">**Example 2** also uses the baf:designer and baf:description extensions to show how to create a custom property value window for the **BatchSize** property that only accepts values between 1 and 99, inclusive.</span></span>  
  
-   <span data-ttu-id="47ec2-106">**例 3** baf:Password を 8 文字に制限する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="47ec2-106">**Example 3** shows how to limit the baf:Password to 8 characters.</span></span> <span data-ttu-id="47ec2-107">既定では、22 文字をできます。</span><span class="sxs-lookup"><span data-stu-id="47ec2-107">By default, it allows 22 characters.</span></span>  
  
-   <span data-ttu-id="47ec2-108">**例 4** XSD パターンがサポートされていないために、プロパティ値に対するパターン照合制約を実装する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="47ec2-108">**Example 4** shows how to implement pattern-matching constraints on property values because XSD patterns are not supported.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="47ec2-109">例 1</span><span class="sxs-lookup"><span data-stu-id="47ec2-109">Example 1</span></span>  
 <span data-ttu-id="47ec2-110">この例では、完全なカスタム XSD スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="47ec2-110">This example shows a complete custom XSD schema.</span></span> <span data-ttu-id="47ec2-111">これは、baf:designer 拡張と baf:description 拡張を使用してアダプターのプロパティ ページを表します。</span><span class="sxs-lookup"><span data-stu-id="47ec2-111">It represents an adapter property page using the baf:designer and baf:description extensions.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<xs:schema   targetNamespace="http://tempuri.org/XMLSchema.xsd"   
         elementFormDefault="qualified" xmlns="http://tempuri.org/XMLSchema.xsd"   
         xmlns:baf="BiztalkAdapterFramework.xsd"   
         xmlns:xs="http://www.w3.org/2001/XMLSchema"   
         xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:import namespace="BiztalkAdapterFramework.xsd" />  
   <xs:element name="Send">  
      <xs:complexType>  
         <xs:sequence>  
            <xs:element name="directory" type="xs:string" />  
               <xs:annotation>  
                  <xs:appinfo>  
                     <baf:designer>  
                        <baf:description>Enter the directory that will receive sent files..  
                        </baf:description>  
                     </baf:designer>  
                  </xs:appinfo>  
               </xs:annotation>  
            </xs:element>  
            <xs:element name="fileName" type="" />  
            <xs:element name="sendBatchSize" type="xs:int" />  
            <xs:element name="fileCopyMode" type="CopyMode" />  
            <xs:element name="uri" type="xs:string" >  
               <xs:annotation>  
                  <xs:appinfo>  
                     <baf:designer>  
                        <baf:browsable show="false" />  
                     </baf:designer>  
                  </xs:appinfo>  
               </xs:annotation>  
            </xs:element>  
         </xs:sequence>  
      </xs:complexType>  
   </xs:element>  
   <xs:simpleType name="CopyMode">  
      <xs:restriction base="xs:string">  
         <xs:enumeration value="Append">  
            <xs:annotation>  
               <xs:documentation>= 0</xs:documentation>  
            </xs:annotation>  
         <xs:enumeration value="Create">  
            <xs:annotation>  
               <xs:documentation>= 1</xs:documentation>  
            </xs:annotation>  
         <xs:enumeration value="CreateNew">  
            <xs:annotation>  
               <xs:documentation>= 2</xs:documentation>  
            </xs:annotation>  
         </xs:enumeration>  
      </xs:restriction>  
   </xs:simpleType>  
</xs:schema>  
```  
  
## <a name="example-2"></a><span data-ttu-id="47ec2-112">例 2</span><span class="sxs-lookup"><span data-stu-id="47ec2-112">Example 2</span></span>  
 <span data-ttu-id="47ec2-113">この例では、baf:designer 拡張と baf:description 拡張機能を使用して、カスタム プロパティ値ウィンドウを作成する方法を示して、 **BatchSize** 1 と 99 の間の値のみを受け入れるプロパティ。</span><span class="sxs-lookup"><span data-stu-id="47ec2-113">This example uses the baf:designer and baf:description extensions to show how to create a custom property value window for the **BatchSize** property that only accepts values between 1 and 99, inclusive.</span></span>  
  
```  
   <xs:element name="BatchSize">  
          <xs:simpleType>  
            <xs:annotation>  
              <xs:appinfo>  
                <baf:designer>  
                  <baf:displayname>Batch Size</baf:displayname>  
                  <baf:description>Enter the batch size (1-99)</baf:description>  
                </baf:designer>  
              </xs:appinfo>  
            </xs:annotation>  
            <xs:restriction base="xs:int">  
              <xs:minInclusive value="1" />  
              <xs:maxInclusive value="99" />  
            </xs:restriction>  
          </xs:simpleType>  
        </xs:element>  
```  
  
## <a name="example-3"></a><span data-ttu-id="47ec2-114">例 3</span><span class="sxs-lookup"><span data-stu-id="47ec2-114">Example 3</span></span>  
 <span data-ttu-id="47ec2-115">この例では、8 文字、baf:Password を制限する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="47ec2-115">This example shows how to limit the baf:Password to 8 characters.</span></span> <span data-ttu-id="47ec2-116">既定では、22 文字をできます。</span><span class="sxs-lookup"><span data-stu-id="47ec2-116">By default, it allows 22 characters.</span></span>  
  
```  
<xs:element name="AdapterPassword">  
          <xs:simpleType>  
            <xs:annotation>  
              <xs:appinfo>  
                <baf:designer>  
                  <baf:displayname>Adapter Password</baf:displayname>  
                  <baf:description>Enter the password (up to 8 characters)</baf:description>  
                  <baf:editor assembly="%BTSROOT%\\Developer Tools\\Microsoft.BizTalk.Adapter.Framework.dll">Microsoft.BizTalk.Adapter.Framework.ComponentModel.PasswordUITypeEditor</baf:editor>  
                  <baf:converter assembly="%BTSROOT%\\Developer Tools\\Microsoft.BizTalk.Adapter.Framework.dll">Microsoft.BizTalk.Adapter.Framework.ComponentModel.PasswordTypeConverter</baf:converter>  
                </baf:designer>  
              </xs:appinfo>  
            </xs:annotation>  
            <xs:restriction base="xs:string">  
              <xs:maxLength value="8" />  
            </xs:restriction>  
          </xs:simpleType>  
        </xs:element>  
```  
  
## <a name="example-4"></a><span data-ttu-id="47ec2-117">例 4</span><span class="sxs-lookup"><span data-stu-id="47ec2-117">Example 4</span></span>  
 <span data-ttu-id="47ec2-118">この例では、XSD パターンがサポートされていないために、プロパティ値に対するパターン照合制約を実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="47ec2-118">This example shows how to implement pattern-matching constraints on property values because XSD patterns are not supported.</span></span>  
  
 <span data-ttu-id="47ec2-119">などのフィールド**ClientIdentifier** 3 文字の数値文字列では常にします。</span><span class="sxs-lookup"><span data-stu-id="47ec2-119">Fields such as **ClientIdentifier** are always a three-character numeric string.</span></span> <span data-ttu-id="47ec2-120">010 は有効なプロパティ値の 10 が有効でありません。</span><span class="sxs-lookup"><span data-stu-id="47ec2-120">A property value of 10 is not valid, whereas 010 is valid.</span></span> <span data-ttu-id="47ec2-121">次の構成スキーマ フラグメントを定義、 **ClientIdentifier**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="47ec2-121">The following configuration schema fragment defines a **ClientIdentifier** property.</span></span> <span data-ttu-id="47ec2-122">**ClientIdentifierConverter**クラスは、アダプターのアセンブリで実装されたパターン マッチングに実装します。</span><span class="sxs-lookup"><span data-stu-id="47ec2-122">The **ClientIdentifierConverter** class, implemented in your adapter assembly, implements pattern matching.</span></span> <span data-ttu-id="47ec2-123">この場合は、カスタム型コンバーターは、3 桁 (000 ~ 999) の文字列に値を制限します。</span><span class="sxs-lookup"><span data-stu-id="47ec2-123">In this case, the custom type converter restricts values to a string of exactly three digits (000 to 999).</span></span> <span data-ttu-id="47ec2-124">構成のスキーマで、baf:converter ノードが、アセンブリと型の完全な名前が正しく設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="47ec2-124">In the configuration schema, make sure the baf:converter node has the assembly and type full name set correctly.</span></span> <span data-ttu-id="47ec2-125">ユーザーが有効でない値を入力しようとすると場合、プロパティ ページで、検証エラーが発生したときに例外メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="47ec2-125">If the user attempts to enter a value that is not valid, an exception message pops up when a validation error occurs in the property page.</span></span>  
  
 <span data-ttu-id="47ec2-126">アダプターのプロパティ ページの構成スキーマでは、次のコードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="47ec2-126">You can use the following code in the adapter property page configuration schemas.</span></span>  
  
```  
        <xs:element name="ClientIdentifier" type="xs:string">  
          <xs:annotation>  
            <xs:appinfo>  
              <baf:designer>  
                <baf:displayname>Adapter Client</baf:displayname>  
                <baf:description>Enter the Adapter Client (3 digit string)</baf:description>  
                <baf:converter assembly="%BTSROOT%\\Developer Tools\\Microsoft.BizTalk.TestAdapter.dll">Microsoft.BizTalk.TestAdapter.ClientIdentifierConverter</baf:converter>  
              </baf:designer>  
            </xs:appinfo>  
          </xs:annotation>  
        </xs:element>  
```  
  
 <span data-ttu-id="47ec2-127">アダプターのアセンブリには、次のコードを配置できます。</span><span class="sxs-lookup"><span data-stu-id="47ec2-127">You can place the following code in your adapter assembly.</span></span>  
  
```  
using System;  
using System.ComponentModel;  
using System.Globalization;  
using System.Text.RegularExpressions;  
  
namespace Microsoft.BizTalk.TestAdapter  
{  
       /// <summary>  
       /// Summary description for ClientIdentifierConverter.  
       /// </summary>  
       public class ClientIdentifierConverter : System.ComponentModel.StringConverter   
       {  
              private void Validate(string value)  
              {  
                     Regex regex = new Regex(@"^\d{3}$"); // ^=begin, \d=digit, {3}=exactly 3 occurrences, $=end  
                     Match match = regex.Match((string)value);  
                     if (!match.Success)  
                     {  
                           throw new ApplicationException("Value does not match pattern \"" + regex.ToString() + "\".");  
                     }  
              }  
  
              public override object ConvertFrom(ITypeDescriptorContext context, CultureInfo culture, object value)  
              {  
                     if (value is string)  
                     {  
                           this.Validate((string)value);  
                     }  
                     return base.ConvertFrom(context, culture, value);  
              }  
  
              public override object ConvertTo(ITypeDescriptorContext context, CultureInfo culture, object value, Type destinationType)  
              {  
                     if (typeof(string) == destinationType && value is string)  
                     {  
                           this.Validate((string)value);  
                     }  
                     return base.ConvertTo(context, culture, value, destinationType);  
              }  
       }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="47ec2-128">参照</span><span class="sxs-lookup"><span data-stu-id="47ec2-128">See Also</span></span>  
 [<span data-ttu-id="47ec2-129">アダプター フレームワーク構成スキーマの拡張機能</span><span class="sxs-lookup"><span data-stu-id="47ec2-129">Adapter Framework Configuration Schema Extensions</span></span>](../core/adapter-framework-configuration-schema-extensions.md)
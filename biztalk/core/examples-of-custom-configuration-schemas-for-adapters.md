---
title: アダプターのカスタム構成スキーマの例を示します |Microsoft ドキュメント
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
ms.openlocfilehash: b11cb16c7b7ae9285b6ffb77c7177964d211482f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245914"
---
# <a name="examples-of-custom-configuration-schemas-for-adapters"></a>アダプターのカスタム構成スキーマの例
このセクションでは、アダプターの構成スキーマをカスタマイズする方法を次の例を示します。  
  
-   **例 1** baf:designer 拡張と baf:description 拡張を使用してアダプターのプロパティ ページを表す完全なカスタム XSD スキーマ ファイルを示しています。  
  
-   **例 2**用のカスタム プロパティ値ウィンドウを作成する方法を示す、baf:designer 拡張と baf:description 拡張を使用しても、 **BatchSize** 1 と 99 の間の値のみを受け入れるプロパティです。  
  
-   **例 3** baf:Password を 8 文字に制限する方法を示します。 既定では、22 文字まで使用できます。  
  
-   **例 4** XSD パターンがサポートされていないために、プロパティ値に対するパターン照合制約を実装する方法を示します。  
  
## <a name="example-1"></a>例 1  
 この例では、完全なカスタム XSD スキーマを示します。 このスキーマは、baf:designer 拡張と baf:description 拡張を使用してアダプターのプロパティ ページを表します。  
  
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
  
## <a name="example-2"></a>例 2  
 この例では、baf:designer 拡張と baf:description 拡張機能を使用して、カスタム プロパティ値ウィンドウを作成する方法を示して、 **BatchSize** 1 と 99 の間の値のみを受け入れるプロパティです。  
  
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
  
## <a name="example-3"></a>例 3  
 この例では、baf:Password を 8 文字までに制限する方法を示します。 既定では、22 文字まで使用できます。  
  
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
  
## <a name="example-4"></a>例 4  
 XSD パターンがサポートされていないため、この例では、プロパティ値に対するパターン照合制約を実装する方法を示します。  
  
 などのフィールド**ClientIdentifier** 3 文字の数値の文字列は、常にします。 10 のプロパティ値は無効ですが、010 は有効です。 次の構成スキーマ フラグメントを定義、 **ClientIdentifier**プロパティです。 **ClientIdentifierConverter**パターンに一致するアダプターのアセンブリに実装されているクラスを実装します。 この場合、カスタム型コンバーターは、値を 3 桁の文字列 (000 ～ 999) だけに制限します。 構成スキーマでは、baf:converter ノードがアセンブリを含んでいることを確認して、完全な名前を正しく入力します。 ユーザーが無効な値を入力しようとすると、プロパティ ページで検証エラーが発生して例外メッセージがポップアップ表示されます。  
  
 アダプター プロパティ ページの構成スキーマで次のコードを使用できます。  
  
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
  
 アダプターのアセンブリに、次のコードを配置できます。  
  
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
  
## <a name="see-also"></a>参照  
 [アダプター フレームワーク構成スキーマの拡張機能](../core/adapter-framework-configuration-schema-extensions.md)
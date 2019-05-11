---
title: アダプター フレームワーク構成拡張機能の有効化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 851f4a20-502d-45f8-9647-13bec33fa460
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63831845dee97a4ce03bb5ac19595b2db42e3327
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349669"
---
# <a name="enabling-adapter-framework-configuration-extensions"></a>アダプター フレームワーク構成拡張機能を有効にします。
BizTalk アダプター フレームワークは、ユーザー エクスペリエンスを向上させるためにいくつかの拡張機能を提供します。 これらの拡張機能を使用するには、フレームワークのスキーマ、BiztalkAdapterFramework.xsd をインポートします。 スキーマをインポートする、文字装飾および特化された型にアクセスして、アダプターの構成のスキーマで使用する以下に示すようできます。 次のコードでは、スキーマをインポートする方法を示します。  
  
```  
<?xml version="1.0" encoding="utf-8" ?><xs:schema   targetNamespace="http://tempuri.org/XMLSchema.xsd"   
         elementFormDefault="qualified" xmlns="http://tempuri.org/XMLSchema.xsd"   
         xmlns:baf="BiztalkAdapterFramework.xsd"   
         xmlns:xs="http://www.w3.org/2001/XMLSchema"   
         xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:import namespace="BiztalkAdapterFramework.xsd" />  
. . .  
</xs:schema>  
```  
  
## <a name="importing-the-biztalk-adapter-framework-extensions-schema-xsd"></a>BizTalk アダプター フレームワークの拡張機能スキーマ XSD をインポートします。  
 アダプター フレームワークの拡張機能スキーマ XSD をインポートすることによって、使用できる文字装飾など\<baf:FileName\>として要素の型を示すファイル名ポップアップ要素を編集するときにします。  
  
 さらに装飾では、インターフェイスのプロパティの表示を制御します。 \<Baf:description\>装飾はたとえば、要素にヘルプ テキストを追加します。 \<Baf:description\>装飾には、プロパティ ページの下部にあるテキストが表示されます。 \<Baf: ブラウズ\>装飾には、インターフェイスから要素が非表示にします。 次のコードは、構成スキーマ内でこれらの要素を使用する方法を示しています。  
  
```  
<?xml version="1.0" encoding="utf-8" ?><xs:schema   targetNamespace="http://tempuri.org/XMLSchema.xsd"   
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
  
## <a name="see-also"></a>参照  
 [アダプター フレームワーク構成スキーマの拡張機能](../core/adapter-framework-configuration-schema-extensions.md)
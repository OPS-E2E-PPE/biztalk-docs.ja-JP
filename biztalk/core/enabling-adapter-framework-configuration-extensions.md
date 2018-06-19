---
title: アダプター フレームワーク構成の拡張機能の有効化 |Microsoft ドキュメント
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
ms.openlocfilehash: e111a271654b40a01032805bbfdb8eb54bc31ead
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970152"
---
# <a name="enabling-adapter-framework-configuration-extensions"></a><span data-ttu-id="68e4a-102">アダプター フレームワーク構成の拡張機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="68e4a-102">Enabling Adapter Framework Configuration Extensions</span></span>
<span data-ttu-id="68e4a-103">ユーザー エクスペリエンスを向上させるために、BizTalk アダプター フレームワークでは拡張機能がいくつか提供されています。</span><span class="sxs-lookup"><span data-stu-id="68e4a-103">The BizTalk Adapter Framework provides several extensions to improve the user experience.</span></span> <span data-ttu-id="68e4a-104">これらの拡張機能を使用するのには、フレームワークのスキーマ、BiztalkAdapterFramework.xsd をインポートします。</span><span class="sxs-lookup"><span data-stu-id="68e4a-104">To use these extensions, import the framework's schema, BiztalkAdapterFramework.xsd.</span></span> <span data-ttu-id="68e4a-105">スキーマをインポートする、装飾および特化された型にアクセスして、アダプターの構成スキーマでの使用を以下に示すようできます。</span><span class="sxs-lookup"><span data-stu-id="68e4a-105">Importing the schema enables you to access decorations and specialized types and to use them in the adapter's configuration schema, as described below.</span></span> <span data-ttu-id="68e4a-106">次のコードは、スキーマのインポート方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="68e4a-106">The following code shows how to import the schema:</span></span>  
  
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
  
## <a name="importing-the-biztalk-adapter-framework-extensions-schema-xsd"></a><span data-ttu-id="68e4a-107">BizTalk アダプター フレームワークの拡張機能スキーマ XSD のインポート</span><span class="sxs-lookup"><span data-stu-id="68e4a-107">Importing the BizTalk Adapter Framework Extensions Schema XSD</span></span>  
 <span data-ttu-id="68e4a-108">アダプター フレームワークの拡張機能スキーマ XSD をインポートする装飾など、使用できる\<baf:FileName\>要素の種類を示すファイル名ポップアップ要素を編集するとき。</span><span class="sxs-lookup"><span data-stu-id="68e4a-108">By importing the Adapter Framework extensions schema XSD, you can use decorations such as \<baf:FileName\> as an element's type, which shows the file name pop-up when editing the element.</span></span>  
  
 <span data-ttu-id="68e4a-109">さらに装飾を追加して、インターフェイス内のプロパティ表示を制御できます。</span><span class="sxs-lookup"><span data-stu-id="68e4a-109">Additional decorations control the display of the property in the interface.</span></span> <span data-ttu-id="68e4a-110">\<Baf:description\>装飾はたとえば、要素にヘルプ テキストを追加します。</span><span class="sxs-lookup"><span data-stu-id="68e4a-110">The \<baf:description\> decoration, for example, adds help text to the element.</span></span> <span data-ttu-id="68e4a-111">\<Baf:description\>装飾には、プロパティ ページの下部にあるテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="68e4a-111">The \<baf:description\> decoration displays the text at the bottom of the property page.</span></span> <span data-ttu-id="68e4a-112">\<Baf: ブラウズ\>装飾には、インターフェイスから要素が非表示にします。</span><span class="sxs-lookup"><span data-stu-id="68e4a-112">The \<baf:browsable\> decoration hides an element from the interface.</span></span> <span data-ttu-id="68e4a-113">次のコードは、このような要素を構成スキーマで使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="68e4a-113">The following code shows how you can use these elements within a configuration schema:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="68e4a-114">参照</span><span class="sxs-lookup"><span data-stu-id="68e4a-114">See Also</span></span>  
 [<span data-ttu-id="68e4a-115">アダプター フレームワーク構成スキーマの拡張機能</span><span class="sxs-lookup"><span data-stu-id="68e4a-115">Adapter Framework Configuration Schema Extensions</span></span>](../core/adapter-framework-configuration-schema-extensions.md)
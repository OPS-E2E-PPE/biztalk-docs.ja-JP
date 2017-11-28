---
title: "アダプター構成スキーマ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc08fa71-c5f7-4365-9506-e02351b17567
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2afa0e2f06471d90326b0dd8e2b83b8d4c38a82b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-configuration-schemas"></a><span data-ttu-id="4f222-102">アダプター構成スキーマ</span><span class="sxs-lookup"><span data-stu-id="4f222-102">Adapter Configuration Schemas</span></span>
<span data-ttu-id="4f222-103">アダプターのデザイン時構成では、さまざまな種類のスキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="4f222-103">Different types of schemas are used in design-time configuration of an adapter.</span></span> <span data-ttu-id="4f222-104">プロパティ値の可視性とスコープに応じて、さまざまなスキーマを変更して使用します。</span><span class="sxs-lookup"><span data-stu-id="4f222-104">Depending upon the visibility and scope of property values, different schemas are modified and used.</span></span>  
  
## <a name="handler-schemas"></a><span data-ttu-id="4f222-105">ハンドラーのスキーマ</span><span class="sxs-lookup"><span data-stu-id="4f222-105">Handler Schemas</span></span>  
 <span data-ttu-id="4f222-106">ハンドラーから取得したアダプター構成は、アダプターとそのコンシューマーすべてにグローバル スコープで適用されます。</span><span class="sxs-lookup"><span data-stu-id="4f222-106">Adapter configuration that comes from a handler applies to the adapter and all its consumers on a global scope.</span></span> <span data-ttu-id="4f222-107">管理者は、デザイン時に、ハンドラー構成を静的に変更できます。そのためには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用してアダプターの受信ハンドラーまたは送信ハンドラーを展開し、指定したホストのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="4f222-107">An administrator can statically alter handler configuration at design time by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to expand the adapter's receive or send handler and bring up the properties of the specified host.</span></span>  
  
 <span data-ttu-id="4f222-108">SDK に付属するサンプル ファイル アダプターには、受信場所、送信ポート、受信ハンドラー、および送信ハンドラーの構成に使用する一連の XSD ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f222-108">The sample file adapter included in the SDK has a set of XSD files used to configure its receive location, send port, receive handler, and send handler.</span></span> <span data-ttu-id="4f222-109">カスタム アダプターが必要とする構成プロパティを受け取るよう、これらの XSD ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="4f222-109">Modify these XSD files so that your custom adapter receives the configuration properties it requires.</span></span> <span data-ttu-id="4f222-110">サンプル ファイル アダプターに含まれているファイルのうち、変更する必要があるのは、スキーマ ファイル TransmitHandler.xsd および ReceiveHandler.xsd です。</span><span class="sxs-lookup"><span data-stu-id="4f222-110">The files included with the sample file adapter that you need to modify are the TransmitHandler.xsd and ReceiveHandler.xsd schema files.</span></span> <span data-ttu-id="4f222-111">これらのファイルでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールでハンドラーの構成に使用されるプロパティ ページを制御することにより、それぞれ送信ハンドラーと受信ハンドラーを構成します。</span><span class="sxs-lookup"><span data-stu-id="4f222-111">These files configure the send handler and receive handler, respectively, by controlling the property pages used to configure the handlers in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="4f222-112">アダプターの要件に基づいて、各エンドポイントに必要な構成プロパティの一覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="4f222-112">Using your adapter requirements, create a list of configuration properties required for each of the endpoints.</span></span> <span data-ttu-id="4f222-113">すべての構成プロパティがグローバルである場合、変更する必要があるのは送受信ポートの構成だけです。</span><span class="sxs-lookup"><span data-stu-id="4f222-113">If all of your configuration properties are global, you may only need to modify the send and receive port configurations.</span></span> <span data-ttu-id="4f222-114">送信ポートまたは受信場所ごとにアダプター プロパティを設定する必要がある場合、受信場所と送信ポートの構成ファイルも変更しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="4f222-114">If the adapter properties need to be set for each send port or receive location, you have to modify the receive location and send port configuration files as well.</span></span>  
  
 <span data-ttu-id="4f222-115">アダプター フレームワークには、一般的なアダプター構成の要件をサポートするための、スキーマ拡張機能および詳細構成オプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="4f222-115">The Adapter Framework provides schema extensions and advanced configuration options to support common adapter configuration requirements.</span></span> <span data-ttu-id="4f222-116">また、サンプル ファイル アダプターに含まれているスキーマにはない拡張機能も用意されています。</span><span class="sxs-lookup"><span data-stu-id="4f222-116">It also provides extensions that are not in the schema included with the sample file adapter.</span></span> <span data-ttu-id="4f222-117">アダプター フレームワーク スキーマの拡張機能の詳細については、次を参照してください。[アダプター フレームワーク構成スキーマの拡張機能](../core/adapter-framework-configuration-schema-extensions.md)します。</span><span class="sxs-lookup"><span data-stu-id="4f222-117">For more information about the Adapter Framework schema extensions, see [Adapter Framework Configuration Schema Extensions](../core/adapter-framework-configuration-schema-extensions.md).</span></span> <span data-ttu-id="4f222-118">カスタム ドロップダウン エディターやカスタム型コンバーターなどの高度な構成オプションの詳細については、次を参照してください。[アダプターの高度な構成コンポーネント](../core/advanced-configuration-components-for-adapters.md)です。</span><span class="sxs-lookup"><span data-stu-id="4f222-118">For more information about advanced configuration options such as custom drop-down editors and custom type converters, see [Advanced Configuration Components for Adapters](../core/advanced-configuration-components-for-adapters.md).</span></span>  
  
 <span data-ttu-id="4f222-119">TransmitHandler.xsd ファイルのコードを、このトピックの最後に示します。このコードにより、次のプロパティ ページが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4f222-119">The code at the end of this topic is from the TransmitHandler.xsd file, and produces the following property page.</span></span>  
  
 ![](../core/media/ebiz-prog-custad-sh.gif "ebiz_prog_custad_sh")  
<span data-ttu-id="4f222-120">TransmitHandler.xsd ファイルによって作成される送信ハンドラー プロパティ ページ</span><span class="sxs-lookup"><span data-stu-id="4f222-120">Send handler property page created by the TransmitHandler.xsd file</span></span>  
  
 <span data-ttu-id="4f222-121">使用に注意してください、 \<baf:designer >、 \<baf:displayname >、および\<baf:description > 次に示す TransmitHandler.xsd コード内のタグ。</span><span class="sxs-lookup"><span data-stu-id="4f222-121">Note the use of the \<baf:designer>, \<baf:displayname>, and \<baf:description> tags in the TransmitHandler.xsd code that is shown below.</span></span> <span data-ttu-id="4f222-122">これらは、アダプター フレームワークによって提供されているカスタム装飾であり、このようなプロパティ ページの生成を高速化します。</span><span class="sxs-lookup"><span data-stu-id="4f222-122">These are custom decorations provided by the Adapter Framework to make the generation of these property pages faster.</span></span>  
  
 <span data-ttu-id="4f222-123">すべてのアダプター フレームワーク内で使用できる装飾の一覧は、次を参照してください。[アダプター フレームワーク構成スキーマの装飾タグ](../core/adapter-framework-configuration-schema-decoration-tags.md)です。</span><span class="sxs-lookup"><span data-stu-id="4f222-123">For a list of all of the decorations available for use within the Adapter Framework, see [Adapter Framework Configuration Schema Decoration Tags](../core/adapter-framework-configuration-schema-decoration-tags.md).</span></span>  
  
 <span data-ttu-id="4f222-124">このスキーマには、要素が 1 つだけ含まれており、URI 要素は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="4f222-124">Note that the schema has only one element and does not contain a URI element.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4f222-125">既定のアダプター スキーマに、機密性の高い顧客データを格納しない。</span><span class="sxs-lookup"><span data-stu-id="4f222-125">Do not store sensitive customer data in the default adapter schema.</span></span> <span data-ttu-id="4f222-126">セキュリティ上の理由により、ユーザー名とパスワードの情報を構成するのは、アダプターの展開後にしてください。</span><span class="sxs-lookup"><span data-stu-id="4f222-126">For security reasons, configure user name and password information only after you deploy an adapter.</span></span> <span data-ttu-id="4f222-127">これにより、エンタープライズ シングル サインオン (SSO) データベースに確実に情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="4f222-127">This ensures that the information gets stored in the Enterprise Single Sign-On (SSO) database.</span></span> <span data-ttu-id="4f222-128">SSO データベースの詳細については、次を参照してください。[を使用して SSO](../core/using-sso.md)です。</span><span class="sxs-lookup"><span data-stu-id="4f222-128">For more information about the SSO database, see [Using SSO](../core/using-sso.md).</span></span>  
  
```  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:baf="BiztalkAdapterFramework.xsd"   
xmlns:b="http://schemas.microsoft.com/BizTalk/2003"   
xmlns="http://tempuri.org/XMLSchema1.xsd"   
elementFormDefault="qualified" targetNamespace="http://tempuri.org/XMLSchema1.xsd"   
id="TransmitHandler" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="Config">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element default="50" name="sendBatchSize" type="xs:int" >  
      <xs:annotation>  
         <xs:appinfo>  
            <baf:designer>  
               <baf:displayname _locID="sendBatchSizeName">Batch Size</baf:displayname>  
               <baf:description _locID="sendBatchSizeDesc">Enter the   
maximum number of files to be transmitted per batch</baf:description>  
            </baf:designer>  
         </xs:appinfo>  
      </xs:annotation>  
   </xs:element>  
  
        <xs:element default="4096" name="bufferSize" type="xs:int" >  
      <xs:annotation>  
         <xs:appinfo>  
            <baf:designer>  
               <baf:displayname _locID="bufferSizeName">Write Buffer Size</baf:displayname>  
               <baf:description _locID="bufferSizeDesc">Enter the size of   
the buffer used to write the file</baf:description>  
            </baf:designer>  
         </xs:appinfo>  
      </xs:annotation>  
   </xs:element>  
  
        <xs:element default="1" name="threadsPerCPU" type="xs:int" >  
      <xs:annotation>  
         <xs:appinfo>  
            <baf:designer>  
               <baf:displayname _locID="threadsPerCPUName">Threads Per CPU</baf:displayname>  
               <baf:description _locID="threadsPerCPUDesc">Enter the   
number of threads per CPU to execute in the thread pool</baf:description>  
            </baf:designer>  
         </xs:appinfo>  
      </xs:annotation>  
   </xs:element>  
  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
## <a name="send-port-and-receive-location-schemas"></a><span data-ttu-id="4f222-129">送信ポートおよび受信場所のスキーマ</span><span class="sxs-lookup"><span data-stu-id="4f222-129">Send Port and Receive Location Schemas</span></span>  
 <span data-ttu-id="4f222-130">アダプターにポート固有のプロパティを設定するには、受信場所および送信ポートの構成スキーマを変更します。</span><span class="sxs-lookup"><span data-stu-id="4f222-130">To set port-specific properties for your adapter, modify the receive location and send port configuration schemas.</span></span> <span data-ttu-id="4f222-131">スキーマ ファイル TransmitLocation.xsd および ReceiveLocation.xsd では、それぞれ送信ポートと受信場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="4f222-131">The TransmitLocation.xsd and ReceiveLocation.xsd schema files configure the send port and receive location, respectively.</span></span>  
  
 <span data-ttu-id="4f222-132">アダプター フレームワークには、一般的なアダプター構成の要件をサポートするための、スキーマ拡張機能および詳細構成オプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="4f222-132">The Adapter Framework provides schema extensions and advanced configuration options to support common adapter configuration requirements.</span></span> <span data-ttu-id="4f222-133">アダプター フレームワーク スキーマの拡張機能の詳細については、次を参照してください。[アダプター フレームワーク構成スキーマの拡張機能](../core/adapter-framework-configuration-schema-extensions.md)します。</span><span class="sxs-lookup"><span data-stu-id="4f222-133">For more information about the Adapter Framework schema extensions, see [Adapter Framework Configuration Schema Extensions](../core/adapter-framework-configuration-schema-extensions.md).</span></span> <span data-ttu-id="4f222-134">カスタム ドロップダウン エディターやカスタム型コンバーターなどの高度な構成オプションの詳細については、次を参照してください。[アダプターの高度な構成コンポーネント](../core/advanced-configuration-components-for-adapters.md)です。</span><span class="sxs-lookup"><span data-stu-id="4f222-134">For more information about advanced configuration options such as custom drop-down editors and custom type converters, see [Advanced Configuration Components for Adapters](../core/advanced-configuration-components-for-adapters.md).</span></span>  
  
 <span data-ttu-id="4f222-135">TransmitLocation.xsd ファイルのコードを以下に示します。このコードにより、次のプロパティ ページが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4f222-135">The code that follows is from the TransmitLocation.xsd file, and produces the following property page.</span></span>  
  
 ![](../core/media/ebiz-prog-custad-sp.gif "ebiz_prog_custad_sp")  
<span data-ttu-id="4f222-136">サンプル ファイル アダプターの送信ポート プロパティ ページを示します</span><span class="sxs-lookup"><span data-stu-id="4f222-136">Illustrates the send port property page for the sample file adapter</span></span>  
  
 <span data-ttu-id="4f222-137">送信ポートの構成が含まれている下の TransmitLocation.xsd ファイルに注意してください、 \<baf:designer >、 \<baf:displayname >、および\<baf:description > タグで、送信ハンドラの場合にも、使用する場合と同じように、\<baf:category > タグです。</span><span class="sxs-lookup"><span data-stu-id="4f222-137">Note in the TransmitLocation.xsd file below that the send port configuration contains the \<baf:designer>, \<baf:displayname>, and \<baf:description> tags, just like the send handler, and it also uses the \<baf:category> tag.</span></span> <span data-ttu-id="4f222-138">このカテゴリ タグを使用すると、複数のプロパティをグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="4f222-138">The category tag enables you to group properties together.</span></span> <span data-ttu-id="4f222-139">カテゴリが複数ある場合は、展開したり折りたたんだりできます。また、カテゴリに含まれるプロパティの上には、そのカテゴリがヘッダーとして灰色で表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f222-139">If you have more than one category, the category is expandable and collapsible and appears in gray as a header above the properties in that category.</span></span> <span data-ttu-id="4f222-140">詳細については、次を参照してください。[アダプター フレームワーク構成スキーマの拡張機能](../core/adapter-framework-configuration-schema-extensions.md)します。</span><span class="sxs-lookup"><span data-stu-id="4f222-140">For more information, see [Adapter Framework Configuration Schema Extensions](../core/adapter-framework-configuration-schema-extensions.md).</span></span>  
  
 <span data-ttu-id="4f222-141">このスキーマには URI フィールドも含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f222-141">This schema also contains a URI field.</span></span> <span data-ttu-id="4f222-142">これは、送信ポート プロパティ ページのフィールド情報をすべて入力した後に表示されるページに、アダプターによる検証処理中に自動入力されます。</span><span class="sxs-lookup"><span data-stu-id="4f222-142">This is populated on the page that appears after you enter all of the field information on the send port property page during the validation processing by the adapter.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:baf="BiztalkAdapterFramework.xsd" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" xmlns="http://tempuri.org/XMLSchema1.xsd" elementFormDefault="qualified" targetNamespace="http://tempuri.org/XMLSchema1.xsd" id="TransmitLocation" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="Config">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="directory" type="xs:string">  
      <xs:annotation>  
         <xs:appinfo>  
            <baf:designer xmlns:baf="BiztalkAdapterFramework.xsd">  
               <baf:displayname _locID="sendDirectoryName">Directory</baf:displayname>  
               <baf:description _locID="sendDirectoryDesc">Directory to write the file to</baf:description>  
                         <baf:category _locID="transmitLocationCategory">Transmit Location</baf:category>  
                    </baf:designer>  
         </xs:appinfo>  
      </xs:annotation>  
        </xs:element>  
  
        <xs:element default="%MessageID%.xml" name="fileName" type="xs:string">  
          <xs:annotation>  
            <xs:appinfo>  
              <baf:designer xmlns:baf="BiztalkAdapterFramework.xsd">  
                <baf:displayname _locID="fileNameName">File Name</baf:displayname>  
      <baf:description _locID="fileNameDesc">The name of the file that will be written</baf:description>  
                <baf:category _locID="transmitLocationCategory">Transmit Location</baf:category>  
              </baf:designer>  
            </xs:appinfo>  
          </xs:annotation>  
        </xs:element>  
  
        <xs:element default="2" name="fileCopyMode" type="CopyMode">  
          <xs:annotation>  
            <xs:appinfo>  
              <baf:designer xmlns:baf="BiztalkAdapterFramework.xsd">  
                <baf:displayname _locID="fileCopyModeName">File Mode</baf:displayname>  
                <baf:category _locID="transmitLocationCategory">Transmit Location</baf:category>  
              </baf:designer>  
            </xs:appinfo>  
          </xs:annotation>  
        </xs:element>  
  
        <xs:element name="uri" type="xs:string">  
          <xs:annotation>  
            <xs:appinfo>  
              <baf:designer xmlns:baf="BiztalkAdapterFramework.xsd">  
                <baf:browsable show="false" />  
              </baf:designer>  
            </xs:appinfo>  
          </xs:annotation>  
        </xs:element>  
  
   <!-- An example of how an SSO affiliate application would be configured for this endpoint: -->  
   <!--  
   <xs:element name="ssoAffiliateApplication" type="baf:SSOList">  
      <xs:annotation>  
         <xs:appinfo>  
            <baf:designer>  
               <baf:displayname _locID="ssoAffiliateApplicationName">SSO Affiliate</baf:displayname>  
               <baf:description _locID="ssoAffiliateApplicationDesc">The Single Sign On (SSO) Affiliate Application</baf:description>  
               <baf:category _locID="ftpCategory">FTP</baf:category>  
            </baf:designer>  
         </xs:appinfo>  
      </xs:annotation>  
   </xs:element>  
   -->  
  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
  
  <xs:simpleType name="CopyMode">  
    <xs:restriction base="xs:int">  
      <xs:enumeration value="0">  
        <xs:annotation>  
          <xs:appinfo>  
            <baf:designer xmlns:baf="BiztalkAdapterFramework.xsd">  
              <baf:displayname _locID="appendName">Append</baf:displayname>  
            </baf:designer>  
          </xs:appinfo>  
        </xs:annotation>  
      </xs:enumeration>  
      <xs:enumeration value="1">  
        <xs:annotation>  
          <xs:appinfo>  
            <baf:designer xmlns:baf="BiztalkAdapterFramework.xsd">  
              <baf:displayname _locID="createName">Create</baf:displayname>  
            </baf:designer>  
          </xs:appinfo>  
        </xs:annotation>  
      </xs:enumeration>  
      <xs:enumeration value="2">  
        <xs:annotation>  
          <xs:appinfo>  
            <baf:designer xmlns:baf="BiztalkAdapterFramework.xsd">  
              <baf:displayname _locID="createNewName">CreateNew</baf:displayname>  
            </baf:designer>  
          </xs:appinfo>  
        </xs:annotation>  
      </xs:enumeration>  
    </xs:restriction>  
  </xs:simpleType>  
</xs:schema>  
```
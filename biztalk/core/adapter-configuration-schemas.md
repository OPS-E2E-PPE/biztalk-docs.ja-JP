---
title: アダプター構成スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc08fa71-c5f7-4365-9506-e02351b17567
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 837e4ff704b086f5511c42f8184c1edc03928ef8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361562"
---
# <a name="adapter-configuration-schemas"></a><span data-ttu-id="650b4-102">アダプター構成スキーマ</span><span class="sxs-lookup"><span data-stu-id="650b4-102">Adapter Configuration Schemas</span></span>
<span data-ttu-id="650b4-103">さまざまな種類のスキーマは、アダプターのデザイン時構成で使用されます。</span><span class="sxs-lookup"><span data-stu-id="650b4-103">Different types of schemas are used in design-time configuration of an adapter.</span></span> <span data-ttu-id="650b4-104">可視性とスコープのプロパティの値に応じて、さまざまなスキーマ変更され使用します。</span><span class="sxs-lookup"><span data-stu-id="650b4-104">Depending upon the visibility and scope of property values, different schemas are modified and used.</span></span>  
  
## <a name="handler-schemas"></a><span data-ttu-id="650b4-105">ハンドラーのスキーマ</span><span class="sxs-lookup"><span data-stu-id="650b4-105">Handler Schemas</span></span>  
 <span data-ttu-id="650b4-106">ハンドラーから取得したアダプター構成は、アダプターにグローバル スコープですべてのコンシューマーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="650b4-106">Adapter configuration that comes from a handler applies to the adapter and all its consumers on a global scope.</span></span> <span data-ttu-id="650b4-107">使用して、管理者がデザイン時にハンドラー構成を静的に変更、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをアダプターの展開を受信または送信ハンドラーと、指定したホストのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="650b4-107">An administrator can statically alter handler configuration at design time by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to expand the adapter's receive or send handler and bring up the properties of the specified host.</span></span>  
  
 <span data-ttu-id="650b4-108">SDK に含まれているサンプル ファイル アダプターが、一連の構成に使用される XSD ファイルの受信場所、送信ポート、受信ハンドラー、および送信ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="650b4-108">The sample file adapter included in the SDK has a set of XSD files used to configure its receive location, send port, receive handler, and send handler.</span></span> <span data-ttu-id="650b4-109">これらの XSD ファイルを変更して、カスタム アダプターの受信設定のプロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="650b4-109">Modify these XSD files so that your custom adapter receives the configuration properties it requires.</span></span> <span data-ttu-id="650b4-110">変更する必要のあるサンプル ファイル アダプターに含まれているファイルは、TransmitHandler.xsd および ReceiveHandler.xsd スキーマ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="650b4-110">The files included with the sample file adapter that you need to modify are the TransmitHandler.xsd and ReceiveHandler.xsd schema files.</span></span> <span data-ttu-id="650b4-111">これらのファイル送信ハンドラを構成し、受信ハンドラー、それぞれのハンドラーの構成に使用されるプロパティ ページを制御することで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="650b4-111">These files configure the send handler and receive handler, respectively, by controlling the property pages used to configure the handlers in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="650b4-112">アダプターの要件を使用して、各エンドポイントに必要な構成プロパティの一覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="650b4-112">Using your adapter requirements, create a list of configuration properties required for each of the endpoints.</span></span> <span data-ttu-id="650b4-113">グローバルすべて、構成プロパティの場合は、変更の送信と受信ポートの構成にだけことがあります。</span><span class="sxs-lookup"><span data-stu-id="650b4-113">If all of your configuration properties are global, you may only need to modify the send and receive port configurations.</span></span> <span data-ttu-id="650b4-114">アダプターのプロパティは、各送信ポートまたは受信場所に対して設定する場合に、受信場所を変更し、送信ポートの構成ファイルもが必要です。</span><span class="sxs-lookup"><span data-stu-id="650b4-114">If the adapter properties need to be set for each send port or receive location, you have to modify the receive location and send port configuration files as well.</span></span>  
  
 <span data-ttu-id="650b4-115">アダプター フレームワークは、スキーマの拡張機能および一般的なアダプター構成の要件をサポートするために高度な構成オプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="650b4-115">The Adapter Framework provides schema extensions and advanced configuration options to support common adapter configuration requirements.</span></span> <span data-ttu-id="650b4-116">サンプル ファイル アダプターに含まれているスキーマではない拡張機能も提供します。</span><span class="sxs-lookup"><span data-stu-id="650b4-116">It also provides extensions that are not in the schema included with the sample file adapter.</span></span> <span data-ttu-id="650b4-117">アダプター フレームワーク スキーマの拡張機能の詳細については、次を参照してください。[アダプター フレームワーク構成スキーマの拡張機能](../core/adapter-framework-configuration-schema-extensions.md)します。</span><span class="sxs-lookup"><span data-stu-id="650b4-117">For more information about the Adapter Framework schema extensions, see [Adapter Framework Configuration Schema Extensions](../core/adapter-framework-configuration-schema-extensions.md).</span></span> <span data-ttu-id="650b4-118">カスタム ドロップダウン エディターやカスタム型コンバーターなどの高度な構成オプションの詳細については、次を参照してください。[アダプターの高度な構成コンポーネント](../core/advanced-configuration-components-for-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="650b4-118">For more information about advanced configuration options such as custom drop-down editors and custom type converters, see [Advanced Configuration Components for Adapters](../core/advanced-configuration-components-for-adapters.md).</span></span>  
  
 <span data-ttu-id="650b4-119">このトピックの最後に、コードは、TransmitHandler.xsd ファイルからは、し、次のプロパティ ページを生成します。</span><span class="sxs-lookup"><span data-stu-id="650b4-119">The code at the end of this topic is from the TransmitHandler.xsd file, and produces the following property page.</span></span>  
  
 <span data-ttu-id="650b4-120">![](../core/media/ebiz-prog-custad-sh.gif "ebiz_prog_custad_sh")</span><span class="sxs-lookup"><span data-stu-id="650b4-120">![](../core/media/ebiz-prog-custad-sh.gif "ebiz_prog_custad_sh")</span></span>  
<span data-ttu-id="650b4-121">TransmitHandler.xsd ファイルによって作成されたハンドラーのプロパティ ページを送信します。</span><span class="sxs-lookup"><span data-stu-id="650b4-121">Send handler property page created by the TransmitHandler.xsd file</span></span>  
  
 <span data-ttu-id="650b4-122">使用に注意してください、 \<baf:designer\>、 \<baf:displayname\>、および\<baf:description\>以下に示す TransmitHandler.xsd コード内のタグ。</span><span class="sxs-lookup"><span data-stu-id="650b4-122">Note the use of the \<baf:designer\>, \<baf:displayname\>, and \<baf:description\> tags in the TransmitHandler.xsd code that is shown below.</span></span> <span data-ttu-id="650b4-123">これらは、これらのプロパティ ページの生成を速くアダプター フレームワークによって提供されるカスタムの装飾です。</span><span class="sxs-lookup"><span data-stu-id="650b4-123">These are custom decorations provided by the Adapter Framework to make the generation of these property pages faster.</span></span>  
  
 <span data-ttu-id="650b4-124">アダプター フレームワーク内で使用できる文字装飾のすべての一覧は、次を参照してください。[アダプター フレームワーク構成スキーマの装飾タグ](../core/adapter-framework-configuration-schema-decoration-tags.md)します。</span><span class="sxs-lookup"><span data-stu-id="650b4-124">For a list of all of the decorations available for use within the Adapter Framework, see [Adapter Framework Configuration Schema Decoration Tags](../core/adapter-framework-configuration-schema-decoration-tags.md).</span></span>  
  
 <span data-ttu-id="650b4-125">スキーマは 1 つだけ要素があり、URI 要素が含まれていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="650b4-125">Note that the schema has only one element and does not contain a URI element.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="650b4-126">既定のアダプター スキーマでは、顧客の機密データを格納しないでください。</span><span class="sxs-lookup"><span data-stu-id="650b4-126">Do not store sensitive customer data in the default adapter schema.</span></span> <span data-ttu-id="650b4-127">セキュリティ上の理由には、アダプターを展開した後にのみ、ユーザー名とパスワード情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="650b4-127">For security reasons, configure user name and password information only after you deploy an adapter.</span></span> <span data-ttu-id="650b4-128">これにより、情報を取得します、エンタープライズ シングル サインオン (SSO) データベースに格納されていること。</span><span class="sxs-lookup"><span data-stu-id="650b4-128">This ensures that the information gets stored in the Enterprise Single Sign-On (SSO) database.</span></span> <span data-ttu-id="650b4-129">SSO データベースの詳細については、次を参照してください。[を使用して SSO](../core/using-sso.md)します。</span><span class="sxs-lookup"><span data-stu-id="650b4-129">For more information about the SSO database, see [Using SSO](../core/using-sso.md).</span></span>  
  
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
  
## <a name="send-port-and-receive-location-schemas"></a><span data-ttu-id="650b4-130">送信ポートと受信場所のスキーマ</span><span class="sxs-lookup"><span data-stu-id="650b4-130">Send Port and Receive Location Schemas</span></span>  
 <span data-ttu-id="650b4-131">アダプターのポートに固有のプロパティを設定するには、受信場所を変更し、ポートの構成スキーマを送信します。</span><span class="sxs-lookup"><span data-stu-id="650b4-131">To set port-specific properties for your adapter, modify the receive location and send port configuration schemas.</span></span> <span data-ttu-id="650b4-132">TransmitLocation.xsd および ReceiveLocation.xsd スキーマ ファイルは、送信ポートを構成し、それぞれの場所を受信します。</span><span class="sxs-lookup"><span data-stu-id="650b4-132">The TransmitLocation.xsd and ReceiveLocation.xsd schema files configure the send port and receive location, respectively.</span></span>  
  
 <span data-ttu-id="650b4-133">アダプター フレームワークは、スキーマの拡張機能および一般的なアダプター構成の要件をサポートするために高度な構成オプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="650b4-133">The Adapter Framework provides schema extensions and advanced configuration options to support common adapter configuration requirements.</span></span> <span data-ttu-id="650b4-134">アダプター フレームワーク スキーマの拡張機能の詳細については、次を参照してください。[アダプター フレームワーク構成スキーマの拡張機能](../core/adapter-framework-configuration-schema-extensions.md)します。</span><span class="sxs-lookup"><span data-stu-id="650b4-134">For more information about the Adapter Framework schema extensions, see [Adapter Framework Configuration Schema Extensions](../core/adapter-framework-configuration-schema-extensions.md).</span></span> <span data-ttu-id="650b4-135">カスタム ドロップダウン エディターやカスタム型コンバーターなどの高度な構成オプションの詳細については、次を参照してください。[アダプターの高度な構成コンポーネント](../core/advanced-configuration-components-for-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="650b4-135">For more information about advanced configuration options such as custom drop-down editors and custom type converters, see [Advanced Configuration Components for Adapters](../core/advanced-configuration-components-for-adapters.md).</span></span>  
  
 <span data-ttu-id="650b4-136">次のコードは、TransmitLocation.xsd ファイルから、次のプロパティ ページが生成されます。</span><span class="sxs-lookup"><span data-stu-id="650b4-136">The code that follows is from the TransmitLocation.xsd file, and produces the following property page.</span></span>  
  
 <span data-ttu-id="650b4-137">![](../core/media/ebiz-prog-custad-sp.gif "ebiz_prog_custad_sp")</span><span class="sxs-lookup"><span data-stu-id="650b4-137">![](../core/media/ebiz-prog-custad-sp.gif "ebiz_prog_custad_sp")</span></span>  
<span data-ttu-id="650b4-138">サンプル ファイル アダプターの送信ポートのプロパティ ページを示しています。</span><span class="sxs-lookup"><span data-stu-id="650b4-138">Illustrates the send port property page for the sample file adapter</span></span>  
  
 <span data-ttu-id="650b4-139">下の TransmitLocation.xsd ファイルの送信ポートの構成を含むことに注意してください、 \<baf:designer\>、 \<baf:displayname\>、および\<baf:description\>タグと同じように、。送信ハンドラーの場合と使用、 \<baf:category\>タグ。</span><span class="sxs-lookup"><span data-stu-id="650b4-139">Note in the TransmitLocation.xsd file below that the send port configuration contains the \<baf:designer\>, \<baf:displayname\>, and \<baf:description\> tags, just like the send handler, and it also uses the \<baf:category\> tag.</span></span> <span data-ttu-id="650b4-140">カテゴリ タグには、まとめてグループのプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="650b4-140">The category tag enables you to group properties together.</span></span> <span data-ttu-id="650b4-141">1 つ以上のカテゴリがある場合は、カテゴリは展開と折りたたみし、そのカテゴリのプロパティ上のヘッダーとして灰色で表示されます。</span><span class="sxs-lookup"><span data-stu-id="650b4-141">If you have more than one category, the category is expandable and collapsible and appears in gray as a header above the properties in that category.</span></span> <span data-ttu-id="650b4-142">詳細については、次を参照してください。[アダプター フレームワーク構成スキーマの拡張機能](../core/adapter-framework-configuration-schema-extensions.md)します。</span><span class="sxs-lookup"><span data-stu-id="650b4-142">For more information, see [Adapter Framework Configuration Schema Extensions](../core/adapter-framework-configuration-schema-extensions.md).</span></span>  
  
 <span data-ttu-id="650b4-143">このスキーマには、URI フィールドも含まれています。</span><span class="sxs-lookup"><span data-stu-id="650b4-143">This schema also contains a URI field.</span></span> <span data-ttu-id="650b4-144">これはすべてのフィールド情報、送信ポートのプロパティ ページの検証処理中に入力した後に表示されるページで、アダプターによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="650b4-144">This is populated on the page that appears after you enter all of the field information on the send port property page during the validation processing by the adapter.</span></span>  
  
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
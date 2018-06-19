---
title: アダプター構成スキーマ |Microsoft ドキュメント
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
ms.openlocfilehash: 89ca7d02c756fdbdf819e1a15069a95d0784d764
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966504"
---
# <a name="adapter-configuration-schemas"></a>アダプター構成スキーマ
アダプターのデザイン時構成では、さまざまな種類のスキーマを使用します。 プロパティ値の可視性とスコープに応じて、さまざまなスキーマを変更して使用します。  
  
## <a name="handler-schemas"></a>ハンドラーのスキーマ  
 ハンドラーから取得したアダプター構成は、アダプターとそのコンシューマーすべてにグローバル スコープで適用されます。 管理者は、デザイン時に、ハンドラー構成を静的に変更できます。そのためには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用してアダプターの受信ハンドラーまたは送信ハンドラーを展開し、指定したホストのプロパティを表示します。  
  
 SDK に付属するサンプル ファイル アダプターには、受信場所、送信ポート、受信ハンドラー、および送信ハンドラーの構成に使用する一連の XSD ファイルが含まれています。 カスタム アダプターが必要とする構成プロパティを受け取るよう、これらの XSD ファイルを変更します。 サンプル ファイル アダプターに含まれているファイルのうち、変更する必要があるのは、スキーマ ファイル TransmitHandler.xsd および ReceiveHandler.xsd です。 これらのファイルでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールでハンドラーの構成に使用されるプロパティ ページを制御することにより、それぞれ送信ハンドラーと受信ハンドラーを構成します。  
  
 アダプターの要件に基づいて、各エンドポイントに必要な構成プロパティの一覧を作成します。 すべての構成プロパティがグローバルである場合、変更する必要があるのは送受信ポートの構成だけです。 送信ポートまたは受信場所ごとにアダプター プロパティを設定する必要がある場合、受信場所と送信ポートの構成ファイルも変更しなければなりません。  
  
 アダプター フレームワークには、一般的なアダプター構成の要件をサポートするための、スキーマ拡張機能および詳細構成オプションが用意されています。 また、サンプル ファイル アダプターに含まれているスキーマにはない拡張機能も用意されています。 アダプター フレームワーク スキーマの拡張機能の詳細については、次を参照してください。[アダプター フレームワーク構成スキーマの拡張機能](../core/adapter-framework-configuration-schema-extensions.md)します。 カスタム ドロップダウン エディターやカスタム型コンバーターなどの高度な構成オプションの詳細については、次を参照してください。[アダプターの高度な構成コンポーネント](../core/advanced-configuration-components-for-adapters.md)です。  
  
 TransmitHandler.xsd ファイルのコードを、このトピックの最後に示します。このコードにより、次のプロパティ ページが作成されます。  
  
 ![](../core/media/ebiz-prog-custad-sh.gif "ebiz_prog_custad_sh")  
TransmitHandler.xsd ファイルによって作成される送信ハンドラー プロパティ ページ  
  
 使用に注意してください、 \<baf:designer\>、 \<baf:displayname\>、および\<baf:description\>次に示す TransmitHandler.xsd コード内のタグ。 これらは、アダプター フレームワークによって提供されているカスタム装飾であり、このようなプロパティ ページの生成を高速化します。  
  
 すべてのアダプター フレームワーク内で使用できる装飾の一覧は、次を参照してください。[アダプター フレームワーク構成スキーマの装飾タグ](../core/adapter-framework-configuration-schema-decoration-tags.md)です。  
  
 このスキーマには、要素が 1 つだけ含まれており、URI 要素は含まれていません。  
  
> [!IMPORTANT]
>  既定のアダプター スキーマに、機密性の高い顧客データを格納しない。 セキュリティ上の理由により、ユーザー名とパスワードの情報を構成するのは、アダプターの展開後にしてください。 これにより、エンタープライズ シングル サインオン (SSO) データベースに確実に情報が格納されます。 SSO データベースの詳細については、次を参照してください。[を使用して SSO](../core/using-sso.md)です。  
  
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
  
## <a name="send-port-and-receive-location-schemas"></a>送信ポートおよび受信場所のスキーマ  
 アダプターにポート固有のプロパティを設定するには、受信場所および送信ポートの構成スキーマを変更します。 スキーマ ファイル TransmitLocation.xsd および ReceiveLocation.xsd では、それぞれ送信ポートと受信場所を構成します。  
  
 アダプター フレームワークには、一般的なアダプター構成の要件をサポートするための、スキーマ拡張機能および詳細構成オプションが用意されています。 アダプター フレームワーク スキーマの拡張機能の詳細については、次を参照してください。[アダプター フレームワーク構成スキーマの拡張機能](../core/adapter-framework-configuration-schema-extensions.md)します。 カスタム ドロップダウン エディターやカスタム型コンバーターなどの高度な構成オプションの詳細については、次を参照してください。[アダプターの高度な構成コンポーネント](../core/advanced-configuration-components-for-adapters.md)です。  
  
 TransmitLocation.xsd ファイルのコードを以下に示します。このコードにより、次のプロパティ ページが作成されます。  
  
 ![](../core/media/ebiz-prog-custad-sp.gif "ebiz_prog_custad_sp")  
サンプル ファイル アダプターの送信ポート プロパティ ページを示します  
  
 送信ポートの構成が含まれている下の TransmitLocation.xsd ファイルに注意してください、 \<baf:designer\>、 \<baf:displayname\>、および\<baf:description\>とまったく同様に、タグ送信ハンドラーもパラメーターを使用して、 \<baf:category\>タグ。 このカテゴリ タグを使用すると、複数のプロパティをグループ化できます。 カテゴリが複数ある場合は、展開したり折りたたんだりできます。また、カテゴリに含まれるプロパティの上には、そのカテゴリがヘッダーとして灰色で表示されます。 詳細については、次を参照してください。[アダプター フレームワーク構成スキーマの拡張機能](../core/adapter-framework-configuration-schema-extensions.md)します。  
  
 このスキーマには URI フィールドも含まれています。 これは、送信ポート プロパティ ページのフィールド情報をすべて入力した後に表示されるページに、アダプターによる検証処理中に自動入力されます。  
  
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
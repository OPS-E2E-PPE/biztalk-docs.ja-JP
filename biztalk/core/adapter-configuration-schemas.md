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
# <a name="adapter-configuration-schemas"></a>アダプター構成スキーマ
さまざまな種類のスキーマは、アダプターのデザイン時構成で使用されます。 可視性とスコープのプロパティの値に応じて、さまざまなスキーマ変更され使用します。  
  
## <a name="handler-schemas"></a>ハンドラーのスキーマ  
 ハンドラーから取得したアダプター構成は、アダプターにグローバル スコープですべてのコンシューマーに適用されます。 使用して、管理者がデザイン時にハンドラー構成を静的に変更、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをアダプターの展開を受信または送信ハンドラーと、指定したホストのプロパティを表示します。  
  
 SDK に含まれているサンプル ファイル アダプターが、一連の構成に使用される XSD ファイルの受信場所、送信ポート、受信ハンドラー、および送信ハンドラー。 これらの XSD ファイルを変更して、カスタム アダプターの受信設定のプロパティが必要です。 変更する必要のあるサンプル ファイル アダプターに含まれているファイルは、TransmitHandler.xsd および ReceiveHandler.xsd スキーマ ファイルです。 これらのファイル送信ハンドラを構成し、受信ハンドラー、それぞれのハンドラーの構成に使用されるプロパティ ページを制御することで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
 アダプターの要件を使用して、各エンドポイントに必要な構成プロパティの一覧を作成します。 グローバルすべて、構成プロパティの場合は、変更の送信と受信ポートの構成にだけことがあります。 アダプターのプロパティは、各送信ポートまたは受信場所に対して設定する場合に、受信場所を変更し、送信ポートの構成ファイルもが必要です。  
  
 アダプター フレームワークは、スキーマの拡張機能および一般的なアダプター構成の要件をサポートするために高度な構成オプションを提供します。 サンプル ファイル アダプターに含まれているスキーマではない拡張機能も提供します。 アダプター フレームワーク スキーマの拡張機能の詳細については、次を参照してください。[アダプター フレームワーク構成スキーマの拡張機能](../core/adapter-framework-configuration-schema-extensions.md)します。 カスタム ドロップダウン エディターやカスタム型コンバーターなどの高度な構成オプションの詳細については、次を参照してください。[アダプターの高度な構成コンポーネント](../core/advanced-configuration-components-for-adapters.md)します。  
  
 このトピックの最後に、コードは、TransmitHandler.xsd ファイルからは、し、次のプロパティ ページを生成します。  
  
 ![](../core/media/ebiz-prog-custad-sh.gif "ebiz_prog_custad_sh")  
TransmitHandler.xsd ファイルによって作成されたハンドラーのプロパティ ページを送信します。  
  
 使用に注意してください、 \<baf:designer\>、 \<baf:displayname\>、および\<baf:description\>以下に示す TransmitHandler.xsd コード内のタグ。 これらは、これらのプロパティ ページの生成を速くアダプター フレームワークによって提供されるカスタムの装飾です。  
  
 アダプター フレームワーク内で使用できる文字装飾のすべての一覧は、次を参照してください。[アダプター フレームワーク構成スキーマの装飾タグ](../core/adapter-framework-configuration-schema-decoration-tags.md)します。  
  
 スキーマは 1 つだけ要素があり、URI 要素が含まれていないことに注意してください。  
  
> [!IMPORTANT]
>  既定のアダプター スキーマでは、顧客の機密データを格納しないでください。 セキュリティ上の理由には、アダプターを展開した後にのみ、ユーザー名とパスワード情報を構成します。 これにより、情報を取得します、エンタープライズ シングル サインオン (SSO) データベースに格納されていること。 SSO データベースの詳細については、次を参照してください。[を使用して SSO](../core/using-sso.md)します。  
  
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
  
## <a name="send-port-and-receive-location-schemas"></a>送信ポートと受信場所のスキーマ  
 アダプターのポートに固有のプロパティを設定するには、受信場所を変更し、ポートの構成スキーマを送信します。 TransmitLocation.xsd および ReceiveLocation.xsd スキーマ ファイルは、送信ポートを構成し、それぞれの場所を受信します。  
  
 アダプター フレームワークは、スキーマの拡張機能および一般的なアダプター構成の要件をサポートするために高度な構成オプションを提供します。 アダプター フレームワーク スキーマの拡張機能の詳細については、次を参照してください。[アダプター フレームワーク構成スキーマの拡張機能](../core/adapter-framework-configuration-schema-extensions.md)します。 カスタム ドロップダウン エディターやカスタム型コンバーターなどの高度な構成オプションの詳細については、次を参照してください。[アダプターの高度な構成コンポーネント](../core/advanced-configuration-components-for-adapters.md)します。  
  
 次のコードは、TransmitLocation.xsd ファイルから、次のプロパティ ページが生成されます。  
  
 ![](../core/media/ebiz-prog-custad-sp.gif "ebiz_prog_custad_sp")  
サンプル ファイル アダプターの送信ポートのプロパティ ページを示しています。  
  
 下の TransmitLocation.xsd ファイルの送信ポートの構成を含むことに注意してください、 \<baf:designer\>、 \<baf:displayname\>、および\<baf:description\>タグと同じように、。送信ハンドラーの場合と使用、 \<baf:category\>タグ。 カテゴリ タグには、まとめてグループのプロパティを使用します。 1 つ以上のカテゴリがある場合は、カテゴリは展開と折りたたみし、そのカテゴリのプロパティ上のヘッダーとして灰色で表示されます。 詳細については、次を参照してください。[アダプター フレームワーク構成スキーマの拡張機能](../core/adapter-framework-configuration-schema-extensions.md)します。  
  
 このスキーマには、URI フィールドも含まれています。 これはすべてのフィールド情報、送信ポートのプロパティ ページの検証処理中に入力した後に表示されるページで、アダプターによって設定されます。  
  
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
---
title: '(Azure) の手順 1: EDI プロジェクトを作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9d353129-04f0-456b-b371-b346959f5155
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51264a79480031bd334dfb7d699a3a701f2c0254
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010003"
---
# <a name="step-1-for-azure-create-the-edi-project"></a>手順 1 (Azure 用): EDI プロジェクトを作成します。
このセクションでは、Contoso が、[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)] の 2012 年 4 月リリース版を使用して EDI プロジェクトを作成します。 プロジェクトの一部として、Contoso は以下の項目を追加します。  
  
-   内部の販売注文スキーマ (**ECommerceSalesOrder.xsd**) を X12 840 EDI 販売注文スキーマに変換されます。 Contoso は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で受信した後のメッセージの処理に内部スキーマを使用します。  
  
-   変換 (**EDI840TOSALESORDER です。TRFM**) 840 販売注文スキーマを X12 に変換する、 **ECommerceSalesOrder**スキーマです。  
  
 Contoso は、[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)] で Azure BizTalk ポータルのアグリーメントを作成するときにこれらのアイテムを使用します。  
  
### <a name="to-create-edi-project"></a>EDI プロジェクトを作成するには  
  
1.  Visual Studio を開き、**ファイル**メニュー をポイント**新規**、順にクリック**プロジェクト**です。  
  
2.  **新しいプロジェクト**] ダイアログ ボックスから、**インストールされたテンプレート**[ **Service Bus**です。 プロジェクト名と、プロジェクトの場所を指定し、クリックして**OK**です。  
  
##  <a name="BKMK_CreateSchema"></a>EDI プロジェクト内のスキーマを作成するには  
  
1.  ソリューション エクスプ ローラーで、先ほど作成したプロジェクト名を右クリックし、**追加**、クリックして**新しい項目の**します。  
  
2.  **新しい項目の追加**] ダイアログ ボックスから、**インストールされたテンプレート**[**スキーマ**とスキーマの名前を指定**ECommerceSalesOrder.xsd**、クリックして**追加**です。  
  
3.  スキーマを編集して以下のように構築します。  
  
    ```  
    <?xml version="1.0" encoding="utf-16"?>  
    <xs:schema xmlns="http://ECommerceSalesOrder.Inbound" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" targetNamespace="http://ECommerceSalesOrder.Inbound" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
      <xs:element name="SalesOrder">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="CompanyCode" type="xs:string" />  
            <xs:element name="PartID" type="xs:int" />  
            <xs:element name="Quantity" type="xs:int" />  
            <xs:element name="AskPrice" type="xs:decimal" />  
            <xs:element name="RequestShipmentDate" type="xs:date" />  
            <xs:element name="Address">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="Line1" type="xs:string" />  
                  <xs:element name="Line2" type="xs:string" />  
                  <xs:element name="City" type="xs:string" />  
                  <xs:element name="State" type="xs:string" />  
                  <xs:element name="Country" type="xs:string" />  
                  <xs:element name="Zipcode" type="xs:int" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
            <xs:element name="Contact">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="Firstname" type="xs:string" />  
                  <xs:element name="Lastname" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
            <xs:element name="Comments" type="xs:string" />  
            <xs:element name="DateNow" type="xs:date" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:schema>  
    ```  
  
     スキーマの構築にはスキーマ エディターを使用することができます。 詳細については、次を参照してください。 [BizTalk エディターを使用して](../core/using-biztalk-editor.md)です。  
  
4.  スキーマを保存します。  
  
##  <a name="BKMK_CreateTrfm"></a>EDI プロジェクト内の変換を作成するには  
  
1.  ソリューション エクスプ ローラーで、先ほど作成したプロジェクト名を右クリックし、**追加**、クリックして**新しい項目の**します。  
  
2.  **新しい項目の追加**] ダイアログ ボックスから、**インストールされたテンプレート**[**マップ**とスキーマの名前を指定**Edi840ToSalesOrder.trfm**、クリックして**追加**です。  
  
3.  マップでは、送信元スキーマの選択**X12_00401_840.xsd**です。 これは、EDI 販売注文の標準 X12 スキーマです。 作成した EDI プロジェクトに既にこのスキーマが追加されている必要があります。 これには、およびその他の X12 をダウンロードすることができますからスキーマ[http://go.microsoft.com/fwlink/p/?LinkId=235057](http://go.microsoft.com/fwlink/p/?LinkId=235057)です。 スキーマの一部は、X12、 **MicrosoftEdiXSDTemplates.zip**ダウンロード場所からパッケージを使用可能です。  
  
4.  送信先スキーマの選択**ECommerceSalesOrder.xsd**です。 このスキーマは、このトピックで既に作成済みです。  
  
5.  送信元と送信先のスキーマ内の関連するノードを接続してマップを作成します。  
  
6.  マップを保存します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 4: BizTalk Server 2013 を使用するハイブリッド アプリケーションを作成します。](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)
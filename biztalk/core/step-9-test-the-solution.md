---
title: 手順 9:ソリューションのテスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df446ccc-add3-4dd3-b674-253dda385541
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94a2f21def846b2f30554fc3472c4aec075dfee7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244211"
---
# <a name="step-9-test-the-solution"></a>手順 9:ソリューションをテストします。
このトピックで、X12 840 販売注文を HTTP エンドポイントにメッセージが EDI アグリーメントの配置を送信することによって、ハイブリッド アプリケーションをテストします。 サンプル販売注文メッセージは、次のようになります。  
  
```  
ISA*00*          *00*          *ZZ*CONTOSO        *ZZ*NORTHWIND      *991221*1226*U*00401*000000025*0*T*:~  
GS*PO*THEM*US*19991221*1226*1*X*004010~  
ST*840*0002~  
BQT*00*BQT02*20120619*001*20120719~  
PER*1A*John*EM*John@contoso.com~  
N1*001~  
N2*co~  
N3*Contoso*One Contoso Way~  
N4*Redmond*WA*98052*US~  
PO1*PO101*121*01*10*AA*A1*1~  
CTT*475~  
SE*10*0002~  
GE*1*1~  
IEA*1*000000025~  
```  
  
 このメッセージの強調表示されたセグメント (で始まる行**PO1**)、注文数量が含まれています。 このメッセージでは、注文数量が*121*します。 そのため、このメッセージを送信する場合に挿入してください、 **SalesOrder**テーブル。 100 未満に数量を更新し、メッセージを再送信できますが、FILE 送信ポートで指定したファイルの場所に送信する必要があります。  
  
 このメッセージを EDI アグリーメントを送信する使用することができます、 **MessageSender**ツールに付属のサンプル[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]します。 サンプルをダウンロードすることができます[ http://go.microsoft.com/fwlink/p/?LinkId=235057](http://go.microsoft.com/fwlink/p/?LinkId=235057)します。  
  
### <a name="to-send-a-message"></a>メッセージを送信するには  
  
1.  検索、 **MessageSender**サンプル パッケージでプロジェクトをビルドします。  
  
2.  結果を使用して、 **MessageSender** (プロジェクト内の \bin\Debug フォルダー) の下のコマンドライン実行可能ファイル、デプロイされた EDI アグリーメントにメッセージを送信します。 このツールは、次の形式でコマンド ライン パラメーターを受け取ります。  
  
    ```  
    MessageSender.exe <ServiceBusNamespace> <IssuerName> <IssuerKey> <EDI agreement endpoint> <MessageFilepath> <ContentType>  
    ```  
  
     どこ  
  
    |[パラメーター名]|説明|  
    |--------------------|-----------------|  
    |ServiceBusNamespace|Service Bus 名前空間|  
    |IssuerName|指定した名前空間の発行者名|  
    |IssuerKey|指定した名前空間の発行者キー|  
    |EDI アグリーメント エンドポイント|EDI アグリーメントが展開されているエンドポイントです。 このエンドポイント URL を取得するには、受信の設定 タブから (および、トランスポート ページ内) で展開した EDI アグリーメントの[手順 2 (Azure 用)。EDI アグリーメントを作成](../core/step-2-for-azure-create-an-edi-agreement.md)です。|  
    |MessageFilePath|要求メッセージのサンプルを含むファイルへのパス。|  
    |ContentType|このチュートリアルでは、このパラメーターを設定**テキスト/プレーン**します。|  
  
     コマンド プロンプトを開き、ビルドしたソリューションに移動、 **MessageSender**プロジェクト。 注文数量が 100 を超えると、要求メッセージを送信するには、次のコマンドを実行します。  
  
    ```  
    MessageSender.exe <service bus namespace> owner <issuer key>https://<namespace>.servicebus.appfabriclabs.com/7576ff3d-a0f3-4a46-a4f6-f5be4a50616a/DemoAgreement<path to the sample message> "text/plain"  
    ```  
  
3.  SQL Server Management Studio を開きを含むデータベースへの接続、 **SalesOrder**テーブル、およびテーブルに新しいレコードが挿入されていることを確認します。 値に注意してください、 **Qty**列があります*121*します。  
  
4.  使用**MessageSender**にメッセージの注文数量の値を設定別のメッセージがこの時間を送信する*99*します。 現時点では、そのレコードは挿入されません、 **SalesOrder**テーブル。 代わりに、メッセージは、注文数量が 100 未満のメッセージを受信するために指定したファイルの場所にコピーされます。 受信したメッセージには、次のようになります。  
  
    ```  
    <ns1:SalesOrder xmlns:ns0="http://schemas.microsoft.com/BizTalk/EDI/X12/2006" xmlns:ns1="http://ECommerceSalesOrder.Inbound">  
      <CompanyCode>co</CompanyCode>  
      <PartID>1</PartID>  
      <Quantity>99</Quantity>  
      <AskPrice>10</AskPrice>  
      <RequestShipmentDate>2012-07-19</RequestShipmentDate>  
      <Address>  
        <Line1>Contoso</Line1>  
        <Line2>One Contoso Way</Line2>  
        <City>Redmond</City>  
        <State>WA</State>  
        <Country>US</Country>  
        <Zipcode>98052</Zipcode>  
      </Address>  
      <Contact>  
        <Firstname>John</Firstname>  
        <Lastname>John@contoso.com</Lastname>  
      </Contact>  
      <Comments>Order from Partnerco</Comments>  
      <DateNow>2012-06-19</DateNow>  
    </ns1:SalesOrder>  
  
    ```  
  
     値に注意してください、**数量**要素。 *99*します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 4: BizTalk Server 2013 を使用してハイブリッド アプリケーションを作成します。](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)
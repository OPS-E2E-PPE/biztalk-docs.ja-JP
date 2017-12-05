---
title: "手順 9: ソリューションのテスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df446ccc-add3-4dd3-b674-253dda385541
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89a3722d6d8e1d4b730341dfaf16d60af1686f21
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-9-test-the-solution"></a>手順 9: ソリューションをテストします。
このトピックでは、EDI アグリーメントが展開されている HTTP エンドポイントに X12 840 販売注文メッセージを送信することで、ハイブリッド アプリケーションをテストします。 販売注文メッセージのサンプルは次のようになります。  
  
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
  
 このメッセージの強調表示されたセグメント (で始まる行**PO1**)、注文数量が含まれています。 このメッセージに、注文数量が*121*です。 そのため、このメッセージを送信する場合に挿入してください、 **SalesOrder**テーブル。 数量を 100 未満に変更してメッセージを再送信することができます。その場合は FILE 送信ポートに指定したファイルの場所に送信される必要があります。  
  
 このメッセージを EDI アグリーメントを送信する際、 **MessageSender**するサンプルに付属のツール[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]です。 サンプルをダウンロードする[http://go.microsoft.com/fwlink/p/?LinkId=235057](http://go.microsoft.com/fwlink/p/?LinkId=235057)です。  
  
### <a name="to-send-a-message"></a>メッセージを送信するには  
  
1.  検索、 **MessageSender**サンプル パッケージにプロジェクトを読み込んでビルドします。  
  
2.  その結果を使用して**MessageSender**コマンドライン実行可能ファイル (プロジェクトの \bin\Debug フォルダー)、デプロイされた EDI アグリーメントにメッセージを送信します。 このツールは、次の形式のコマンド ライン パラメーターを受け付けます。  
  
    ```  
    MessageSender.exe <ServiceBusNamespace> <IssuerName> <IssuerKey> <EDI agreement endpoint> <MessageFilepath> <ContentType>  
    ```  
  
     どこ  
  
    |[パラメーター名]|Description|  
    |--------------------|-----------------|  
    |ServiceBusNamespace|Service Bus の名前空間|  
    |IssuerName|指定した名前空間の発行者名|  
    |IssuerKey|指定した名前空間の発行者キー|  
    |EDI agreement endpoint|EDI アグリーメントが展開されているエンドポイント。 受信の設定 タブから (とそのトランスポート ページ) は、このエンドポイントの URL を取得できますで展開した EDI アグリーメントの[ステップ 2 (Azure 用): EDI アグリーメントを作成する](../core/step-2-for-azure-create-an-edi-agreement.md)です。|  
    |MessageFilePath|要求メッセージのサンプルを含むファイルのパス。|  
    |ContentType|このチュートリアルでは、このパラメーターを設定**テキスト/プレーン**です。|  
  
     コマンド プロンプトを開き、ビルドしたソリューションに移動、 **MessageSender**プロジェクト。 次のコマンドを実行し、注文数が 100 を超える要求メッセージを送信します。  
  
    ```  
    MessageSender.exe <service bus namespace> owner <issuer key>https://<namespace>.servicebus.appfabriclabs.com/7576ff3d-a0f3-4a46-a4f6-f5be4a50616a/DemoAgreement<path to the sample message> "text/plain"  
    ```  
  
3.  SQL Server Management Studio を開き、含まれているデータベースへの接続、 **SalesOrder**テーブル、および、新しいレコードがテーブルに挿入されることを確認します。 値に注意してください、 **Qty**列である必要があります*121*です。  
  
4.  使用して**MessageSender**別のメッセージがこの時間、数量の値の設定を送信するメッセージの順序付けに*99*です。 現時点では、そのレコードは挿入されません、 **SalesOrder**テーブル。 代わりに、メッセージは、注文数量が 100 未満のメッセージを受信するために指定したファイルの場所にコピーされます。 受信したメッセージには、次のようになります。  
  
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
  
     値に注意してください、**数量**要素。 *99*です。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 4: BizTalk Server 2013 を使用するハイブリッド アプリケーションを作成します。](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)
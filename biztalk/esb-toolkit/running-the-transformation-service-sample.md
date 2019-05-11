---
title: 変換サービス サンプルを実行している |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 42064d32-5ec5-4219-a338-c5769969b958
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6278287e93211356c5c7440020032c798bc7d16
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394040"
---
# <a name="running-the-transformation-service-sample"></a>変換サービス サンプルを実行しています。
好きなツール、Web サービス メソッドを実行できるユーティリティを使用して変換サービス サンプルを実行することができます。 使用可能な Storm を使用するなど、 [CodePlex](http://go.microsoft.com/fwlink/?LinkId=187762) ([http://go.microsoft.com/fwlink/?LinkId=187762](http://go.microsoft.com/fwlink/?LinkId=187762))、または変換 Web サービスを呼び出す独自のテスト クライアントを作成することができます。  
  
 変換サービス サンプルの正しいインストールをテストする、.NET Web サービスの Studio を使用するには、変換の ASMX ベースの Web サービスの URL を入力、 **WSDL エンドポイント**テキスト ボックス、およびクリック、 **取得**ボタンをクリックします。 これには、図 1 に示すように、ESB 変換の Web サービスの呼び出しに使用できるクライアントのフロント エンド インターフェイスが生成されます。  
  
 ![変換サービス](../esb-toolkit/media/ch6-transformationservice.gif "Ch6 TransformationService")  
  
 **図 1**  
  
 **.NET Web サービスの Studio を使用して、変換サービス サンプルをテストするには**  
  
 変換サービス サンプルには、2 つの Microsoft BizTalk マップが含まれていて、2 つのテスト メッセージの XML ドキュメント。 TEST_CanonicalOrder_to_OrderConfirmation.xml および TEST_RetailOrder_to_CanonicalOrder.xml (\Source\Samples\TransformServices\Test\Data フォルダーにあります) という名前の XML メッセージでは、変換の Web サービスを実行できます。  
  
 サービスは CanonicalOrder.xsd と RetailOrder.xsd OrderConfirmation.xsd (、\Source\Samples\TransformServices\Source\ESB にありますスキーマを使用してメッセージを自動的に変換します。TransformServices.Schemas フォルダーの場合)、.NET Web サービスの Studio は、結果として得られる変換されたメッセージを表示します。 次の手順では、CanonicalOrder_To_OrderConfirmation マップをテストする方法を示します。  
  
 **GlobalBank.ESB.TransformServices.Maps.CanonicalOrder_To_OrderConfirmation マップをテストするには**  
  
1.  GlobalBank.ESB アプリケーションが実行されていない場合は、BizTalk 管理コンソールを使用して開始します。  
  
2.  値として TEST_CanonicalOrder_to_OrderConfirmation.xml ファイルの次の文字列表現を入力、**メッセージ**パラメーター、**入力**ツリー ビューの .NET Web サービスの Studio。 この文字列は、GlobalBank.ESB.TransformServices.Schemas.CanonicalOrder スキーマに準拠しています。  
  
    ```  
    <ns0:CanonicalOrder OrderID="OrderID_0" OrderDate="OrderDate_1"   
        Status="Status_2" xmlns:ns0=  
        "http://schemas.globalbank.esb.transformservices.com">  
        <OrderHeader><CustomerName>CustomerName_0</CustomerName>  
        <CustomerID>CustomerID_0</CustomerID><ShipToLine1>  
        ShipToLine1_0</ShipToLine1><ShipToLine2>ShipToLine2_0  
        </ShipToLine2><BillToLine1>BillToLine1_0</BillToLine1>  
        <BillToLine2>BillToLine2_0</BillToLine2><OrderTotal>OrderTotal_0  
        </OrderTotal></OrderHeader><OrderDetails><LineItem Qty="Qty_0"   
        PartNum="PartNum_1" Description="Description_2"   
        UnitPrice="UnitPrice_3" Ext="Ext_4" /></OrderDetails>  
        <B2BPartnerDetails CreditLimit="CreditLimit_0"   
        AccountBalance="AccountBalance_1"   
        LastOrderedData="LastOrderedData_2"   
        DiscountLevel="DiscountLevel_3" /></ns0:CanonicalOrder>  
    ```  
  
3.  値として、次の文字列を入力、 **mapName**パラメーター、**入力**ツリー ビューの .NET Web サービスの Studio。 これは、完全に型指定されたメッセージに対して実行する BizTalk マップの名前です。  
  
    ```  
    GlobalBank.ESB.TransformServices.Maps.CanonicalOrder_To_  
        OrderConfirmation, GlobalBank.ESB.TransformServices.Maps,   
        Version=1.0.0.0, Culture=neutral, PublicKeyToken=<insertYourPublicKeyTokenHere>  
    ```  
  
4.  をクリックして、 **Invoke** Web サービスを実行するボタン。 **出力**テスト ボックスには、結果が表示されます。
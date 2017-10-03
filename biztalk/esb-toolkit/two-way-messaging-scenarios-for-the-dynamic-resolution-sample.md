---
title: "動的解決のサンプルについては、双方向のメッセージング シナリオ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e89792f1-c725-46c4-946c-23211e2f892a
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 852b1f203b693c7783c7eb461c521f3fbe0ceffe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="two-way-messaging-scenarios-for-the-dynamic-resolution-sample"></a>動的解決のサンプルについては、双方向のメッセージング シナリオ
このトピックの双方向のメッセージング シナリオを実行する方法を示しています、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]動的解決のサンプルです。  
  
 **動的解決のサンプルの双方向のメッセージング シナリオを実行するには**  
  
1.  最初にこのサンプルを実行する前に、受信場所の URL が適切な Web サービスを指していることを確認してください。 Web サービス URL/ESB を指定します。NorthAmericanServices/CustomerOrder.asmx、DynamicResolutionReqResp_SOAP の場所が表示されます。 また、DynamicResolutionSolicitResp をという名前の動的送信ポートが存在することを確認します。  
  
    > [!NOTE]
    >  動的解決サンプルでは、動的な解決を使用してメッセージを送信し、カナダの Web サービス (http://localhost/ESB.CanadianServices/SubmitPOService.asmx) から応答を受信します。 このサンプルの静的な送信ポートが定義されていないためにです。 動的解決のコンポーネントは、解像度から、送信 URL を取得し、受信場所のアダプターのプロバイダー フレームワーク、DynamicResolutionReqResp_SOAP 内で構成されている ESBReceiveXml パイプラインによって呼び出されます。 双方向のメッセージングの例の一部では、ESBMapSend パイプラインは、解決して、Microsoft BizTalk マップを実行します。  
  
2.  GlobalBank.ESB アプリケーションが既に実行されていない場合は、BizTalk 管理コンソールを使用して、開始します。  
  
3.  実行する例を決定します。 双方向のすべてのメッセージング シナリオでは、ESB を使用します。NorthAmericanServices Web サービスにある http://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx DynamicResolutionReqResp_SOAP をという名前の受信場所を使用する BizTalk に要求メッセージを公開します。 10 の双方向メッセージングの例は、それぞれ固有のバインド ファイルで表されます。 次の表では、これらの例は、その関連付けられたバインド ファイルと説明の一覧表示します。  
  
    |SOAP 送信 (submitOrder アクション) が SOAP 受信、BRE の競合回避モジュールを使用します。|  
    |---------------------------------------------------------------------------------|  
    |GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_BRE_Bindings.xml をという名前のバインド ファイルを使用して、受信場所を設定し、送信ポートのプロパティです。|  
    |エンドポイント解決のため、受信場所で ESB ディスパッチャーを使用します。|  
  
    |SOAP 送信 (submitOrder アクション) が SOAP 受信エンドポイントおよび変換の解像度、BRE の競合回避モジュールを使用します。|  
    |----------------------------------------------------------------------------------------------------------------------------|  
    |GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_BRE_Routing_AND_ Transform_Bindings.xml をという名前のバインド ファイルを使用して、受信場所を設定し、送信ポートのプロパティです。|  
    |使用して、出力方向の送信ポートで ESB ディスパッチャー コンポーネントのパイプラインし、発信の受信場所のパイプライン、マップを動的に解決しています。|  
    |エンドポイント解決のため、受信場所で ESB ディスパッチャーを使用します。|  
  
    |SOAP 受信 SOAP 送信 (submitOrder アクション) を静的な競合回避モジュールを使用します。|  
    |------------------------------------------------------------------------------------|  
    |GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_STATIC_Bindings.xml をという名前のバインド ファイルを使用して、受信場所を設定し、送信ポートのプロパティです。|  
    |受信ポートでマップを静的に設定します。|  
    |エンドポイント解決のため、受信場所で ESB ディスパッチャーを使用します。|  
  
    |SOAP 送信 (submitOrder アクション) が SOAP 受信サーバーを使用して、UDDI リゾルバーに対して、Microsoft UDDI|  
    |--------------------------------------------------------------------------------------------------------------------|  
    |GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_UDDI_MSFTREGISTRY_ Bindings.xml をという名前のバインド ファイルを使用して、受信場所を設定し、送信ポートのプロパティです。|  
    |受信ポートでマップを静的に設定します。|  
    |エンドポイント解決のため、受信場所で ESB ディスパッチャーを使用します。|  
  
    > [!NOTE]
    >  前の例では、ターゲット UDDI サーバー上に存在する 1 つに、バインド ファイル内のサービス キーを変更する必要があります。  
  
    |SOAP 送信 (submitOrder アクション) が SOAP 受信サーバーを使用して、UDDI リゾルバーに対して、SOA ソフトウェア UDDI|  
    |-----------------------------------------------------------------------------------------------------------------------|  
    |GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_UDDI_SOAREGISTRY_ Bindings.xml をという名前のバインド ファイルを使用して、受信場所を設定し、送信ポートのプロパティです。|  
    |受信ポートでマップを静的に設定します。|  
    |エンドポイント解決のため、受信場所で ESB ディスパッチャーを使用します。|  
  
    |SOAP 受信 SOAP 送信 (submitOrder アクション) を XPATH の競合回避モジュールを使用します。|  
    |-----------------------------------------------------------------------------------|  
    |GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_XPATH_Bindings.xml をという名前のバインド ファイルを使用して、受信場所を設定し、送信ポートのプロパティです。|  
    |受信ポートでマップを静的に設定します。|  
    |エンドポイント解決のため、受信場所で ESB ディスパッチャーを使用します。|  
    |メッセージには、エンドポイント構成の ID が含まれています。 = http://localhost/ESB.CanadianServices/SubmitPOService.asmx および customerName http://globalbank.esb.dynamicresolution.com/canadianservices/を = です。|  
  
    |SOAP 送信 (submitPurchase アクション) が SOAP 受信、BRE の競合回避モジュールのエンドポイントと変換の解決策を使用します。|  
    |---------------------------------------------------------------------------------------------------------------------------|  
    |GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitPurchaseOrder_BRE_Routing_ AND_Transform_Bindings.xml をという名前のバインド ファイルを使用して、受信場所を設定し、送信ポートのプロパティです。|  
    |使用して、出力方向の送信ポートで ESB ディスパッチャー コンポーネントのパイプラインし、発信の受信場所のパイプライン、マップを動的に解決しています。|  
    |エンドポイント解決のため、受信場所で ESB ディスパッチャーを使用します。|  
    |BRE の競合回避モジュールの変更、**アクション**から**submitOrder**に**submitPurchase**です。|  
  
    |SOAP 受信 SOAP 送信 (submitPurchase アクション) を静的な競合回避モジュールを使用します。|  
    |---------------------------------------------------------------------------------------|  
    |GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitPurchaseOrder_STATIC_ Bindings.xml をという名前のバインド ファイルを使用して、受信場所を設定し、送信ポートのプロパティです。|  
    |受信ポートでマップを静的に設定します。|  
    |エンドポイント解決のため、受信場所で ESB ディスパッチャーを使用します。|  
    |静的な競合回避モジュールの変更、**アクション**から**submitOrder**に**submitPurchase**です。|  
  
4.  GlobalBank.ESB アプリケーションを実行するメッセージの例については、バインド ファイルをインポートします。  
  
5.  Microsoft InfoPath、.NET の Web サービス Studio またはその他の適切なメカニズムを使用して、NorthAmerican Web サービスを呼び出します。 操作に必要なすべてのパラメーターを含めることを確認します。  
  
6.  返されたメッセージ応答を探します。 指定した場合、 **submitOrder**アクションのテキスト"Submit Order"の値が前に、 **ID**フィールドに返されたメッセージ。 指定した場合、 **submitPurchase**操作の「送信購買」テキストの値が前に、 **ID**フィールドに返されたメッセージ。  
  
 このサンプルでの ESB ディスパッチャーと ESB ディスパッチャーの逆アセンブラー パイプライン コンポーネントの使用方法を理解するのを参照してください。 [「動的解決サンプルの動作](../esb-toolkit/how-the-dynamic-resolution-sample-works.md)です。
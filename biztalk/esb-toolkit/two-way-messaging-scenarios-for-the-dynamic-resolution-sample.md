---
title: 動的解決サンプルの双方向のメッセージング シナリオ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e89792f1-c725-46c4-946c-23211e2f892a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6787edc22c06d6935518be9d223f5968a595d6cf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997019"
---
# <a name="two-way-messaging-scenarios-for-the-dynamic-resolution-sample"></a>動的解決サンプルの双方向のメッセージング シナリオ
このトピックでは、双方向のメッセージング シナリオを実行する方法、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]動的解決サンプル。  

 **動的解決サンプルの双方向メッセージング シナリオを実行するには**  

1. 最初にこのサンプルを実行する前に、受信場所の URL が適切な Web サービスを指していることを確認してください。 Web サービス URL/ESB を指定します。NorthAmericanServices/CustomerOrder.asmx、DynamicResolutionReqResp_SOAP の場所が表示されます。 また、DynamicResolutionSolicitResp をという名前の動的送信ポートが存在することを確認します。  

   > [!NOTE]
   >  動的解決サンプルでは、動的解決を使用して、メッセージを送信し、カナダの Web サービスから応答を受信 (http://localhost/ESB.CanadianServices/SubmitPOService.asmx)します。 このサンプルの静的な送信ポートが定義されていないためにです。 動的解決のコンポーネントは、解像度から、送信 URL を取得し、受信場所のアダプターのプロバイダー フレームワーク、DynamicResolutionReqResp_SOAP 内で構成されている ESBReceiveXml パイプラインによって呼び出されます。 一部の例は、双方向メッセージング、ESBMapSend パイプラインは解決し、Microsoft BizTalk マップを実行します。  

2. GlobalBank.ESB アプリケーションが実行されていない場合は、BizTalk 管理コンソールを使用して開始します。  

3. 実行する例を決定します。 すべての双方向メッセージング シナリオでは、ESB を使用します。NorthAmericanServices Web サービスがあるhttp://localhost/ESB.NorthAmericanServices/CustomerOrder.asmxDynamicResolutionReqResp_SOAP という名前の受信場所を使用して、BizTalk に要求メッセージを発行します。 10 の双方向メッセージングの例は、それぞれの一意のバインド ファイルで表されます。 次の表は、その関連付けられたバインド ファイルの説明と、これらの例を一覧表示します。  

   |SOAP 送信 (submitOrder アクション) が SOAP 受信 BRE リゾルバーの使用|  
   |---------------------------------------------------------------------------------|  
   |受信場所を設定し、送信ポートのプロパティを GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_BRE_Bindings.xml をという名前のバインド ファイルを使用します。|  
   |ESB ディスパッチャーを受信場所でエンドポイントの解決を使用します。|  

   |SOAP 送信 (submitOrder アクション) が SOAP 受信エンドポイントと変換の解像度、BRE の競合回避モジュールを使用します。|  
   |----------------------------------------------------------------------------------------------------------------------------|  
   |受信場所を設定し、送信ポートのプロパティを GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_BRE_Routing_AND_ Transform_Bindings.xml をという名前のバインド ファイルを使用します。|  
   |使用して、送信の送信ポートで ESB ディスパッチャー コンポーネントのパイプラインし、送信の受信場所のパイプライン、マップを動的に解決しています。|  
   |ESB ディスパッチャーを受信場所でエンドポイントの解決を使用します。|  

   |SOAP の受信 SOAP 送信 (submitOrder アクション) を静的な競合回避モジュールを使用します。|  
   |------------------------------------------------------------------------------------|  
   |受信場所を設定し、送信ポートのプロパティを GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_STATIC_Bindings.xml をという名前のバインド ファイルを使用します。|  
   |受信ポートでマップを静的に設定します。|  
   |ESB ディスパッチャーを受信場所でエンドポイントの解決を使用します。|  

   |SOAP 送信 (submitOrder アクション) が SOAP 受信サーバーを使用して、UDDI リゾルバーに対して、Microsoft UDDI|  
   |--------------------------------------------------------------------------------------------------------------------|  
   |受信場所を設定し、送信ポートのプロパティを GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_UDDI_MSFTREGISTRY_ Bindings.xml をという名前のバインド ファイルを使用します。|  
   |受信ポートでマップを静的に設定します。|  
   |ESB ディスパッチャーを受信場所でエンドポイントの解決を使用します。|  

   > [!NOTE]
   >  前の例では、ターゲットの UDDI サーバー上に存在する 1 つに、バインド ファイルにサービス キーを変更する必要があります。  

   |SOAP 送信 (submitOrder アクション) が SOAP 受信サーバーを使用して、UDDI リゾルバーに対して、SOA ソフトウェア UDDI|  
   |-----------------------------------------------------------------------------------------------------------------------|  
   |受信場所を設定し、送信ポートのプロパティを GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_UDDI_SOAREGISTRY_ Bindings.xml をという名前のバインド ファイルを使用します。|  
   |受信ポートでマップを静的に設定します。|  
   |ESB ディスパッチャーを受信場所でエンドポイントの解決を使用します。|  

   |                                                            SOAP の受信 SOAP 送信 (submitOrder アクション) を XPATH の競合回避モジュールを使用します。                                                            |
   |---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                 受信場所を設定し、送信ポートのプロパティを GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_XPATH_Bindings.xml をという名前のバインド ファイルを使用します。                  |
   |                                                                           受信ポートでマップを静的に設定します。                                                                           |
   |                                                             ESB ディスパッチャーを受信場所でエンドポイントの解決を使用します。                                                              |
   | メッセージには、エンドポイントの構成の ID が含まれています。 =<http://localhost/ESB.CanadianServices/SubmitPOService.asmx> ] と [customerName =<http://globalbank.esb.dynamicresolution.com/canadianservices/>します。 |

   |SOAP 送信 (submitPurchase アクション) を SOAP の受信、BRE の競合回避モジュールのエンドポイントと変換の解決策を使用します。|  
   |---------------------------------------------------------------------------------------------------------------------------|  
   |受信場所を設定し、送信ポートのプロパティを GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitPurchaseOrder_BRE_Routing_ AND_Transform_Bindings.xml をという名前のバインド ファイルを使用します。|  
   |使用して、送信の送信ポートで ESB ディスパッチャー コンポーネントのパイプラインし、送信の受信場所のパイプライン、マップを動的に解決しています。|  
   |ESB ディスパッチャーを受信場所でエンドポイントの解決を使用します。|  
   |BRE の競合回避モジュールの変更、**アクション**から**submitOrder**に**submitPurchase**します。|  

   |                                              SOAP の受信 SOAP 送信 (submitPurchase アクション) を静的な競合回避モジュールを使用します。                                               |
   |----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | 受信場所を設定し、送信ポートのプロパティを GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitPurchaseOrder_STATIC_ Bindings.xml をという名前のバインド ファイルを使用します。 |
   |                                                               受信ポートでマップを静的に設定します。                                                                |
   |                                                  ESB ディスパッチャーを受信場所でエンドポイントの解決を使用します。                                                  |
   |                                           静的な競合回避モジュールの変更、**アクション**から**submitOrder**に**submitPurchase**します。                                           |


4. メッセージングに GlobalBank.ESB アプリケーションを実行する例については、バインド ファイルをインポートします。  

5. Microsoft InfoPath、.NET Web サービスの Studio またはその他の適切なメカニズムを使用して NorthAmerican Web サービスを呼び出します。 操作に必要なすべてのパラメーターを含めることを確認します。  

6. 返されたメッセージの応答を参照してください。 指定した場合、 **submitOrder**アクションのテキスト"Submit Order"の値が前に、 **ID**フィールドに返されたメッセージ。 指定した場合、 **submitPurchase**アクションの [購入の送信] のテキストの値が前に、 **ID**フィールドに返されたメッセージ。  

   ESB ディスパッチャーと ESB ディスパッチャー逆アセンブラー パイプライン コンポーネントのサンプルの使用については、次を参照してください。 [、動的解決サンプルのしくみ](../esb-toolkit/how-the-dynamic-resolution-sample-works.md)します。
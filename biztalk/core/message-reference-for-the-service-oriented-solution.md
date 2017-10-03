---
title: "メッセージの参照をサービス指向ソリューション |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: service solution tutorial, message reference
ms.assetid: 47b56d83-799d-444d-b7ef-c2db56a0e470
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d970b34874d893b9c110f360abc27336c4cba80d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-reference-for-the-service-oriented-solution"></a>サービス指向ソリューションのメッセージ リファレンス
このセクションでは、ソリューションの各オーケストレーションで使用されるメッセージおよびメッセージの種類の一覧を示します。 メッセージおよびメッセージの種類は、アプリケーションのバージョンごとに記載されています。  
  
## <a name="adapter-version"></a>アダプタ バージョン  
 表内の\<SolutionPrefix > microsoft.samples.biztalk.woodgrovebank テーブルの書式を設定してヘルプを表していますが置き換えられます。  
  
 以下にオーケストレーション、メッセージ、および種類を示します。  
  
|オーケストレーション|メッセージ|メッセージの種類|  
|-------------------|-------------|------------------|  
|CustomerService.odx|LastPaymentRequest|\<SolutionPrefix >。Schemas.LastPaymentRequest|  
|CustomerService.odx|LastPaymentResponse|\<SolutionPrefix >。Schemas.LastPaymentResponse|  
|CustomerService.odx|PendingTransactionsWSRequest|\<SolutionPrefix >。Orchestrations.Adapter.PendTransWS.PendingTransactionsWebService_ です。GetPendingTransactions_request|  
|CustomerService.odx|PendingTransactionsWSResponse|\<SolutionPrefix >。Orchestrations.Adapter.PendTransWS.PendingTransactionsWebService_ です。GetPendingTransactions_response|  
|CustomerService.odx|CreditLimitRequest|\<SolutionPrefix >。Schemas.BAPI_BANKACCT_GET_DETAIL です。BAPI_BANKACCT_GET_DETAIL_Request|  
|CustomerService.odx|CreditLimitResponse|\<SolutionPrefix >。Schemas.BAPI_BANKACCT_GET_DETAIL です。BAPI_BANKACCT_GET_DETAIL_Response|  
|CustomerService.odx|PendingTransactionsRequest|\<SolutionPrefix >。Schemas.PendingTransactionsRequest|  
|CustomerService.odx|PendingTransactionsResponse|\<SolutionPrefix >。Schemas.PendingTransactionsResponse|  
|CustomerService.odx|StubSAPWebServiceRequest|\<SolutionPrefix >。Orchestrations.Adapter.StubSAPWS.StubSAPWS_ です。GetAccountDetails_request|  
|CustomerService.odx|StubSAPWebServiceResponse|\<SolutionPrefix >。Orchestrations.Adapter.StubSAPWS.StubSAPWS_ です。GetAccountDetails_response|  
|CustomerService.odx|CustomerServiceRequest|\<SolutionPrefix >。Schemas.CustomerServiceRequest|  
|CustomerService.odx|CustomerServiceResponse|\<SolutionPrefix >。Schemas.CustomerServiceResponse|  
|CustomerServiceNativeRequestResponse.odx|CustomerServiceRequest|\<SolutionPrefix >。Schemas.CustomerServiceRequest|  
|CustomerServiceNativeRequestResponse.odx|CustomerServiceResponse|\<SolutionPrefix >。Schemas.CustomerServiceResponse|  
|CustomerServiceReceiveSend.odx|CustomerServiceResponse2|\<SolutionPrefix >。Schemas.CustomerServiceResponse|  
|CustomerServiceReceiveSend.odx|CustomerServiceResponse|\<SolutionPrefix >。Schemas.CustomerServiceResponse|  
|CustomerServiceReceiveSend.odx|CustomerServiceRequest|\<SolutionPrefix >。Schemas.CustomerServiceRequest|  
  
## <a name="adapter-with-sap-version"></a>SAP バージョンのアダプタ  
 表内の\<SolutionPrefix > microsoft.samples.biztalk.woodgrovebank テーブルの書式を設定してヘルプを表していますが置き換えられます。  
  
 以下にオーケストレーション、メッセージ、および種類を示します。  
  
|オーケストレーション|メッセージ|メッセージの種類|  
|-------------------|-------------|------------------|  
|CustomerService.odx|LastPaymentRequest|\<SolutionPrefix >。Schemas.LastPaymentRequest|  
|CustomerService.odx|LastPaymentResponse|\<SolutionPrefix >。Schemas.LastPaymentResponse|  
|CustomerService.odx|PendingTransactionsWSRequest|\<SolutionPrefix >。Orchestrations.Adapter.PendTransWS.PendingTransactionsWebService_ です。GetPendingTransactions_request|  
|CustomerService.odx|PendingTransactionsWSResponse|\<SolutionPrefix >。Orchestrations.Adapter.PendTransWS.PendingTransactionsWebService_ です。GetPendingTransactions_response|  
|CustomerService.odx|CreditLimitRequest|\<SolutionPrefix >。Schemas.BAPI_BANKACCT_GET_DETAIL です。BAPI_BANKACCT_GET_DETAIL_Request|  
|CustomerService.odx|CreditLimitResponse|\<SolutionPrefix >。Schemas.BAPI_BANKACCT_GET_DETAIL です。BAPI_BANKACCT_GET_DETAIL_Response|  
|CustomerService.odx|PendingTransactionsRequest|\<SolutionPrefix >。Schemas.PendingTransactionsRequest|  
|CustomerService.odx|PendingTransactionsResponse|\<SolutionPrefix >。Schemas.PendingTransactionsResponse|  
|CustomerService.odx|CustomerServiceRequest|\<SolutionPrefix >。Schemas.CustomerServiceRequest|  
|CustomerService.odx|CustomerServiceResponse|\<SolutionPrefix >。Schemas.CustomerServiceResponse|  
  
## <a name="inline-version"></a>インライン バージョン  
 表内の\<SolutionPrefix > microsoft.samples.biztalk.woodgrovebank テーブルの書式設定のヘルプを表していますが置き換えられます。  
  
 以下にオーケストレーション、メッセージ、および種類を示します。  
  
|オーケストレーション|メッセージ|メッセージの種類|  
|--------------------|-------------|------------------|  
|CustomerService.odx|LastPaymentRequest|\<SolutionPrefix >。Schemas.LastPaymentRequest|  
|CustomerService.odx|LastPaymentResponse|\<SolutionPrefix >。Schemas.LastPaymentResponse|  
|CustomerService.odx|PendingTransactionsWSRequest|\<SolutionPrefix >。Schemas.PendingTransactionsRequest|  
|CustomerService.odx|PendingTransactionsWSResponse|\<SolutionPrefix >。Schemas.PendingTransactionsResponse|  
|CustomerService.odx|CreditLimitRequest|\<SolutionPrefix >。Schemas.BAPI_BANKACCT_GET_DETAIL です。BAPI_BANKACCT_GET_DETAIL_Request|  
|CustomerService.odx|CreditLimitResponse|\<SolutionPrefix >。Schemas.BAPI_BANKACCT_GET_DETAIL です。BAPI_BANKACCT_GET_DETAIL_Response|  
|CustomerService.odx|LastPaymentRequestAfterSendPipeline|System.Xml.XmlDocument|  
|CustomerService.odx|LastPaymentResponseBeforeReceivePipeline|System.Xml.XmlDocument|  
|CustomerService.odx|CustomerServiceRequest|\<SolutionPrefix >。Schemas.CustomerServiceRequest|  
|CustomerService.odx|CustomerServiceResponse|\<SolutionPrefix >。Schemas.CustomerServiceResponse|  
|CustomerServiceNativeRequestResponse.odx|CustomerServiceRequest|\<SolutionPrefix >。Schemas.CustomerServiceRequest|  
|CustomerServiceNativeRequestResponse.odx|CustomerServiceResponse|\<SolutionPrefix >。Schemas.CustomerServiceResponse|  
|CustomerServiceReceiveSend.odx|CustomerServiceResponse2|\<SolutionPrefix >。Schemas.CustomerServiceResponse|  
|CustomerServiceReceiveSend.odx|CustomerServiceResponse|\<SolutionPrefix >。Schemas.CustomerServiceResponse|  
|CustomerServiceReceiveSend.odx|CustomerServiceRequest|\<SolutionPrefix >。Schemas.CustomerServiceRequest|  
  
## <a name="stub-version"></a>スタブ バージョン  
 表内の\<SolutionPrefix > microsoft.samples.biztalk.woodgrovebank テーブルの書式設定のヘルプを表していますが置き換えられます。  
  
 以下にオーケストレーション、メッセージ、および種類を示します。  
  
|オーケストレーション|メッセージ|メッセージの種類|  
|-------------------|-------------|------------------|  
|CustomerService.odx|LastPaymentRequest|\<SolutionPrefix >。Schemas.LastPaymentRequest|  
|CustomerService.odx|LastPaymentResponse|\<SolutionPrefix >。Schemas.LastPaymentResponse|  
|CustomerService.odx|PendingTransactionsWSRequest|\<SolutionPrefix >。Orchestrations.Stubbed.StubPendTransWS.StubPendingTransactionsWebService_ です。GetPendingTransactions_request|  
|CustomerService.odx|PendingTransactionsWSResponse|\<SolutionPrefix >。Orchestrations.Stubbed.StubPendTransWS.StubPendingTransactionsWebService_ です。GetPendingTransactions_response|  
|CustomerService.odx|CreditLimitRequest|\<SolutionPrefix >。Schemas.BAPI_BANKACCT_GET_DETAIL です。BAPI_BANKACCT_GET_DETAIL_Request|  
|CustomerService.odx|CreditLimitResponse|\<SolutionPrefix >。Schemas.BAPI_BANKACCT_GET_DETAIL です。BAPI_BANKACCT_GET_DETAIL_Response|  
|CustomerService.odx|PendingTransactionsRequest|\<SolutionPrefix >。Schemas.PendingTransactionsRequest|  
|CustomerService.odx|PendingTransactionsResponse|\<SolutionPrefix >。Schemas.PendingTransactionsResponse|  
|CustomerService.odx|PaymentTrackerWSRequest|\<SolutionPrefix >。Orchestrations.Stubbed.StubPmntTrckWS.StubPaymentTrackerWebService_ です。GetLastPayments_request|  
|CustomerService.odx|PaymentTrackerWSResponse|\<SolutionPrefix >。Orchestrations.Stubbed.StubPmntTrckWS.StubPaymentTrackerWebService_ です。GetLastPayments_response|  
|CustomerService.odx|StubSAPWSRequest|\<SolutionPrefix >。Orchestrations.Stubbed.StubSAPWS.StubSAPWS_ です。GetAccountDetails_request|  
|CustomerService.odx|StubSAPWSResponse|\<SolutionPrefix >。Orchestrations.Stubbed.StubSAPWS.StubSAPWS_ です。GetAccountDetails_response|  
|CustomerService.odx|CustomerServiceRequest|\<SolutionPrefix >。Schemas.CustomerServiceRequest|  
|CustomerService.odx|CustomerServiceResponse|\<SolutionPrefix >。Schemas.CustomerServiceResponse|  
|CustomerServiceNativeRequestResponse.odx|CustomerServiceRequest|\<SolutionPrefix >。Schemas.CustomerServiceRequest|  
|CustomerServiceNativeRequestResponse.odx|CustomerServiceResponse|\<SolutionPrefix >。Schemas.CustomerServiceResponse|  
  
## <a name="see-also"></a>参照  
 [サービス指向ソリューション リファレンス](../core/service-oriented-solution-reference.md)
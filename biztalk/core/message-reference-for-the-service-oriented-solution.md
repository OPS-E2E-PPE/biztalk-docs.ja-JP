---
title: メッセージの参照をサービス指向ソリューション |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solution tutorial, message reference
ms.assetid: 47b56d83-799d-444d-b7ef-c2db56a0e470
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2415fd7e48c3936520d7669a80a357094266c56
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974792"
---
# <a name="message-reference-for-the-service-oriented-solution"></a>サービス指向ソリューションのメッセージ リファレンス
このセクションでは、ソリューションの各オーケストレーションで使用されるメッセージおよびメッセージの種類の一覧を示します。 メッセージおよびメッセージの種類は、アプリケーションのバージョンごとに記載されています。  
  
## <a name="adapter-version"></a>アダプタ バージョン  
 表内の\<SolutionPrefix\> microsoft.samples.biztalk.woodgrovebank テーブルの書式を設定してヘルプを表していますが置き換えられます。  
  
 以下にオーケストレーション、メッセージ、および種類を示します。  
  
|オーケストレーション|メッセージ|メッセージの種類|  
|-------------------|-------------|------------------|  
|CustomerService.odx|LastPaymentRequest|\<SolutionPrefix\>です。Schemas.LastPaymentRequest|  
|CustomerService.odx|LastPaymentResponse|\<SolutionPrefix\>です。Schemas.LastPaymentResponse|  
|CustomerService.odx|PendingTransactionsWSRequest|\<SolutionPrefix\>です。Orchestrations.Adapter.PendTransWS.PendingTransactionsWebService_ です。GetPendingTransactions_request|  
|CustomerService.odx|PendingTransactionsWSResponse|\<SolutionPrefix\>です。Orchestrations.Adapter.PendTransWS.PendingTransactionsWebService_ です。GetPendingTransactions_response|  
|CustomerService.odx|CreditLimitRequest|\<SolutionPrefix\>です。Schemas.BAPI_BANKACCT_GET_DETAIL です。BAPI_BANKACCT_GET_DETAIL_Request|  
|CustomerService.odx|CreditLimitResponse|\<SolutionPrefix\>です。Schemas.BAPI_BANKACCT_GET_DETAIL です。BAPI_BANKACCT_GET_DETAIL_Response|  
|CustomerService.odx|PendingTransactionsRequest|\<SolutionPrefix\>です。Schemas.PendingTransactionsRequest|  
|CustomerService.odx|PendingTransactionsResponse|\<SolutionPrefix\>です。Schemas.PendingTransactionsResponse|  
|CustomerService.odx|StubSAPWebServiceRequest|\<SolutionPrefix\>です。Orchestrations.Adapter.StubSAPWS.StubSAPWS_ です。GetAccountDetails_request|  
|CustomerService.odx|StubSAPWebServiceResponse|\<SolutionPrefix\>です。Orchestrations.Adapter.StubSAPWS.StubSAPWS_ です。GetAccountDetails_response|  
|CustomerService.odx|CustomerServiceRequest|\<SolutionPrefix\>です。Schemas.CustomerServiceRequest|  
|CustomerService.odx|CustomerServiceResponse|\<SolutionPrefix\>です。Schemas.CustomerServiceResponse|  
|CustomerServiceNativeRequestResponse.odx|CustomerServiceRequest|\<SolutionPrefix\>です。Schemas.CustomerServiceRequest|  
|CustomerServiceNativeRequestResponse.odx|CustomerServiceResponse|\<SolutionPrefix\>です。Schemas.CustomerServiceResponse|  
|CustomerServiceReceiveSend.odx|CustomerServiceResponse2|\<SolutionPrefix\>です。Schemas.CustomerServiceResponse|  
|CustomerServiceReceiveSend.odx|CustomerServiceResponse|\<SolutionPrefix\>です。Schemas.CustomerServiceResponse|  
|CustomerServiceReceiveSend.odx|CustomerServiceRequest|\<SolutionPrefix\>です。Schemas.CustomerServiceRequest|  
  
## <a name="adapter-with-sap-version"></a>SAP バージョンのアダプタ  
 表内の\<SolutionPrefix\> microsoft.samples.biztalk.woodgrovebank テーブルの書式を設定してヘルプを表していますが置き換えられます。  
  
 以下にオーケストレーション、メッセージ、および種類を示します。  
  
|オーケストレーション|メッセージ|メッセージの種類|  
|-------------------|-------------|------------------|  
|CustomerService.odx|LastPaymentRequest|\<SolutionPrefix\>です。Schemas.LastPaymentRequest|  
|CustomerService.odx|LastPaymentResponse|\<SolutionPrefix\>です。Schemas.LastPaymentResponse|  
|CustomerService.odx|PendingTransactionsWSRequest|\<SolutionPrefix\>です。Orchestrations.Adapter.PendTransWS.PendingTransactionsWebService_ です。GetPendingTransactions_request|  
|CustomerService.odx|PendingTransactionsWSResponse|\<SolutionPrefix\>です。Orchestrations.Adapter.PendTransWS.PendingTransactionsWebService_ です。GetPendingTransactions_response|  
|CustomerService.odx|CreditLimitRequest|\<SolutionPrefix\>です。Schemas.BAPI_BANKACCT_GET_DETAIL です。BAPI_BANKACCT_GET_DETAIL_Request|  
|CustomerService.odx|CreditLimitResponse|\<SolutionPrefix\>です。Schemas.BAPI_BANKACCT_GET_DETAIL です。BAPI_BANKACCT_GET_DETAIL_Response|  
|CustomerService.odx|PendingTransactionsRequest|\<SolutionPrefix\>です。Schemas.PendingTransactionsRequest|  
|CustomerService.odx|PendingTransactionsResponse|\<SolutionPrefix\>です。Schemas.PendingTransactionsResponse|  
|CustomerService.odx|CustomerServiceRequest|\<SolutionPrefix\>です。Schemas.CustomerServiceRequest|  
|CustomerService.odx|CustomerServiceResponse|\<SolutionPrefix\>です。Schemas.CustomerServiceResponse|  
  
## <a name="inline-version"></a>インライン バージョン  
 表内の\<SolutionPrefix\> microsoft.samples.biztalk.woodgrovebank テーブルの書式設定のヘルプを表していますが置き換えられます。  
  
 以下にオーケストレーション、メッセージ、および種類を示します。  
  
|オーケストレーション|メッセージ|メッセージの種類|  
|--------------------|-------------|------------------|  
|CustomerService.odx|LastPaymentRequest|\<SolutionPrefix\>です。Schemas.LastPaymentRequest|  
|CustomerService.odx|LastPaymentResponse|\<SolutionPrefix\>です。Schemas.LastPaymentResponse|  
|CustomerService.odx|PendingTransactionsWSRequest|\<SolutionPrefix\>です。Schemas.PendingTransactionsRequest|  
|CustomerService.odx|PendingTransactionsWSResponse|\<SolutionPrefix\>です。Schemas.PendingTransactionsResponse|  
|CustomerService.odx|CreditLimitRequest|\<SolutionPrefix\>です。Schemas.BAPI_BANKACCT_GET_DETAIL です。BAPI_BANKACCT_GET_DETAIL_Request|  
|CustomerService.odx|CreditLimitResponse|\<SolutionPrefix\>です。Schemas.BAPI_BANKACCT_GET_DETAIL です。BAPI_BANKACCT_GET_DETAIL_Response|  
|CustomerService.odx|LastPaymentRequestAfterSendPipeline|System.Xml.XmlDocument|  
|CustomerService.odx|LastPaymentResponseBeforeReceivePipeline|System.Xml.XmlDocument|  
|CustomerService.odx|CustomerServiceRequest|\<SolutionPrefix\>です。Schemas.CustomerServiceRequest|  
|CustomerService.odx|CustomerServiceResponse|\<SolutionPrefix\>です。Schemas.CustomerServiceResponse|  
|CustomerServiceNativeRequestResponse.odx|CustomerServiceRequest|\<SolutionPrefix\>です。Schemas.CustomerServiceRequest|  
|CustomerServiceNativeRequestResponse.odx|CustomerServiceResponse|\<SolutionPrefix\>です。Schemas.CustomerServiceResponse|  
|CustomerServiceReceiveSend.odx|CustomerServiceResponse2|\<SolutionPrefix\>です。Schemas.CustomerServiceResponse|  
|CustomerServiceReceiveSend.odx|CustomerServiceResponse|\<SolutionPrefix\>です。Schemas.CustomerServiceResponse|  
|CustomerServiceReceiveSend.odx|CustomerServiceRequest|\<SolutionPrefix\>です。Schemas.CustomerServiceRequest|  
  
## <a name="stub-version"></a>スタブ バージョン  
 表内の\<SolutionPrefix\> microsoft.samples.biztalk.woodgrovebank テーブルの書式設定のヘルプを表していますが置き換えられます。  
  
 以下にオーケストレーション、メッセージ、および種類を示します。  
  
|オーケストレーション|メッセージ|メッセージの種類|  
|-------------------|-------------|------------------|  
|CustomerService.odx|LastPaymentRequest|\<SolutionPrefix\>です。Schemas.LastPaymentRequest|  
|CustomerService.odx|LastPaymentResponse|\<SolutionPrefix\>です。Schemas.LastPaymentResponse|  
|CustomerService.odx|PendingTransactionsWSRequest|\<SolutionPrefix\>です。Orchestrations.Stubbed.StubPendTransWS.StubPendingTransactionsWebService_ です。GetPendingTransactions_request|  
|CustomerService.odx|PendingTransactionsWSResponse|\<SolutionPrefix\>です。Orchestrations.Stubbed.StubPendTransWS.StubPendingTransactionsWebService_ です。GetPendingTransactions_response|  
|CustomerService.odx|CreditLimitRequest|\<SolutionPrefix\>です。Schemas.BAPI_BANKACCT_GET_DETAIL です。BAPI_BANKACCT_GET_DETAIL_Request|  
|CustomerService.odx|CreditLimitResponse|\<SolutionPrefix\>です。Schemas.BAPI_BANKACCT_GET_DETAIL です。BAPI_BANKACCT_GET_DETAIL_Response|  
|CustomerService.odx|PendingTransactionsRequest|\<SolutionPrefix\>です。Schemas.PendingTransactionsRequest|  
|CustomerService.odx|PendingTransactionsResponse|\<SolutionPrefix\>です。Schemas.PendingTransactionsResponse|  
|CustomerService.odx|PaymentTrackerWSRequest|\<SolutionPrefix\>です。Orchestrations.Stubbed.StubPmntTrckWS.StubPaymentTrackerWebService_ です。GetLastPayments_request|  
|CustomerService.odx|PaymentTrackerWSResponse|\<SolutionPrefix\>です。Orchestrations.Stubbed.StubPmntTrckWS.StubPaymentTrackerWebService_ です。GetLastPayments_response|  
|CustomerService.odx|StubSAPWSRequest|\<SolutionPrefix\>です。Orchestrations.Stubbed.StubSAPWS.StubSAPWS_ です。GetAccountDetails_request|  
|CustomerService.odx|StubSAPWSResponse|\<SolutionPrefix\>です。Orchestrations.Stubbed.StubSAPWS.StubSAPWS_ です。GetAccountDetails_response|  
|CustomerService.odx|CustomerServiceRequest|\<SolutionPrefix\>です。Schemas.CustomerServiceRequest|  
|CustomerService.odx|CustomerServiceResponse|\<SolutionPrefix\>です。Schemas.CustomerServiceResponse|  
|CustomerServiceNativeRequestResponse.odx|CustomerServiceRequest|\<SolutionPrefix\>です。Schemas.CustomerServiceRequest|  
|CustomerServiceNativeRequestResponse.odx|CustomerServiceResponse|\<SolutionPrefix\>です。Schemas.CustomerServiceResponse|  
  
## <a name="see-also"></a>参照  
 [サービス指向ソリューション リファレンス](../core/service-oriented-solution-reference.md)
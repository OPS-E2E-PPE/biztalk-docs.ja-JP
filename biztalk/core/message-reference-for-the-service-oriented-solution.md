---
title: メッセージの参照をサービス指向ソリューション |Microsoft Docs
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
ms.openlocfilehash: 79467e6e3eec6e635071c2494c5463a7e4692554
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394568"
---
# <a name="message-reference-for-the-service-oriented-solution"></a>メッセージの参照をサービス指向ソリューション
このセクションでは、メッセージと、ソリューション内の各オーケストレーションで使用されるメッセージ型を示します。 アプリケーションのバージョンでは、メッセージと型が一覧表示されます。  
  
## <a name="adapter-version"></a>アダプターのバージョン  
 表に、 \<SolutionPrefix\> microsoft.samples.biztalk.woodgrovebank テーブルの書式設定に関するヘルプを表していますが置き換えられます。  
  
 オーケストレーションやメッセージの種類は次のとおりです。  
  
|オーケストレーション|メッセージ|メッセージ型|  
|-------------------|-------------|------------------|  
|CustomerService.odx|LastPaymentRequest|\<SolutionPrefix\>.Schemas.LastPaymentRequest|  
|CustomerService.odx|LastPaymentResponse|\<SolutionPrefix\>します。Schemas.LastPaymentResponse|  
|CustomerService.odx|PendingTransactionsWSRequest|\<SolutionPrefix\>.Orchestrations.Adapter.PendTransWS.PendingTransactionsWebService_.GetPendingTransactions_request|  
|CustomerService.odx|PendingTransactionsWSResponse|\<SolutionPrefix\>.Orchestrations.Adapter.PendTransWS.PendingTransactionsWebService_.GetPendingTransactions_response|  
|CustomerService.odx|CreditLimitRequest|\<SolutionPrefix\>します。Schemas.BAPI_BANKACCT_GET_DETAIL します。BAPI_BANKACCT_GET_DETAIL_Request|  
|CustomerService.odx|CreditLimitResponse|\<SolutionPrefix\>します。Schemas.BAPI_BANKACCT_GET_DETAIL します。BAPI_BANKACCT_GET_DETAIL_Response|  
|CustomerService.odx|PendingTransactionsRequest|\<SolutionPrefix\>します。Schemas.PendingTransactionsRequest|  
|CustomerService.odx|PendingTransactionsResponse|\<SolutionPrefix\>します。Schemas.PendingTransactionsResponse|  
|CustomerService.odx|StubSAPWebServiceRequest|\<SolutionPrefix\>.Orchestrations.Adapter.StubSAPWS.StubSAPWS_.GetAccountDetails_request|  
|CustomerService.odx|StubSAPWebServiceResponse|\<SolutionPrefix\>.Orchestrations.Adapter.StubSAPWS.StubSAPWS_.GetAccountDetails_response|  
|CustomerService.odx|CustomerServiceRequest|\<SolutionPrefix\>します。Schemas.CustomerServiceRequest|  
|CustomerService.odx|CustomerServiceResponse|\<SolutionPrefix\>します。Schemas.CustomerServiceResponse|  
|CustomerServiceNativeRequestResponse.odx|CustomerServiceRequest|\<SolutionPrefix\>します。Schemas.CustomerServiceRequest|  
|CustomerServiceNativeRequestResponse.odx|CustomerServiceResponse|\<SolutionPrefix\>します。Schemas.CustomerServiceResponse|  
|CustomerServiceReceiveSend.odx|CustomerServiceResponse2|\<SolutionPrefix\>します。Schemas.CustomerServiceResponse|  
|CustomerServiceReceiveSend.odx|CustomerServiceResponse|\<SolutionPrefix\>します。Schemas.CustomerServiceResponse|  
|CustomerServiceReceiveSend.odx|CustomerServiceRequest|\<SolutionPrefix\>します。Schemas.CustomerServiceRequest|  
  
## <a name="adapter-with-sap-version"></a>SAP バージョンのアダプター  
 表に、 \<SolutionPrefix\> microsoft.samples.biztalk.woodgrovebank テーブルの書式設定に関するヘルプを表していますが置き換えられます。  
  
 オーケストレーションやメッセージの種類は次のとおりです。  
  
|オーケストレーション|メッセージ|メッセージ型|  
|-------------------|-------------|------------------|  
|CustomerService.odx|LastPaymentRequest|\<SolutionPrefix\>.Schemas.LastPaymentRequest|  
|CustomerService.odx|LastPaymentResponse|\<SolutionPrefix\>します。Schemas.LastPaymentResponse|  
|CustomerService.odx|PendingTransactionsWSRequest|\<SolutionPrefix\>.Orchestrations.Adapter.PendTransWS.PendingTransactionsWebService_.GetPendingTransactions_request|  
|CustomerService.odx|PendingTransactionsWSResponse|\<SolutionPrefix\>.Orchestrations.Adapter.PendTransWS.PendingTransactionsWebService_.GetPendingTransactions_response|  
|CustomerService.odx|CreditLimitRequest|\<SolutionPrefix\>します。Schemas.BAPI_BANKACCT_GET_DETAIL します。BAPI_BANKACCT_GET_DETAIL_Request|  
|CustomerService.odx|CreditLimitResponse|\<SolutionPrefix\>します。Schemas.BAPI_BANKACCT_GET_DETAIL します。BAPI_BANKACCT_GET_DETAIL_Response|  
|CustomerService.odx|PendingTransactionsRequest|\<SolutionPrefix\>します。Schemas.PendingTransactionsRequest|  
|CustomerService.odx|PendingTransactionsResponse|\<SolutionPrefix\>します。Schemas.PendingTransactionsResponse|  
|CustomerService.odx|CustomerServiceRequest|\<SolutionPrefix\>します。Schemas.CustomerServiceRequest|  
|CustomerService.odx|CustomerServiceResponse|\<SolutionPrefix\>します。Schemas.CustomerServiceResponse|  
  
## <a name="inline-version"></a>インライン バージョン  
 表に、 \<SolutionPrefix\> microsoft.samples.biztalk.woodgrovebank テーブルの書式設定のヘルプを表していますが置き換えられます。  
  
 オーケストレーションやメッセージの種類は次のとおりです。  
  
|オーケストレーション|メッセージ|メッセージ型|  
|--------------------|-------------|------------------|  
|CustomerService.odx|LastPaymentRequest|\<SolutionPrefix\>.Schemas.LastPaymentRequest|  
|CustomerService.odx|LastPaymentResponse|\<SolutionPrefix\>します。Schemas.LastPaymentResponse|  
|CustomerService.odx|PendingTransactionsWSRequest|\<SolutionPrefix\>します。Schemas.PendingTransactionsRequest|  
|CustomerService.odx|PendingTransactionsWSResponse|\<SolutionPrefix\>します。Schemas.PendingTransactionsResponse|  
|CustomerService.odx|CreditLimitRequest|\<SolutionPrefix\>します。Schemas.BAPI_BANKACCT_GET_DETAIL します。BAPI_BANKACCT_GET_DETAIL_Request|  
|CustomerService.odx|CreditLimitResponse|\<SolutionPrefix\>します。Schemas.BAPI_BANKACCT_GET_DETAIL します。BAPI_BANKACCT_GET_DETAIL_Response|  
|CustomerService.odx|LastPaymentRequestAfterSendPipeline|System.Xml.XmlDocument|  
|CustomerService.odx|LastPaymentResponseBeforeReceivePipeline|System.Xml.XmlDocument|  
|CustomerService.odx|CustomerServiceRequest|\<SolutionPrefix\>します。Schemas.CustomerServiceRequest|  
|CustomerService.odx|CustomerServiceResponse|\<SolutionPrefix\>します。Schemas.CustomerServiceResponse|  
|CustomerServiceNativeRequestResponse.odx|CustomerServiceRequest|\<SolutionPrefix\>します。Schemas.CustomerServiceRequest|  
|CustomerServiceNativeRequestResponse.odx|CustomerServiceResponse|\<SolutionPrefix\>します。Schemas.CustomerServiceResponse|  
|CustomerServiceReceiveSend.odx|CustomerServiceResponse2|\<SolutionPrefix\>します。Schemas.CustomerServiceResponse|  
|CustomerServiceReceiveSend.odx|CustomerServiceResponse|\<SolutionPrefix\>します。Schemas.CustomerServiceResponse|  
|CustomerServiceReceiveSend.odx|CustomerServiceRequest|\<SolutionPrefix\>します。Schemas.CustomerServiceRequest|  
  
## <a name="stub-version"></a>スタブ バージョン  
 表に、 \<SolutionPrefix\> microsoft.samples.biztalk.woodgrovebank テーブルの書式設定のヘルプを表していますが置き換えられます。  
  
 オーケストレーションやメッセージの種類は次のとおりです。  
  
|オーケストレーション|メッセージ|メッセージ型|  
|-------------------|-------------|------------------|  
|CustomerService.odx|LastPaymentRequest|\<SolutionPrefix\>.Schemas.LastPaymentRequest|  
|CustomerService.odx|LastPaymentResponse|\<SolutionPrefix\>します。Schemas.LastPaymentResponse|  
|CustomerService.odx|PendingTransactionsWSRequest|\<SolutionPrefix\>.Orchestrations.Stubbed.StubPendTransWS.StubPendingTransactionsWebService_.GetPendingTransactions_request|  
|CustomerService.odx|PendingTransactionsWSResponse|\<SolutionPrefix\>.Orchestrations.Stubbed.StubPendTransWS.StubPendingTransactionsWebService_.GetPendingTransactions_response|  
|CustomerService.odx|CreditLimitRequest|\<SolutionPrefix\>します。Schemas.BAPI_BANKACCT_GET_DETAIL します。BAPI_BANKACCT_GET_DETAIL_Request|  
|CustomerService.odx|CreditLimitResponse|\<SolutionPrefix\>します。Schemas.BAPI_BANKACCT_GET_DETAIL します。BAPI_BANKACCT_GET_DETAIL_Response|  
|CustomerService.odx|PendingTransactionsRequest|\<SolutionPrefix\>します。Schemas.PendingTransactionsRequest|  
|CustomerService.odx|PendingTransactionsResponse|\<SolutionPrefix\>します。Schemas.PendingTransactionsResponse|  
|CustomerService.odx|PaymentTrackerWSRequest|\<SolutionPrefix\>.Orchestrations.Stubbed.StubPmntTrckWS.StubPaymentTrackerWebService_.GetLastPayments_request|  
|CustomerService.odx|PaymentTrackerWSResponse|\<SolutionPrefix\>.Orchestrations.Stubbed.StubPmntTrckWS.StubPaymentTrackerWebService_.GetLastPayments_response|  
|CustomerService.odx|StubSAPWSRequest|\<SolutionPrefix\>.Orchestrations.Stubbed.StubSAPWS.StubSAPWS_.GetAccountDetails_request|  
|CustomerService.odx|StubSAPWSResponse|\<SolutionPrefix\>.Orchestrations.Stubbed.StubSAPWS.StubSAPWS_.GetAccountDetails_response|  
|CustomerService.odx|CustomerServiceRequest|\<SolutionPrefix\>します。Schemas.CustomerServiceRequest|  
|CustomerService.odx|CustomerServiceResponse|\<SolutionPrefix\>します。Schemas.CustomerServiceResponse|  
|CustomerServiceNativeRequestResponse.odx|CustomerServiceRequest|\<SolutionPrefix\>します。Schemas.CustomerServiceRequest|  
|CustomerServiceNativeRequestResponse.odx|CustomerServiceResponse|\<SolutionPrefix\>します。Schemas.CustomerServiceResponse|  
  
## <a name="see-also"></a>参照  
 [サービス指向ソリューション リファレンス](../core/service-oriented-solution-reference.md)
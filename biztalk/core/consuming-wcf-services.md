---
title: WCF サービスの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- consuming, WCF services
- WCF services, consuming
ms.assetid: ca6c0514-c1df-43ad-8f02-df117271b0b5
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0969fb98cbf9ea79f4e32138d795b6b4de81f513
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354620"
---
# <a name="consuming-wcf-services"></a>WCF サービスの使用
WCF サービスの使用には、既存の WCF サービスをビジネス プロセスに追加することができます。 いくつかの WCF サービスは、1 つのオーケストレーションに集計できます。  
  
 BizTalk WCF サービス使用ウィザードを使用して、オーケストレーションから (呼び出し)、WCF サービスを利用できます。 BizTalk WCF サービス使用ウィザードに作成、ポートの種類とメッセージの種類が必要な WCF サービスを使用します。 BizTalk WCF サービス使用ウィザードでは、コマンド ライン ツールの開発や、システム指定のバインド WCF アダプタと Wcf-custom アダプタと送信ポートを構成するウィザードでインポートできる 2 つのバインド ファイルも作成します。 ウィザードを使用すると、SOAP ヘッダーを使用する WCF サービスを使用、利用する WCF サービスの URI を変更して使用する Web サービスの WCF を動的に設定できます。 WCF 送信アダプタが WCF サービスを使用して、WCF 受信場所の WCF サービスを発行します。  
  
 BizTalk WCF 送信アダプタは、WCF 定義済みバインドを表す 5 つの物理送信アダプタ**BasicHttpBinding**、 **WsHttpBinding**、 **NetTcpBinding**、**NetNamedPipeBinding**、および**NetMsmqBinding**します。 BizTalk WCF アダプターでは、WCF バインドと、送信ポートの動作情報を自由に構成するためのカスタム アダプターも含まれます。 WCF 送信ハンドラーを構成し、ポートを送信する方法の詳細については、の各 WCF アダプタの操作方法に関するトピックを参照してください。 [WCF アダプタ](../core/wcf-adapters.md)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [WCF サービスを WCF 送信アダプターと共に使用する場合の考慮事項](../core/considerations-when-consuming-wcf-services-with-the-wcf-send-adapters.md)  
  
-   [消費済み WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-consumed-wcf-services.md)  
  
-   [WCF アダプター コンテキスト プロパティによる動的送信ポートの構成](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)  
  
-   [BizTalk WCF サービス使用ウィザードを使用して WCF サービスを使用する方法](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md)  
  
-   [オーケストレーションで型指定されたエラー コントラクトを処理する方法](../core/how-to-handle-typed-fault-contracts-in-orchestrations.md)  
  
-   [WCF 送信アダプター用の SOAP アクションの指定](../core/specifying-soap-actions-for-wcf-send-adapters.md)
---
title: "WCF サービスの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- consuming, WCF services
- WCF services, consuming
ms.assetid: ca6c0514-c1df-43ad-8f02-df117271b0b5
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3fc0764295cbbc793b07757691e1f0c730a4049
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="consuming-wcf-services"></a>WCF サービスの利用
WCF サービスを利用して、既存の WCF サービスをビジネス プロセスに追加できます。 複数の WCF サービスを 1 つのオーケストレーションに集計できます。  
  
 BizTalk WCF サービス使用ウィザードを使用して、オーケストレーションから WCF サービスを利用 (呼び出し) することができます。 BizTalk WCF サービス使用ウィザードで、WCF サービスの利用に必要なポートの種類とメッセージの種類を作成します。 また、このウィザードでは、開発用コマンド ライン ツールまたはウィザードでインポート可能な 2 つのバインド ファイルも作成します。これにより、システムで提供されているバインド WCF アダプタと WCF-Custom アダプタを使用して送信ポートを構成できます。 ウィザードを使用すると、利用する WCF サービスで SOAP ヘッダーを使用できるだけではなく、利用する WCF サービスの URI を変更したり、利用する Web サービスの WCF を動的に設定したりすることもできます。 WCF 送信アダプターは WCF サービスを利用し、WCF 受信場所は WCF サービスを公開します。  
  
 BizTalk WCF 送信アダプタは、WCF 定義済みバインドを表す 5 つの物理送信アダプターを含める**BasicHttpBinding**、 **WsHttpBinding**、 **NetTcpBinding**、**NetNamedPipeBinding**、および**NetMsmqBinding**です。 BizTalk WCF アダプターには、送信ポートの WCF バインドと動作情報を自在に構成できるカスタム アダプターも含まれています。 WCF 送信ハンドラを構成してポートを送信する方法の詳細については、の各 WCF アダプタの操作方法に関するトピックを参照してください。 [WCF アダプタ](../core/wcf-adapters.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [WCF での WCF サービスを使用する際の考慮事項の送信アダプタ](../core/considerations-when-consuming-wcf-services-with-the-wcf-send-adapters.md)  
  
-   [消費済み WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-consumed-wcf-services.md)  
  
-   [WCF アダプター コンテキスト プロパティを使用して動的送信ポートの構成](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)  
  
-   [BizTalk WCF サービス使用ウィザードを使用して WCF サービスを使用する方法](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md)  
  
-   [オーケストレーションで型指定されたエラー コントラクトを処理する方法](../core/how-to-handle-typed-fault-contracts-in-orchestrations.md)  
  
-   [送信アダプタの WCF の SOAP アクションの指定](../core/specifying-soap-actions-for-wcf-send-adapters.md)